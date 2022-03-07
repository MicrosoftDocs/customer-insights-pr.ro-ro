---
title: Schimbarea tranzacției predicție (conține videoclipul)
description: Preziceți dacă un client prezintă riscul de a nu mai cumpăra produsele sau serviciile companiei dvs.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 9aa208ad94dcb6b1e0f110a3f974c56de00bbd07
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355674"
---
# <a name="transaction-churn-prediction"></a>Predicție retragere din tranzacții

Predicția retragerii tranzacționale ajută la a prezice dacă un client nu va mai cumpăra produsele sau serviciile dvs. într-o anumită fereastră de timp. Puteți crea noi predicții de retragere pe **Informații** > **Predicții**. Selectați **Predicțiile mele** pentru a vedea alte predicții pe care le-ați creat. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Pentru medii bazate pe conturi de business, putem prezice retrageri din tranzacții pentru un cont și, de asemenea, o combinație de cont și un alt nivel de informații, cum ar fi categoria de produse. Adăugarea unui parametru vă poate ajuta să aflați cât de probabil este ca contul „Contoso” să nu mai cumpere categoria de produse „articole de birou”. În plus, pentru conturile de afaceri, putem folosi, de asemenea, AI pentru a genera o listă de motive potențiale pentru care este probabil ca un cont să se schimbe pentru o categorie de informații de nivel secundar.

> [!TIP]
> Încercați tutorialul pentru o pierdere a tranzacțiilor predicție folosind date exemplu: [Ghid de exemplu pentru ratarea tranzacțiilor predicție](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Cerințe preliminare

# <a name="individual-consumers-b-to-c"></a>[Consumatori individuali (B2C)](#tab/b2c)

- Cel puțin [Permisiuni de contributor](permissions.md) în Customer Insights.
- Cunoștințe despre afaceri pentru a înțelege ce înseamnă reducerea pentru afacerea dvs. Acceptăm definițiile bazate pe timp ale retragerii, ceea ce înseamnă că un client este considerat a fi retras după o perioadă fără achiziții.
- Date despre tranzacțiile/achizițiile dvs. și istoricul acestora:
    - Identificatori de tranzacții pentru a distinge achizițiile/tranzacțiile.
    - Identificatorii clienților pentru a potrivi tranzacțiile cu clienții dvs.
    - Datele evenimentului tranzacției, care definesc datele la care a avut loc tranzacția.
    - Schema de date semantice pentru achiziții/tranzacții necesită următoarele informații:
        - **ID-ul de tranzacție**: Un identificator unic al unei achiziții sau al unei tranzacții.
        - **Data tranzacției**: Data achiziționării sau tranzacției.
        - **Valoarea tranzacției**: Moneda/valoarea numerică a tranzacției/articolului.
        - (Opțional) **Cod unic produs**: ID-ul produsului sau serviciului achiziționat dacă datele dvs. se află la un nivel de element rând.
        - (Opțional) **Dacă această tranzacție a fost o returnare**: Un câmp adevărat/fals care identifică dacă tranzacția a fost un retur sau nu. Dacă **Valoarea tranzacției** este negativă, vom folosi și aceste informații pentru a deduce un retur.
- (Opțional) Date despre activitățile clienților:
    - Identificatori de activitate pentru a distinge activitățile de același tip.
    - Identificatori ai clienților pentru asocia activitățile cu clienții dvs.
    - Informații despre activitate care conțin numele și data activității.
    - Schema de date semantice pentru activitățile clienților include:
        - **Cheia primară:** Un identificator unic pentru o activitate. De exemplu, o vizită pe site sau o înregistrare de utilizare care arată că clientul a încercat un eșantion de produs.
        - **Marcaj temporal:** Data și ora evenimentului identificate de cheia primară.
        - **Eveniment:** Numele evenimentului pe care doriți să-l utilizați. De exemplu, un câmp numit „UserAction” într-un magazin alimentar ar putea fi o utilizare a cuponului de către client.
        - **Detalii:** Informații detaliate despre eveniment. De exemplu, un câmp numit „CouponValue” într-un magazin alimentar ar putea fi valoarea valutară a cuponului.

# <a name="business-accounts-b-to-b"></a>[Conturi de afaceri (B2B)](#tab/b2b)

- Cel puțin [Permisiuni de contributor](permissions.md) în Customer Insights.
- Cunoștințe despre afaceri pentru a înțelege ce înseamnă reducerea pentru afacerea dvs. Acceptăm definițiile bazate pe timp ale retragerii, ceea ce înseamnă că un client este considerat a fi retras după o perioadă fără achiziții.
- Date despre tranzacțiile/achizițiile dvs. și istoricul acestora:
    - Identificatori de tranzacții pentru a distinge achizițiile/tranzacțiile.
    - Identificatorii clienților pentru a potrivi tranzacțiile cu clienții dvs.
    - Datele evenimentului tranzacției, care definesc datele la care a avut loc tranzacția.
    - Schema de date semantice pentru achiziții/tranzacții necesită următoarele informații:
        - **ID-ul de tranzacție**: Un identificator unic al unei achiziții sau al unei tranzacții.
        - **Data tranzacției**: Data achiziționării sau tranzacției.
        - **Valoarea tranzacției**: Moneda/valoarea numerică a tranzacției/articolului.
        - (Opțional) **Cod unic produs**: ID-ul produsului sau serviciului achiziționat dacă datele dvs. se află la un nivel de element rând.
        - (Opțional) **Dacă această tranzacție a fost o returnare**: Un câmp adevărat/fals care identifică dacă tranzacția a fost un retur sau nu. Dacă **Valoarea tranzacției** este negativă, vom folosi și aceste informații pentru a deduce un retur.
- (Opțional) Date despre activitățile clienților:
    - Identificatori de activitate pentru a distinge activitățile de același tip.
    - Identificatori ai clienților pentru asocia activitățile cu clienții dvs.
    - Informații despre activitate care conțin numele și data activității.
    - Schema de date semantice pentru activitățile clienților include:
        - **Cheia primară:** Un identificator unic pentru o activitate. De exemplu, o vizită pe site sau o înregistrare de utilizare care arată că clientul a încercat un eșantion de produs.
        - **Marcaj temporal:** Data și ora evenimentului identificate de cheia primară.
        - **Eveniment:** Numele evenimentului pe care doriți să-l utilizați. De exemplu, un câmp numit „UserAction” într-un magazin alimentar ar putea fi o utilizare a cuponului de către client.
        - **Detalii:** Informații detaliate despre eveniment. De exemplu, un câmp numit „CouponValue” într-un magazin alimentar ar putea fi valoarea valutară a cuponului.
- (Opțional) Date despre clienții dvs.:
    - Aceste date ar trebui să se alinieze la atribute mai statice pentru a se asigura că modelul funcționează cel mai bine.
    - Schema de date semantice pentru datele clienților include:
        - **CustomerID:** Un identificator unic pentru un client.
        - **Data creată:** Data la care a fost adăugat inițial clientul.
        - **Stat sau provincie:** Locația statului sau provinciei unui client.
        - **Țară:** Țara unui client.
        - **Industrie:** Tipul de activitate al unui client. De exemplu, un câmp numit „Industrie” dintr-un prăjitor de cafea ar putea indica dacă clientul a fost cu amănuntul.
        - **Clasificare:** Clasificarea unui client pentru afacerea dvs. De exemplu, un câmp numit „ValueSegment” într-un prăjitor de cafea ar putea fi nivelul clientului în funcție de mărimea clientului.

---

- Caracteristici de date sugerate:
    - Date istorice suficiente: date despre tranzacție pentru cel puțin dublul intervalului de timp selectat. De preferință, doi până la trei ani de istoric al tranzacțiilor. 
    - Achiziții multiple pe client: ideal cel puțin două tranzacții pe client.
    - Număr de clienți: cel puțin 10 profiluri de clienți, de preferință mai mult de 1.000 de clienți unici. Modelul va eșua cu mai puțin de 10 clienți și cu date istorice insuficiente.
    - Completitatea datelor: mai puțin de 20% din valorile lipsă din câmpul de date al entității furnizate.

> [!NOTE]
> Pentru o companie cu frecvență ridicată de cumpărare a clienților (la fiecare câteva săptămâni), se recomandă să selectați o fereastră mai scurtă predicție și să definiți churn. Pentru o frecvență scăzută de cumpărare (o dată la câteva luni sau o dată pe an), alegeți o fereastră mai lungă predicție și definiția retragerii.

## <a name="create-a-transaction-churn-prediction"></a>Creați o predicție de retragere din tranzacții

1. În Customer Insights, accesați secțiunea **Informații** > **Predicții**.

1. Selectează **Model de retragere a clienților** țiglă și selectați **Utilizați acest model**.

1. În panoul **Modelul de retragere a clienților**, alegeți **Tranzacţie** și selectați **Începeți**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Captură de ecran cu opțiunea de tranzacție selectată în panoul modelului Retragerea clienților.":::
 
### <a name="name-model"></a>Denumire model

1. Furnizați un nume pentru model pentru a-l distinge de alte modele.

1. Furnizați un nume pentru entitatea de ieșire folosind doar litere și numere, fără spații. Acesta este numele pe care îl va folosi entitatea model. 

1. Selectați **Următorul**.

### <a name="define-customer-churn"></a>Definiți retragerea clienților

1. Seteaza **fereastra predicție**. De exemplu, preziceți riscul de retragere pentru clienții dvs. în următoarele 90 de zile pentru a se alinia la eforturile dvs. de marketing de retenție. Predicția riscului de retragere pentru o perioadă mai lungă sau mai scurtă de timp poate face mai dificilă abordarea factorilor din profilul dvs. de risc de retragere, dar depinde de cerințele dvs. de afaceri specifice.
   >[!TIP]
   > Puteți selecta **Salveaza schita** în orice moment pentru a salva predicție ca schiță. Veți găsi schița predicției în fila **Predicțiile mele** pentru a continua.

1. Introduceți numărul de zile pentru a defini abandonul în **Definiția churn** camp. De exemplu, dacă un client nu a efectuat nicio achiziție în ultimele 30 de zile, acesta ar putea fi considerat ca fiind retras pentru afacerea dvs. 

1. Selectați **Următorul** pentru a continua.

### <a name="add-required-data"></a>Adăugați datele necesare

1. Selectați **Adăugați date** și alegeți tipul de activitate panoul lateral care conține informațiile necesare despre tranzacții sau istoricul achizițiilor.

1. Sub **Selectați activități**, alegeți activitățile specifice din tipul de activitate selectat pe care doriți să se concentreze calculul.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Panoul lateral care arată alegerea activităților specifice sub tipul semantic.":::

   Dacă nu ați mapat încă activitatea la un tip semantic, selectați **Editați** pentru a face acest lucru. Se deschide experiența ghidată pentru cartografierea activităților semantice. Mapați datele dvs. la câmpurile corelate în tipul de activitate selectat.

1. Asociați atributele semantice câmpurilor necesare pentru a rula modelul. Dacă câmpurile de mai jos nu sunt completate, configurați relația de la entitatea din istoricul achizițiilor la entitatea *Client*. Selectați **Salvare**.

1. În **Adăugați datele necesare** pas, selectați **Următorul** pentru a continua dacă nu doriți să adăugați mai multe activități.


# <a name="individual-consumers-b-to-c"></a>[Consumatori individuali (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Adăugați date suplimentare (opțional)

Configurați relația de la entitatea dvs. de activitate a clienților la entitatea *Client*.

1. Selectați câmpul care identifică clientul în tabelul de activitate a clienților. Poate fi legat direct de ID-ul de client principal al entității dvs. *Client*.

1. Selectați entitatea care este principalula dvs. entitate *Client*.

1. Introduceți un nume care descrie relația.

#### <a name="customer-activities"></a>Activități ale clienților

1. Opțional, selectați **Adăugare date** pentru **Activitățile clienților**.

1. Selectați tipul de activitate semantică care conține datele pe care doriți să le utilizați, apoi selectați una sau mai multe activități în secțiunea **Activități**.

1. Selectați un tip de activitate care să corespundă tipului de activitate a clientului pe care o configurați. Selectați **Creare nou** și alegeți un tip de activitate disponibil sau creați un tip nou.

1. Selectați **Următorul**, apoi **Salvați**.

1. Dacă aveți alte activități ale clienților pe care doriți să le includeți, repetați pașii de mai sus.

# <a name="business-accounts-b-to-b"></a>[Conturi de afaceri (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Selectați nivelul de predicție

Majoritatea predicțiilor sunt create la nivel de client. În unele situații, este posibil să nu fie suficient de granular pentru a răspunde nevoilor dvs. de afaceri. Puteți utiliza această caracteristică pentru a prezice retragere pentru o ramură a unui client, de exemplu, mai degrabă decât pentru client în ansamblu.

1. Pentru a crea un predicție la un nivel mai granular decât clientul, selectați **Selectați entitatea pentru un nivel secundar**. Dacă opțiunea nu este disponibilă, asigurați-vă că ați finalizat secțiunea anterioară.

1. Extindeți entitățile din care doriți să alegeți nivelul secundar sau utilizați caseta de filtrare a căutării pentru a filtra opțiunile selectate.

1. Alegeți atributul pe care doriți să îl utilizați ca nivel secundar, apoi selectați **Adăugare**.

1. Selectați **Următorul**.

> [!NOTE]
> Entitățile disponibile în această secțiune sunt afișate deoarece au o relație cu entitatea pe care ați ales-o în secțiunea anterioară. Dacă nu vedeți entitatea pe care doriți să o adăugați, asigurați-vă că are o relație validă în **Relații**. Numai relațiile unu-la-unu și mai multe la unu sunt valabile pentru această configurație.

### <a name="add-additional-data-optional"></a>Adăugați date suplimentare (opțional)

Configurați relația de la entitatea dvs. de activitate a clienților la entitatea *Client*.

1. Selectați câmpul care identifică clientul în tabelul de activitate a clienților. Poate fi legat direct de ID-ul de client principal al entității dvs. *Client*.

1. Selectați entitatea care este principalula dvs. entitate *Client*.

1. Introduceți un nume care descrie relația.

#### <a name="customer-activities"></a>Activități ale clienților

1. Opțional, selectați **Adăugare date** pentru **Activitățile clienților**.

1. Selectați tipul de activitate semantică care conține datele pe care doriți să le utilizați, apoi selectați una sau mai multe activități în secțiunea **Activități**.

1. Selectați un tip de activitate care să corespundă tipului de activitate a clientului pe care o configurați. Selectați **Creare nou** și alegeți un tip de activitate disponibil sau creați un tip nou.

1. Selectați **Următorul**, apoi **Salvați**.

1. Dacă aveți alte activități ale clienților pe care doriți să le includeți, repetați pașii de mai sus.

#### <a name="customers-data"></a>Datele clienților

1. Opțional, selectați **Adăugați date** pentru **Date despre clienți**.

1. Mapați atributele semantice la câmpurile din propriile date ale clienților, așa cum au fost identificate. Datele din câmpurile utilizate nu ar trebui să se schimbe des pentru a asigura cea mai bună performanță a modelului. De exemplu, selectarea unui câmp pentru „Clasificare” care s-a schimbat în fiecare lună va avea doar ultima valoare utilizată în predicție, chiar dacă din punct de vedere istoric aceeași valoare s-ar putea să nu se aplice clientului atunci când construiește modelele de predicție.

1. Selectați **Următorul**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Furnizați o listă opțională de conturi de referință

Adăugați o listă a clienților și conturilor dvs. de afaceri pe care doriți să le utilizați ca etaloane de referință. Veți primi [detalii pentru aceste conturi de referință](#review-a-prediction-status-and-results) inclusiv scorul lor de churn și cele mai influente caracteristici care au afectat predicția lor de retragere.

1. Selectați **+ Adăugați clienți**.

1. Alegeți clienții care acționează ca reper.

1. Selectați **Următorul** pentru a continua.

---

### <a name="set-schedule-and-review-configuration"></a>Setați programul și examinați configurația

1. Setați o frecvență pentru a vă reinstrui modelul. Această setare este importantă pentru a actualiza precizia predicțiilor pe măsură ce sunt ingerate date noi. Majoritatea firmelor pot reinstrui o dată pe lună și pot obține o precizie bună pentru predicția lor.

1. Selectați **Următorul**.

1. Verificați configurația predicției. Puteți reveni la pașii anteriori selectând **Editare** sub valoarea arătată. Sau puteți selecta un pas de configurare din indicatorul de progres.

1. Dacă toate valorile sunt configurate corect, selectați **Salvare și rulare** pentru a începe procesul de predicție. Din fila **Predicțiile mele**, puteți vedea starea predicțiilor dvs. Procesul poate dura câteva ore până la finalizare, în funcție de cantitatea de date utilizate în predicție.

## <a name="review-a-prediction-status-and-results"></a>Analizați starea predicțiilor și rezultatele

1. Mergeți la **Informații** > **Predicții** și selectați fila **Previziunile mele**.

1. Selectați predicția pe care doriți să o revizuiți.
   - **Nume predicție**: Numele predicției furnizat la crearea acesteia.
   - **Tip predicție**: Tipul modelului utilizat pentru predicție
   - **Entitate de ieșire**: Numele entității care va stoca rezultatul predicției. Puteți găsi o entitate cu acest nume în **Date** > **Entități**.
     În entitatea de ieșire, *ChurnScore* este probabilitatea prezisă de dezactivare și *IsChurn* este o etichetă binară bazată pe *ChurnScore* cu 0,5 prag. Este posibil ca pragul implicit să nu funcționeze pentru scenariul dvs. [Creați un segment nou](segments.md#create-a-new-segment) cu pragul preferat.
     Nu toți clienții sunt în mod necesar clienți activi. Este posibil ca unii dintre ei să nu fi avut nicio activitate de mult timp și să fie considerați deja derutați, pe baza definiției dvs. de retragere. Prezicerea riscului de retragere pentru clienții care deja au retragere nu este utilă deoarece nu sunt publicul de interes.
   - **Câmp prevăzut**: Acest câmp este populat numai pentru anumite tipuri de predicții și nu este utilizat în predicția retragerii.
   - **Stare**: Starea rulării predicției.
        - **În așteptare**: Predicția așteaptă să se execute alte procese.
        - **Reîmprospătare**: Predicția rulează în prezent pentru a produce rezultate care vor curge în entitatea de ieșire.
        - **Eșuat**: Rularea predicției a eșuat. Pentru mai multe detalii, [consultați fișierele-jurnal](manage-predictions.md#troubleshoot-a-failed-prediction).
        - **Reușit**: Predicția a reușit. Selectați **Vizualizare** sub elipsele verticale pentru a analiza predicția
   - **Editat**: Data la care configurația predicției a fost modificată.
   - **Ultima actualizare**: Data la care predicția a fost reîmprospătată având ca rezultat entitatea de ieșire.

1. Selectați elipsele verticale de lângă predicția pentru care doriți să analizați rezultatele și selectați **Vizualizare**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Vizualizați controlul pentru a vedea rezultatele unui predicții.":::

# <a name="individual-consumers-b-to-c"></a>[Consumatori individuali (B2C)](#tab/b2c)

1. Există trei secțiuni principale de date în pagina de rezultate:
   - **Performanța modelului de instruire**: A, B sau C sunt scoruri posibile. Acest scor indică performanța predicției și vă poate ajuta să luați decizia de a utiliza rezultatele stocate în entitatea de ieșire. Scorurile sunt determinate pe baza următoarelor reguli: 
        - **A** atunci când modelul a prezis cu acuratețe cel puțin 50% din predicțiile totale și când procentul de predicții exacte pentru clienții care s-au retras este mai mare decât rata inițială cu cel puțin 10%.
            
        - **B** atunci când modelul a prezis cu acuratețe cel puțin 50% din predicțiile totale și când procentul de predicții exacte pentru clienții care s-au retras este cu până la 10% mai mare decât rata inițială.
            
        - **C** atunci când modelul a prezis cu acuratețe mai puțin de 50% din predicțiile totale sau când procentul de predicții exacte pentru clienții care s-au retras este mai mic decât rata inițială.
               
        - **Referința** preia intrarea ferestrei de timp de predicție pentru model (de exemplu, un an), iar modelul creează fracții diferite de timp împărțindu-l la 2 până ajunge la o lună sau mai puțin. Utilizează aceste fracții pentru a crea o regulă de afaceri pentru clienții care nu au achiziționat în acest interval de timp. Acești clienți sunt considerați ca fiind retrași. Ca rată inițială este aleasă regula de afaceri bazată pe timp, cu cea mai mare capacitate de a prezice cine este susceptibil să se retragă.
            
    - **Probabilitatea de retragere (număr de clienți)**: Grupuri de clienți în funcție de riscul de retragere prognozat. Aceste date vă pot ajuta mai târziu dacă doriți să creați un segment de clienți cu risc ridicat de retragere. Astfel de segmente vă ajută să înțelegeți unde ar trebui să fie delimitarea dvs. pentru membrii segmentului.
       
    - **Cei mai influenți factori**: Există mulți factori care sunt luați în considerare atunci când vă creați predicția. Fiecare dintre factori are importanța sa calculată pentru predicțiile agregate pe care le creează un model. Puteți utiliza acești factori pentru a vă valida rezultatele predicție sau puteți utiliza aceste informații mai târziu pentru a [crea segmente](segments.md) care ar putea ajuta la influențarea riscului de retragere pentru clienți.


# <a name="business-accounts-b-to-b"></a>[Conturi de afaceri (B2B)](#tab/b2b)

1. Există trei secțiuni principale de date în pagina de rezultate:
   - **Performanța modelului de instruire**: A, B sau C sunt scoruri posibile. Acest scor indică performanța predicției și vă poate ajuta să luați decizia de a utiliza rezultatele stocate în entitatea de ieșire. Scorurile sunt determinate pe baza următoarelor reguli: 
        - **A** atunci când modelul a prezis cu acuratețe cel puțin 50% din predicțiile totale și când procentul de predicții exacte pentru clienții care s-au retras este mai mare decât rata inițială cu cel puțin 10%.
            
        - **B** atunci când modelul a prezis cu acuratețe cel puțin 50% din predicțiile totale și când procentul de predicții exacte pentru clienții care s-au retras este cu până la 10% mai mare decât rata inițială.
            
        - **C** atunci când modelul a prezis cu acuratețe mai puțin de 50% din predicțiile totale sau când procentul de predicții exacte pentru clienții care s-au retras este mai mic decât rata inițială.
               
        - **Referința** preia intrarea ferestrei de timp de predicție pentru model (de exemplu, un an), iar modelul creează fracții diferite de timp împărțindu-l la 2 până ajunge la o lună sau mai puțin. Utilizează aceste fracții pentru a crea o regulă de afaceri pentru clienții care nu au achiziționat în acest interval de timp. Acești clienți sunt considerați ca fiind retrași. Ca rată inițială este aleasă regula de afaceri bazată pe timp, cu cea mai mare capacitate de a prezice cine este susceptibil să se retragă.
            
    - **Probabilitatea de retragere (număr de clienți)**: Grupuri de clienți în funcție de riscul de retragere prognozat. Aceste date vă pot ajuta mai târziu dacă doriți să creați un segment de clienți cu risc ridicat de retragere. Astfel de segmente vă ajută să înțelegeți unde ar trebui să fie delimitarea dvs. pentru membrii segmentului.
       
    - **Cei mai influenți factori**: Există mulți factori care sunt luați în considerare atunci când vă creați predicția. Fiecare dintre factori are importanța sa calculată pentru predicțiile agregate pe care le creează un model. Puteți utiliza acești factori pentru a vă valida rezultatele predicție sau puteți utiliza aceste informații mai târziu pentru a [crea segmente](segments.md) care ar putea ajuta la influențarea riscului de retragere pentru clienți.


1. Pentru conturile de afaceri, veți găsi o pagină de informații **Analiza caracteristicilor influențiale**. Conține patru secțiuni de date:

    - Elementul selectat în panoul din dreapta determină conținutul de pe această pagină. Selectați un articol din **Clienți de top** sau **Clienți de referință**. Ambele liste sunt ordonate în funcție de scăderea valorii scurnului, indiferent dacă scorul este doar pentru client sau un scor combinat pentru clienți și un nivel secundar, cum ar fi categoria de produse.
        
        - **Clienți de top**: Lista celor 10 clienți care prezintă cel mai mare risc de retragere și cel mai scăzut risc de retragere pe baza scorurilor lor de retragere. 
        - **Clienți de referință**: Listă de până la 10 clienți care au fost selectați în timpul configurării modelului.
 
    - **Scor de retragere:** Afișează scorul de retragere pentru elementul selectat în panoul din dreapta.
    
    - **Distribuția riscului de retragere:** Arată distribuția riscului de dezactivare între clienți și percentila în care se află clientul selectat. 
    
    - **Caracteristicile de top cresc și scad riscul de retragere:** Pentru elementul selectat din panoul din dreapta, sunt listate primele cinci caracteristici care au crescut și au scăzut riscul de retragere. Pentru fiecare caracteristică influentă, găsiți valoarea caracteristicii pentru acel element și influența acestuia asupra scorului de retragere. Se afișează, de asemenea, valoarea medie a fiecărei caracteristici pe segmente de clienți cu retragere redus, mediu și ridicat. Ajută la o mai bună contextualizare a valorilor caracteristicilor influente de top pentru elementul selectat și compararea acestuia cu segmentele de clienți mici, medii și ridicate.

       - Scăzut: conturi sau combinații de conturi și nivel secundar cu un scor de retragere între 0 și 0,33
       - Mediu: conturi sau combinații de conturi și niveluri secundare cu un scor de retragere între 0,33 și 0,66
       - Ridicat: conturi sau combinații de conturi și niveluri secundare cu un scor de retragere mai mare decât 0,66
    
       Când preziceți churn la nivel de cont, toate conturile sunt luate în considerare la obținerea valorilor medii ale caracteristicilor pentru segmente de retragere. Pentru predicțiile de retragere la nivelul secundar pentru fiecare cont, derivarea segmentelor de retragere depinde de nivelul secundar al elementului selectat în panoul lateral. De exemplu, dacă un articol are un nivel secundar de categorie de produse = rechizite de birou, atunci numai articolele cu rechizite de birou ca categorie de produse sunt luate în considerare la obținerea valorilor medii ale caracteristicilor pentru segmentele de retragere. Această logică este aplicată pentru a asigura o comparație echitabilă a valorilor caracteristicilor articolului cu valorile medii pe segmente mici, medii și mari.

       În unele cazuri, valoarea medie a segmentelor de retragere scăzută, medie sau ridicată este goală sau nu este disponibilă deoarece nu există articole care să aparțină segmentelor de retragere corespunzătoare pe baza definiției de mai sus.
       
       > [!NOTE]
       > Interpretarea valorilor din coloanele medie scăzută, medie și ridicată este diferită pentru caracteristicile de categorii precum țara sau industria. Deoarece noțiunea de valoare „medie” a caracteristicii nu se aplică caracteristicilor de tip categorie, valorile din aceste coloane reprezintă proporția de clienți din segmentele cu retragere scăzută, medie sau mare care au aceeași valoare a caracteristicii de categorie în comparație cu elementul selectat în panoul lateral.

---

## <a name="manage-predictions"></a>Gestionați predicțiile

Este posibil să optimizați, să depanați, să reîmprospătați sau să ștergeți predicțiile. Examinați un raport de utilizare a datelor de intrare pentru a afla cum să faceți o predicție mai rapid și mai fiabil. Pentru informații suplimentare, accesați [Gestionați predicții](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
