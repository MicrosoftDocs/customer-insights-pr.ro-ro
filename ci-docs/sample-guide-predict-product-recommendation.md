---
title: Eșantion de ghid de predicție pentru recomandarea produsului
description: Utilizați acest exemplu de ghid pentru a încerca modelul preinstalat de predicție a recomandării de produs.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610159"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Eșantion de ghid de predicție pentru recomandarea produsului

Acest ghid vă prezintă un exemplu complet de recomandare de produs predicție folosind date eșantion. Vă recomandăm să încercați acest predicție [într-un mediu nou](manage-environments.md).

## <a name="scenario"></a>Scenariu

Contoso este o companie care produce cafea și aparate de cafea de înaltă calitate. Ei vând produsele prin intermediul site-ului lor Contoso Coffee. Scopul lor este să înțeleagă ce produse ar trebui să recomande clienților lor recurenti. Știind care sunt clienții mai mulți **probabil să cumpere** îi poate ajuta să economisească eforturile de marketing concentrându-se pe anumite articole.

## <a name="prerequisites"></a>Cerințe preliminare

- Cel puțin [Permisiuni de contributor](permissions.md) în Customer Insights.

## <a name="task-1---ingest-data"></a>Sarcina 1 - Ingerare date

Examinați articolele [despre ingerarea de date](data-sources.md) și [conectarea la a Power Query sursă de date](connect-power-query.md). Următoarele informații presupun că sunteți familiarizat cu ingerarea datelor în general.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerarea datelor clienților de pe platforma de comerț electronic

1. Creați un Power Query sursă de date numit **eCommerce** și selectați **Text/CSV** conector.

1. Introduceți adresa URL pentru persoanele de contact din comerțul electronic:https://aka.ms/ciadclasscontacts.

1. În timp ce editați datele, selectați **Transforma** și apoi **Utilizați primul rând ca antete**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:
   - **DateOfBirth**: Dată
   - **CreatedOn**: Dată/Oră/Zonă

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformați data nașterii în dată.":::

1. În **Nume** câmpul din panoul din dreapta, redenumiți-vă sursă de date în **eCommerceContacts**.

1. **Salvați** sursa de date.

### <a name="ingest-online-purchase-data"></a>Ingerați date de cumpărare online

1. Adăugați un alt set de date la aceeași sursă de date **eCommerce**. Alegeți din nou conectorul **Text/CSV**.

1. Introduceți adresa URL pentru datele privind achizițiile online https://aka.ms/ciadclassonline.

1. În timp ce editați datele, selectați **Transforma** și apoi **Utilizați primul rând ca antete**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:
   - **PurchasedOn**: Dată/Oră
   - **TotalPrice**: Monedă

1. În **Nume** câmpul din panoul lateral, redenumiți-vă sursă de date în **eCommerceAchiziții**.

1. **Salvați** sursa de date.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerați datele clienților din schema de loialitate

1. Creați un sursă de date numit **Schema de loialitate** și selectați **Text/CSV** conector.

1. Introduceți adresa URL pentru clienții fideli https://aka.ms/ciadclasscustomerloyalty.

1. În timp ce editați datele, selectați **Transforma** și apoi **Utilizați primul rând ca antete**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:
   - **DateOfBirth**: Dată
   - **RewardsPoints**: Număr întreg
   - **CreatedOn**: Dată/Oră

1. În **Nume** câmpul din panoul din dreapta, redenumiți-vă sursă de date în **Clienti loiali**.

1. **Salvați** sursa de date.

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

## <a name="task-4---configure-product-recommendation-prediction"></a>Sarcina 4 - Configurați recomandarea produsului predicție

Cu profilurile de clienți unificate și activitatea creată, rulați recomandarea de produs predicție.

1. Mergi la **Inteligența** > **Previziuni**.

1. Pe **Crea** filă, selectați **Utilizați modelul** pe **Recomandări de produse (previzualizare)** ţiglă.

1. Selectați **Începeți**.

1. Denumiți modelul **Modelul de recomandare pentru produsul OOB predicție** și entitatea de ieșire **OOBProductRecommendationModelPrediction**.

1. Selectați **Următorul**.

1. Definiți preferințele modelului:
   - **Numărul de produse** :**5** pentru a defini câte produse doriți să recomandați clienților dvs.
   - **Achiziții repetate așteptate** :**da** pentru a include produsele achiziționate anterior în recomandare.
   - **Privește fereastra înapoi:** **365 de zile** pentru a defini cât de departe va privi modelul înainte de a recomanda din nou un produs.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferințe de model pentru modelul de recomandare produs.":::

1. Selectați **Următorul**.

1. În **Adăugați istoricul achizițiilor** pas, selectați **Adăugați date**.

1. Selectați **SalesOrderLine** și entitatea eCommercePurchases și selectați **Următorul**. Datele necesare sunt completate automat din activitate. Selectați **Salvați** și apoi **Următorul**.

1. Sari peste **Adăugați informații despre produs** și **Filtre de produs** pași deoarece nu avem date despre informații despre produs.

1. În **Actualizări de date** pas, selectați **Lunar** pentru programul model.

1. Selectați **Următorul**.

1. După examinarea tuturor detaliilor, selectați **Salvați și rulați**.

## <a name="task-5---review-model-results-and-explanations"></a>Sarcina 5 - Examinați rezultatele modelului și explicațiile

Lăsați modelul să finalizeze pregătirea și notarea datelor. Examinați [explicații model de recomandare de produs](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Activitatea 6 - Creați un segment de produse achiziționate

Rularea modelului creează o nouă entitate, care este listată pe **Date** > **Entități**. Puteți crea un segment nou pe baza entității create de model.

1. Pe pagina de rezultate, selectați **Creați segment**.

1. Creați o regulă folosind **OOBProductRecommendationModelPrediction** entitatea și definiți segmentul:
   - **Camp** : ID produs
   - **Valoare** : selectați primele trei ID-uri de produs

1. Selectați **Salvați** și **Alerga** segmentul.

Acum aveți un segment care este actualizat dinamic, care identifică clienții care ar putea fi interesați să cumpere cele mai recomandate cinci produse. Pentru mai multe informații, consultați [Creați și gestionați segmente](segments.md).

> [!TIP]
> De asemenea, puteți crea un segment pentru un model predicție din **Segmente** pagină selectând **Nou** si alegerea **Creați din** > **Inteligența**. Pentru mai multe informații, vezi [Creați un nou segment cu segmente rapide](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
