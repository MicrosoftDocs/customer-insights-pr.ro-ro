---
title: Ghid eșantion de predicție pentru Valoarea ciclului de viață a clientului
description: Utilizați acest exemplu de ghid pentru a încerca modelul de predicție pentru Valoarea ciclului de viață a clientului.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 19c1fbadb79ba22c0dc11aa7c3b5b2415add70a7
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306364"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Ghid eșantion de predicție pentru Valoarea ciclului de viață a clientului (CLV)

Acest ghid vă va explica un exemplu de la un capăt la altul al predicției valorii ciclului de viață al clientului (CLV) în Customer Insights, folosind date eșantion.

## <a name="scenario"></a>Scenariu

Contoso este o companie care produce cafea și aparate de cafea de înaltă calitate. Ei vând produsele prin intermediul site-ului lor de cafea Contoso. Compania dorește să înțeleagă valoarea (veniturile) pe care clienții lor o pot genera în următoarele 12 luni. Cunoașterea valorii așteptate a clienților lor în următoarele 12 luni îi va ajuta să-și direcționeze eforturile de marketing către clienții cu valoare ridicată.

## <a name="prerequisites"></a>Cerințe preliminare

- Cel puțin [Permisiuni de colaborare](permissions.md) în perspectivele publicului.
- Vă recomandăm să implementați pașii următori [într-un mediu nou](manage-environments.md).

## <a name="task-1---ingest-data"></a>Sarcina 1 - Ingerare date

Examinați articolele [despre ingestia de date](data-sources.md) și [importul surselor de date utilizând conectori Power Query](connect-power-query.md). Următoarele informații presupun că v-ați familiarizat cu ingerarea datelor în general.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerarea datelor clienților de pe platforma de comerț electronic

1. Creați un sursă de date numită **eCommerce**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.

1. Introduceți adresa de URL pentru contactele de comerț electronic [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:
   - **DateOfBirth**: Dată
   - **CreatedOn**: Dată/Oră/Zonă

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformați data nașterii în dată.":::

1. În câmpul „Nume” din panoul din dreapta, redenumiți sursa de date din **Interogare** în **eCommerceContacts**

1. **Salvați** sursa de date.

### <a name="ingest-online-purchase-data"></a>Ingerați date de cumpărare online

1. Adăugați un alt set de date la aceeași sursă de date **eCommerce**. Alegeți din nou conectorul **Text/CSV**.

1. Introduceți adresa URL pentru datele de **Achiziții online** https://aka.ms/ciadclassonline.

1. În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:
   - **PurchasedOn**: Dată/Oră
   - **TotalPrice**: Monedă

1. În câmpul **Nume** din panoul lateral, redenumiți sursa de date din **Interogare** în **eCommercePurchases**.

1. **Salvați** sursa de date.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerați datele clienților din schema de loialitate

1. Creați o sursă de date numită **LoyaltyScheme**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.

1. Introduceți adresa de URL pentru contactele de comerț electronic https://aka.ms/ciadclasscustomerloyalty.

1. În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:
   - **DateOfBirth**: Dată
   - **RewardsPoints**: Număr întreg
   - **CreatedOn**: Dată/Oră

1. În câmpul **Nume** din panoul din dreapta, redenumiți sursa de date din **Interogare** în **loyCustomers**.

1. **Salvați** sursa de date.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingerați datele clienților din recenziile site-ului web

1. Creați o sursă de date numită **Website**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.

1. Introduceți adresa de URL pentru contactele de comerț electronic https://aka.ms/CI-ILT/WebReviews.

1. În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:

   - **ReviewRating**: Număr decimal
   - **ReviewDate**: Dată

1. În câmpul „Nume” din panoul din dreapta, redenumiți sursa de date din **Interogare** la **Recenzii**.

1. **Salvați** sursa de date.

## <a name="task-2---data-unification"></a>Sarcina 2 - Unificarea datelor

După ingerarea datelor, începem acum procesul de unificare a datelor pentru a crea un profil de client unificat. Pentru informații suplimentare, consultați [Unificare date](data-unification.md).

### <a name="map"></a>Hartă

1. După ingerarea datelor, mapați contactele de la datele de comerț electronic și de loialitate la tipuri de date obișnuite. Mergeți la **Date** > **Unificare** > **Mapare**.

1. Selectați entitățile care reprezintă profilul clientului - **eCommerceContacts** și **loyCustomers**. Apoi selectați **Se aplică**.

   ![unificați sursele de date privind comerțul electronic și loialitatea.](media/unify-ecommerce-loyalty.png)

1. Selectați **ContactId** ca cheie primară pentru **eCommerceContacts** și **LoyaltyID** ca cheie primară pentru **loyCustomers**.

   ![Unificați LoyaltyId ca cheie principală.](media/unify-loyaltyid.png)

1. Selectați **Salvare**.

### <a name="match"></a>Corespondență

1. Accesați fila **Potrivire** și selectați **Setare ordine**.

1. În lista derulantă **Primar**, alegeți **eCommerceContacts: eCommerce** ca sursă principală și include toate înregistrările.

1. În lista derulantă **Entitate 2**, alegeți **loyCustomers: LoyaltyScheme** și include toate înregistrările.

   ![Potriviți unificarea de comerț electronic și loialitate.](media/unify-match-order.png)

1. Selectați **Adăugați regulă**

1. Adăugați prima condiție folosind FullName.

   - Pentru eCommerceContacts selectați **FullName** în meniul derulant.
   - Pentru loyCustomers selectați **FullName** în lista derulantă.
   - Selectați lista derulantă **Normalizare** și alegeți **Tip (Telefon, Nume, Adresă, ...)**.
   - Setați **Nivel de precizie**: **De bază** și **Valoare**: **Mare**.

1. Introduceți numele **FullName, Email** pentru noua regulă.

   - Adăugați o a doua condiție pentru adresa de e-mail selectând **Adăugați o condiție**
   - Pentru entitatea eCommerceContacts, alegeți **E-mail** în meniul derulant.
   - Pentru entitatea loyCustomers, alegeți **E-mail** în lista derulantă.
   - Lăsați Normalizarea necompletată.
   - Setați **Nivel de precizie**: **De bază** și **Valoare**: **Mare**.

   ![Unificați regula de potrivire pentru nume și e-mail.](media/unify-match-rule.png)

1. Selectați **Terminat**.

1. Selectați **Salvare** și **Rulare**.

### <a name="merge"></a>Îmbinare

1. Accesați fila **Îmbinare**.

1. Pe **ContactId** pentru entitatea **loyCustomers**, schimbați numele afișat în **ContactIdLOYALTY** pentru a-l diferenția de celelalte ID-uri ingerate.

   ![redenumiți contactid din ID-ul de loialitate.](media/unify-merge-contactid.png)

1. Selectați **Salvați** și **Executați procese de îmbinare și din aval**.

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Sarcina 3 - Configurați predicția pentru Valoarea ciclului de viață a clientului

Cu profilurile de clienți unificate, putem acum să rulăm predicția pentru Valoarea ciclului de viață a clientului. Pentru pași detaliați, consultați [Valoarea predicției pentru Valoarea ciclului de viață a clientului (previzualizare)](predict-customer-lifetime-value.md).

1. Accesați **Inteligența**  > **Predicții** și selectați **Modelul pentru Valoarea ciclului de viață al clientului**.

1. Parcurgeți informațiile din panoul lateral și selectați **Începeți**.

1. Denumiți modelul **Predicție OOB eCommerce CLV** și entitatea de ieșire **OOBeCommerceCLVPrediction**.

1. Definiți preferințele modelului pentru modelul CLV:
   - **Predicția perioadei de timp**: **12 luni sau 1 an**. Această setare definește cât de departe în viitor se poate prezice ciclul de viață al clientului.
   - **Clienți activi**: Specificați ce înseamnă clienții activi pentru afacerea dvs. Setați intervalul de timp istoric în care un client trebuie să fi avut cel puțin o tranzacție pentru a fi considerat activ. Modelul va prezice CLV numai pentru clienții activi. Alegeți între a permite modelului să calculeze perioada de timp pe baza datelor istorice ale tranzacțiilor sau să furnizați un anumit interval de timp. În acest exemplu de ghid, noi **lăsăm modelul să calculeze intervalul de cumpărare**, care este opțiunea implicită.
   - **Clienți cu valoare ridicată**: Definiți clienții cu valoare ridicată ca o percentilă a clienților cu plată superioară. Modelul folosește această intrare pentru a oferi rezultate care se potrivesc definiției dvs. de afaceri a clienților cu valoare ridicată. Puteți alege să lăsați modelul să definească clienți de mare valoare. Folosește o regulă euristică din care derivă percentila. De asemenea, puteți defini clienții cu valoare ridicată ca fiind o percentilă a celor mai buni viitori clienți plătitori. În acest exemplu de ghid, definim manual clienții cu valoare ridicată ca **30% din cei mai activi clienți plătitori** și selectați **Următorul**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Preferințele intră în experiența ghidată pentru modelul CLV.":::

1. În pasul **Date necesare**, selectați **Adăugați date** pentru a furniza datele din istoricul tranzacțiilor.

1. Adăugați entitatea **Achiziții eCommerce: eCommerce** și maparea atributelor necesare modelului:
   - ID tranzacție: eCommerce.eCommercePurchases.PurchaseId
   - Data tranzacției: eCommerce.eCommercePurchases.PurchasedOn
   - Valoarea tranzacției: eCommerce.eCommercePurchases.TotalPrice
   - ID produs: eCommerce.eCommercePurchases.ProductId

1. Selectați **Următorul**.

1. Configurați relația dintre entitatea **Achiziții eCommerce: eCommerce** și **eCommerceContacts: eCommerce**.

1. Pasul **Date suplimentare (opțional)** vă permite să adăugați mai multe date despre activitatea clienților. Aceste date vă pot ajuta să obțineți mai multe informații despre interacțiunile clienților cu afacerea dvs., care pot contribui la CLV. Adăugarea de interacțiuni cheie cu clienții, cum ar fi jurnalele web, jurnalele serviciu pentru relații cu clienții sau istoricul programului de recompense, poate îmbunătăți precizia predicțiilor. Selectați **Adăugați date** pentru a include mai multe date despre activitatea clienților.

1. Adăugați entitatea de activitate client și asociați numele câmpurilor acesteia la câmpurile corespunzătoare cerute de model:
   - Entitatea de activitate client: Recenzii: Site web
   - Cheia principală: Website.Reviews.ReviewId
   - Marcă de timp: Website.Reviews.ReviewDate
   - Eveniment (numele activității): Website.Reviews.ActivityTypeDisplay
   - Detalii (suma sau valoarea): Website.Reviews.ReviewRating

1. Selectați **Următorul** și configurați activitatea și relația dintre datele tranzacției și datele clienților:  
   - Tipul activității: Alegeți activitate existentă
   - Eticheta activității: Recenzie
   - Etichetă corespondentă: Website.Reviews.UserId
   - Entitate client: eCommerceContacts:eCommerce
   - Relație: WebsiteReviews

1. Selectați **Următorul** pentru a seta planificarea modelului.

   Modelul trebuie să se antreneze în mod regulat pentru a învăța noi modele atunci când sunt ingerate date noi. Pentru acest exemplu, alegeți **Lunar**.

1. După examinarea tuturor detaliilor, selectați **Salvați și rulați**.

## <a name="task-4---review-model-results-and-explanations"></a>Sarcina 4 - Examinați rezultatele modelului și explicațiile

Lăsați modelul să finalizeze pregătirea și notarea datelor. Apoi, puteți consulta rezultatele și explicațiile modelului CLV. Pentru mai multe informații, consultați [Examinați starea și rezultatele unei predicții](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Sarcina 5 - Creați un segment de clienți de mare valoare

Rularea modelului creează o nouă entitate, care este listată pe **Date** > **Entități**. Puteți crea un nou segment de clienți pe baza entității create de model.

1. Mergeți la **Segmente**. 

1. Selectați **Nou** și alegeți **Creați din** > **Informații**.

   ![Crearea unui segment cu rezultatul modelului.](media/segment-intelligence.png)

1. Selectați entitatea **OOBeCommerceCLVPrediction** și definiți segmentul:
  - Câmp: CLVScore
  - Operator: mai mare decât
  - Valoare: 1500

1. Selectați **Revizuiți** și **Salvați** segmentul.

Acum aveți un segment care identifică clienții despre care se estimează că vor genera mai mult de 1500$ în venituri în următoarele 12 luni. Acest segment se actualizează dinamic dacă sunt ingerate mai multe date.

Pentru mai multe informații, consultați [Creați și gestionați segmente](segments.md).
