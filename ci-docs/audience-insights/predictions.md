---
title: Completați datele parțiale folosind predicții
description: Utilizați predicții pentru a completa datele incomplete ale clienților.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3100acf383d85c00a6ff0a8ebc54e038bd813427
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732441"
---
# <a name="complete-your-partial-data-with-predictions-deprecated"></a>Completați datele parțiale cu predicții (învechit)

> [!IMPORTANT]
> Această caracteristică va fi **depreciat** ca din **5 noiembrie 2021**. Implementările actuale vor continua să funcționeze până când caracteristica este eliminată, dar nu veți putea crea noi integrări folosind instrucțiunile de mai jos.

Predicțiile vă permit să creați cu ușurință valori previzionate care vă pot îmbunătăți înțelegerea despre un client. Pe pagina **Informații** > **Predicții**, puteți selecta **Predicțiile mele** pentru a vedea predicțiile pe care le-ați configurat în alte părți ale detaliilor privind publicul și vă permit să le personalizați în continuare.

> [!NOTE]
> Nu puteți utiliza această caracteristică dacă mediul dvs. utilizează stocarea Azure Data Lake Gen 2.
>
> Funcția de predicții folosește mijloace automate pentru a evalua datele și pentru a face predicții bazate pe acele date și, prin urmare, are capacitatea de a fi utilizată ca metodă de profilare, deoarece acest termen este definit de Regulamentul general privind protecția datelor („RGPD”). Utilizarea acestei funcții de către client pentru prelucrarea datelor poate fi supusă RGPD sau altor legi sau reglementări. Sunteți responsabil să vă asigurați că utilizarea de către dvs. a Dynamics 365 Customer Insights, inclusiv previziunile, respectă toate legile și reglementările aplicabile, inclusiv legile legate de confidențialitate, date personale, date biometrice, protecția datelor și confidențialitatea comunicațiilor.

## <a name="prerequisites"></a>Cerințe preliminare

Înainte ca organizația dvs. să poată utiliza funcția de predicții, trebuie să fie îndeplinite următoarele cerințe preliminare:

1. Organizația dvs. are o instanță [configurat în Microsoft Dataverse](/ai-builder/build-model#prerequisites) și se află în aceeași organizație cu Customer Insights.

2. Mediul dvs. de informații despre public este atașat instanței dvs. Dataverse.

Pentru informații suplimentare, consultați [Creați un mediu nou](create-environment.md).

## <a name="create-a-prediction-in-the-customer-entity"></a>Creați o predicție în entitatea client

1. În Detalii despre public, accesați **Date** > **Entități**.

2. Selectați entitatea **Client**.

3. În entitatea **Client: CustomerInsights**, selectați pe fila **Câmpuri**.

4. Găsiți numele atributului pentru care doriți să preziceți valorile, apoi selectați pictograma **Prezentare generală** din coloana **Rezumat**.
   > [!div class="mx-imgBorder"]
   > ![Pictograma Prezentare generală.](media/intelligence-overviewicon.png "Pictograma Prezentare generală")

5. Dacă există o rată mare de valori lipsă pentru atributul dvs., selectați **Prognozare valori lipsă** pentru a continua cu predicția dvs.
   > [!div class="mx-imgBorder"]
   > ![Prezentarea generală a stării cu afișarea butonului valorilor care lipsesc.](media/intelligence-overviewpredictmissingvalues.png "Prezentarea generală a stării cu afișarea butonului valorilor care lipsesc")

6. Furnizați un **Nume afișat** și un **Nume entitate de ieșire** pentru rezultatele de predicție.

7. Se afișează o listă de opțiuni pre-populată unde puteți mapa valorile cu o categorie prognozată. În acest caz, singurele dvs. opțiuni de categorie vor fi 0 sau 1, pe măsură ce acestea se potrivesc cu valorile true/false sau cu caracterul binar al predicției. În coloana Categorie, mapați valorile câmpului pe care doriți să le clasificați la „0” în predicția finală la „0”, și elementele pe care doriți să le clasificați drept „1” în predicția finală la „1”.
   > [!div class="mx-imgBorder"]
   > ![Exemplu care arată valorile câmpului mapat la categorii.](media/intelligence-categorymapping.png "Exemplu care arată valorile câmpului mapat la categorii")

8. Selectați **Terminat** iar predicția va fi procesată. Procesarea va dura ceva timp, în funcție de dimensiunea și complexitatea datelor. Rezultatele vor fi disponibile într-o nouă entitate pe baza **Nume entitate de ieșire** din predicția pe care ai creat-o.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="create-a-prediction-while-creating-a-segment"></a>Creați o predicție în timp ce creați un segment

Prognozarea valorilor lipsă pentru un atribut specific de alegere este posibilă și la crearea unui segment. Mai exact, atunci când creați rapid un segment în funcție fie de entitatea client unificat, fie de entitatea Customer_Measure.

Ca parte a acestui flux,veți alege un atribut specific pentru a vă defini segmentul pe atribute, cum ar fi satisfacția clientului sau suma de achiziție. După crearea segmentului, sistemul va sugera o metodă pentru a prezice orice valori lipsă pentru acest atribut.

1. În detaliile despre public, accesați **Segmente** și selectați dala **Profiluri**.

2. Alegeți un **Câmp** pentru a crea un segment activat și selectați un **Operator**, apoi selectați **Revizuire**.

3. Furnizați un **Nume** și un **Numele afișat** pentru segment.

4. Selectați **Salvare**.

5. Dacă segmentul pe care l-ați creat are date incomplete în câmpul sursă, puteți alege să preziceți valorile lipsă.
   > [!div class="mx-imgBorder"]
   > ![Buton de predicție.](media/segments-predictoption.png "Buton de predicție")

6. Furnizați un **Nume afișat** și un **Nume entitate de ieșire** pentru rezultatele de predicție.

7. Selectați **Terminat**. Predicția dvs. va fi generată în scurt timp într-o entitate nouă cu numele pe care l-ați furnizat pentru **Nume entitate de ieșire**.

## <a name="view-a-prediction"></a>Previzualizați o predicție

1. În Detalii despre public, accesați **Informații** > **Predicții** > **Predicțiile mele**.

2. Selectați predicția pe care doriți să o revizuiți.

3. Selectați cele trei puncte de suspensie din coloana **Acțiuni** și alegeți **Vizualizare**.

4. Veți vedea o serie de puncte de date în vizualizarea predicției dvs.
   > [!div class="mx-imgBorder"]
   > ![Pagina Predicții.](media/intelligence-predictionsviewpage.png "Pagina Predicții")

   - **Valori previzionate** arată maparea pe care ați creat-o în faza de mapare a valorii câmpului la Categorie. Acestea sunt valorile din setul dvs. de date care au fost mapate într-o anumită categorie.
   -**Factori de influență principali** sunt factorii din setul dvs. de date care sunt cel mai probabil să vă fi influențat încrederea predicției pentru ca valoarea câmpului dvs. să fie mapată într-o anumită categorie.
   - **Performanța** indică evoluția predicțiilor. Selectați linkul pentru a afla mai multe.
   - **Previzualizare** arată eșantioane din setul de date de ieșire pentru predicția dvs. și probabilitatea, sau încrederea noastră, a valorii prognozate în care 0 este incert și 1 este sigur.

## <a name="update-a-prediction"></a>Actualizați o predicție

1. În Detalii despre public, accesați **Informații** > **Predicții** > **Predicțiile mele**.

2. Selectați predicția pe care doriți să o actualizați și selectați pictograma **Actualizare**.

3. Predicția va fi planificată pentru procesare. Puteți vedea ora la care a fost actualizată ultima dată în coloana **Actualizat** din pagina **Predicții**.

## <a name="edit-a-prediction"></a>Editați o predicție

După ce ați creat o predicție, puteți particulariza modelul în AI Builder pentru a mări eficacitatea modelului dvs.  

1. În Detalii despre public, accesați **Informații** > **Predicții** > **Predicțiile mele**.

2. Selectați predicția pe care doriți să o editați.

3. Selectați cele trei puncte de suspensie din coloana **Acțiuni** și alegeți **Vizualizare**.

4. Selectați **Particularizare în AI Builder**.

5. Actualizați-vă modelul în AI Builder. [Aflați mai multe despre gestionarea modelelor din AI builder](/ai-builder/manage-model#retrain-and-republish-existing-models).

Următoarea execuție a predicției dvs. va utiliza modelul actualizat pe care l-ați creat.

> [!NOTE]
> Noile modele create în AI Builder nu vor fi afișate în detaliile despre public decât dacă modelul a fost creat din experiențele enumerate mai sus.

## <a name="remove-a-prediction"></a>Eliminați o predicție

1. În Detalii despre public, accesați **Informații** > **Predicții** > **Predicțiile mele**.

2. Selectați predicția pe care doriți să o ștergeți.

3. Selectați cele trei puncte de suspensie din coloana **Acțiuni** și alegeți **Ștergere**.

4. Confirmați ștergerea.

## <a name="troubleshooting"></a>Depanare

Dacă nu puteți finaliza procesul de atașare Dataverse din cauza unei erori, puteți încerca să finalizați procesul manual. Există două probleme cunoscute care pot apărea în procesul de atașare:

- Soluția de completare a cardului pentru clienți nu este instalată.
    1. Completați instrucțiunile pentru a [instala și configura soluția](customer-card-add-in.md).

- Permisiunile pentru aplicații nu sunt acordate.
    1. Salt la [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Selectați **Medii**.
    1. Selectați elipsele de lângă mediul în care doriți să adăugați permisiunea și selectați **Setări**.
    1. Extindeți **Utilizatori + permisiuni** și selectați **Utilizatori**.
    1. Selectați **Nou** și selectați **Utilizator**.
    1. Selectați **Utilizator aplicație** dacă nu este deja selectat și introduceți următoarele informații:
        - **Nume de utilizator:** cihelp@microsoft.com
        - **ID aplicație:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Prenumele:** clientului
        - **Nume de familie:** Insights
        - **E-mail principal:** cihelp@microsoft.com
    1. Selectați **Salvare și închidere**.
    1. Selectați utilizatorul pe care tocmai l-ați creat.
    1. Selectați din bara de sus a meniului **Gestionați rolurile**.
    1. Selectați **Administrator de sistem**, apoi selectați **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
