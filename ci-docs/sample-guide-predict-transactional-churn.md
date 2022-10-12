---
title: Ghid eșantion de predicție a retragerii tranzacționale
description: Utilizați acest exemplu de ghid pentru a încerca modelul preinstalat de predicție a retragerii tranzacționale.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609699"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Ghid eșantion de predicție a retragerii tranzacționale

Acest ghid vă va explica un exemplu de la capăt la capăt al abandonului tranzacțional predicție folosind date eșantion. Vă recomandăm să încercați acest predicție [într-un mediu nou](manage-environments.md).

## <a name="scenario"></a>Scenariu

Contoso este o companie care produce cafea și aparate de cafea de înaltă calitate. Ei vând produsele prin intermediul site-ului lor Contoso Coffee. Scopul lor este să știe care dintre clienții care le cumpără de obicei produsele nu vor mai fi clienți activi în următoarele 60 de zile. Știind care dintre clienții lor este **susceptibil să se retragă**, îi poate ajuta să economisească eforturile de marketing concentrându-se pe păstrarea lor.

## <a name="prerequisites"></a>Cerințe preliminare

- Minimum [Permisiuni de colaborare](permissions.md).

## <a name="task-1---ingest-data"></a>Sarcina 1 - Ingerare date

Examinați articolele [despre ingerarea de date](data-sources.md) și [conectarea la a Power Query sursă de date](connect-power-query.md). Următoarele informații presupun că sunteți familiarizat cu ingerarea datelor în general.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerarea datelor clienților de pe platforma de comerț electronic

1. Creați un sursă de date numit **eCommerce** și selectați **Text/CSV** conector.

1. Introduceți adresa de URL pentru contactele de comerț electronic https://aka.ms/ciadclasscontacts.

1. În timp ce editați datele, selectați **Transforma** și apoi **Utilizați primul rând ca antete**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:

   - **DateOfBirth**: Dată
   - **CreatedOn**: Dată/Oră/Zonă

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformați data nașterii în dată.":::

1. În **Nume** câmpul din panoul din dreapta, redenumiți-vă sursă de date în **eCommerceContacts**

1. Salvați sursa de date.

### <a name="ingest-online-purchase-data"></a>Ingerați date de cumpărare online

1. Adăugați un alt set de date la aceeași sursă de date **eCommerce**. Alegeți din nou conectorul **Text/CSV**.

1. Introduceți adresa URL pentru datele privind achizițiile online https://aka.ms/ciadclassonline.

1. În timp ce editați datele, selectați **Transforma** și apoi **Utilizați primul rând ca antete**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:

   - **PurchasedOn**: Dată/Oră
   - **TotalPrice**: Monedă

1. În **Nume** câmpul din panoul din dreapta, redenumiți-vă sursă de date în **eCommerceAchiziții**.

1. Salvați sursa de date.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerați datele clienților din schema de loialitate

1. Creați un sursă de date numit **Schema de loialitate** și selectați **Text/CSV** conector.

1. Introduceți adresa de URL pentru contactele de comerț electronic https://aka.ms/ciadclasscustomerloyalty.

1. În timp ce editați datele, selectați **Transforma** și apoi **Utilizați primul rând ca antete**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:

   - **DateOfBirth**: Dată
   - **RewardsPoints**: Număr întreg
   - **CreatedOn**: Dată/Oră

1. În **Nume** câmpul din panoul din dreapta, redenumiți-vă sursă de date în **Clienti loiali**.

1. Salvați sursa de date.

## <a name="task-2---data-unification"></a>Sarcina 2 - Unificarea datelor

Revizuiește articolul [despre unificarea datelor](data-unification.md). Următoarele informații presupun că sunteți familiarizat cu unificarea datelor în general.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Sarcina 3 - Crearea activității istoricului tranzacțiilor

Revizuiește articolul [despre activitățile clienților](activities.md). Următoarele informații presupun că sunteți familiarizat cu crearea de activități în general.

1. Creați o activitate numită **eCommerceAchiziții** cu *eCommercePurchases:eCommerce* entitatea și cheia sa primară, **PurchaseId**.

1. Creați o relație între *eCommercePurchases:eCommerce* și *eCommerceContact:eCommerce* cu **ContactID** ca cheie externă pentru a conecta cele două entități.

1. Selectați **Pretul total** pentru **EventActivity** și **CumpăratLa** pentru **Timestamp-ul**.

1. Selectați **SalesOrderLine** pentru **Tip de activitate** și mapați semantic datele de activitate.

1. Rulați activitatea.

## <a name="task-4---configure-transaction-churn-prediction"></a>Sarcina 4 - Configurați predicția de retragere tranzacțională

Cu profilurile unificate ale clienților la locul lor și activitatea, rulați tranzacția churn predicție.

1. Mergi la **Inteligența** > **Previziuni**.

1. Pe **Crea** filă, selectați **Utilizați modelul** pe **Model de retragere a clienților**.

1. Selectați **Tranzacțional** pentru tipul de renuntare si apoi **Incepe**.

1. Denumiți modelul **OOB eCommerce Transaction Churn Prediction** și entitatea de ieșire **OOBeCommerceChurnPrediction**.

1. Selectați **Următorul**.

1. Definiți preferințele modelului:

   - **fereastra predicție** :**60** zile pentru a defini cât de departe în viitor dorim să anticipăm rata de retragere a clienților.

   - **Definiția churn** :**60** zile pentru a indica durata fără achiziție după care un client este considerat a fi întors.

     :::image type="content" source="media/model-levers.PNG" alt-text="Selectați preferințele modelului predicție Window and Churn Definition.":::

1. Selectați **Următorul**.

1. Selectați **Istoricul achizițiilor (obligatoriu)** și selectați **Adăugare date** pentru istoricul achizițiilor.

1. Selectați **SalesOrderLine** și entitatea eCommercePurchases și selectați **Următorul**. Datele necesare sunt completate automat din activitate. Selectați **Salvați** și apoi **Următorul**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Conectați entitățile eCommerce.":::

1. Sari peste **Date suplimentare (opțional)** Etapa.

1. În **Actualizări de date** pas, selectați **Lunar** pentru programul model.

1. După examinarea tuturor detaliilor, selectați **Salvați și rulați**.

## <a name="task-5---review-model-results-and-explanations"></a>Sarcina 5 - Examinați rezultatele modelului și explicațiile

Lăsați modelul să finalizeze pregătirea și notarea datelor. Examinați explicațiile modelului de abandon. Pentru mai multe informații, vezi [Vedeți rezultatele predicție](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Sarcina 6 - Creați un segment de clienți cu risc de retragere ridicat

Rularea modelului de producție creează o nouă entitate, care este listată pe **Date** > **Entități**. Puteți crea un segment nou pe baza entității create de model.

1. Pe pagina de rezultate, selectați **Creați segment**.

1. Creați o regulă folosind **OOBeCommerceChurnPrediction** entitatea și definiți segmentul:
   - **Camp** : ChurnScore
   - **Operator** : mai mare ca
   - **Valoare** : 0,6

1. Selectați **Salvați** și **Alerga** segmentul.

Acum aveți un segment care este actualizat dinamic, care identifică clienții cu risc ridicat de pierdere. Pentru mai multe informații, consultați [Creați și gestionați segmente](segments.md).

> [!TIP]
> De asemenea, puteți crea un segment pentru un model predicție din **Segmente** pagină selectând **Nou** si alegerea **Creați din** > **Inteligența**. Pentru mai multe informații, vezi [Creați un nou segment cu segmente rapide](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
