---
title: Ghid eșantion de predicție a retragerii abonamentelor
description: Utilizați acest exemplu de ghid pentru a încerca modelul preinstalat de predicție a retragerii abonamentelor.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610021"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Ghid eșantion de predicție a retragerii abonamentelor

Acest ghid vă va explica un exemplu de la capăt la capăt al abandonului de abonament predicție folosind date eșantion. Vă recomandăm să încercați acest predicție [într-un mediu nou](manage-environments.md).

## <a name="scenario"></a>Scenariu

Contoso este o companie care produce cafea și aparate de cafea de înaltă calitate. Ei vând produsele prin intermediul site-ului lor Contoso Coffee. Recent, au început o afacere cu abonamente pentru ca clienții lor să poată obține cafea în mod regulat. Scopul lor este să înțeleagă ce clienți abonați și-ar putea anula abonamentul în următoarele câteva luni. Știind care dintre clienții lor este **susceptibil de a se răsuci** îi poate ajuta să economisească eforturile de marketing concentrându-se pe păstrarea acestora.

## <a name="prerequisites"></a>Cerințe preliminare

- Cel puțin [Permisiuni de contributor](permissions.md) în Customer Insights.

## <a name="task-1---ingest-data"></a>Sarcina 1 - Ingerare date

Examinați articolele [despre ingerarea de date](data-sources.md) și [conectarea la a Power Query sursă de date](connect-power-query.md). Următoarele informații presupun că sunteți familiarizat cu ingerarea datelor în general.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerarea datelor clienților de pe platforma de comerț electronic

1. Creați un Power Query sursă de date numit **eCommerce** și selectați **Text/CSV** conector.

1. Introduceți adresa de URL pentru contactele de comerț electronic https://aka.ms/ciadclasscontacts.

1. În timp ce editați datele, selectați **Transforma** și apoi **Utilizați primul rând ca antete**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:
   - **DateOfBirth**: Dată
   - **CreatedOn**: Dată/Oră/Zonă

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformați data nașterii în dată.":::

1. În **Nume** câmpul din panoul din dreapta, redenumiți-vă sursă de date în **eCommerceContacts**

1. Salvați sursa de date.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerați datele clienților din schema de loialitate

1. Creați un sursă de date numit **Schema de loialitate** și selectați **Text/CSV** conector.

1. Introduceți adresa URL pentru clienții fideli https://aka.ms/ciadclasscustomerloyalty.

1. În timp ce editați datele, selectați **Transforma** și apoi **Utilizați primul rând ca antete**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:
   - **DateOfBirth**: Dată
   - **RewardsPoints**: Număr întreg
   - **CreatedOn**: Dată/Oră

1. În **Nume** câmpul din panoul din dreapta, redenumiți-vă sursă de date în **Clienti loiali**.

1. Salvați sursa de date.

### <a name="ingest-subscription-information"></a>Ingerare informații abonamente

1. Creați un sursă de date numit **Istoricul abonamentului** și selectați **Text/CSV** conector.

1. Introduceți adresa URL pentru abonamente https://aka.ms/ciadchurnsubscriptionhistory.

1. În timp ce editați datele, selectați **Transforma** și apoi **Utilizați primul rând ca antete**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:
   - **SubscriptioID**: Număr întreg
   - **SubscriptionAmount**: Monedă
   - **SubscriptionEndDate**: Dată/Oră
   - **SubscriptionStartDate**: Dată/Oră
   - **TransactionDate**: Dată/Oră
   - **IsRecurring**: Adevărat/Fals
   - **Is_auto_renew**: Adevărat/Fals
   - **RecurringFrequencyInMonths**: Număr întreg

1. În **Nume** câmpul din panoul din dreapta, redenumiți-vă sursă de date în **Istoricul abonamentului**.

1. Salvați sursa de date.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingerați datele clienților din recenziile site-ului web

1. Creați un sursă de date numit **Site-ul web** și selectați **Text/CSV** conector.

1. Introduceți adresa URL pentru recenziile site-ului https://aka.ms/ciadclasswebsite.

1. În timp ce editați datele, selectați **Transforma** și apoi **Utilizați primul rând ca antete**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:
   - **ReviewRating**: Număr întreg
   - **ReviewDate**: Dată

1. În **Nume** câmpul din panoul din dreapta, redenumiți-vă sursă de date în **recenzii web**.

## <a name="task-2---data-unification"></a>Sarcina 2 - Unificarea datelor

Revizuiește articolul [despre unificarea datelor](data-unification.md). Următoarele informații presupun că sunteți familiarizat cu unificarea datelor în general.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Sarcina 3 - Crearea activității istoricului tranzacțiilor

Revizuiește articolul [despre activitățile clienților](activities.md). Următoarele informații presupun că sunteți familiarizat cu crearea de activități în general.

1. Creați o activitate numită **Istoricul abonamentului** cu *Abonament* entitatea și cheia sa primară, **Număr de înregistrare client**.

1. Creați o relație între *SubscriptionHistory:Abonament* și *eCommerceContact:eCommerce* cu **Număr de înregistrare client** ca cheie externă pentru a conecta cele două entități.

1. Selectați **SubscriptionType** pentru **EventActivity** și **SubscriptionEndDate** pentru **Timestamp-ul**.

1. Selectați **Abonament** pentru **Tip de activitate** și mapați semantic datele de activitate.

1. Rulați activitatea.

1. Adăugați o altă activitate și mapați numele câmpurilor acesteia la câmpurile corespunzătoare:
   - Entitatea de activitate client: Recenzii: Site web
   - Cheia principală: Website.Reviews.ReviewId
   - Marcă de timp: Website.Reviews.ReviewDate
   - Eveniment (numele activității): Website.Reviews.ActivityTypeDisplay
   - Detalii (suma sau valoarea): Website.Reviews.ReviewRating

1. Rulați activitatea.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Sarcina 4 - Configurați predicția de retragere a abonamentelor

Cu profilurile unificate ale clienților existente și activitatea creată, rulați abonamentul predicție. Pentru pași detaliați, vezi [Abonament churn predicție](predict-subscription-churn.md).

1. Mergi la **Inteligența** > **Previziuni**.

1. Pe **Crea** filă, selectați **Utilizați modelul** pe **Model de retragere a clienților** ţiglă.

1. Selectați **Abonament** pentru tipul de baraj și apoi **Incepe**.

1. Denumiți modelul **OOB Subscription Churn Prediction** și entitatea de ieșire **OOBSubscriptionChurnPrediction**.

1. Definiți preferințele modelului:
   - **Zile de la încheierea abonamentului** :**60** zile pentru a indica faptul că un client este considerat a fi retras dacă nu reînnoiește abonamentul în această perioadă după încheierea abonamentului.
   - **Zile pentru a investiga viitorul pentru a prezice pierderea** :**93** zile, care este durata în care modelul prezice clienții care ar putea să abandoneze. Cu cât priviți mai departe în viitor, cu atât rezultatele sunt mai puțin precise.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Selectați preferințele modelului și definiția abandonului.":::

1. Selectați **Următorul**.

1. În **Date obligatorii** pas, selectați **Adăugați date** pentru a furniza istoricul abonamentului.

1. Selectați **Abonament** și entitatea SubscriptionHistory și selectați **Următorul**. Datele necesare sunt completate automat din activitate. Selectați **Salvare**.

1. Sub Activitățile clienților, selectați **Adăugați date**.

1. Pentru acest exemplu, adăugați activitatea de revizuire web.

1. Selectați **Următorul**.

1. În **Actualizări de date** pas, selectați **Lunar** pentru programul model.

1. După examinarea tuturor detaliilor, selectați **Salvați și rulați**.

## <a name="task-5---review-model-results-and-explanations"></a>Sarcina 5 - Examinați rezultatele modelului și explicațiile

Lăsați modelul să finalizeze pregătirea și notarea datelor. Examinați explicațiile modelului de pierdere a abonamentului. Pentru mai multe informații, vezi [Vedeți rezultatele predicție](predict-subscription-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Sarcina 6 - Creați un segment de clienți cu risc de retragere ridicat

Rularea modelului creează o nouă entitate, care este listată pe **Date** > **Entități**. Puteți crea un segment nou pe baza entității create de model.

1. Pe pagina de rezultate, selectați **Creați segment**.

1. Creați o regulă folosind **OOBsubscriptionChurnPrediction** entitatea și definiți segmentul:
   - **Camp** : ChurnScore
   - **Operator** : mai mare ca
   - **Valoare** : 0,6

1. Selectați **Salvați** și **Alerga** segmentul.

Acum aveți un segment actualizat dinamic, care identifică clienții cu risc ridicat de retragere pentru această activitate de abonamente. Pentru mai multe informații, consultați [Creați și gestionați segmente](segments.md).

> [!TIP]
> De asemenea, puteți crea un segment pentru un model predicție din **Segmente** pagină selectând **Nou** si alegerea **Creați din** > **Inteligența**. Pentru mai multe informații, vezi [Creați un nou segment cu segmente rapide](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
