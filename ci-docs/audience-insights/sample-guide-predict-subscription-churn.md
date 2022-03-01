---
title: Ghid eșantion de predicție a retragerii abonamentelor
description: Utilizați acest exemplu de ghid pentru a încerca modelul preinstalat de predicție a retragerii abonamentelor.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: fa460fa5c79bc8a356ec5e90050ec85e05c55be8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306318"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a>Ghid eșantion de predicție a retragerii abonamentelor (previzualizare)

Vă vom explica un exemplu complet de predicție a retragerii de abonamente folosind datele eșantion furnizate mai jos. 

## <a name="scenario"></a>Scenariu

Contoso este o companie care produce cafea și aparate de cafea de înaltă calitate, pe care le vând prin intermediul site-ului lor de cafea Contoso. Recent, au început o afacere cu abonamente pentru ca clienții lor să poată obține cafea în mod regulat. Obiectivul lor este să înțeleagă care clienți abonați ar putea anula abonamentul în următoarele câteva luni. Știind care dintre clienții lor este **susceptibil să se retragă**, îi poate ajuta să economisească eforturile de marketing concentrându-se pe păstrarea lor.

## <a name="prerequisites"></a>Cerințe preliminare

- Cel puțin [Permisiuni de contributor](permissions.md) în Customer Insights.
- Vă recomandăm să implementați pașii următori [într-un mediu nou](manage-environments.md).

## <a name="task-1---ingest-data"></a>Sarcina 1 - Ingerare date

Examinați articolele [despre ingestia de date](data-sources.md) și în mod specific [importul surselor de date utilizând conectori Power Query](connect-power-query.md). Următoarele informații presupun că v-ați familiarizat cu ingerarea datelor în general. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerarea datelor clienților de pe platforma de comerț electronic

1. Creați un sursă de date numită **eCommerce**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.

1. Introduceți adresa de URL pentru contactele de comerț electronic https://aka.ms/ciadclasscontacts.

1. În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:

   - **DateOfBirth**: Dată
   - **CreatedOn**: Dată/Oră/Zonă

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformați data nașterii în dată.":::

1. În câmpul **Nume** din panoul din dreapta, redenumiți sursa de date din **Interogare** în **eCommerceContacts**

1. Salvați sursa de date.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerați datele clienților din schema de loialitate

1. Creați o sursă de date numită **LoyaltyScheme**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.

1. Introduceți adresa de URL pentru contactele de comerț electronic https://aka.ms/ciadclasscustomerloyalty.

1. În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:

   - **DateOfBirth**: Dată
   - **RewardsPoints**: Număr întreg
   - **CreatedOn**: Dată/Oră

1. În câmpul **Nume** din panoul din dreapta, redenumiți sursa de date din **Interogare** în **loyCustomers**.

1. Salvați sursa de date.

### <a name="ingest-subscription-information"></a>Ingerare informații abonamente

1. Creați o sursă de date numită **SubscriptionHistory**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.

1. Introduceți adresa de URL pentru contactele de comerț electronic https://aka.ms/ciadchurnsubscriptionhistory.

1. În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:

   - **SubscriptioID**: Număr întreg
   - **SubscriptionAmount**: Monedă
   - **SubscriptionEndDate**: Dată/Oră
   - **SubscriptionStartDate**: Dată/Oră
   - **TransactionDate**: Dată/Oră
   - **IsRecurring**: Adevărat/Fals
   - **Is_auto_renew**: Adevărat/Fals
   - **RecurringFrequencyInMonths**: Număr întreg

1. În câmpul **Nume** din panoul din dreapta, redenumiți sursa de date din **Interogare** în **SubscriptionHistory**.

1. Salvați sursa de date.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingerați datele clienților din recenziile site-ului web

1. Creați o sursă de date numită **Website**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.

1. Introduceți adresa de URL pentru contactele de comerț electronic https://aka.ms/ciadclasswebsite.

1. În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:

   - **ReviewRating**: Număr întreg
   - **ReviewDate**: Dată

1. În câmpul „Nume” din panoul din dreapta, redenumiți sursa de date din **Interogare** în **webReviews**.

## <a name="task-2---data-unification"></a>Sarcina 2 - Unificarea datelor

După ingerarea datelor, începem acum procesul de **Mapare, potrivire, îmbinare** pentru a crea un profil de client unificat. Pentru informații suplimentare, consultați [Unificare date](data-unification.md).

### <a name="map"></a>Hartă

1. După ingerarea datelor, mapați contactele de la datele de comerț electronic și de loialitate la tipuri de date obișnuite. Mergeți la **Date** > **Unificare** > **Mapare**.

1. Selectați entitățile care reprezintă profilul clientului - **eCommerceContacts** și **loyCustomers**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="unificați sursele de date privind comerțul electronic și loialitatea.":::

1. Selectați **ContactId** ca cheie primară pentru **eCommerceContacts** și **LoyaltyID** ca cheie primară pentru **loyCustomers**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unificați LoyaltyId ca cheie principală.":::

### <a name="match"></a>Corespondență

1. Accesați fila **Potrivire** și selectați **Setare ordine**.

1. În lista derulantă **Primar**, alegeți **eCommerceContacts: eCommerce** ca sursă principală și include toate înregistrările.

1. În lista derulantă **Entitate 2**, alegeți **loyCustomers: LoyaltyScheme** și include toate înregistrările.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Potriviți unificarea de comerț electronic și loialitate.":::

1. Selectați **Creare regulă nouă**

1. Adăugați prima condiție folosind FullName.

   * Pentru eCommerceContacts selectați **FullName** în meniul derulant.
   * Pentru loyCustomers selectați **FullName** în lista derulantă.
   * Selectați lista derulantă **Normalizare** și alegeți **Tip (telefon, nume, adresă, ...)**.
   * Setați **Nivel de precizie**: **De bază** și **Valoare**: **Mare**.

1. Introduceți numele **FullName, Email** pentru noua regulă.

   * Adăugați o a doua condiție pentru adresa de e-mail selectând **Adăugați o condiție**
   * Pentru entitatea eCommerceContacts, alegeți **E-mail** în meniul derulant.
   * Pentru entitatea loyCustomers, alegeți **E-mail** în lista derulantă. 
   * Lăsați Normalizarea necompletată. 
   * Setați **Nivel de precizie**: **De bază** și **Valoare**: **Mare**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Unificați regula de potrivire pentru nume și e-mail.":::

7. Selectați **Salvare** și **Rulare**.

### <a name="merge"></a>Îmbinare

1. Accesați fila **Îmbinare**.

1. Pe **ContactId** pentru entitatea **loyCustomers**, schimbați numele afișat în **ContactIdLOYALTY** pentru a-l diferenția de celelalte ID-uri ingerate.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="redenumiți contactid din ID-ul de loialitate.":::

1. Selectați **Salvați** și **Rulați** pentru a porni procesul de îmbinare.


## <a name="task-3---configure-the-subscription-churn-prediction"></a>Sarcina 3 - Configurați predicția de retragere a abonamentelor

Odată stabilite profilurile de clienți unificate, putem rula acum predicția de retragere a abonamentelor. Pentru pași detaliați, consultați articolul [Predicția retragerii abonamentelor (previzualizare)](predict-subscription-churn.md). 

1. Mergeți la **Informații** > **Descoperiți** și selectați pentru a utiliza **Modelul de retragere a clienților**.

1. Selectați opțiunea **Abonament** și selectați **Începeți**.

1. Denumiți modelul **OOB Subscription Churn Prediction** și entitatea de ieșire **OOBSubscriptionChurnPrediction**.

1. Definiți două condiții pentru modelul de retragere:

   * **Zile de la terminarea abonamentului**: **cel puțin 60** de zile. Dacă un client nu își reînnoiește abonamentul în această perioadă după încheierea abonamentului, atunci este considerat retras. 

   * **Definiție retragere**: **cel puțin 93** de zile. Durata pentru care modelul prezice ce clienți s-ar putea retrage. Cu cât priviți mai departe în viitor, cu atât rezultatele sunt mai puțin precise.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Selectați pârghiile model Fereastră de predicție și Definiție retragere.":::

1. Selectați **Adăugare date necesare** și selectați **Adăugare date** pentru istoricul abonamentelor.

1. Adăugați entitatea **Subscription : SubscriptionHistory** și mapați câmpurile din eCommerce la câmpurile corespunzătoare cerute de model.

1. Asociați entitatea **Subscription : SubscriptionHistory** cu **eCommerceContacts: eCommerce**, denumiți relația **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Conectați entitățile eCommerce.":::

1. Sub Activități clienți, adăugați entitatea **webReviews : Website** și mapați câmpurile din webReviews la câmpurile corespunzătoare cerute de model. 
   - Cheie primară: ReviewId
   - Marcă de timp: ReviewDate
   - Eveniment: ReviewRating

1. Configurați o activitate pentru recenziile site-urilor web. Selectați activitatea **Revizuire** și asociați entitatea **webReviews : Website** cu **eCommerceContacts : eCommerce**.

1. Selectați **Următorul** pentru a seta planificarea modelului.

   Modelul trebuie să se antreneze în mod regulat pentru a învăța noi modele atunci când sunt ingerate date noi. Pentru acest exemplu, selectați **Lunar**.

1. După examinarea tuturor detaliilor, selectați **Salvați și rulați**.

## <a name="task-4---review-model-results-and-explanations"></a>Sarcina 4 - Examinați rezultatele modelului și explicațiile

Lăsați modelul să finalizeze pregătirea și notarea datelor. Acum puteți revizui explicațiile modelului de retragere a abonamentelor. Pentru mai multe informații, consultați [Examinați starea și rezultatele unei predicții](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Sarcina 5 - Creați un segment de clienți cu risc de retragere ridicat

Rularea modelului de producție creează o nouă entitate pe care o puteți vedea în **Date** > **Entități**.   

Puteți crea un segment nou pe baza entității create de model.

1.  Mergeți la **Segmente**. Selectați **Nou** și alegeți **Creați din** > **Informații**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Crearea unui segment cu rezultatul modelului.":::

1. Selectați punctul final **OOBSubscriptionChurnPrediction** și definiți segmentul: 
   - Câmp: ChurnScore
   - Operator: mai mare decât
   - Valoare: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configurați un segment de retragere a abonamentului.":::

Acum aveți un segment actualizat dinamic, care identifică clienții cu risc ridicat de retragere pentru această activitate de abonamente.

Pentru mai multe informații, consultați [Creați și gestionați segmente](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]