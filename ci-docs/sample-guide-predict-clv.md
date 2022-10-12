---
title: Ghid eșantion de predicție pentru Valoarea ciclului de viață a clientului (CLV)
description: Utilizați acest exemplu de ghid pentru a încerca modelul de predicție pentru Valoarea ciclului de viață a clientului.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609653"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Ghid eșantion de predicție pentru Valoarea ciclului de viață a clientului (CLV)

Acest ghid vă prezintă un exemplu de la capăt la capăt al valorii de viață a clientului (CLV) predicție în Customer Insights, folosind date eșantion. Vă recomandăm să încercați acest predicție [într-un mediu nou](manage-environments.md).

## <a name="scenario"></a>Scenariu

Contoso este o companie care produce cafea și aparate de cafea de înaltă calitate. Ei vând produsele prin intermediul site-ului lor Contoso Coffee. Compania dorește să înțeleagă valoarea (veniturile) pe care clienții lor o pot genera în următoarele 12 luni. Cunoașterea valorii așteptate a clienților lor în următoarele 12 luni îi va ajuta să-și direcționeze eforturile de marketing către clienții cu valoare ridicată.

## <a name="prerequisites"></a>Cerințe preliminare

- Minimum [Permisiuni de colaborare](permissions.md).

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

1. **Salvați** sursa de date.

### <a name="ingest-online-purchase-data"></a>Ingerați date de cumpărare online

1. Adăugați un alt set de date la aceeași sursă de date **eCommerce**. Alegeți din nou conectorul **Text/CSV**.

1. Introduceți adresa URL pentru datele de **Achiziții online** https://aka.ms/ciadclassonline.

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

### <a name="ingest-customer-data-from-website-reviews"></a>Ingerați datele clienților din recenziile site-ului web

1. Creați un sursă de date numit **Site-ul web** și selectați **Text/CSV** conector.

1. Introduceți adresa URL pentru recenziile site-ului https://aka.ms/CI-ILT/WebReviews.

1. În timp ce editați datele, selectați **Transforma** și apoi **Utilizați primul rând ca antete**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:
   - **ReviewRating**: Număr decimal
   - **ReviewDate**: Dată

1. În **Nume** câmpul din panoul din dreapta, redenumiți-vă sursă de date în **Recenzii**.

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

1. Adăugați o altă activitate și mapați numele câmpurilor acesteia la câmpurile corespunzătoare:
   - **Entitate de activitate** : Recenzii:Site web
   - **Cheia principala** : ReviewId
   - **Timestamp-ul** : ReviewDate
   - **Activitatea evenimentului** : ActivityTypeDisplay
   - **Detaliu suplimentar** : ReviewEvaluare
   - **Tip de activitate** : Revizuire

1. Rulați activitatea.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Sarcina 4 - Configurați predicția pentru Valoarea ciclului de viață a clientului

Cu profilurile unificate ale clienților existente și activitatea creată, rulați valoarea de viață a clientului (CLV) predicție. Pentru pași detaliați, vezi [Valoarea de viață a clientului predicție](predict-customer-lifetime-value.md).

1. Mergi la **Inteligența** > **Previziuni**.

1. Pe **Crea** filă, selectați **Utilizați modelul** pe **Valoarea de viață a clientului** ţiglă.

1. Selectați **Începeți**.

1. Denumiți modelul **Predicție OOB eCommerce CLV** și entitatea de ieșire **OOBeCommerceCLVPrediction**.

1. Definiți preferințele modelului:
   - **predicție perioada de timp** :**12 luni sau 1 an** pentru a defini cât de departe în viitor să prezică CLV.
   - **Clienți activi** :**Lăsați modelul să calculeze intervalul de achiziție** care este intervalul de timp în care un client trebuie să fi avut cel puțin o tranzacție pentru a fi considerat activ.
   - **Client de mare valoare** : definiți manual clienții de mare valoare ca **primii 30% dintre clienții activi**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Preferințele intră în experiența ghidată pentru modelul CLV.":::

1. Selectați **Următorul**.

1. În pasul **Date necesare**, selectați **Adăugați date** pentru a furniza datele din istoricul tranzacțiilor.

    :::image type="content" source="media/clv-model-required.png" alt-text="Adăugați pasul de date necesar în experiența ghidată pentru modelul CLV.":::

1. Selectați **SalesOrderLine** și entitatea eCommercePurchases și selectați **Următorul**. Datele necesare sunt completate automat din activitate. Selectați **Salvați** și apoi **Următorul**.

1. The **Date suplimentare (opțional)** pasul vă permite să adăugați mai multe date despre activitatea clienților pentru a obține mai multe informații despre interacțiunile cu clienții. Pentru acest exemplu, selectați **Adăugați date** și adăugați activitatea de revizuire web.

1. Selectați **Următorul**.

1. În **Actualizări de date** pas, selectați **Lunar** pentru programul model.

1. Selectați **Următorul**.

1. După examinarea tuturor detaliilor, selectați **Salvați și rulați**.

## <a name="task-5---review-model-results-and-explanations"></a>Sarcina 5 - Examinați rezultatele modelului și explicațiile

Lăsați modelul să finalizeze pregătirea și notarea datelor. Examinați [Rezultate și explicații ale modelului CLV](predict-customer-lifetime-value.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Sarcina 6 - Creați un segment de clienți de mare valoare

Rularea modelului creează o nouă entitate, care este listată pe **Date** > **Entități**. Puteți crea un nou segment de clienți pe baza entității create de model.

1. Pe pagina de rezultate, selectați **Creați segment**.

1. Creați o regulă folosind **OOBeCommerceCLVPrediction** entitatea și definiți segmentul:
   - **Camp** : CLVScore
   - **Operator** : mai mare ca
   - **Valoare** : 1500

1. Selectați **Salvați** și **Alerga** segmentul.

Acum aveți un segment care identifică clienții despre care se estimează că vor genera mai mult de 1500$ în venituri în următoarele 12 luni. Acest segment se actualizează dinamic dacă sunt ingerate mai multe date. Pentru mai multe informații, consultați [Creați și gestionați segmente](segments.md).

> [!TIP]
> De asemenea, puteți crea un segment pentru un model predicție din **Segmente** pagină selectând **Nou** si alegerea **Creați din** > **Inteligența**. Pentru mai multe informații, vezi [Creați un nou segment cu segmente rapide](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
