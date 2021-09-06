---
title: Predicție retragere abonament
description: Prognozați dacă un client prezintă riscul de a nu mai utiliza produsele sau serviciile cu abonament ale companiei dvs.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 409dfce02c41d7c52295409912880b9224469908805e199066faeb2b7a4f1f9d
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035338"
---
# <a name="subscription-churn-prediction-preview"></a>Predicție renunțare la abonament (previzualizare)

Predicția renunțării la abonament ajută la predicția existenței riscului ca un client să nu mai utilizeze produsele sau serviciile cu abonament ale companiei dvs. Puteți crea o nouă predicție de renunțare la abonament din pagina **Informații** > **Predicții**. Selectați **Predicțiile mele** pentru a vedea alte predicții pe care le-ați creat.

> [!TIP]
> Încercați tutorialul pentru o predicție a retragerii de abonamente folosind exemple de date: [Ghid eșantion de predicție a retragerii de abonamente](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Cerințe preliminare

- Minimum [Permisiuni de colaborare](permissions.md).
- Cunoștințe despre afaceri pentru a înțelege ce înseamnă reducerea pentru afacerea dvs. Acceptăm definițiile de reducere bazate pe timp, ceea ce înseamnă că un client este considerat că a renunțat la un interval de timp după încheierea abonamentului.
- Date despre abonamentele dvs. și istoricul acestora:
    - Identificatori de abonament pentru a distinge abonamentele.
    - Identificatori ai clienților pentru a asigura corespondența abonamentelor cu clienții dvs.
    - Datele evenimentului de abonament, care definesc datele de început, datele de încheiere și datele la care au avut loc evenimentele de abonare.
    - Informații despre abonament pentru a defini dacă este un abonament recurent și cât de des se reînnoiește.
    - Schema de date semantice pentru abonamente necesită următoarele informații:
        - **ID abonament:** Un identificator unic al unui abonament.
        - **Dată de încheiere a abonamentului:** Data la care abonamentul expiră pentru client.
        - **Dată de începere a abonamentului:** Data la care abonamentul începe pentru client.
        - **Data tranzacției:** Data la care s-a produs o modificare a abonamentului. De exemplu, un client care cumpără sau anulează un abonament.
        - **Este un abonament recurent:** Un câmp boolean adevărat/fals care determină dacă abonamentul se va reînnoi cu același ID de abonament fără intervenția clientului
        - **Frecvența recurenței (în luni):** Pentru abonamentele recurente, este perioada pentru care abonamentul se va reînnoi. Este reprezentată în luni. De exemplu, un abonament anual care se reînnoiește automat pentru un client în fiecare an pentru încă un an are valoarea 12.
        - (Opțional) **Suma abonamentului:** Suma într-o monedă pe care un client o plătește pentru reînnoirea abonamentului. Poate ajuta la identificarea tiparelor pentru diferite niveluri de abonamente.
- Date despre activitățile clienților:
    - Identificatori de activitate pentru a distinge activitățile de același tip.
    - Identificatori ai clienților pentru asocia activitățile cu clienții dvs.
    - Informații despre activitate care conțin numele și data activității.
    - Schema de date semantice pentru activitățile clienților include:
        - **Cheia primară:** Un identificator unic pentru o activitate. De exemplu, o vizită pe un site web sau o înregistrare de utilizare care arată vizionarea de către client a unui episod de emisiune TV.
        - **Marcaj temporal:** Data și ora evenimentului identificate de cheia primară.
        - **Eveniment:** Numele evenimentului pe care doriți să-l utilizați. De exemplu, un câmp numit „UserAction” într-un serviciu de redare în flux video ar putea avea valoarea „Vizualizat”.
        - **Detalii:** Informații detaliate despre eveniment. De exemplu, un câmp numit „ShowTitle” într-un serviciu de redare în flux video ar putea avea valoarea unui videoclip vizualizat de un client.
- Caracteristici de date sugerate:
    - Date istorice suficiente: date despre abonament pentru cel puțin dublul intervalului de timp selectat. De preferință, doi-trei ani de date de abonament.
    - Starea abonamentului: datele includ abonamente active și inactive pentru fiecare client, astfel încât există mai multe intrări pe ID-ul clientului.
    - Număr de clienți: cel puțin 10 profiluri de clienți, de preferință mai mult de 1.000 de clienți unici. Modelul va eșua cu mai puțin de 10 clienți și cu date istorice insuficiente.
    - Completitatea datelor: mai puțin de 20% din valorile lipsă din câmpul de date al entității furnizate.
   
   > [!NOTE]
   > Veți avea nevoie de cel puțin două înregistrări de activitate pentru 50% din clienții pentru care doriți să calculați problemele.

## <a name="create-a-subscription-churn-prediction"></a>Creați o predicție de renunțare la abonament

1. În Detalii despre public, accesați **Informații** > **Predicții**.
1. Selectați dala **Model de predicție de abonament (previzualizare)** și selectați **Utilizați acest model**.
   > [!div class="mx-imgBorder"]
   > ![Dală de model de predicție de reducere abonament cu buton Utilizați acest model.](media/subscription-churn-usethismodel.PNG "Dală de model de predicție de reducere abonament cu buton Utilizați acest model")

### <a name="name-model"></a>Denumire model

1. Furnizați un nume pentru model pentru a-l distinge de alte modele.
1. Furnizați un nume pentru entitatea de ieșire folosind doar litere și numere, fără spații. Acesta este numele pe care îl va folosi entitatea model. Apoi, selectați **Următorul**.

### <a name="define-customer-churn"></a>Definiți retragerea clienților

1. Introduceți numărul de **Zile de la încheierea abonamentului** la care compania dvs. consideră că un client s-a retras. În această perioadă companiile se concentrează pe activități precum ofertele sau alte eforturi de marketing care încearcă să prevină pierderea clientului.
1. Introduceți numărul de **Zile pentru a investiga viitorul pentru a prezice problemele** pentru a seta o fereastră pentru care să prezică problemele. De exemplu, pentru a prezice riscul problemelor pentru clienții dvs. în următoarele 90 de zile pentru a se alinia la eforturile dvs. de păstrare a marketingului. Predicția riscului de retragere pentru perioade mai lungi sau mai scurte de timp poate face mai dificilă abordarea factorilor din profilul dvs. de risc de retragere, în funcție de cerințele dvs. comerciale specifice. Selectați **Următorul** pentru a continua
   >[!TIP]
   > Puteți selecta **Salvare și închidere** pentru a salva oricând predicția ca schiță. Veți găsi schița predicției în fila **Predicțiile mele** pentru a continua.

### <a name="add-required-data"></a>Adăugați datele necesare

1. Selectați **Adăugare date** pentru **Istoricul abonamentelor** și alegeți entitatea care furnizează informațiile despre istoricul abonamentelor descrise în [Cerințe preliminare](#prerequisites).
1. Când câmpurile de mai jos nu sunt populate, configurați relația de la entitatea pentru istoricul abonamentelor la entitatea Client.
    1. Selectați **Entitatea istoric abonamente**.
    1. Selectați **Câmpul** pentru identificarea clientului în entitatea istoricul abonamentelor. Trebuie să fie asociat ID-ului clientului primar al entității dvs. client.
    1. Selectați **Entitatea client** care se potrivește cu entitatea clientului primar.
    1. Introduceți un nume care descrie relația.
       > [!div class="mx-imgBorder"]
       > ![Pagina istoric abonamente care arată crearea unei relații cu clientul.](media/subscription-churn-subscriptionhistoryrelationship.PNG "Pagina istoric abonamente care arată crearea unei relații cu clientul")
1. Selectați **Următorul**.
1. Asociați câmpurile semantice cu atributele din entitatea istoricul abonamentelor și selectați **Salvare**. Pentru descrierea câmpurilor, consultați secțiunea [Cerințe preliminare](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Pagina istoric abonamente care prezintă atribute semantice care sunt asociate câmpurilor din entitatea istoric abonamente selectată.](media/subscription-churn-subscriptionhistorymapping.PNG "Pagina istoric abonamente care prezintă atribute semantice care sunt asociate câmpurilor din entitatea istoric abonamente selectată")
1. Selectați **Adăugare date** pentru **Activitățile clienților** și alegeți entitatea care furnizează informațiile despre activitățile clienților descrise în Cerințele preliminare.
1. Selectați un tip de activitate care să corespundă tipului de activitate a clientului pe care o configurați.  Selectați **Creare nou** și furnizați un nume dacă nu vedeți o opțiune care se potrivește tipului de activitate de care aveți nevoie.
1. Va trebui să configurați relația de la entitatea activitatea clientului la entitatea client.
    1. Selectați câmpul pentru identificarea clientului în tabelul activitatea clientului, care poate fi direct asociat de ID-ul clientului primar al entității dvs. client.
    1. Selectați entitatea client care se potrivește cu entitatea clientului primar
    1. Introduceți un nume care descrie relația.
1. Selectați **Următorul**.
1. Asociați câmpurile semantice cu atributele din entitatea activitatea clientului și selectați **Salvare**. Pentru descrierea câmpurilor, consultați secțiunea [Cerințe preliminare](#prerequisites).
1. (Opțional) Dacă aveți orice alte activități ale clienților pe care doriți să le includeți, repetați pașii de mai sus.
   > [!div class="mx-imgBorder"]
   > ![Definiți relația dintre entități.](media/subscription-churn-customeractivitiesmapping.PNG "Pagina activități clienți care prezintă atribute semantice care sunt asociate câmpurilor din entitatea activități clienți selectată")
1. Selectați **Următorul**.

### <a name="set-schedule-and-review-configuration"></a>Setați programul și examinați configurația

1. Setați o frecvență pentru a vă reinstrui modelul. Această setare este importantă pentru a actualiza precizia predicțiilor pe măsură ce sunt ingerate date noi în detaliile despre public. Majoritatea firmelor pot reinstrui o dată pe lună și pot obține o precizie bună pentru predicția lor.
1. Selectați **Următorul**.
1. Analizați configurarea. Puteți reveni la orice parte a configurării predicției selectând **Editare** sub valoarea afișată. Sau puteți selecta un pas de configurare din indicatorul de progres.
1. Dacă toate valorile sunt configurate corect, selectați **Salvare și rulare** pentru a începe procesul de predicție. Din fila **Predicțiile mele**, puteți vedea starea predicțiilor dvs. Procesul poate dura câteva ore până la finalizare, în funcție de cantitatea de date utilizate în predicție.

## <a name="review-a-prediction-status-and-results"></a>Analizați starea predicțiilor și rezultatele

1. Accesați fila **Predicțiile mele** din **Informații** > **Predicții**.
   > [!div class="mx-imgBorder"]
   > ![Vizualizare a paginii Predicțiile mele.](media/subscription-churn-mypredictions.PNG "Vizualizare a paginii Predicțiile mele")
1. Selectați predicția pe care doriți să o revizuiți.
   - **Numele predicției:** Numele predicției furnizat la crearea acesteia.
   - **Tip de predicție:** Tipul de model utilizat pentru predicție
   - **Entitate de ieșire:** Numele entității care va stoca rezultatul predicției. Puteți găsi o entitate cu acest nume în **Date** > **Entități**.    
     În entitatea de ieșire, *ChurnScore* este probabilitatea prezisă de dezactivare și *IsChurn* este o etichetă binară bazată pe *ChurnScore* cu 0,5 prag. Este posibil ca pragul implicit să nu funcționeze pentru scenariul dvs. [Creați un segment nou](segments.md#create-a-new-segment) cu pragul preferat.
   - **Câmp prognozat:** Acest câmp este populat doar pentru anumite tipuri de predicții și nu este utilizat în predicția de renunțare la abonament.
   - **Stare:** Starea curentă a rulării predicției.
        - **În coadă:** În prezent, predicția așteaptă să fie rulate alte procese.
        - **Reîmprospătare:** Predicția rulează în prezent etapa de „evaluare” a procesării pentru a produce rezultate care vor trece în entitatea de ieșire.
        - **Eșuat:** predicția a eșuat. Selectați **Jurnale** pentru mai multe detalii.
        - **Reușit:** predicția a reușit. Selectați **Vizualizare** sub elipsele verticale pentru a analiza predicția
   - **Editat:** Data la care configurația predicției a fost modificată.
   - **Ultima actualizare:** Data la care predicția a fost reîmprospătată având ca rezultat entitatea de ieșire.
1. Selectați elipsele verticale de lângă predicția pentru care doriți să analizați rezultatele și selectați **Vizualizare**.
   > [!div class="mx-imgBorder"]
   > ![Vizualizarea opțiunilor din meniul elipselor verticale pentru o predicție, incluzând editare, actualizare, vizualizare, jurnale și ștergere.](media/subscription-churn-verticalellipses.PNG "Vizualizarea opțiunilor din meniul elipselor verticale pentru o predicție, incluzând editare, actualizare, vizualizare, jurnale și ștergere")
1. Există trei secțiuni principale de date în pagina de rezultate:
    1. **Performanța modelului de instruire:** A, B sau C sunt scoruri posibile. Acest scor indică performanța predicției și vă poate ajuta să luați decizia de a utiliza rezultatele stocate în entitatea de ieșire.
        - Scorurile sunt determinate pe baza următoarelor reguli:
            - **A** când modelul a prezis cu exactitate cel puțin 50% din totalul previziunilor și când procentul de previziuni exacte pentru clienții care s-au retras este mai mare decât rata medie de retragere istorică cu cel puțin 10% din rata medie a retragerii.
            - **B** atunci când modelul a prezis cu exactitate cel puțin 50% din totalul previziunilor și când procentul de previziuni exacte pentru clienții care s-au retras este cu până la 10% mai mare decât rata medie de retragere a ratei medii istorice.
            - **C** când modelul a prezis cu precizie mai puțin de 50% din totalul previziunilor sau când procentul de previziuni exacte pentru clienții care s-au retras este mai mic decât rata medie istorică.
               > [!div class="mx-imgBorder"]
               > ![Vizualizarea rezultatului performanței modelului.](media/subscription-churn-modelperformance.PNG "Vizualizarea rezultatului performanței modelului")
    1. **Probabilitatea de retragere (număr de clienți):** Grupuri de clienți în funcție de riscul de retragere prognozat. Aceste date vă pot ajuta mai târziu dacă doriți să creați un segment de clienți cu risc ridicat de retragere. Astfel de segmente vă ajută să înțelegeți unde ar trebui să fie delimitarea dvs. pentru membrii segmentului.
       > [!div class="mx-imgBorder"]
       > ![Graficul care arată distribuția rezultatelor retragerii, împărțită în intervale cuprinse între 0-100%.](media/subscription-churn-resultdistribution.PNG "Graficul care arată distribuția rezultatelor retragerii, împărțită în intervale cuprinse între 0-100%")
    1. **Cei mai influenți factori:** Există mulți factori care sunt luați în considerare atunci când vă creați predicția. Fiecare dintre factori are o importanță calculată pentru predicțiile agregate pe care le creează un model. Puteți utiliza acești factori pentru a vă ajuta la validarea rezultatelor predicției. Sau puteți utiliza aceste informații mai târziu pentru a [crea segmente](segments.md) care ar putea ajuta la influențarea riscului de retragere pentru clienți.
       > [!div class="mx-imgBorder"]
       > ![Listă care arată factorii influenți și importanța lor în predicția rezultatului retragerii.](media/subscription-churn-influentialfactors.PNG "Listă care arată factorii influenți și importanța lor în predicția rezultatului retragerii")

## <a name="manage-predictions"></a>Gestionați predicțiile

Este posibil să optimizați, să depanați, să reîmprospătați sau să ștergeți predicțiile. Examinați un raport de utilizare a datelor de intrare pentru a afla cum să faceți o predicție mai rapid și mai fiabil. Pentru mai multe informații, consultați [Gestionați o predicție](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
