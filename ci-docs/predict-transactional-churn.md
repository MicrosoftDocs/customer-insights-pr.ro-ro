---
title: Schimbarea tranzacției predicție (conține videoclipul)
description: Preziceți dacă un client prezintă riscul de a nu mai cumpăra produsele sau serviciile companiei dvs.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610527"
---
# <a name="predict-transaction-churn"></a>Previzionați retragere din tranzacții

Predicția retragerii tranzacționale ajută la a prezice dacă un client nu va mai cumpăra produsele sau serviciile dvs. într-o anumită fereastră de timp.

Trebuie să aveți cunoștințe de afaceri pentru a înțelege ce înseamnă pierderea pentru afacerea dvs. Acceptăm definițiile bazate pe timp ale retragerii, ceea ce înseamnă că un client este considerat a fi retras după o perioadă fără achiziții.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Pentru medii bazate pe conturi de business, putem prezice retrageri din tranzacții pentru un cont și, de asemenea, o combinație de cont și un alt nivel de informații, cum ar fi categoria de produse. De exemplu, adăugarea unui parametru poate ajuta la stabilirea cât de probabil este ca contul „Contoso” să nu mai cumpere categoria de produse „papetărie de birou”. În plus, pentru conturile de afaceri, putem folosi, de asemenea, AI pentru a genera o listă de motive potențiale pentru care este probabil ca un cont să se schimbe pentru o categorie de informații de nivel secundar.

> [!TIP]
> Încercați tranzacția churn predicție folosind date exemplu: [Ghid de exemplu de eliminare a tranzacțiilor predicție](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Cerințe preliminare

- Minimum [Permisiuni de colaborare](permissions.md).
- Cel puțin 10 profiluri de clienți, de preferință mai mult de 1.000 de clienți unici.
- Customer Identifier, un identificator unic pentru a potrivi tranzacțiile cu clienții dvs.
- Date despre tranzacții pentru cel puțin două ori fereastra de timp selectată, cum ar fi doi până la trei ani de istoric al tranzacțiilor. În mod ideal, cel puțin două tranzacții per client. Istoricul tranzacțiilor trebuie să includă:
  - **ID-ul de tranzacție** : identificatorul unic al unei achiziții sau tranzacții.
  - **Data tranzacției** : Data achiziției sau tranzacției.
  - **Valoarea tranzacției** : Valoarea valutară sau valoarea numerică a tranzacției.
  - **ID unic de produs** : ID-ul produsului sau serviciului achiziționat dacă datele dvs. sunt la nivel de element rând.
  - **Dacă această tranzacție a fost o retur** : Un câmp adevărat/fals care identifică dacă tranzacția a fost returnată sau nu. Dacă **Valoarea tranzacției** este negativ, deducem un randament.
- Date despre activitatea clientului:
  - Customer Identifier, un identificator unic pentru a mapa activitățile clienților dvs.
  - **Cheia principala:** Identificator unic pentru o activitate. De exemplu, o vizită pe site sau o înregistrare de utilizare care arată că clientul a încercat un eșantion de produs.
  - **Timestamp-ul:** Data și ora evenimentului identificate prin cheia primară.
  - **Eveniment:** Numele evenimentului pe care doriți să îl utilizați. De exemplu, un câmp numit „UserAction” într-un magazin alimentar ar putea fi o utilizare a cuponului de către client.
  - **Detalii:** Informații detaliate despre eveniment. De exemplu, un câmp numit „CouponValue” într-un magazin alimentar ar putea fi valoarea valutară a cuponului.
- Mai puțin de 20% din valorile lipsă în câmpul de date al entității furnizate

Pentru conturile de afaceri (B-to-B), adăugați date despre clienți aliniate la atribute mai statice pentru a vă asigura că modelul funcționează cel mai bine:
- **Număr de înregistrare client:** Identificator unic pentru un client.
- **Data creata:** Data la care clientul a fost adăugat inițial.
- **Stat sau provincie:** Locația de stat sau provincie a unui client.
- **Țară:** Țara unui client.
- **Industrie:** Tipul de industrie al unui client. De exemplu, un câmp numit „Industrie” dintr-un prăjitor de cafea ar putea indica dacă clientul a fost cu amănuntul.
- **Clasificare:** Clasificarea unui client pentru afacerea dvs. De exemplu, un câmp numit „ValueSegment” într-un prăjitor de cafea ar putea fi nivelul clientului în funcție de mărimea clientului.

> [!NOTE]
> Pentru o companie cu frecvență ridicată de cumpărare a clienților (la fiecare câteva săptămâni), se recomandă să selectați o fereastră mai scurtă predicție și să definiți churn. Pentru o frecvență scăzută de cumpărare (o dată la câteva luni sau o dată pe an), alegeți o fereastră mai lungă predicție și definiția retragerii.

## <a name="create-a-transaction-churn-prediction"></a>Creați o predicție de retragere din tranzacții

1. Mergi la **Inteligența** > **Previziuni**.

1. Pe **Crea** filă, selectați **Utilizați modelul** pe **Model de retragere a clienților** ţiglă.

1. Selectați **Tranzacţie** pentru tipul de baraj și apoi **Incepe**.

1. **Denumiți acest model** și **Numele entității de ieșire** pentru a le distinge de alte modele sau entități.

1. Selectați **Următorul**.

### <a name="define-customer-churn"></a>Definiți retragerea clienților

Selectați **Salveaza schita** oricând pentru a salva predicție ca schiță. Proiectul predicție este afișat în **Previziunile mele** fila.

1. Seteaza **fereastra predicție**. De exemplu, preziceți riscul de retragere pentru clienții dvs. în următoarele 90 de zile pentru a se alinia la eforturile dvs. de marketing de retenție. Predicția riscului de retragere pentru o perioadă mai lungă sau mai scurtă de timp poate face mai dificilă abordarea factorilor din profilul dvs. de risc de retragere, dar depinde de cerințele dvs. de afaceri specifice.

1. Introduceți numărul de zile pentru a defini abandonul în **Definiția churn** camp. De exemplu, dacă un client nu a făcut o achiziție în ultimele 30 de zile, acesta ar putea fi considerat ca fiind reluat pentru afacerea dvs.

1. Selectați **Următorul**.

### <a name="add-purchase-history"></a>Adăugați istoricul achizițiilor

1. Selectați **Adăugați date** pentru **Istoricul tranzacțiilor clienților**.

1. Selectați tipul de activitate semantică, **Comandă de vânzări** sau **SalesOrderLine**, care conține informații despre istoricul tranzacțiilor. Dacă activitatea nu a fost configurată, selectați **Aici** și creează-l.

1. Sub **Activități**, dacă atributele activității au fost mapate semantic atunci când activitatea a fost creată, alegeți atributele sau entitatea specifice pe care doriți să se concentreze calculul. Dacă maparea semantică nu a avut loc, selectați **Editați | ×** și mapați datele dvs.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Panoul lateral care arată alegerea activităților specifice sub tipul semantic.":::

1. Selectați **Următorul** și revizuiți atributele necesare pentru acest model.

1. Selectați **Salvare**.

1. Adăugați mai multe activități sau selectați **Următorul**.

# <a name="individual-consumers-b-to-c"></a>[Consumatori individuali (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Adăugați date suplimentare (opțional)

1. Selectați **Adăugați date** pentru **Activități ale clienților**.

1. Selectați tipul de activitate semantică care conține datele pe care doriți să le utilizați. Dacă activitatea nu a fost configurată, selectați **Aici** și creează-l.

1. Sub **Activități**, dacă atributele activității au fost mapate semantic atunci când activitatea a fost creată, alegeți atributele sau entitatea specifice pe care doriți să se concentreze calculul. Dacă maparea semantică nu a avut loc, selectați **Editați | ×** și mapați datele dvs.

1. Selectați **Următorul** și revizuiți atributele necesare pentru acest model.

1. Selectați **Salvare**.

1. Selectați **Următorul**

# <a name="business-accounts-b-to-b"></a>[Conturi de afaceri (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Selectați nivelul de predicție

Majoritatea predicțiilor sunt create la nivel de client. În unele situații, este posibil să nu fie suficient de granular pentru a răspunde nevoilor dvs. de afaceri. Utilizați această caracteristică pentru a estima pierderea pentru o sucursală a unui client, de exemplu, mai degrabă decât pentru clientul în ansamblu.

1. Selectați **Selectați entitate pentru un nivel secundar**. Dacă opțiunea nu este disponibilă, asigurați-vă că ați finalizat secțiunea anterioară.

1. Extindeți entitățile din care doriți să alegeți nivelul secundar sau utilizați caseta de filtrare a căutării pentru a filtra opțiunile selectate.

1. Alegeți atributul pe care doriți să îl utilizați ca nivel secundar, apoi selectați **Adăugare**.

1. Selectați **Următorul**.

> [!NOTE]
> Entitățile disponibile în această secțiune sunt afișate deoarece au o relație cu entitatea pe care ați ales-o în secțiunea anterioară. Dacă nu vedeți entitatea pe care doriți să o adăugați, asigurați-vă că are o relație validă în **Relații**. Numai relațiile unu-la-unu și mai multe la unu sunt valabile pentru această configurație.

### <a name="add-additional-data-optional"></a>Adăugați date suplimentare (opțional)

1. Selectați **Adăugați date** pentru **Activități ale clienților**.

1. Selectați tipul de activitate semantică care conține datele pe care doriți să le utilizați. Dacă activitatea nu a fost configurată, selectați **Aici** și creează-l.

1. Sub **Activități**, dacă atributele activității au fost mapate semantic atunci când activitatea a fost creată, alegeți atributele sau entitatea specifice pe care doriți să se concentreze calculul. Dacă maparea semantică nu a avut loc, selectați **Editați | ×** și mapați datele dvs.

1. Selectați **Următorul** și revizuiți atributele necesare pentru acest model.

1. Selectați **Salvare**.

1. Selectați **Următorul**

1. Opțional, selectați **Adăugați date** pentru **Date despre clienți**.

1. Mapați atributele semantice la câmpurile din propriile date ale clienților, așa cum au fost identificate. Datele din câmpurile utilizate nu ar trebui să se schimbe des pentru a asigura cea mai bună performanță a modelului. De exemplu, selectarea unui câmp pentru „Clasificare” care s-a schimbat în fiecare lună va avea doar ultima valoare utilizată în predicție, chiar dacă din punct de vedere istoric aceeași valoare s-ar putea să nu se aplice clientului atunci când construiește modelele de predicție.

1. Selectați **Următorul**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Furnizați o listă opțională de conturi de referință

Adăugați o listă a clienților și conturilor dvs. de afaceri pe care doriți să le utilizați ca etaloane de referință. The [detalii pentru aceste conturi de referință](#view-prediction-results) includeți scorul lor de pierdere și cele mai influente caracteristici care au avut impact asupra pierderii lor predicție.

1. Selectați **+ Adăugați clienți**.

1. Alegeți clienții care acționează ca reper.

1. Selectați **Următorul**.

---

### <a name="set-update-schedule"></a>Configurați planificarea actualizărilor

1. Pentru **Actualizări de date** pas, alegeți o frecvență pentru a vă reanaliza modelul. Această setare este importantă pentru a actualiza acuratețea predicțiilor pe măsură ce noi date sunt ingerate în Customer Insights. Majoritatea firmelor pot reinstrui o dată pe lună și pot obține o precizie bună pentru predicția lor.

1. Selectați **Următorul**.

### <a name="review-and-run-the-model-configuration"></a>Examinați și rulați configurația modelului

The **Examinați și alergați** pasul arată un rezumat al configurației și oferă șansa de a face modificări înainte de a crea predicție.

1. Selectați **Editați | ×** pe oricare dintre pașii pentru a revizui și a face orice modificări.

1. Dacă sunteți mulțumit de selecțiile dvs., selectați **Salvați și rulați** pentru a începe rularea modelului. Selectați **Terminat**. The **Previziunile mele** se afișează fila în timp ce predicție este creată. Procesul poate dura câteva ore până la finalizare, în funcție de cantitatea de date utilizate în predicție.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Vedeți rezultatele predicție

1. Mergi la **Inteligența** > **Previziuni**.

1. În **Previziunile mele** fila, selectați predicție pe care doriți să-l vizualizați.

# <a name="individual-consumers-b-to-c"></a>[Consumatori individuali (B2C)](#tab/b2c)

Există trei secțiuni principale de date în pagina de rezultate:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Conturi de afaceri (B2B)](#tab/b2b)

Există trei secțiuni principale de date în pagina de rezultate:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

Un **Analiza caracteristicilor influente** pagina de informații conține patru secțiuni de date:

- În panoul din dreapta, selectați un articol din **Clienți de top** sau **Clienți de referință**. Ambele liste sunt ordonate în funcție de scăderea valorii scurnului, indiferent dacă scorul este doar pentru client sau un scor combinat pentru clienți și un nivel secundar, cum ar fi categoria de produse. Elementul selectat determină conținutul acestei pagini.

  - **Clienți de top**: Lista celor 10 clienți care prezintă cel mai mare risc de retragere și cel mai scăzut risc de retragere pe baza scorurilor lor de retragere.
  - **Clienți de referință**: Listă de până la 10 clienți care au fost selectați în timpul configurării modelului.

- **Scor de retragere:** Afișează scorul de retragere pentru elementul selectat în panoul din dreapta.

- **Distribuția riscului de pierdere:** Afișează distribuția riscului de abandon între clienți și percentila în care se află clientul selectat.

- **Funcții de top care cresc și scad riscul de abandon:** Listează primele cinci caracteristici care au crescut și au scăzut riscul de pierdere pentru articolul selectat în panoul din dreapta. Afișează valoarea caracteristicii pentru acel articol și influența acesteia asupra scorului de pierdere pentru fiecare caracteristică influentă. Se afișează, de asemenea, valoarea medie a fiecărei caracteristici pe segmente de clienți cu retragere redus, mediu și ridicat. Ajută la o mai bună contextualizare a valorilor caracteristicilor influente de top pentru elementul selectat și compararea acestuia cu segmentele de clienți mici, medii și ridicate.

  - Scăzut: conturi sau combinații de cont și nivel secundar cu un scor de pierdere între 0 și 0,33.
  - Medie: conturi sau combinații de conturi și niveluri secundare cu un scor de pierdere între 0,33 și 0,66.
  - Ridicat: conturi sau combinații de conturi și niveluri secundare cu un scor de pierdere mai mare de 0,66.

  Când preziceți churn la nivel de cont, toate conturile sunt luate în considerare la obținerea valorilor medii ale caracteristicilor pentru segmente de retragere. Pentru predicțiile de retragere la nivelul secundar pentru fiecare cont, derivarea segmentelor de retragere depinde de nivelul secundar al elementului selectat în panoul lateral. De exemplu, dacă un articol are un nivel secundar de categorie de produse (rechizite de birou), atunci numai articolele care au rechizite de birou ca categorie de produse sunt luate în considerare atunci când se calculează valorile medii ale caracteristicilor pentru segmentele de abandon. Această logică este aplicată pentru a asigura o comparație echitabilă a valorilor caracteristicilor articolului cu valorile medii pe segmente mici, medii și mari.

  În unele cazuri, valoarea medie a segmentelor de retragere scăzută, medie sau ridicată este goală sau nu este disponibilă deoarece nu există articole care să aparțină segmentelor de retragere corespunzătoare pe baza definiției de mai sus.

  Interpretarea valorilor din coloanele medie scăzută, medie și ridicată este diferită pentru caracteristicile de categorii precum țara sau industria. Deoarece noțiunea de valoare „medie” a caracteristicii nu se aplică caracteristicilor de tip categorie, valorile din aceste coloane reprezintă proporția de clienți din segmentele cu retragere scăzută, medie sau mare care au aceeași valoare a caracteristicii de categorie în comparație cu elementul selectat în panoul lateral.

---

 > [!NOTE]
 > În entitatea de ieșire pentru acest model, *ChurnScore* arată probabilitatea prezisă de abandon și *IsChurn* este o etichetă binară bazată pe *ChurnScore* cu prag de 0,5. Dacă acest prag implicit nu funcționează pentru scenariul dvs.,[creați un nou segment](segments.md#create-a-segment) cu pragul preferat. Nu toți clienții sunt în mod necesar clienți activi. Este posibil ca unii dintre ei să nu fi avut nicio activitate de mult timp și să fie considerați deja derutați, pe baza definiției dvs. de retragere. Prezicerea riscului de retragere pentru clienții care deja au retragere nu este utilă deoarece nu sunt publicul de interes.
>
> Pentru a vedea scorul de pierdere, accesați **Date** > **Entități** și vizualizați fila de date pentru entitatea de ieșire pe care ați definit-o pentru acest model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
