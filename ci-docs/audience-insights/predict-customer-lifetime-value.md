---
title: Predicția valorii pe viață a clientului (CLV)
description: Prevedeți potențialul de venituri pentru clienții activi în viitor.
ms.date: 02/05/2021
ms.reviewer: wameng
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 363a46c81b5bb737d274998f9a699dc662e38d7c
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268609"
---
# <a name="customer-lifetime-value-clv-prediction-preview"></a>Valoare ciclu de viață client (versiune preliminară) (CLV)

Preziceți valoarea potențială (veniturile) pe care clienții activi individuali o vor aduce în afacerea dvs. într-o perioadă de timp viitoare definită. Această funcție vă poate ajuta să atingeți diferite obiective: 
- Identificați clienții cu valoare ridicată și procesați această perspectivă
- Creați segmente de clienți strategici pe baza valorii potențiale a acestora pentru a derula campanii personalizate cu eforturi de vânzări, marketing și asistență direcționate
- Ghidați dezvoltarea produselor concentrându-vă pe caracteristicile care măresc valoarea clienților
- Optimizați strategia de vânzări sau de marketing și alocați bugetul mai precis pentru contactarea clienților
- Recunoașteți și recompensați clienții cu valoare ridicată prin programe de loialitate sau recompense 

## <a name="prerequisites"></a>Cerințe preliminare

Înainte de a începe, reflectați ce înseamnă CLV pentru afacerea dvs. În prezent, acceptăm CLV bazat pe tranzacții predicție. Valoarea estimată a unui client se bazează pe istoricul tranzacțiilor comerciale. Pentru a crea predicție, aveți nevoie de permisiuni de cel puțin [Colaborator](permissions.md).

Deoarece configurarea și rularea unui model CLV nu necesită mult timp, luați în considerare crearea mai multor modele cu preferințe de intrare variate și comparați rezultatele modelului pentru a vedea ce scenariu de model se potrivește cel mai bine nevoilor dvs. de afaceri.

###  <a name="data-requirements"></a>Cerinţe de date

Următoarele date sunt necesare și, dacă sunt marcate opțional, recomandate pentru o performanță sporită a modelului. Cu cât modelul poate prelucra mai multe date, cu atât va fi mai precisă predicția. Prin urmare, vă încurajăm să efectuați ingerarea mai multor date despre activitatea clienților, dacă sunt disponibile.

- Identificator client: identificator unic pentru a potrivi tranzacțiile cu un client individual

- Istoricul tranzacțiilor: jurnalul istoric al tranzacțiilor cu schema de date semantice de mai jos
    - ID-ul de tranzacție: identificator unic al fiecărei tranzacții
    - Data tranzacției: Data, de preferință un marcaj de timp al fiecărei tranzacții
    - Valoarea tranzacției: valoarea monetară (de exemplu, venitul sau marja de profit) a fiecărei tranzacții
    - Etichetă atribuită returnărilor (opțional): valoare booleană care indică dacă tranzacția este o returnare 
    - ID produs (opțional): ID produs al produsului implicat în tranzacție

- Date suplimentare (opțional), de exemplu
    - Activități web: istoricul vizitelor site-ului web, istoricul e-mailurilor
    - Activități de loialitate: puncte de recompensă de loialitate acumulate și istoricul de răscumpărare
    - Serviciu pentru relații cu clienții jurnal, apel de serviciu, reclamație sau istoricul de returnare
- Date despre activitățile clienților (opțional):
    - Identificatori de activitate pentru a distinge activitățile de același tip
    - Identificatori ai clienților pentru asocia activitățile cu clienții dvs.
    - Informații despre activitate care conțin numele și data activității
    - Schema de date semantice pentru activități include: 
        - Cheia primară: Un identificator unic pentru o activitate
        - Marcaj temporal: Data și ora evenimentului identificate de cheia primară
        - Eveniment (numele activității): numele evenimentului pe care doriți să îl utilizați
        - Detalii (suma sau valoarea): detalii despre activitatea clientului

## <a name="create-a-customer-lifetime-value-prediction"></a>Creați o predicție a valorii duratei de viață a clientului

1. În Detalii despre public, accesați **Informații** > **Predicții**.

1. Selectați dala **Valoarea duratei de viață a clientului** și selectați **Utilizați modelul**. 

1. În panoul **Valoarea duratei de viață a clientului (previzualizare)**, selectați **Începeți**.

1. **Denumiți acest model** și **Numele entității de ieșire** pentru a le distinge de alte modele sau entități.

1. Selectați **Următorul**.

### <a name="define-model-preferences"></a>Definiți preferințe de model

1. Setați o **Perioadă de timp de predicție** pentru a defini cât de departe în viitor doriți să preziceți CLV.    
   În mod implicit, unitatea este setată ca luni. Îl puteți schimba în ani pentru a privi mai departe în viitor.

   > [!TIP]
   > Pentru a prezice cu precizie CLV pentru perioada de timp setată, aveți nevoie de o perioadă comparabilă de date istorice. De exemplu, dacă doriți să preziceți pentru următoarele 12 luni, se recomandă să aveți cel puțin 18 - 24 de luni de date istorice.

1. Specificați ce înseamnă **Clienți activi** pentru afacerea ta. Setați intervalul de timp în care un client trebuie să fi avut cel puțin o tranzacție pentru a fi considerat activ. Modelul va prezice CLV numai pentru clienții activi. 
   - **Lăsați modelul să calculeze intervalul de cumpărare (recomandat)**: Modelul analizează datele dvs. și determină o perioadă de timp pe baza achizițiilor istorice.
   - **Setați intervalul manual**: Dacă aveți o definiție comercială specifică a unui client activ, alegeți această opțiune și setați perioada de timp în consecință.

1. Definiți percentila de **Client cu valoare ridicată** pentru a permite modelului să ofere rezultate care se potrivesc definiției afacerii dvs.
    - **Calculul modelului (recomandat)**: Modelul analizează datele dvs. și determină ce ar putea fi un client de valoare ridicată pentru afacerea dvs. pe baza istoricului tranzacțiilor clienților dvs. Modelul folosește o regulă euristică (inspirată de regula 80/20 sau principiul pareto) pentru a găsi proporția clienților cu valoare ridicată. Procentul de clienți care au contribuit la 80% din venitul cumulat pentru afacerea dvs. în perioada istorică sunt considerați clienți cu valoare ridicată. De obicei, mai puțin de 30-40% clienți contribuie la 80% venituri cumulate. Cu toate acestea, acest număr poate varia în funcție de afacerea și industria dvs.    
    - **Procentul clienților activi de top**: Definiți clienți de mare valoare pentru afacerea dvs. ca o percentilă a clienților cu plată activă de top. De exemplu, puteți utiliza această opțiune pentru a defini clienții cu valoare ridicată ca primii 20% din viitorii clienți plătitori.

    Dacă afacerea dvs. definește clienții cu valoare ridicată într-un mod diferit, [anunțați-ne pentru că ne-ar plăcea să aflăm](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Selectați **Următorul** pentru a trece la pasul următor.

### <a name="add-required-data"></a>Adăugați datele necesare

1. În pasul **Date necesare**, selectați **Adăugați date** pentru **Istoric tranzacții clienți** și alegeți entitatea care furnizează informații despre istoricul tranzacțiilor așa cum este descris în [cerințele preliminare](#prerequisites).

1. Asociați câmpurile semantice la atributele din cadrul entității din istoricul achizițiilor și selectați **Următorul**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Imagine a pasului de configurare pentru maparea atributelor de date pentru datele necesare.":::
 
1. Dacă câmpurile de mai jos nu sunt completate, configurați relația de la entitatea din istoricul achizițiilor la entitatea *Client* și selectați **Salvare**.
    1. Selectați entitate istoric tranzacții.
    1. Selectați câmpul care identifică un client în entitatea de istoric al achizițiilor. Trebuie să fie asociat ID-ului clientului primar al entității dvs. client.
    1. Selectați entitatea care corespunde entității clientului dvs. primar.
    1. Introduceți un nume care descrie relația.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Imagine a etapei de configurare pentru a defini relația cu entitatea client.":::

1. Selectați **Următorul**.

### <a name="add-optional-data"></a>Adăugați date opționale

Datele care reflectă interacțiunile cheie ale clienților (cum ar fi web, serviciu pentru relații cu clienții și jurnalele de evenimente) adaugă context înregistrărilor tranzacțiilor. Mai multe modele găsite în datele de activitate ale clienților dvs. pot îmbunătăți precizia predicțiilor. 

1. În pasul **Date suplimentare (opțional)**, selectați **Adăugați date**. Alegeți entitatea de activitate client care furnizează informații despre activitatea clienților așa cum este descris în [cerințele preliminare](#prerequisites).

1. Asociați câmpurile semantice la atributele din cadrul entității cu activitatea clientului și selectați **Următorul**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Imagine a pasului de configurare pentru maparea câmpurilor pentru date adiționale.":::

1. Selectați un tip de activitate care se potrivește cu tipul de activitate a clienților pe care îl adăugați. Alegeți dintre tipurile de activitate existente sau adăugați un tip de activitate nou.

1. Configurați relația de la entitatea dvs. de activitate a clienților la entitatea *Client*.
    
    1. Selectați câmpul care identifică clientul în tabelul de activitate a clienților. Poate fi legat direct de ID-ul de client principal al entității dvs. *Client*.
    1. Selectați entitatea *Client* care se potrivește cu entitatea *Client* primară.
    1. Introduceți un nume care descrie relația.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Imagine a pasului din fluxul de configurare pentru a adăuga date suplimentare și pentru a configura activitatea cu exemple completate.":::

1. Selectați **Salvare**.    
    Adăugați mai multe date dacă doriți să includeți alte activități ale clienților.

1. Selectați **Următorul**.

### <a name="set-update-schedule"></a>Configurați planificarea actualizărilor

1. În pasul **Planificare de actualizare a datelor**, alegeți frecvența de re-instruire a modelului pe baza celor mai recente date. Această setare este importantă pentru a actualiza precizia predicțiilor pe măsură ce sunt ingerate date noi în detaliile despre public. Majoritatea firmelor pot reinstrui o dată pe lună și pot obține o precizie bună pentru predicția lor.

1. Selectați **Următorul**.


### <a name="review-and-run-the-model-configuration"></a>Examinați și rulați configurația modelului

1. În pasul **Examinați detaliile modelului**, validați configurația predicției. Puteți reveni la orice parte a configurării predicției selectând **Editare** sub valoarea afișată. De asemenea, puteți selecta un pas de configurare din indicatorul de progres.

1. Dacă toate valorile sunt configurate corect, selectați **Salvați și rulați** pentru a începe rularea modelului. Pe fila **Previziunile mele**, puteți vedea starea procesului predicție. Procesul poate dura câteva ore până la finalizare, în funcție de cantitatea de date utilizate în predicție.

## <a name="review-prediction-status-and-results"></a>Examinați starea și rezultatele predicție

### <a name="review-prediction-status"></a>Examinați starea de predicție

1.  Mergeți la **Informații** > **Predicții** și selectați fila **Previziunile mele**.
2.  Selectați predicția pe care doriți să o revizuiți.

- **Nume predicție**: Numele predicției furnizat la crearea acesteia.
- **Tip predicție**: Tipul modelului utilizat pentru predicție
- **Entitate de ieșire**: Numele entității care va stoca rezultatul predicției. Accesați **Date** > **Entități** pentru a găsi entitatea cu acest nume.
- **Câmp estimat**: Acest câmp este populat numai pentru anumite tipuri de predicții și nu este utilizat în predicția valorii ciclului de viață a clientului.
- **Stare**: Starea rulării predicției.
    - **În așteptare**: Predicția așteaptă să se finalizeze alte procese.
    - **Reîmprospătare**: Predicția rulează în prezent pentru a crea rezultate care vor curge în entitatea de ieșire.
    - **Eșuat**: Rularea predicției a eșuat. Pentru mai multe detalii, [consultați fișierele-jurnal](#troubleshoot-a-failed-prediction).
    - **Reușit**: Predicția a reușit. Selectați **Vizualizare** sub elipsele verticale pentru a examina rezultatele predicției.
- **Editat**: Data la care configurația predicției a fost modificată.
- **Ultima actualizare**: Data la care predicția a fost reîmprospătată având ca rezultat entitatea de ieșire.


### <a name="review-prediction-results"></a>Examinați rezultatele predicției

1. Mergeți la **Informații** > **Predicții** și selectați fila **Previziunile mele**.

1. Selectați predicția pentru care doriți să examinați rezultatele.

Există trei secțiuni principale de date în pagina de rezultate.

- **Performanța modelului de antrenament** : A, B sau C sunt posibile niveluri. Această notă indică performanța predicție și vă poate ajuta să luați decizia de a utiliza rezultatele stocate în entitatea de ieșire. Selectați **Aflați mai multe despre acest scor** pentru a înțelege mai bine valorile de bază ale performanței modelului și modul în care a fost derivat nivelul final de performanță al modelului.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Imagine a casetei de informare a scorului modelului cu nota A.":::

  Folosind definiția clienților cu valoare ridicată furnizată în timp ce configurați predicție, sistemul evaluează modul în care a funcționat modelul AI în prezicerea clienților cu valoare ridicată în comparație cu un model de bază.    

  Nivelurile sunt stabilite pe baza următoarelor reguli:
  - A când modelul a prezis cu precizie cu cel puțin 5% mai mulți clienți de valoare ridicată în comparație cu modelul de bază.
  - B când modelul a prezis cu precizie între 0-5% mai mulți clienți de valoare ridicată în comparație cu modelul de bază.
  - C când modelul a prezis cu precizie mai puțini clienți de valoare ridicată în comparație cu modelul de bază.

  Panoul **Evaluarea modelului** afișează detalii suplimentare despre performanța modelului AI și modelul de bază. Modelul de bază folosește o abordare care nu se bazează pe IA pentru a calcula valoarea pe viață a clienților pe baza în principal a achizițiilor istorice efectuate de clienți.     
  Formula standard utilizată pentru a calcula CLV după modelul de bază:    

  *CLV pentru fiecare client = cumpărarea medie lunară efectuată de client în fereastra activă a clientului * Numărul de luni în perioada CLV predicție * Rata de retenție în ansamblu a tuturor clienților*

  Modelul AI este comparat cu modelul de bază bazat pe două valori de performanță ale modelului.
  
  - **Rata de succes în prezicerea clienților de valoare ridicată**

  Vedeți diferența în prezicerea clienților cu valoare ridicată utilizând modelul AI comparativ cu modelul de bază. De exemplu, rata de succes de 84% înseamnă că dintre toți clienții cu valoare ridicată din datele de instruire, modelul AI a reușit să capteze cu precizie 84%. Apoi comparăm această rată de succes cu rata de succes a modelului de bază pentru a raporta modificarea relativă. Această valoare este utilizată pentru a atribui un nivel modelului.

  - **Valori de eroare**
    
  O altă valoare vă permite să examinați performanța generală a modelului în termeni de eroare în prezicerea valorilor viitoare. Folosim măsurătoarea generală Root Mean Squared Error (RMSE) pentru a evalua această eroare. RMSE este un mod standard de măsurare a erorii unui model în prezicerea datelor cantitative. RMSE al modelului AI este comparat cu RMSE al modelului de bază și se raportează diferența relativă.

  Modelul AI acordă prioritate clasării exacte a clienților în funcție de valoarea pe care o aduc afacerii dvs. Deci, numai rata de succes a prezicerii clienților cu valoare ridicată este utilizată pentru a obține nota modelului final. Valoarea RMSE este sensibilă la valori aberante. În scenariile în care aveți un procent mic de clienți cu valori de achiziție extraordinar de mari, valoarea generală RMSE ar putea să nu ofere o imagine completă a performanței modelului.   

- **Valoarea clienților după procente**: Folosind definiția dvs. de clienți cu valoare ridicată, clienții sunt grupați în valoare scăzută și valoare ridicată, pe baza predicțiilor CLV și sunt afișați într-un grafic. Plasând cursorul peste barele din histogramă, puteți vedea numărul de clienți din fiecare grup și valoarea medie CLV a grupului respectiv. Aceste date vă pot ajuta dacă doriți să [creați segmente de clienți](segments.md) pe baza predicțiilor CLV.

- **Cei mai influenți factori**: Diverși factori sunt luați în considerare atunci când creați CLV-ul predicție pe baza datelor de intrare furnizate modelului AI. Fiecare dintre factori are o importanță calculată pentru predicțiile agregate pe care le creează un model. Puteți utiliza acești factori pentru a vă ajuta la validarea rezultatelor predicției. Acești factori oferă, de asemenea, mai multe informații despre cei mai influenți factori care au contribuit la prezicerea CLV pentru toți clienții dvs.

## <a name="refresh-a-prediction"></a>Reîmprospătați o predicție

Predicțiile se reîmprospătează automat pe același [program cu care se reîmprospătează datele](system.md#schedule-tab) așa cum este configurat în setări. Le puteți reîmprospăta și manual.

1. Mergeți la **Informații** > **Predicții** și selectați fila **Previziunile mele**.
2. Selectați elipsele verticale de lângă predicția pe care doriți să o reîmprospătați.
3. Selectați **Reîmprospătare**.

## <a name="delete-a-prediction"></a>Ștergerea unei predicții

Ștergerea unui predicții elimină și entitatea acesteia de ieșire.

1. Mergeți la **Informații** > **Predicții** și selectați fila **Previziunile mele**.
2. Selectați elipsele verticale de lângă predicția pe care doriți să o ștergeți.
3. Selectați **Ștergere**.

## <a name="troubleshoot-a-failed-prediction"></a>Depanarea unei predicții eșuate

1. Mergeți la **Informații** > **Predicții** și selectați fila **Previziunile mele**.
2. Selectați elipsele verticale de lângă predicția pentru care doriți să vedeți jurnalele de erori.
3. Selectați **Jurnale**.
4. Analizarea tuturor erorilor. Există mai multe tipuri de erori care pot apărea și ce descriu condiția care a cauzat eroarea. De exemplu, o eroare conform căreia nu există suficiente date pentru a prezice cu precizie este de obicei rezolvată prin încărcarea mai multor date în detalii despre public.


[!INCLUDE[footer-include](../includes/footer-banner.md)]