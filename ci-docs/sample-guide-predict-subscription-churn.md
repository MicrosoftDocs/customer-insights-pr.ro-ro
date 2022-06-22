---
title: Ghid eșantion de predicție a retragerii abonamentelor
description: Utilizați acest exemplu de ghid pentru a încerca modelul preinstalat de predicție a retragerii abonamentelor.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5a8eeafecacef3d0bb4a798b698cf490423ca98d
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741426"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Ghid eșantion de predicție a retragerii abonamentelor

Vă vom explica un exemplu complet de predicție a retragerii de abonamente folosind datele eșantion furnizate mai jos. 

## <a name="scenario"></a>Scenariu

Contoso este o companie care produce cafea și aparate de cafea de înaltă calitate, pe care le vinde prin intermediul site-ului web Contoso Coffee. Recent, au început o afacere cu abonamente pentru ca clienții lor să poată obține cafea în mod regulat. Obiectivul lor este să înțeleagă care clienți abonați ar putea anula abonamentul în următoarele câteva luni. Știind care dintre clienții lor este **susceptibil să se retragă**, îi poate ajuta să economisească eforturile de marketing concentrându-se pe păstrarea lor.

## <a name="prerequisites"></a>Cerințe preliminare

- Cel puțin [Permisiuni de contributor](permissions.md) în Customer Insights.
- Vă recomandăm să implementați pașii următori [într-un mediu nou](manage-environments.md).

## <a name="task-1---ingest-data"></a>Sarcina 1 - Ingerare date

Examinați articolele [despre ingerarea de date](data-sources.md) și [importul surselor de date folosind Power Query conectori](connect-power-query.md) specific. Următoarele informații presupun că v-ați familiarizat cu ingerarea datelor în general. 

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

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-the-subscription-churn-prediction"></a>Sarcina 3 - Configurați predicția de retragere a abonamentelor

Odată stabilite profilurile de clienți unificate, putem rula acum predicția de retragere a abonamentelor. Pentru pași detaliați, consultați [Abonament churn predicție](predict-subscription-churn.md) articol. 

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


[!INCLUDE [footer-include](includes/footer-banner.md)]