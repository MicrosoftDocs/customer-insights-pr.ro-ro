---
title: Predicție de recomandare de produse
description: Preziceți produsele pe care un client este probabil să le cumpere sau să interacționeze cu acestea.
ms.date: 03/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: bcbafa513c2c61b0280c91aa7ed71e211c32c35c
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/13/2021
ms.locfileid: "6556139"
---
# <a name="product-recommendation-prediction-preview"></a>Predicție de recomandare de produse (previzualizare)

Modelul de recomandare a produsului creează seturi de recomandări predictive pentru produse. Recomandările se bazează pe comportamentul de cumpărare anterior și pe clienții cu modele de achiziție similare. Puteți crea predicții de recomandări de produse noi pe pagina **Inteligență** > **Predicții**. Selectați **Predicțiile mele** pentru a vedea alte predicții pe care le-ați creat.

Recomandările de produse pot fi supuse legilor și reglementărilor locale și așteptărilor clienților, pe care modelul nu este conceput pentru a le lua în considerare în mod specific.  Ca utilizator al acestei capacități predictive, **trebuie să examinați recomandările înainte de a le trimite clienților dvs.** pentru a vă asigura că respectați orice legi sau reglementări aplicabile și așteptările clienților pentru ceea ce ați putea recomanda. 

În plus, rezultatul acestui model vă va oferi recomandări pe baza ID-ului produsului. Mecanismul dvs. de livrare va trebui să asocieze ID-urile de produs prevăzute la conținutul adecvat pentru ca clienții dvs. să țină cont de localizare, conținut de imagine și alte tipuri de conținut sau comportament specific companiei.

## <a name="sample-guide"></a>Ghid de probă

Dacă sunteți interesat să încercați această caracteristică, dar nu aveți date pentru a îndeplini cerințele de mai jos, puteți să [creați un exemplu de implementare](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Cerințe preliminare

- Cel puțin [Permisiuni de contributor](permissions.md) în Customer Insights.

- Cunoașterea afacerii pentru a înțelege diferite tipuri de produse pentru afacerea dvs. și modul în care clienții dvs. interacționează cu ei. Susținem recomandarea de produse care au fost achiziționate anterior de clienții dvs. sau recomandări pentru produse noi.

- Date despre tranzacțiile, achizițiile dvs. și istoricul acestora:
    - Identificatori de tranzacții pentru a distinge achizițiile sau tranzacțiile.
    - Identificatorii clienților pentru a mapa tranzacțiile cu clienții dvs.
    - Datele evenimentului tranzacției, care specifică datele la care a avut loc tranzacția.
    - Informații despre ID produs pentru tranzacție.
    - (Opțional) O entitate de date din catalogul de produse pentru a utiliza un filtru de produse.
    - (Opțional) Dacă o tranzacție este sau nu o returnare.
    - Schema de date semantice necesită următoarele informații:
        - **ID-ul de tranzacție:** Un identificator unic al unei achiziții sau al unei tranzacții.
        - **Data tranzacției:** Data achiziționării sau tranzacției.
        - **Valoarea tranzacției:** Valoarea numerică a achiziției sau tranzacției.
        - **Cod unic produs:** ID-ul produsului sau serviciului achiziționat dacă datele dvs. se află la un nivel de element rând.
        - (Opțional) **Achiziționați sau returnați:** Un câmp boolean în care valoarea *adevărat* identifică faptul că o tranzacție a fost o returnare. Dacă datele de achiziționare sau returnare nu sunt furnizate, modelul și **Valoarea tranzacției** este negativ, vom folosi și aceste informații pentru a deduce o rentabilitate.
- Caracteristici de date sugerate:
    - Date istorice suficiente: cel puțin un an de date tranzacționale, de preferință doi până la trei ani pentru a include o anumită sezonalitate.
    - Achiziții multiple pe client: Trei sau mai multe tranzacții pe ID-ul clientului
    - Număr de clienți: cel puțin 100 de clienți, de preferință mai mult de 10.000 de clienți. Modelul va eșua cu mai puțin de 100 de clienți.

> [!NOTE]
> - Modelul necesită istoricul tranzacțiilor clienților dvs. Definiția unei tranzacții este destul de flexibilă. Orice date care descriu o interacțiune utilizator-produs pot funcționa ca o intrare. De exemplu, achiziționarea unui produs, participarea la un curs sau participarea la un eveniment.
> - În prezent, poate fi configurată o singură entitate din istoricul tranzacțiilor. Dacă există mai multe entități de cumpărare, uniți-le în Power Query înainte de ingestia de date.
> - Dacă detaliile comenzii și comenzii sunt entități diferite, alăturați-vă acestora înainte de a le utiliza în model. Modelul nu funcționează doar cu un ID de comandă sau un ID de primire într-o entitate.


## <a name="create-a-product-recommendation-prediction"></a>Creați o predicție de recomandare de produs

1. În Customer Insights, accesați secțiunea **Informații** > **Predicții**.

1. Selectați dala **Model de recomandări de produse (previzualizare)** și selectați **Utilizați acest model**.
   > [!div class="mx-imgBorder"]
   > ![Recomandarea produsului model de dale cu Utilizați acest buton model.](media/product-recommendation-usethismodel.PNG "Recomandarea produsului model de dale cu Utilizați acest buton model")

1. Consultați informațiile despre cerințele modelului. Dacă aveți datele necesare, selectați **Începeți**.

### <a name="name-model"></a>Denumire model

1. Furnizați un nume pentru model pentru a-l distinge de alte modele.

1. Introduceți un nume pentru entitatea de ieșire folosind numai litere și cifre, fără spații. Acesta este numele pe care îl va folosi entitatea model. Apoi, selectați **Următorul**.

### <a name="define-product-recommendation-configuration"></a>Definiți configurația recomandării produsului

1. Setați **Numărul de produse** pe care doriți să îl recomandați unui client. Această valoare depinde de modul în care metoda dvs. de livrare umple datele. Dacă puteți recomanda trei produse, setați această valoare în consecință.
   
   >[!TIP]
   > Puteți selecta **Salvare și închidere** pentru a salva oricând predicția ca schiță. Veți găsi proiectul predicție în fila **Predicțiile mele**.

1. Alegeți dacă doriți să **Sugerați produse pe care clienții le-au achiziționat recent**.

1. Dacă ați ales să *nu* recomandați produsele achiziționate recent, setați **Fereastră de privire retrospectivă**. Această setare specifică intervalul de timp pe care îl are în vedere modelul înainte de a recomanda produsului utilizatorului din nou. De exemplu, indicați că un client achiziționează un laptop la fiecare doi ani. Această fereastră va analiza istoricul achizițiilor din ultimii doi ani și, dacă găsesc un articol, articolul va fi filtrat din recomandări.

1. Selectați **Următorul**

### <a name="add-required-data"></a>Adăugați datele necesare

1. Selectați **Adăugați date** pentru **Istoricul tranzacțiilor de client** și alegeți entitatea care furnizează informațiile despre istoricul tranzacțiilor/achizițiilor, așa cum este descris în [cerințe preliminare](#prerequisites).

1. Asociați câmpurile semantice la atributele din cadrul entității din istoricul achizițiilor și selectați **Următorul**. Pentru descrierea câmpurilor, consultați secțiunea [Cerințe preliminare](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Definiți relația dintre entități.](media/product-recommendation-purchasehistorymapping.PNG "Pagina istoric achiziții care arată atributele semantice care sunt mapate la câmpurile din entitatea istoric achiziții selectată")

1. Dacă câmpurile nu sunt completate, configurați relația de la entitatea din istoricul achizițiilor la entitatea *Client*.
    1. Selectați **Entitate istoric achiziții**.
    1. Selectați **Câmpul** care identifică clientul în entitatea de istoric al achizițiilor. Trebuie să fie asociat ID-ului clientului primar al entității dvs. *Client*.
    1. Selectați **Entitatea client** care se potrivește cu entitatea clientului primar.
    1. Introduceți un nume care descrie relația.
       > [!div class="mx-imgBorder"]
       > ![Pagina cu istoricul achizițiilor care arată crearea unei relații cu clientul.](media/model-purchase-join.png "Pagina cu istoricul achizițiilor care arată crearea unei relații cu clientul")

1. Selectați **Salvare**.

1. Selectați **Următorul**.

### <a name="configure-product-filters"></a>Configurați filtre de produse

Uneori, numai anumite produse sunt benefice sau adecvate pentru tipul de predicție pe care îl construiți. Filtrele de produse vă permit să identificați un subset de produse cu caracteristici specifice pe care să le recomandați clienților dvs. Modelul va utiliza toate produsele disponibile pentru a învăța modele, dar va utiliza numai produsele care corespund filtrului de produs în ieșirea sa.

1. În pasul **Adăugați informații despre produs**, adăugați catalogul dvs. de produse cu informații pentru fiecare produs. Hartați informațiile solicitate în selectați **Următorul**.

3. În pasul **Filtre pentru produse**, alegeți dintre următoarele opțiuni.

   * **Fără filtre**: Utilizați toate produsele din recomandarea produsului predicție.

   * **Definiți anumite filtre de produse**: Utilizați produse specifice în recomandarea produsului predicție.

1. Selectați **Următorul**.

1. Dacă alegeți să definiți un filtru de produs, trebuie să îl definiți acum. În panoul **Atributele catalogului de produse**, selectați atributele din *Entitatea din catalogul de produse* pe care doriți să le includeți în filtru.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Panoul lateral afișat atribuit în entitatea din catalogul de produse de selectat pentru filtrele de produse.":::

1. Alegeți dacă doriți ca filtrul de produse să folosească conectorii **și** sau **sau** pentru a combina în mod logic selecția dvs. de atribute din catalogul de produse.
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="Exemplu de configurație a filtrelor de produs combinate cu conectori AND logici.":::

1. Selectați **Următorul**.

### <a name="set-update-schedule-and-review-configuration"></a>Setați planificarea de actualizare și examinați configurația

1. Setați o frecvență pentru a vă reinstrui modelul. Această setare este importantă pentru a actualiza precizia predicțiilor, deoarece datele noi sunt importate în Customer Insights. Majoritatea firmelor pot reinstrui o dată pe lună și pot obține o precizie bună pentru predicția lor.

1. Selectați **Următorul**.

1. Analizați configurarea. Puteți reveni la orice parte a configurării predicției selectând **Editare** sub valoarea afișată. Sau puteți selecta un pas de configurare din indicatorul de progres.

1. Dacă toate valorile sunt configurate corect, selectați **Salvare și rulare** pentru a începe procesul de predicție. Din fila **Predicțiile mele**, puteți vedea starea predicțiilor dvs. Procesul poate dura câteva ore până la finalizare, în funcție de cantitatea de date utilizate în predicție.

## <a name="review-a-prediction-status-and-results"></a>Analizați starea predicțiilor și rezultatele

1. Accesați fila **Predicțiile mele** din **Informații** > **Predicții**.
   > [!div class="mx-imgBorder"]
   > ![Vizualizare a paginii Predicțiile mele.](media/product-recommendation-mypredictions.PNG "Vizualizare a paginii Predicțiile mele")

1. Selectați predicția pe care doriți să o revizuiți.
   - **Numele predicției:** Numele predicției furnizat la crearea acesteia.
   - **Tip de predicție:** Tipul de model utilizat pentru predicție
   - **Entitate de ieșire:** Numele entității care va stoca rezultatul predicției. Puteți găsi o entitate cu acest nume în **Date** > **Entități**.    
      *Scor* în entitatea de ieșire este o măsură cantitativă a recomandării. Modelul recomandă produse cu un scor mai mare față de produsele cu un scor mai mic.
   - **Câmp estimat:** Acest câmp este completat numai pentru anumite tipuri de predicții și nu este utilizat în Recomandarea produsului predicție.
   - **Stare:** Starea curentă a rulării predicției.
        - **În coadă:** În prezent, predicția așteaptă să fie rulate alte procese.
        - **Reîmprospătare:** Predicția rulează în prezent etapa de „evaluare” a procesării pentru a produce rezultate care vor trece în entitatea de ieșire.
        - **Eșuat:** predicția a eșuat. Selectați **Jurnale** pentru mai multe detalii.
        - **Reușit:** predicția a reușit. Selectați **Vizualizare** sub elipsele verticale pentru a analiza predicția
   - **Editat:** Data la care configurația predicției a fost modificată.
   - **Ultima actualizare:** Data la care predicția a fost reîmprospătată având ca rezultat entitatea de ieșire.

1. Selectați elipsele verticale de lângă predicția pentru care doriți să analizați rezultatele și selectați **Vizualizare**.
   > [!div class="mx-imgBorder"]
   > ![Vizualizarea opțiunilor din meniul elipselor verticale pentru o predicție, incluzând editare, actualizare, vizualizare, jurnale și ștergere.](media/product-recommendation-verticalellipses.PNG "Vizualizarea opțiunilor din meniul elipselor verticale pentru o predicție, incluzând editare, actualizare, vizualizare, jurnale și ștergere")

1. Există cinci secțiuni principale de date în pagina de rezultate:
    1. **Performanța modelului de instruire:** A, B sau C sunt scoruri posibile. Acest scor indică performanța predicției și vă poate ajuta să luați decizia de a utiliza rezultatele stocate în entitatea de ieșire.
        - Scorurile sunt determinate pe baza următoarelor reguli:
            - **A** Modelul va fi considerat de calitate **A** dacă valoarea „Success @ K” este cu cel puțin 10% mai mare decât valoarea de bază. 
            - **B** Modelul va fi considerat de calitate **B** dacă valoarea „Success @ K” este cu 0% până la 10% mai mare decât valoarea de bază.
            - **C** Modelul va fi considerat de calitate **C** dacă valoarea „Success @ K” este mai mică decât valoarea de bază.
               
               > [!div class="mx-imgBorder"]
               > ![Vizualizarea rezultatului performanței modelului.](media/product-recommendation-modelperformance.PNG "Vizualizarea rezultatului performanței modelului")
            - **De bază**: Modelul ia cele mai recomandate produse în funcție de numărul de achiziții pentru toți clienții și folosește reguli învățate identificate de model pentru a crea un set de recomandări pentru clienți. Predicțiile sunt apoi comparate cu produsele de top, calculate după numărul de clienți care au achiziționat produsul. Dacă un client are cel puțin un produs recomandat în produsele sale, care a fost văzut și în produsele cumpărate de top, acesta este considerat o parte a liniei de bază. Dacă ar exista 10 dintre acești clienți care au achiziționat un produs recomandat din 100 de clienți în total, valoarea inițială ar fi de 10%.
            - **Succes @ K**: Folosind un set de validare a perioadei de timp a tranzacțiilor, se creează recomandări pentru toți clienții și se compară cu setul de validare al tranzacțiilor. De exemplu, într-o perioadă de 12 luni, luna 12 ar putea fi rezervată ca set de date de validare. Dacă modelul prezice cel puțin un lucru pe care l-ați cumpăra în luna 12 pe baza a ceea ce a învățat din cele 11 luni anterioare, clientul ar crește măsurătoarea „Success @ K”.
    
    1. **Cele mai sugerate produse (cu număr):** Primele cinci produse care au fost prezise pentru clienții dvs.
       > [!div class="mx-imgBorder"]
       > ![Grafic care prezintă primele 5 cele mai recomandate produse.](media/product-recommendation-topproducts.PNG "Grafic care prezintă primele 5 cele mai recomandate produse")
    
    1. **Factori cheie de recomandare:** Modelul folosește istoricul tranzacțiilor clienților pentru a face recomandări de produse. Învață modele bazate pe achiziții anterioare și găsește similitudini între clienți și produse. Aceste asemănări sunt apoi utilizate pentru a genera recomandări de produse.
    Următorii sunt factorii care ar putea influența o recomandare de produs generată de model. 
        - **Tranzacții anterioare**: Modelele de achiziționare din trecut au fost utilizate de model pentru a genera recomandări de produse. De exemplu, modelul poate recomanda un _Surface Arc Mouse_ dacă cineva a cumpărat recent un _Surface Book 3_ și un _Surface Pen_. Modelul a aflat că, din punct de vedere istoric, mulți clienți au cumpărat un _Surface Arc Mouse_ după achiziționarea unui _Surface Book 3_ și a unui _Surface Pen_.
        - **Similitudinea clientului**: Un produs recomandat a fost achiziționat în mod istoric de alți clienți care prezintă modele de achiziție similare. De exemplu, lui John is s-au recomandat _Surface Headphones 2_ pentru că Jennifer și Brad au cumpărat recent _Surface Headphones 2_. Modelul crede că John este similar cu Jennifer și Brad, deoarece au avut în mod istoric modele de cumpărare similare.
        - **Asemănarea produsului**: Un produs recomandat este similar cu alte produse cumpărate anterior de client. Modelul consideră că două produse sunt similare dacă au fost cumpărate împreună sau de către clienți similari. De exemplu, cineva primește o recomandare pentru o _Unitate de stocare USB_ deoarece anterior au cumpărat un _Adaptor USB-C la USB_ iar modelul crede că _Unitate de stocare USB_ este similar cu _Adaptor USB-C la USB_ pe baza modelelor istorice de cumpărare.

        Fiecare recomandare de produs este influențată de unul sau mai mulți dintre acești factori. Procentul recomandărilor în care fiecare factor de influență a jucat un rol este vizualizat într-un grafic. În exemplul următor, 100% din recomandări au fost influențate de tranzacțiile anterioare, 60% de similitudinea clienților și 22% de similaritatea produsului. Plasați cursorul peste barele din grafic pentru a vedea procentajul exact la care au contribuit factorii de influență.

        > [!div class="mx-imgBorder"]
        > ![Principalii factori pentru recomandări.](media/product-recommendation-keyrecommendationfactors.png "Factorii cheie de recomandare învățați de model pentru a genera recomandări de produse")
       
     
   1. **Statistici de date**: Oferă o prezentare generală a numărului de tranzacții, clienți și produse pe care le-a luat în considerare modelul. Se bazează pe datele de intrare care au fost utilizate pentru a învăța tiparele și a genera recomandări de produse.

      > [!div class="mx-imgBorder"]
      > ![Statistici de date.](media/product-recommendation-datastatistics.png "Statistici de date despre datele inout utilizate de model pentru a învăța tiparele")

      Această secțiune prezintă statistici în jurul punctelor de date care au fost utilizate de model pentru a învăța modele și a genera recomandări de produse. Filtrarea, așa cum este configurată în configurația modelului, se va aplica la ieșirea generată de model. Cu toate acestea, modelul folosește toate datele disponibile pentru a învăța tiparele. Prin urmare, dacă utilizați filtrarea produselor în configurația modelului, această secțiune va arăta numărul total de produse pe care modelul le-a analizat pentru a învăța modele, care ar putea diferi de numărul de produse care corespund criteriilor de filtrare definite.

   1. **Recomandări de produse de înaltă încredere:** Un eșantion de recomandări oferite clienților dvs. despre care modelul consideră că este probabil să fie cumpărate de client.    
      Dacă se adaugă un catalog de produse, codurile de produs vor fi înlocuite cu nume de produse. Numele produselor oferă informații mai ușor de acționat și mai intuitive despre predicții.
       > [!div class="mx-imgBorder"]
       > ![Listă care prezintă sugestii de mare încredere pentru un set selectat de clienți individuali.](media/product-recommendation-highconfidence.PNG "Listă care prezintă sugestii de mare încredere pentru un set selectat de clienți individuali")

## <a name="manage-predictions"></a>Gestionați predicțiile

Este posibil să optimizați, să depanați, să reîmprospătați sau să ștergeți predicțiile. Examinați un raport de utilizare a datelor de intrare pentru a afla cum să faceți o predicție mai rapid și mai fiabil. Pentru mai multe informații, consultați [Gestionați o predicție](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
