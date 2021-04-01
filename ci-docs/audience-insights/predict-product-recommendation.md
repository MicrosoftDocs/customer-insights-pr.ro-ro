---
title: Predicție de recomandare de produse
description: Preziceți produsele pe care un client este probabil să le cumpere sau să interacționeze cu acestea.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5ae78b6bbc51fd8a25bc408050a23479698a1414
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598078"
---
# <a name="product-recommendation-prediction-preview"></a>Predicție de recomandare de produse (previzualizare)

Modelul de recomandare a produsului creează seturi de recomandări predictive pentru produse. Recomandările se bazează pe comportamentul de cumpărare anterior și pe clienții cu modele de achiziție similare. Puteți crea predicții de recomandări de produse noi pe pagina **Inteligență** > **Predicții**. Selectați **Predicțiile mele** pentru a vedea alte predicții pe care le-ați creat.

Recomandările de produse pot fi supuse legilor și reglementărilor locale, precum și așteptărilor clienților, pe care modelul nu este conceput pentru a le ține seama în mod specific.  Ca utilizator al acestei capacități predictive, **trebuie să examinați recomandările înainte de a le livra clienților dvs.** pentru a vă asigura că respectați orice legi sau reglementări aplicabile, precum și așteptările clienților pentru ceea ce ați putea recomanda. 

În plus, rezultatul acestui model vă va oferi recomandări pe baza ID-ului produsului. Mecanismul dvs. de livrare va trebui să preia codurile de produs prevăzute și să le mapeze la conținutul adecvat pentru ca clienții dvs. să țină cont de localizare, conținut de imagine și alte tipuri de conținut sau comportament specific companiei.

## <a name="sample-guide"></a>Ghid de probă

Dacă sunteți interesat să încercați această caracteristică, dar nu aveți date pentru a îndeplini cerințele de mai jos, puteți să [creați un exemplu de implementare](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Cerințe preliminare

- Cel puțin [Permisiuni de contributor](permissions.md) în Customer Insights.
- Cunoașterea afacerii pentru a înțelege diferite tipuri de produse pentru afacerea dvs. și modul în care clienții dvs. interacționează cu ei. Susținem recomandarea de produse care au fost achiziționate anterior de clienții dvs. sau recomandări pentru produse noi.
- Date despre tranzacțiile, achizițiile dvs. și istoricul acestora:
    - Identificatori de tranzacții pentru a distinge achizițiile sau tranzacțiile.
    - Identificatorii clienților pentru a mapa tranzacțiile cu clienții dvs.
    - Datele evenimentului tranzacției, care specifică datele la care a avut loc tranzacția.
    - (Opțional) Informații despre ID produs pentru tranzacție.
    - (Opțional) Dacă o tranzacție este sau nu o returnare.
    - Schema de date semantice necesită următoarele informații:
        - **ID-ul de tranzacție:** Un identificator unic al unei achiziții sau al unei tranzacții.
        - **Data tranzacției:** Data cumpărării sau tranzacției.
        - **Valoarea tranzacției:** Valoarea numerică a achiziției sau tranzacției.
        - **Cod unic produs:** ID-ul produsului sau serviciului achiziționat dacă datele dvs. se află la un nivel de element rând.
        - (Opțional) **Achiziție sau returnare:** Un câmp adevărat/fals care identifică dacă tranzacția a fost un retur sau nu. Dacă **Valoarea tranzacției** este negativă, vom folosi și aceste informații pentru a deduce un retur.


## <a name="create-a-product-recommendation-prediction"></a>Creați o predicție de recomandare de produs

1. În Customer Insights, accesați secțiunea **Informații** > **Predicții**.

1. Selectați dala **Model de recomandări de produse (previzualizare)** și selectați **Utilizați acest model**.
   > [!div class="mx-imgBorder"]
   > ![Recomandarea produsului model de dale cu Utilizați acest buton model](media/product-recommendation-usethismodel.PNG "Recomandarea produsului model de dale cu Utilizați acest buton model")

1. Consultați informațiile despre cerințele modelului. Dacă aveți datele necesare, selectați **Începeți**.

### <a name="name-model"></a>Denumire model

1. Furnizați un nume pentru model pentru a-l distinge de alte modele.

1. Introduceți un nume pentru entitatea de ieșire folosind numai litere și cifre, fără spații. Acesta este numele pe care îl va folosi entitatea model. Apoi, selectați **Următorul**.

### <a name="define-product-recommendation-configuration"></a>Definiți configurația recomandării produsului

1. Setați **Numărul de produse** pe care doriți să îl recomandați unui client. Această valoare depinde de modul în care metoda dvs. de livrare umple datele. Dacă puteți recomanda trei produse, setați această valoare în consecință.
   
   >[!TIP]
   > Puteți selecta **Salvare și închidere** pentru a salva oricând predicția ca schiță. Veți găsi proiectul predicție în fila **Predicțiile mele**.

1. Alegeți dacă doriți să **Sugerați produse pe care clienții le-au achiziționat recent**.

1. Dacă ați ales să *nu* recomandați produsele achiziționate recent, setați **Fereastră de privire retrospectivă**. Această setare specifică intervalul de timp pe care îl are în vedere modelul înainte de a recomanda produsului utilizatorului din nou. De exemplu, indicați că un client achiziționează un laptop la fiecare 2 ani. Această fereastră va analiza istoricul achizițiilor din ultimii 2 ani și, dacă găsesc un element, acesta va fi filtrat din recomandări.

1. Selectați **Următorul**

### <a name="add-required-data"></a>Adăugați datele necesare

1. Selectați **Adăugați date** pentru **Istoricul tranzacțiilor de client** și alegeți entitatea care furnizează informațiile despre istoricul tranzacțiilor/achizițiilor, așa cum este descris în [cerințe preliminare](#prerequisites).

1. Asociați câmpurile semantice la atributele din cadrul entității din istoricul achizițiilor și selectați **Următorul**. Pentru descrierea câmpurilor, consultați secțiunea [Cerințe preliminare](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Definiți relația dintre entități](media/product-recommendation-purchasehistorymapping.PNG "Pagina istoric achiziții care arată atributele semantice care sunt mapate la câmpurile din entitatea istoric achiziții selectată")

1. Dacă câmpurile nu sunt completate, configurați relația de la entitatea din istoricul achizițiilor la entitatea *Client*.
    1. Selectați **Entitate istoric achiziții**.
    1. Selectați **Câmpul** care identifică clientul în entitatea de istoric al achizițiilor. Trebuie să fie asociat ID-ului clientului primar al entității dvs. *Client*.
    1. Selectați **Entitatea client** care se potrivește cu entitatea clientului primar.
    1. Introduceți un nume care descrie relația.
       > [!div class="mx-imgBorder"]
       > ![Pagina cu istoricul achizițiilor care arată crearea unei relații cu clientul](media/model-purchase-join.png "Pagina cu istoricul achizițiilor care arată crearea unei relații cu clientul")

1. Selectați **Salvare**.

1. Selectați **Următorul**.

### <a name="set-schedule-and-review-configuration"></a>Setați programul și examinați configurația

1. Setați o frecvență pentru a vă reinstrui modelul. Această setare este importantă pentru a actualiza precizia predicțiilor, deoarece datele noi sunt importate în Customer Insights. Majoritatea firmelor pot reinstrui o dată pe lună și pot obține o precizie bună pentru predicția lor.

1. Selectați **Următorul**.

1. Analizați configurarea. Puteți reveni la orice parte a configurării predicției selectând **Editare** sub valoarea afișată. Sau puteți selecta un pas de configurare din indicatorul de progres.

1. Dacă toate valorile sunt configurate corect, selectați **Salvare și rulare** pentru a începe procesul de predicție. Din fila **Predicțiile mele**, puteți vedea starea predicțiilor dvs. Procesul poate dura câteva ore până la finalizare, în funcție de cantitatea de date utilizate în predicție.

## <a name="review-a-prediction-status-and-results"></a>Analizați starea predicțiilor și rezultatele

1. Accesați fila **Predicțiile mele** din **Informații** > **Predicții**.
   > [!div class="mx-imgBorder"]
   > ![Vizualizare a paginii Predicțiile mele](media/product-recommendation-mypredictions.PNG "Vizualizare a paginii Predicțiile mele")

1. Selectați predicția pe care doriți să o revizuiți.
   - **Numele predicției:** Numele predicției furnizat la crearea acesteia.
   - **Tip de predicție:** Tipul de model utilizat pentru predicție
   - **Entitate de ieșire:** Numele entității care va stoca rezultatul predicției. Puteți găsi o entitate cu acest nume în **Date** > **Entități**.
   - **Câmp estimat:** Acest câmp este populat numai pentru anumite tipuri de predicții și nu este utilizat în predicția retragerii.
   - **Stare:** Starea curentă a rulării predicției.
        - **În coadă:** În prezent, predicția așteaptă să fie rulate alte procese.
        - **Reîmprospătare:** Predicția rulează în prezent etapa de „evaluare” a procesării pentru a produce rezultate care vor trece în entitatea de ieșire.
        - **Eșuat:** predicția a eșuat. Selectați **Jurnale** pentru mai multe detalii.
        - **Reușit:** predicția a reușit. Selectați **Vizualizare** sub elipsele verticale pentru a analiza predicția
   - **Editat:** Data la care configurația predicției a fost modificată.
   - **Ultima actualizare:** Data la care predicția a fost reîmprospătată având ca rezultat entitatea de ieșire.

1. Selectați elipsele verticale de lângă predicția pentru care doriți să analizați rezultatele și selectați **Vizualizare**.
   > [!div class="mx-imgBorder"]
   > ![Vizualizarea opțiunilor din meniul elipselor verticale pentru o predicție, incluzând editare, actualizare, vizualizare, jurnale și ștergere](media/product-recommendation-verticalellipses.PNG "Vizualizarea opțiunilor din meniul elipselor verticale pentru o predicție, incluzând editare, actualizare, vizualizare, jurnale și ștergere")

1. Există trei secțiuni principale de date în pagina de rezultate:
    1. **Performanța modelului de instruire:** A, B sau C sunt scoruri posibile. Acest scor indică performanța predicției și vă poate ajuta să luați decizia de a utiliza rezultatele stocate în entitatea de ieșire.
        - Scorurile sunt determinate pe baza următoarelor reguli:
            - **A** Modelul va fi considerat de calitate **A** dacă valoarea „Success @ K” este cu cel puțin 10% mai mare decât valoarea de bază. 
            - **B** Modelul va fi considerat de calitate **B** dacă valoarea „Success @ K” este cu 0 până la 10% mai mare decât valoarea de bază.
            - **C** Modelul va fi considerat de calitate **C** dacă valoarea „Success @ K” este mai mică decât valoarea de bază.
               
               > [!div class="mx-imgBorder"]
               > ![Vizualizarea rezultatului performanței modelului](media/product-recommendation-modelperformance.PNG "Vizualizarea rezultatului performanței modelului")
            - **De bază**: Modelul ia cele mai recomandate produse în funcție de numărul de achiziții pentru toți clienții și folosește reguli învățate identificate de model pentru a crea un set de recomandări pentru clienți. Predicțiile sunt apoi comparate cu produsele de top, calculate după numărul de clienți care au achiziționat produsul. Dacă un client are cel puțin un produs recomandat în produsele sale, care a fost văzut și în produsele cumpărate de top, acesta este considerat o parte a liniei de bază. Dacă ar exista 10 dintre acești clienți care au achiziționat un produs recomandat din 100 de clienți în total, valoarea inițială ar fi de 10%.
            - **Succes @ K**: Folosind un set de validare a perioadei de timp a tranzacțiilor, se creează recomandări pentru toți clienții și se compară cu setul de validare al tranzacțiilor. De exemplu, într-o perioadă de 12 luni, luna 12 ar putea fi rezervată ca set de date de validare. Dacă modelul prezice cel puțin un lucru pe care l-ați cumpăra în luna 12 pe baza a ceea ce a învățat din cele 11 luni anterioare, clientul ar crește măsurătoarea „Success @ K”.
    
    1. **Cele mai sugerate produse (cu număr):** Primele 5 produse care au fost prezise pentru clienții dvs.
       > [!div class="mx-imgBorder"]
       > ![Grafic care prezintă primele 5 cele mai recomandate produse](media/product-recommendation-topproducts.PNG "Grafic care prezintă primele 5 cele mai recomandate produse")
    
    1. **Recomandări de produse de înaltă încredere:** Un eșantion de recomandări oferite clienților dvs. despre care modelul consideră că este probabil să fie cumpărate de client.
       > [!div class="mx-imgBorder"]
       > ![Listă care prezintă sugestii de mare încredere pentru un set selectat de clienți individuali](media/product-recommendation-highconfidence.PNG "Listă care prezintă sugestii de mare încredere pentru un set selectat de clienți individuali")

## <a name="fix-a-failed-prediction"></a>Remediați o predicție eșuată

1. Accesați fila **Predicțiile mele** din **Informații** > **Predicții**.

1. Selectați predicția pentru care doriți să vizualizați jurnalele de eroare și selectați **Jurnale**.

1. Analizarea tuturor erorilor. Există mai multe tipuri de erori care pot apărea și ce descriu condiția care a cauzat eroarea. De exemplu, o eroare pentru date insuficiente pentru o predicție exactă este de obicei rezolvată prin încărcarea de date suplimentare în Customer Insights.

## <a name="refresh-a-prediction"></a>Reîmprospătați o predicție

Predicțiile se reîmprospătează automat pe același [program cu care se reîmprospătează datele](system.md#schedule-tab) așa cum este configurat în setări.

1. Accesați fila **Predicțiile mele** din **Informații** > **Predicții**.

1. Selectați elipsele verticale de lângă predicția pe care doriți să o reîmprospătați.

1. Selectați **Reîmprospătare**.

## <a name="delete-a-prediction"></a>Ștergerea unei predicții

Ștergerea unui predicții va elimina și entitatea acesteia de ieșire.

1. Accesați fila **Predicțiile mele** din **Informații** > **Predicții**.

1. Selectați elipsele verticale de lângă predicția pe care doriți să o ștergeți.

1. Selectați **Ștergere**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]