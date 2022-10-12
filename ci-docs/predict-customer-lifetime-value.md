---
title: Preziceți valoarea ciclului de viață a clientului (CLV)
description: Prevedeți potențialul de venituri pentru clienții activi în viitor.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610389"
---
# <a name="predict-customer-lifetime-value-clv"></a>Preziceți valoarea ciclului de viață a clientului (CLV)

Preziceți valoarea potențială (veniturile) pe care clienții activi individuali o vor aduce în afacerea dvs. într-o perioadă de timp viitoare definită. Acest predicție vă ajută:

- Identificați clienții de mare valoare și procesați această perspectivă.
- Creați segmente strategice de clienți pe baza valorii lor potențiale pentru a derula campanii personalizate cu vânzări, marketing și eforturi de asistență direcționate.
- Ghidați dezvoltarea produsului concentrându-vă pe caracteristicile care măresc valoarea clientului.
- Optimizați strategia de vânzări sau de marketing și alocați bugetul mai precis pentru atingerea clienților.
- Recunoașteți și recompensați clienții de mare valoare prin programe de loialitate sau de recompense.

Determinați ce înseamnă CLV pentru afacerea dvs. Acceptăm CLV bazat pe tranzacții predicție. Valoarea estimată a unui client se bazează pe istoricul tranzacțiilor comerciale. Luați în considerare crearea mai multor modele cu preferințe de intrare diferite și comparați rezultatele modelului pentru a vedea care scenariu de model se potrivește cel mai bine nevoilor dvs. de afaceri.

> [!TIP]
> Încercați CLV predicție folosind date eșantion: [Valoarea de viață a clientului (CLV) predicție exemplu de ghid](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Cerințe preliminare

- Macar [Colaborator](permissions.md) permisiuni
- Cel puțin 100 de clienți unici, de preferință mai mult de 10.000 de clienți
- Customer Identifier, un identificator unic pentru a potrivi tranzacțiile cu un client individual
- Cel puțin un an de istorie a tranzacțiilor, de preferință doi până la trei ani. În mod ideal, cel puțin două până la trei tranzacții pentru fiecare ID de client, de preferință pe mai multe date. Istoricul tranzacțiilor trebuie să includă:
  - **ID-ul de tranzacție**: identificator unic al fiecărei tranzacții
  - **Data tranzacției** : marcarea datei sau orei fiecărei tranzacții
  - **Valoarea tranzacției**: valoarea monetară (de exemplu, venitul sau marja de profit) a fiecărei tranzacții
  - **Etichetă atribuită retururilor** : Valoare booleană adevărat/fals care indică dacă tranzacția este o returnare
  - **ID produs** : ID-ul produsului al produsului implicat în tranzacție
- Date despre activitățile clienților:
  - **Cheia principala** : identificator unic pentru o activitate
  - **Timestamp-ul** : Data și ora evenimentului identificat de cheia primară
  - **Eveniment (numele activității)** : Numele evenimentului pe care doriți să îl utilizați
  - **Detalii (suma sau valoarea)**: detalii despre activitatea clientului
- Date suplimentare precum:
  - Activități web: istoricul vizitelor pe site sau istoricul e-mailurilor
  - Activități de loialitate: acumulări de puncte de recompensă de loialitate și istoric de răscumpărare
  - Serviciu pentru relații cu clienții jurnal: istoricul apelurilor de service, al reclamației sau al returnărilor
  - Informații despre profilul clientului
- Mai puțin de 20% valori lipsă în câmpurile obligatorii

> [!NOTE]
> Poate fi configurată o singură entitate istorică a tranzacțiilor. Dacă există mai multe entități de cumpărare sau tranzacție, combinați-le Power Query înainte de ingerarea datelor.

## <a name="create-a-customer-lifetime-value-prediction"></a>Creați o predicție a valorii duratei de viață a clientului

Selectați **Salveaza schita** oricând pentru a salva predicție ca schiță. Proiectul predicție este afișat în **Previziunile mele** fila.

1. Mergi la **Inteligența** > **Previziuni**.

1. Pe **Crea** filă, selectați **Utilizați modelul** pe **Valoarea de viață a clientului** ţiglă.

1. Selectați **Începeți**.

1. **Denumiți acest model** și **Numele entității de ieșire** pentru a le distinge de alte modele sau entități.

1. Selectați **Următorul**.

### <a name="define-model-preferences"></a>Definiți preferințe de model

1. Setați o **Perioadă de timp de predicție** pentru a defini cât de departe în viitor doriți să preziceți CLV. În mod implicit, unitatea este setată ca luni.

   > [!TIP]
   > Pentru a prezice cu exactitate CLV pentru perioada de timp stabilită, este necesară o perioadă comparabilă de date istorice. De exemplu, dacă doriți să estimați CLV pentru următoarele 12 luni, aveți cel puțin 18 – 24 de luni de date istorice.

1. Setați intervalul de timp în care un client trebuie să fi avut cel puțin o tranzacție pentru a fi considerat activ. Modelul prezice doar CLV pentru **Clienți activi**.
   - **Lăsați modelul să calculeze intervalul de achiziție (recomandat)** : Modelul analizează datele dvs. și determină o perioadă de timp pe baza achizițiilor istorice.
   - **Setați manual intervalul** : Perioada de timp pentru definirea dvs. a unui client activ.

1. Definiți percentila a **Client de mare valoare**.
    - **Calcul model (recomandat)** : Modelul folosește regula 80/20. Procentul de clienți care au contribuit la 80% din venitul cumulat pentru afacerea dvs. în perioada istorică sunt considerați clienți cu valoare ridicată. De obicei, mai puțin de 30-40% clienți contribuie la 80% venituri cumulate. Cu toate acestea, acest număr poate varia în funcție de afacerea și industria dvs.
    - **Procentul de clienți activi de top** : Percentilă specifică pentru un client de mare valoare. De exemplu, introduceți **25** pentru a defini clienții de mare valoare ca fiind primii 25% dintre viitorii clienți plătitori.

    Dacă afacerea dvs. definește clienții cu valoare ridicată într-un mod diferit, [anunțați-ne pentru că ne-ar plăcea să aflăm](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Selectați **Următorul**.

### <a name="add-required-data"></a>Adăugați datele necesare

1. Selectați **Adăugați date** pentru **Istoricul tranzacțiilor clienților**.

1. Selectați tipul de activitate semantică, **Comandă de vânzări** sau **SalesOrderLine**, care conține istoricul tranzacțiilor. Dacă activitatea nu a fost configurată, selectați **Aici** și creează-l.

1. Sub **Activități**, dacă atributele activității au fost mapate semantic atunci când activitatea a fost creată, alegeți atributele sau entitatea specifice pe care doriți să se concentreze calculul. Dacă maparea semantică nu a avut loc, selectați **Editați | ×** și mapați datele dvs.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Adăugați datele necesare pentru modelul CLV":::

1. Selectați **Următorul** și revizuiți atributele necesare pentru acest model.

1. Selectați **Salvare**.

1. Adăugați mai multe activități sau selectați **Următorul**.

### <a name="add-optional-activity-data"></a>Adăugați date de activitate opționale

Datele care reflectă interacțiunile cheie ale clienților (cum ar fi web, serviciu pentru relații cu clienții și jurnalele de evenimente) adaugă context înregistrărilor tranzacțiilor. Mai multe modele găsite în datele de activitate ale clienților dvs. pot îmbunătăți precizia predicțiilor.

1. Selectați **Adăugați date** sub **Îmbunătățiți informațiile despre model cu date suplimentare despre activitate**.

1. Selectați un tip de activitate care se potrivește cu tipul de activitate a clienților pe care îl adăugați. Dacă activitatea nu a fost configurată, selectați **Aici** și creează-l.

1. Sub **Activități**, dacă atributele activității au fost mapate atunci când activitatea a fost creată, alegeți atributele sau entitatea specifice pe care doriți să se concentreze calculul. Dacă maparea nu a avut loc, selectați **Editați | ×** și mapați datele dvs.

1. Selectați **Următorul** și revizuiți atributele necesare pentru acest model.

1. Selectați **Salvare**.

1. Selectați **Următorul**.

1. [Adăugați date opționale ale clienților](#add-optional-customer-data) sau selectați **Următorul** și du-te la [Setați programul de actualizare](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Adăugați date opționale ale clienților

Selectați dintre 18 atribute de profil de client utilizate în mod obișnuit pentru a le include ca intrare în model. Aceste atribute pot duce la rezultate de model mai personalizate, relevante și mai acționabile pentru cazurile de utilizare ale afacerii dvs.

De exemplu: Contoso Coffee vrea să prezică valoarea de viață a clientului pentru a viza clienții de mare valoare cu o ofertă personalizată legată de lansarea noului lor espressor. Contoso folosește modelul CLV și adaugă toate cele 18 atribute ale profilului clientului pentru a vedea ce factori influențează clienții lor cu cea mai mare valoare. Ei consideră că locația clienților este factorul cel mai influent pentru acești clienți.
Cu aceste informații, ei organizează un eveniment local pentru lansarea espressorului și se asociază cu vânzătorii locali pentru oferte personalizate și o experiență specială la eveniment. Fără aceste informații, Contoso ar fi trimis doar e-mailuri de marketing generice și ar fi ratat ocazia de a se personaliza pentru acest segment local al clienților lor de mare valoare.

1. Selectați **Adăugați date** sub **Îmbunătățiți și mai mult informațiile despre model cu date suplimentare despre clienți**.

1. Pentru **Entitate**, alege **Client: CustomerInsights** pentru a selecta profilul unificat al clientului care se mapează cu datele despre atributele clientului. Pentru **Număr de înregistrare client**, alege **System.Customer.CustomerId**.

1. Hartați mai multe câmpuri dacă datele sunt disponibile în profilurile dvs. unificate de clienți.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Exemplu de câmpuri mapate pentru datele profilului clientului.":::

1. Selectați **Salvare**.

1. Selectați **Următorul**.

### <a name="set-update-schedule"></a>Configurați planificarea actualizărilor

1. Alegeți frecvența pentru a vă reeduca modelul pe baza celor mai recente date. Această setare este importantă pentru a actualiza acuratețea predicțiilor pe măsură ce noi date sunt ingerate în Customer Insights. Majoritatea firmelor pot reinstrui o dată pe lună și pot obține o precizie bună pentru predicția lor.

1. Selectați **Următorul**.

### <a name="review-and-run-the-model-configuration"></a>Examinați și rulați configurația modelului

The **Examinați și alergați** pasul arată un rezumat al configurației și oferă șansa de a face modificări înainte de a crea predicție.

1. Selectați **Editați | ×** pe oricare dintre pașii pentru a revizui și a face orice modificări.

1. Dacă sunteți mulțumit de selecțiile dvs., selectați **Salvați și rulați** pentru a începe rularea modelului. Selectați **Terminat**. The **Previziunile mele** se afișează fila în timp ce predicție este creată. Procesul poate dura câteva ore până la finalizare, în funcție de cantitatea de date utilizate în predicție.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Vedeți rezultatele predicție

1. Mergi la **Inteligența** > **Previziuni**.

1. În **Previziunile mele** fila, selectați predicție pe care doriți să-l vizualizați.

Există trei secțiuni principale de date în pagina de rezultate.

- **Performanța modelului de antrenament** : Notele A, B sau C indică performanța predicție și vă pot ajuta să luați decizia de a utiliza rezultatele stocate în entitatea de ieșire.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Imagine a casetei de informare a scorului modelului cu nota A.":::

  Customer Insights evaluează modul în care modelul de inteligență artificială s-a comportat în prezicerea clienților cu valoare mare în comparație cu un model de bază.

  Nivelurile sunt stabilite pe baza următoarelor reguli:
  - **A** când modelul a prezis cu precizie cu cel puțin 5% mai mulți clienți de valoare ridicată în comparație cu modelul de bază.
  - **B** când modelul a prezis cu precizie între 0-5% mai mulți clienți de valoare ridicată în comparație cu modelul de bază.
  - **C** când modelul a prezis cu precizie mai puțini clienți de valoare ridicată în comparație cu modelul de bază.
  
  Selectați [**Aflați despre acest scor**](#learn-about-the-score) pentru a deschide **Evaluarea modelului** panoul care arată mai multe detalii despre performanța modelului AI și modelul de bază. Vă va ajuta să înțelegeți mai bine valorile de bază ale performanței modelului și modul în care a fost obținut nota finală de performanță a modelului. Modelul de bază folosește o abordare care nu se bazează pe IA pentru a calcula valoarea pe viață a clienților pe baza în principal a achizițiilor istorice efectuate de clienți.

- **Valoarea clienților pe percentilă** : Clienții de valoare mică și de mare valoare sunt afișați într-un grafic. Plasați cursorul peste barele din histogramă pentru a vedea numărul de clienți din fiecare grup și CLV-ul mediu al grupului respectiv. Opțional, [creați segmente de clienți](prediction-based-segment.md) pe baza previziunilor lor CLV.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Valoarea clienților în funcție de percentilă pentru modelul CLV":::

- **Cei mai influenți factori**: Diverși factori sunt luați în considerare atunci când creați CLV-ul predicție pe baza datelor de intrare furnizate modelului AI. Fiecare dintre factori are o importanță calculată pentru predicțiile agregate pe care le creează un model. Folosiți acești factori pentru a vă valida rezultatele predicție. Acești factori oferă, de asemenea, mai multe informații despre cei mai influenți factori care au contribuit la prezicerea CLV pentru toți clienții dvs.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Cei mai influenți factori pentru modelul CLV":::

### <a name="learn-about-the-score"></a>Aflați despre scor

Formula standard utilizată pentru a calcula CLV după modelul de bază:

 _**CLV pentru fiecare client** = Achiziția medie lunară efectuată de client în fereastra clientului activ * Numărul de luni în perioada CLV predicție * Rata generală de retenție a tuturor clienților_

Modelul AI este comparat cu modelul de bază bazat pe două valori de performanță ale modelului.
  
- **Rata de succes în prezicerea clienților de valoare ridicată**

  Vedeți diferența în prezicerea clienților cu valoare ridicată utilizând modelul AI comparativ cu modelul de bază. De exemplu, rata de succes de 84% înseamnă că dintre toți clienții cu valoare ridicată din datele de instruire, modelul AI a reușit să capteze cu precizie 84%. Apoi comparăm această rată de succes cu rata de succes a modelului de bază pentru a raporta modificarea relativă. Această valoare este utilizată pentru a atribui un nivel modelului.

- **Valori de eroare**

  Vedeți performanța generală a modelului în ceea ce privește eroarea în prezicerea valorilor viitoare. Folosim măsurătoarea generală Root Mean Squared Error (RMSE) pentru a evalua această eroare. RMSE este un mod standard de măsurare a erorii unui model în prezicerea datelor cantitative. RMSE al modelului AI este comparat cu RMSE al modelului de bază și se raportează diferența relativă.

Modelul AI acordă prioritate clasării exacte a clienților în funcție de valoarea pe care o aduc afacerii dvs. Deci, numai rata de succes a prezicerii clienților cu valoare ridicată este utilizată pentru a obține nota modelului final. Valoarea RMSE este sensibilă la valori aberante. În scenariile în care aveți un procent mic de clienți cu valori de achiziție extraordinar de mari, valoarea generală RMSE ar putea să nu ofere o imagine completă a performanței modelului.

[!INCLUDE [footer-include](includes/footer-banner.md)]
