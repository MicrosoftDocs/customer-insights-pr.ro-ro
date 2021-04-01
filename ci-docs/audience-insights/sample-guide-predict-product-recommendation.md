---
title: Eșantion de ghid de predicție pentru recomandarea produsului
description: Utilizați acest exemplu de ghid pentru a încerca modelul preinstalat de predicție a recomandării de produs.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 20072d14b160e54f5ad044adc1de6c079bf790e4
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595288"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>Eșantion de ghid pentru recomandarea produsului predicție (previzualizare)

Vă vom explica un exemplu complet de predicție a recomandării de produs folosind datele eșantion furnizate mai jos.

## <a name="scenario"></a>Scenariu

Contoso este o companie care produce cafea și aparate de cafea de înaltă calitate, pe care le vinde prin intermediul site-ului web Contoso Coffee. Scopul lor este să înțeleagă ce produse ar trebui să recomande clienților lor recurenti. Știind ce sunt mai mulți clienți **probabil să cumpere**, îi poate ajuta să economisească eforturile de marketing concentrându-se pe anumite elemente.

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

5. În câmpul „Nume” din panoul din dreapta, redenumiți sursa de date din **Interogare** în **eCommerceContacts**

6. **Salvați** sursa de date.

### <a name="ingest-online-purchase-data"></a>Ingerați date de cumpărare online

1. Adăugați un alt set de date la aceeași sursă de date **eCommerce**. Alegeți din nou conectorul **Text/CSV**.

1. Introduceți adresa URL pentru datele de **Achiziții online** https://aka.ms/ciadclassonline.

1. În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:
   - **PurchasedOn**: Dată/Oră
   - **TotalPrice**: Monedă

1. În câmpul **Nume** din panoul lateral, redenumiți sursa de date din **Interogare** în **eCommercePurchases**.

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

După ingerarea datelor, începem acum procesul de **Mapare, potrivire, îmbinare** pentru a crea un profil de client unificat. Pentru informații suplimentare, consultați [Unificare date](data-unification.md).

### <a name="map"></a>Hartă

1. După ingerarea datelor, mapați contactele de la datele de comerț electronic și de loialitate la tipuri de date obișnuite. Mergeți la **Date** > **Unificare** > **Mapare**.

2. Selectați entitățile care reprezintă profilul clientului - **eCommerceContacts** și **loyCustomers**.

   ![unificați sursele de date privind comerțul electronic și loialitatea.](media/unify-ecommerce-loyalty.png)

3. Selectați **ContactId** ca cheie primară pentru **eCommerceContacts** și **LoyaltyID** ca cheie primară pentru **loyCustomers**.

   ![Unificați LoyaltyId ca cheie principală.](media/unify-loyaltyid.png)

### <a name="match"></a>Corespondență

1. Accesați fila **Potrivire** și selectați **Setare ordine**.

2. În lista derulantă **Primar**, alegeți **eCommerceContacts: eCommerce** ca sursă principală și includeți toate înregistrările.

3. În lista derulantă **Entitate 2**, alegeți **loyCustomers: LoyaltyScheme** și includeți toate înregistrările.

   ![Potriviți unificarea de comerț electronic și loialitate.](media/unify-match-order.png)

4. Selectați **Creare regulă nouă**

5. Adăugați prima condiție folosind FullName.

   - Pentru eCommerceContacts selectați **FullName** din meniul derulant.
   - Pentru loyCustomers selectați **FullName** din meniul derulant.
   - Selectați lista derulantă **Normalizare** și alegeți **Tip (telefon, nume, adresă, ...)**.
   - Setați **Nivel de precizie**: **De bază** și **Valoare**: **Mare**.

6. Introduceți numele **FullName, Email** pentru noua regulă.

   - Adăugați o a doua condiție pentru adresa de e-mail selectând **Adăugați o condiție**
   - Pentru entitatea eCommerceContacts, alegeți **E-mail** din meniul derulant.
   - Pentru entitatea loyCustomers, alegeți **E-mail** din meniul derulant.
   - Lăsați Normalizarea necompletată.
   - Setați **Nivel de precizie**: **De bază** și **Valoare**: **Mare**.

   ![Unificați regula de potrivire pentru nume și e-mail.](media/unify-match-rule.png)

7. Selectați **Salvare** și **Rulare**.

### <a name="merge"></a>Îmbinare

1. Accesați fila **Îmbinare**.

1. Pe **ContactId** pentru entitatea **loyCustomers**, schimbați numele afișat în **ContactIdLOYALTY** pentru a-l diferenția de celelalte ID-uri ingerate.

   ![redenumiți contactid din ID-ul de loialitate.](media/unify-merge-contactid.png)

1. Selectați **Salvați** și **Rulați** pentru a porni procesul de îmbinare.

## <a name="task-3---configure-product-recommendation-prediction"></a>Sarcina 3 - Configurați recomandarea produsului predicție

Odată stabilite profilurile de clienți unificate, putem rula acum predicția de retragere a abonamentelor.

1. Accesați **Informații** > **Predicție** alegeți **Recomandarea produsului**.

1. Selectați **Începeți**.

1. Denumiți modelul **Modelul de recomandare pentru produsul OOB predicție** și entitatea de ieșire **OOBProductRecommendationModelPrediction**.

1. Definiți trei condiții pentru model:

   - **Numărul de produse**: Setați această valoare la **5**. Această setare definește câte produse doriți să le recomandați clienților dvs.

   - **Sugerați produse achiziționate recent de clienți?**: Selectați **Da** pentru a indica faptul că doriți să includeți produse în recomandarea pe care clienții dvs. au achiziționat-o anterior.

   - **Fereastră de privire retrospectivă:** Selectați cel puțin **365 de zile**. Această setare definește cât de departe va privi modelul înapoi spre activitatea clientului pentru a o utiliza drept intrare pentru recomandările sale.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferințe de model pentru modelul de recomandare produs.":::

1. Selectați **Date necesare** și selectați **Adăugare date** pentru istoricul achizițiilor.

1. Adăugați entitatea **eCommercePurchases : eCommerce** și mapați câmpurile din eCommerce la câmpurile corespunzătoare cerute de model.

1. Conectați entitatea **eCommercePurchases : eCommerce** cu **eCommerceContacts: eCommerce**.

   ![Conectați entitățile eCommerce.](media/model-purchase-join.png)

1. Selectați **Următorul** pentru a seta planificarea modelului.

   Modelul trebuie să se antreneze în mod regulat pentru a învăța noi modele atunci când sunt ingerate date noi. Pentru acest exemplu, selectați **Lunar**.

1. După examinarea tuturor detaliilor, selectați **Salvați și rulați**.


## <a name="task-4---review-model-results-and-explanations"></a>Sarcina 4 - Examinați rezultatele modelului și explicațiile

Lăsați modelul să finalizeze pregătirea și notarea datelor. Acum puteți revizui explicațiile modelului de recomandare a produsului. Pentru mai multe informații, consultați [Examinați starea și rezultatele unei predicții](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Activitatea 5 - Creați un segment de produse achiziționate

Rularea modelului de producție creează o nouă entitate pe care o puteți vedea în **Date** > **Entități**.

Puteți crea un segment nou pe baza entității create de model.

1. Mergeți la **Segmente**. Selectați **Nou** și alegeți **Creați din** > **Informații**.

   ![Crearea unui segment cu rezultatul modelului.](media/segment-intelligence.png)

1. Selectați punctul final **OOBProductRecommendationModelPrediction** și definiți segmentul:

   - Câmp: ID produs
   - Operator: valoare
   - Valoare: selectați primele trei ID-uri de produs

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Creați un segment din rezultatele modelului.":::

Acum aveți un segment actualizat dinamic, care identifică clienții care sunt mai dispuși să achiziționeze cele mai recomandate trei produse 

Pentru mai multe informații, consultați [Creați și gestionați segmente](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]