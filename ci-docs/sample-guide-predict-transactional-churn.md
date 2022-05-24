---
title: Ghid eșantion de predicție a retragerii tranzacționale
description: Utilizați acest exemplu de ghid pentru a încerca modelul preinstalat de predicție a retragerii tranzacționale.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741334"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Ghid eșantion de predicție a retragerii tranzacționale

Acest ghid vă va explica un exemplu complet de predicție a retragerii tranzacționale în Customer Insights folosind datele furnizate mai jos. Toate datele utilizate în acest ghid nu sunt date reale ale clienților și fac parte din setul de date Contoso găsit în mediul *Demo* în cadrul abonamentului dvs. Customer Insights.

## <a name="scenario"></a>Scenariu

Contoso este o companie care produce cafea și aparate de cafea de înaltă calitate, pe care le vinde prin intermediul site-ului web Contoso Coffee. Scopul lor este să știe care dintre clienții care le cumpără de obicei produsele nu vor mai fi clienți activi în următoarele 60 de zile. Știind care dintre clienții lor este **susceptibil să se retragă**, îi poate ajuta să economisească eforturile de marketing concentrându-se pe păstrarea lor.

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

### <a name="ingest-online-purchase-data"></a>Ingerați date de cumpărare online

1. Adăugați un alt set de date la aceeași sursă de date **eCommerce**. Alegeți din nou conectorul **Text/CSV**.

1. Introduceți adresa URL pentru datele de **Achiziții online** https://aka.ms/ciadclassonline.

1. În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:

   - **PurchasedOn**: Dată/Oră
   - **TotalPrice**: Monedă
   
1. În câmpul **Nume** din panoul din dreapta, redenumiți sursa de date din **Interogare** în **eCommercePurchases**.

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

## <a name="task-2---data-unification"></a>Sarcina 2 - Unificarea datelor

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>Sarcina 3 - Configurați predicția de retragere tranzacțională

Cu profilurile unificate ale clienților, acum putem rula tranzacțiile predicție. Pentru pași detaliați, consultați [Schimbarea tranzacției predicție](predict-transactional-churn.md) articol. 

1. Mergeți la **Informații** > **Descoperiți** și selectați pentru a utiliza **Modelul de retragere a clienților**.

1. Selectați opțiunea **Tranzacțional** și selectați **Începeți**.

1. Denumiți modelul **OOB eCommerce Transaction Churn Prediction** și entitatea de ieșire **OOBeCommerceChurnPrediction**.

1. Definiți două condiții pentru modelul de retragere:

   * **Fereastra de predicție**: **cel puțin 60** de zile. Această setare definește cât de departe în viitor vrem să prezicem retragerea clienților.

   * **Definiție retragere**: **cel puțin 60** de zile. Durata fără cumpărare, după care un client este considerat retras.

     :::image type="content" source="media/model-levers.PNG" alt-text="Selectați pârghiile model Fereastră de predicție și Definiție retragere.":::

1. Selectați **Istoricul achizițiilor (obligatoriu)** și selectați **Adăugare date** pentru istoricul achizițiilor.

1. Adăugați entitatea **eCommercePurchases : eCommerce** și mapați câmpurile din eCommerce la câmpurile corespunzătoare cerute de model.

1. Conectați entitatea **eCommercePurchases : eCommerce** cu **eCommerceContacts: eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Conectați entitățile eCommerce.":::

1. Selectați **Următorul** pentru a seta planificarea modelului.

   Modelul trebuie să se antreneze în mod regulat pentru a învăța noi modele atunci când sunt ingerate date noi. Pentru acest exemplu, selectați **Lunar**.

1. După examinarea tuturor detaliilor, selectați **Salvați și rulați**.

## <a name="task-4---review-model-results-and-explanations"></a>Sarcina 4 - Examinați rezultatele modelului și explicațiile

Lăsați modelul să finalizeze pregătirea și notarea datelor. Acum puteți revizui explicațiile modelului de abandon. Pentru mai multe informații, consultați [Examinați starea și rezultatele unei predicții](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Sarcina 5 - Creați un segment de clienți cu risc de retragere ridicat

Rularea modelului de producție creează o nouă entitate pe care o puteți vedea în **Date** > **Entități**.   

Puteți crea un segment nou pe baza entității create de model.

1.  Mergeți la **Segmente**. Selectați **Nou** și alegeți **Creați din** > **Informații**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Crearea unui segment cu rezultatul modelului.":::

1. Selectează **OOBeCommerceChurnPrediction** punctul final și definiți segmentul: 
   - Câmp: ChurnScore
   - Operator: mai mare decât
   - Valoare: 0,6

Acum aveți un segment care este actualizat dinamic, care identifică clienții cu risc ridicat de pierdere.

Pentru mai multe informații, consultați [Creați și gestionați segmente](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
