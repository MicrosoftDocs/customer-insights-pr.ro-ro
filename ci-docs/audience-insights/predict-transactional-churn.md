---
title: Prezicerea retragerii tranzacționale
description: Preziceți dacă un client prezintă riscul de a nu mai cumpăra produsele sau serviciile companiei dvs.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f0d56fc6595fcbb226897fcb52148924d00306b6d75b617fc8cafbcc0aab0641
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034925"
---
# <a name="transactional-churn-prediction-preview"></a>Prezicerea retragerii tranzacționale (previzualizare)

Predicția retragerii tranzacționale ajută la a prezice dacă un client nu va mai cumpăra produsele sau serviciile dvs. într-o anumită fereastră de timp. Puteți crea noi predicții de retragere pe **Informații** > **Predicții**. Selectați **Predicțiile mele** pentru a vedea alte predicții pe care le-ați creat.

> [!TIP]
> Încercați tutorialul pentru o predicție a retragerii tranzacționale folosind exemple de date: [Ghid eșantion de predicție a retragerii tranzacționale (previzualizare)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Cerințe preliminare

- Cel puțin [Permisiuni de contributor](permissions.md) în Customer Insights.
- Cunoștințe despre afaceri pentru a înțelege ce înseamnă reducerea pentru afacerea dvs. Acceptăm definițiile bazate pe timp ale retragerii, ceea ce înseamnă că un client este considerat a fi retras după o perioadă fără achiziții.
- Date despre tranzacțiile/achizițiile dvs. și istoricul acestora:
    - Identificatori de tranzacții pentru a distinge achizițiile/tranzacțiile.
    - Identificatorii clienților pentru a potrivi tranzacțiile cu clienții dvs.
    - Datele evenimentului tranzacției, care definesc datele la care a avut loc tranzacția.
    - Schema de date semantice pentru achiziții/tranzacții necesită următoarele informații:
        - **ID-ul de tranzacție:** Un identificator unic al unei achiziții sau al unei tranzacții.
        - **Data tranzacției:** Data cumpărării sau tranzacției.
        - **Valoarea tranzacției:** Moneda/valoarea numerică a tranzacției/articolului.
        - (Opțional) **Cod unic produs:** ID-ul produsului sau serviciului achiziționat dacă datele dvs. se află la un nivel de element rând.
        - (Opțional) **Dacă această tranzacție a fost o returnare:** Un câmp adevărat/fals care identifică dacă tranzacția a fost un retur sau nu. Dacă **Valoarea tranzacției** este negativă, vom folosi și aceste informații pentru a deduce un retur.
- (Opțional) Date despre activitățile clienților:
    - Identificatori de activitate pentru a distinge activitățile de același tip.
    - Identificatori ai clienților pentru asocia activitățile cu clienții dvs.
    - Informații despre activitate care conțin numele și data activității.
    - Schema de date semantice pentru activitățile clienților include:
        - **Cheia primară:** Un identificator unic pentru o activitate. De exemplu, o vizită pe site sau o înregistrare de utilizare care arată că clientul a încercat un eșantion de produs.
        - **Marcaj temporal:** Data și ora evenimentului identificate de cheia primară.
        - **Eveniment:** Numele evenimentului pe care doriți să-l utilizați. De exemplu, un câmp numit „UserAction” într-un magazin alimentar ar putea fi o utilizare a cuponului de către client.
        - **Detalii:** Informații detaliate despre eveniment. De exemplu, un câmp numit „CouponValue” într-un magazin alimentar ar putea fi valoarea valutară a cuponului.
- Caracteristici de date sugerate:
    - Date istorice suficiente: date despre tranzacție pentru cel puțin dublul intervalului de timp selectat. De preferință, doi până la trei ani de istoric al tranzacțiilor. 
    - Achiziții multiple pe client: ideal cel puțin două tranzacții pe client.
    - Număr de clienți: cel puțin 10 profiluri de clienți, de preferință mai mult de 1.000 de clienți unici. Modelul va eșua cu mai puțin de 10 clienți și cu date istorice insuficiente.
    - Completitatea datelor: mai puțin de 20% din valorile lipsă din câmpul de date al entității furnizate.

> [!NOTE]
> Pentru o companie cu frecvență ridicată de cumpărare a clienților (la fiecare câteva săptămâni), se recomandă să selectați o fereastră mai scurtă predicție și să definiți churn. Pentru o frecvență scăzută de cumpărare (o dată la câteva luni sau o dată pe an), alegeți o fereastră mai lungă predicție și definiția retragerii.

## <a name="create-a-transactional-churn-prediction"></a>Creați o predicție a retragerii tranzacționale

1. În Customer Insights, accesați secțiunea **Informații** > **Predicții**.

1. Selectați dala **Modelul de retragere a clienților (previzualizare)** și selectați **Folosiți acest model**.
   
1. În panoul **Modelul de retragere a clienților**, alegeți **Tranzacțional** și selectați **Începeți**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Captură de ecran cu opțiunea tranzacțională selectată în panoul modelul de retragere a clienților.":::

### <a name="name-model"></a>Denumire model

1. Furnizați un nume pentru model pentru a-l distinge de alte modele.

1. Furnizați un nume pentru entitatea de ieșire folosind doar litere și numere, fără spații. Acesta este numele pe care îl va folosi entitatea model. 

1. Selectați **Următorul**.

### <a name="define-customer-churn"></a>Definiți retragerea clienților

1. Setați o fereastră de zile pentru a prezice retragerea în câmpul **Identificați clienții care s-ar putea re trage în următoarea perioadă de**. De exemplu, preziceți riscul de retragere pentru clienții dvs. în următoarele 90 de zile pentru a se alinia la eforturile dvs. de marketing de retenție. Predicția riscului de retragere pentru o perioadă mai lungă sau mai scurtă de timp poate face mai dificilă abordarea factorilor din profilul dvs. de risc de retragere, dar depinde de cerințele dvs. de afaceri specifice. 
   >[!TIP]
   > Puteți selecta **Salvare și închidere** pentru a salva oricând predicția ca schiță. Veți găsi schița predicției în fila **Predicțiile mele** pentru a continua.

1. Introduceți numărul de zile pentru a defini retragerea în câmpul **Un client este retras dacă nu a efectuat achiziții în:**. De exemplu, dacă un client nu a efectuat nicio achiziție în ultimele 30 de zile, acesta ar putea fi considerat ca fiind retras pentru afacerea dvs. 

1. Selectați **Următorul** pentru a continua

### <a name="add-required-data"></a>Adăugați datele necesare

1. Selectați **Adăugați date** pentru **Istoricul cumpărăturilor** și alegeți entitatea care furnizează informațiile despre istoricul tranzacțiilor/achizițiilor, așa cum este descris în [cerințe preliminare](#prerequisites).

1. Asociați câmpurile semantice la atributele din cadrul entității din istoricul achizițiilor și selectați **Următorul**. Pentru descrierea câmpurilor, consultați secțiunea [Cerințe preliminare](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Maparea câmpurilor semantice ale entității de cumpărare.":::

1. Dacă câmpurile de mai jos nu sunt completate, configurați relația de la entitatea din istoricul achizițiilor la entitatea Client.
    1. Selectați **Entitate istoric achiziții**.
    1. Selectați **Câmpul** care identifică clientul în entitatea de istoric al achizițiilor. Trebuie să fie asociat ID-ului clientului primar al entității dvs. client.
    1. Selectați **Entitatea client** care se potrivește cu entitatea clientului primar.
    1. Introduceți un nume care descrie relația.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Pagina cu istoricul achizițiilor care arată crearea unei relații cu clientul.":::
   
1. Selectați **Următorul**.

1. Opțional, selectați **Adăugare date** pentru **Activitățile clienților**. Alegeți entitatea care furnizează informații despre activitatea clienților, așa cum este descris în condițiile prealabile.

1. Asociați câmpurile semantice la atributele din cadrul entității cu activitatea clientului și selectați **Următorul**. Pentru descrierea câmpurilor, consultați secțiunea [Cerințe preliminare](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Mapați câmpurile clienților pentru datele tranzacționale.":::

1. Selectați un tip de activitate care să corespundă tipului de activitate a clientului pe care o configurați. Selectați **Creare nou** și alegeți un tip de activitate disponibil sau creați un tip nou.

1. Va trebui să configurați relația de la entitatea activitatea clientului la entitatea client.
    1. Selectați câmpul care identifică clientul în tabelul de activitate a clienților. Poate fi legat direct de ID-ul de client principal al entității dvs. de client.
    1. Selectați entitatea client care se potrivește cu entitatea clientului primar
    1. Introduceți un nume care descrie relația.

1. Selectați **Salvare**.

1. Dacă aveți alte activități ale clienților pe care doriți să le includeți, repetați pașii de mai sus.

1. Selectați **Următorul**.

### <a name="set-schedule-and-review-configuration"></a>Setați programul și examinați configurația

1. Setați o frecvență pentru a vă reinstrui modelul. Această setare este importantă pentru a actualiza precizia predicțiilor pe măsură ce sunt ingerate date noi. Majoritatea firmelor pot reinstrui o dată pe lună și pot obține o precizie bună pentru predicția lor.

1. Selectați **Următorul**.

1. Verificați configurația predicției. Puteți reveni la pașii anteriori selectând **Editare** sub valoarea arătată. Sau puteți selecta un pas de configurare din indicatorul de progres.

1. Dacă toate valorile sunt configurate corect, selectați **Salvare și rulare** pentru a începe procesul de predicție. Din fila **Predicțiile mele**, puteți vedea starea predicțiilor dvs. Procesul poate dura câteva ore până la finalizare, în funcție de cantitatea de date utilizate în predicție.

## <a name="review-a-prediction-status-and-results"></a>Analizați starea predicțiilor și rezultatele

1. Mergeți la **Informații** > **Predicții** și selectați fila **Previziunile mele**.

1. Selectați predicția pe care doriți să o revizuiți.
   - **Nume predicție:** Numele predicției furnizat la crearea acesteia.
   - **Tip predicție:** Tipul modelului utilizat pentru predicție
   - **Entitate de ieșire:** Numele entității care va stoca rezultatul predicției. Puteți găsi o entitate cu acest nume în **Date** > **Entități**.    
     În entitatea de ieșire, *ChurnScore* este probabilitatea prezisă de dezactivare și *IsChurn* este o etichetă binară bazată pe *ChurnScore* cu 0,5 prag. Este posibil ca pragul implicit să nu funcționeze pentru scenariul dvs. [Creați un segment nou](segments.md#create-a-new-segment) cu pragul preferat.
     Nu toți clienții sunt în mod necesar clienți activi. Este posibil ca unii dintre ei să nu fi avut nicio activitate de mult timp și să fie considerați deja derutați, pe baza definiției dvs. de retragere. Prezicerea riscului de retragere pentru clienții care deja s-au retras nu este utilă deoarece nu sunt publicul de interes.
   - **Câmp estimat:** Acest câmp este populat numai pentru anumite tipuri de predicții și nu este utilizat în predicția retragerii.
   - **Stare:** Starea rulării predicției.
        - **În așteptare:** Predicția așteaptă să se execute alte procese.
        - **Reîmprospătare:** Predicția rulează în prezent pentru a produce rezultate care vor curge în entitatea de ieșire.
        - **Eșuat:** Rularea predicției a eșuat. Pentru mai multe detalii, [consultați fișierele-jurnal](manage-predictions.md#troubleshoot-a-failed-prediction).
        - **Reușit:** Predicția a reușit. Selectați **Vizualizare** sub elipsele verticale pentru a analiza predicția
   - **Editat:** Data la care configurația predicției a fost modificată.
   - **Ultima actualizare:** Data la care predicția a fost reîmprospătată având ca rezultat entitatea de ieșire.

1. Selectați elipsele verticale de lângă predicția pentru care doriți să analizați rezultatele și selectați **Vizualizare**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Vizualizați controlul pentru a vedea rezultatele unui predicții.":::   

1. Există trei secțiuni principale de date în pagina de rezultate:
    1. **Performanța modelului de instruire:** A, B sau C sunt scoruri posibile. Acest scor indică performanța predicției și vă poate ajuta să luați decizia de a utiliza rezultatele stocate în entitatea de ieșire. Scorurile sunt determinate pe baza următoarelor reguli:
         
         - **A** atunci când modelul a prezis cu acuratețe cel puțin 50% din predicțiile totale și când procentul de predicții exacte pentru clienții care s-au retras este mai mare decât rata inițială cu cel puțin 10%.
            
         - **B** atunci când modelul a prezis cu acuratețe cel puțin 50% din predicțiile totale și când procentul de predicții exacte pentru clienții care s-au retras este cu până la 10% mai mare decât rata inițială.
            
         - **C** atunci când modelul a prezis cu acuratețe mai puțin de 50% din predicțiile totale sau când procentul de predicții exacte pentru clienții care s-au retras este mai mic decât rata inițială.
               
         - **Rata inițială** preia intrarea ferestrei de timp de predicție pentru model (de exemplu, un an), iar modelul creează fracții diferite de timp împărțindu-l la 2 până ajunge la o lună sau mai puțin. Utilizează aceste fracții pentru a crea o regulă de afaceri pentru clienții care nu au achiziționat în acest interval de timp. Acești clienți sunt considerați ca fiind retrași. Ca rată inițială este aleasă regula de afaceri bazată pe timp, cu cea mai mare capacitate de a prezice cine este susceptibil să se retragă.
            
    1. **Probabilitatea de retragere (număr de clienți):** Grupuri de clienți în funcție de riscul de retragere prognozat. Aceste date vă pot ajuta mai târziu dacă doriți să creați un segment de clienți cu risc ridicat de retragere. Astfel de segmente vă ajută să înțelegeți unde ar trebui să fie delimitarea dvs. pentru membrii segmentului.
       
    1. **Cei mai influenți factori:** Există mulți factori care sunt luați în considerare atunci când vă creați predicția. Fiecare dintre factori are importanța sa calculată pentru predicțiile agregate pe care le creează un model. Puteți utiliza acești factori pentru a vă ajuta la validarea rezultatelor predicției. Sau puteți utiliza aceste informații mai târziu pentru a [crea segmente](segments.md) care ar putea ajuta la influențarea riscului de retragere pentru clienți.

## <a name="manage-predictions"></a>Gestionați predicțiile

Este posibil să optimizați, să depanați, să reîmprospătați sau să ștergeți predicțiile. Examinați un raport de utilizare a datelor de intrare pentru a afla cum să faceți o predicție mai rapid și mai fiabil. Pentru mai multe informații, consultați [Gestionați o predicție](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
