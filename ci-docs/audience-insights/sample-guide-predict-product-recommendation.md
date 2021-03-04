---
title: Eșantion de ghid de predicție pentru recomandarea produsului
description: Utilizați acest exemplu de ghid pentru a încerca modelul preinstalat de predicție a recomandării de produs.
ms.date: 02/10/2021
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ee873d9b7caa5f891cb2d5b8c665dec90ad0e59
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270524"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="dfccf-103">Eșantion de ghid pentru recomandarea produsului predicție (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="dfccf-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="dfccf-104">Vă vom explica un exemplu complet de predicție a recomandării de produs folosind datele eșantion furnizate mai jos.</span><span class="sxs-lookup"><span data-stu-id="dfccf-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="dfccf-105">Scenariu</span><span class="sxs-lookup"><span data-stu-id="dfccf-105">Scenario</span></span>

<span data-ttu-id="dfccf-106">Contoso este o companie care produce cafea și aparate de cafea de înaltă calitate, pe care le vinde prin intermediul site-ului web Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="dfccf-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="dfccf-107">Scopul lor este să înțeleagă ce produse ar trebui să recomande clienților lor recurenti.</span><span class="sxs-lookup"><span data-stu-id="dfccf-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="dfccf-108">Știind ce sunt mai mulți clienți **probabil să cumpere**, îi poate ajuta să economisească eforturile de marketing concentrându-se pe anumite elemente.</span><span class="sxs-lookup"><span data-stu-id="dfccf-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dfccf-109">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="dfccf-109">Prerequisites</span></span>

- <span data-ttu-id="dfccf-110">Cel puțin [Permisiuni de contributor](permissions.md) în Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="dfccf-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="dfccf-111">Vă recomandăm să implementați pașii următori [într-un mediu nou](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="dfccf-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="dfccf-112">Sarcina 1 - Ingerare date</span><span class="sxs-lookup"><span data-stu-id="dfccf-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="dfccf-113">Examinați articolele [despre ingestia de date](data-sources.md) și în mod specific [importul surselor de date utilizând conectori Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="dfccf-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="dfccf-114">Următoarele informații presupun că v-ați familiarizat cu ingerarea datelor în general.</span><span class="sxs-lookup"><span data-stu-id="dfccf-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="dfccf-115">Ingerarea datelor clienților de pe platforma de comerț electronic</span><span class="sxs-lookup"><span data-stu-id="dfccf-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="dfccf-116">Creați un sursă de date numită **eCommerce**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="dfccf-117">Introduceți adresa de URL pentru contactele de comerț electronic https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="dfccf-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="dfccf-118">În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="dfccf-119">Actualizați tipul de date pentru coloanele enumerate mai jos:</span><span class="sxs-lookup"><span data-stu-id="dfccf-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="dfccf-120">**DateOfBirth**: Dată</span><span class="sxs-lookup"><span data-stu-id="dfccf-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="dfccf-121">**CreatedOn**: Dată/Oră/Zonă</span><span class="sxs-lookup"><span data-stu-id="dfccf-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformați data nașterii în dată.":::

5. <span data-ttu-id="dfccf-123">În câmpul „Nume” din panoul din dreapta, redenumiți sursa de date din **Interogare** în **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="dfccf-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="dfccf-124">**Salvați** sursa de date.</span><span class="sxs-lookup"><span data-stu-id="dfccf-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="dfccf-125">Ingerați date de cumpărare online</span><span class="sxs-lookup"><span data-stu-id="dfccf-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="dfccf-126">Adăugați un alt set de date la aceeași sursă de date **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="dfccf-127">Alegeți din nou conectorul **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="dfccf-128">Introduceți adresa URL pentru datele de **Achiziții online** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="dfccf-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="dfccf-129">În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="dfccf-130">Actualizați tipul de date pentru coloanele enumerate mai jos:</span><span class="sxs-lookup"><span data-stu-id="dfccf-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="dfccf-131">**PurchasedOn**: Dată/Oră</span><span class="sxs-lookup"><span data-stu-id="dfccf-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="dfccf-132">**TotalPrice**: Monedă</span><span class="sxs-lookup"><span data-stu-id="dfccf-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="dfccf-133">În câmpul **Nume** din panoul lateral, redenumiți sursa de date din **Interogare** în **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="dfccf-134">Salvați sursa de date.</span><span class="sxs-lookup"><span data-stu-id="dfccf-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="dfccf-135">Ingerați datele clienților din schema de loialitate</span><span class="sxs-lookup"><span data-stu-id="dfccf-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="dfccf-136">Creați o sursă de date numită **LoyaltyScheme**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="dfccf-137">Introduceți adresa de URL pentru contactele de comerț electronic https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="dfccf-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="dfccf-138">În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="dfccf-139">Actualizați tipul de date pentru coloanele enumerate mai jos:</span><span class="sxs-lookup"><span data-stu-id="dfccf-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="dfccf-140">**DateOfBirth**: Dată</span><span class="sxs-lookup"><span data-stu-id="dfccf-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="dfccf-141">**RewardsPoints**: Număr întreg</span><span class="sxs-lookup"><span data-stu-id="dfccf-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="dfccf-142">**CreatedOn**: Dată/Oră</span><span class="sxs-lookup"><span data-stu-id="dfccf-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="dfccf-143">În câmpul **Nume** din panoul din dreapta, redenumiți sursa de date din **Interogare** în **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="dfccf-144">Salvați sursa de date.</span><span class="sxs-lookup"><span data-stu-id="dfccf-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="dfccf-145">Sarcina 2 - Unificarea datelor</span><span class="sxs-lookup"><span data-stu-id="dfccf-145">Task 2 - Data unification</span></span>

<span data-ttu-id="dfccf-146">După ingerarea datelor, începem acum procesul de **Mapare, potrivire, îmbinare** pentru a crea un profil de client unificat.</span><span class="sxs-lookup"><span data-stu-id="dfccf-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="dfccf-147">Pentru informații suplimentare, consultați [Unificare date](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="dfccf-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="dfccf-148">Hartă</span><span class="sxs-lookup"><span data-stu-id="dfccf-148">Map</span></span>

1. <span data-ttu-id="dfccf-149">După ingerarea datelor, mapați contactele de la datele de comerț electronic și de loialitate la tipuri de date obișnuite.</span><span class="sxs-lookup"><span data-stu-id="dfccf-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="dfccf-150">Mergeți la **Date** > **Unificare** > **Mapare**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="dfccf-151">Selectați entitățile care reprezintă profilul clientului - **eCommerceContacts** și **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![unificați sursele de date privind comerțul electronic și loialitatea.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="dfccf-153">Selectați **ContactId** ca cheie primară pentru **eCommerceContacts** și **LoyaltyID** ca cheie primară pentru **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Unificați LoyaltyId ca cheie principală.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="dfccf-155">Corespondență</span><span class="sxs-lookup"><span data-stu-id="dfccf-155">Match</span></span>

1. <span data-ttu-id="dfccf-156">Accesați fila **Potrivire** și selectați **Setare ordine**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="dfccf-157">În lista derulantă **Primar**, alegeți **eCommerceContacts: eCommerce** ca sursă principală și includeți toate înregistrările.</span><span class="sxs-lookup"><span data-stu-id="dfccf-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="dfccf-158">În lista derulantă **Entitate 2**, alegeți **loyCustomers: LoyaltyScheme** și includeți toate înregistrările.</span><span class="sxs-lookup"><span data-stu-id="dfccf-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Potriviți unificarea de comerț electronic și loialitate.](media/unify-match-order.png)

4. <span data-ttu-id="dfccf-160">Selectați **Creare regulă nouă**</span><span class="sxs-lookup"><span data-stu-id="dfccf-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="dfccf-161">Adăugați prima condiție folosind FullName.</span><span class="sxs-lookup"><span data-stu-id="dfccf-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="dfccf-162">Pentru eCommerceContacts selectați **FullName** din meniul derulant.</span><span class="sxs-lookup"><span data-stu-id="dfccf-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="dfccf-163">Pentru loyCustomers selectați **FullName** din meniul derulant.</span><span class="sxs-lookup"><span data-stu-id="dfccf-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="dfccf-164">Selectați lista derulantă **Normalizare** și alegeți **Tip (telefon, nume, adresă, ...)**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="dfccf-165">Setați **Nivel de precizie**: **De bază** și **Valoare**: **Mare**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="dfccf-166">Introduceți numele **FullName, Email** pentru noua regulă.</span><span class="sxs-lookup"><span data-stu-id="dfccf-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="dfccf-167">Adăugați o a doua condiție pentru adresa de e-mail selectând **Adăugați o condiție**</span><span class="sxs-lookup"><span data-stu-id="dfccf-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="dfccf-168">Pentru entitatea eCommerceContacts, alegeți **E-mail** din meniul derulant.</span><span class="sxs-lookup"><span data-stu-id="dfccf-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="dfccf-169">Pentru entitatea loyCustomers, alegeți **E-mail** din meniul derulant.</span><span class="sxs-lookup"><span data-stu-id="dfccf-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="dfccf-170">Lăsați Normalizarea necompletată.</span><span class="sxs-lookup"><span data-stu-id="dfccf-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="dfccf-171">Setați **Nivel de precizie**: **De bază** și **Valoare**: **Mare**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Unificați regula de potrivire pentru nume și e-mail.](media/unify-match-rule.png)

7. <span data-ttu-id="dfccf-173">Selectați **Salvare** și **Rulare**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="dfccf-174">Îmbinare</span><span class="sxs-lookup"><span data-stu-id="dfccf-174">Merge</span></span>

1. <span data-ttu-id="dfccf-175">Accesați fila **Îmbinare**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="dfccf-176">Pe **ContactId** pentru entitatea **loyCustomers**, schimbați numele afișat în **ContactIdLOYALTY** pentru a-l diferenția de celelalte ID-uri ingerate.</span><span class="sxs-lookup"><span data-stu-id="dfccf-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![redenumiți contactid din ID-ul de loialitate.](media/unify-merge-contactid.png)

1. <span data-ttu-id="dfccf-178">Selectați **Salvați** și **Rulați** pentru a porni procesul de îmbinare.</span><span class="sxs-lookup"><span data-stu-id="dfccf-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="dfccf-179">Sarcina 3 - Configurați recomandarea produsului predicție</span><span class="sxs-lookup"><span data-stu-id="dfccf-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="dfccf-180">Odată stabilite profilurile de clienți unificate, putem rula acum predicția de retragere a abonamentelor.</span><span class="sxs-lookup"><span data-stu-id="dfccf-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="dfccf-181">Accesați **Informații** > **Predicție** alegeți **Recomandarea produsului**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="dfccf-182">Selectați **Începeți**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-182">Select **Get started**.</span></span>

1. <span data-ttu-id="dfccf-183">Denumiți modelul **Modelul de recomandare pentru produsul OOB predicție** și entitatea de ieșire **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="dfccf-184">Definiți trei condiții pentru model:</span><span class="sxs-lookup"><span data-stu-id="dfccf-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="dfccf-185">**Numărul de produse**: Setați această valoare la **5**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="dfccf-186">Această setare definește câte produse doriți să le recomandați clienților dvs.</span><span class="sxs-lookup"><span data-stu-id="dfccf-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="dfccf-187">**Sugerați produse achiziționate recent de clienți?**: Selectați **Da** pentru a indica faptul că doriți să includeți produse în recomandarea pe care clienții dvs. au achiziționat-o anterior.</span><span class="sxs-lookup"><span data-stu-id="dfccf-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="dfccf-188">**Fereastră de privire retrospectivă:** Selectați cel puțin **365 de zile**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="dfccf-189">Această setare definește cât de departe va privi modelul înapoi spre activitatea clientului pentru a o utiliza drept intrare pentru recomandările sale.</span><span class="sxs-lookup"><span data-stu-id="dfccf-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferințe de model pentru modelul de recomandare produs.":::

1. <span data-ttu-id="dfccf-191">Selectați **Date necesare** și selectați **Adăugare date** pentru istoricul achizițiilor.</span><span class="sxs-lookup"><span data-stu-id="dfccf-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="dfccf-192">Adăugați entitatea **eCommercePurchases : eCommerce** și mapați câmpurile din eCommerce la câmpurile corespunzătoare cerute de model.</span><span class="sxs-lookup"><span data-stu-id="dfccf-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="dfccf-193">Conectați entitatea **eCommercePurchases : eCommerce** cu **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Conectați entitățile eCommerce.](media/model-purchase-join.png)

1. <span data-ttu-id="dfccf-195">Selectați **Următorul** pentru a seta planificarea modelului.</span><span class="sxs-lookup"><span data-stu-id="dfccf-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="dfccf-196">Modelul trebuie să se antreneze în mod regulat pentru a învăța noi modele atunci când sunt ingerate date noi.</span><span class="sxs-lookup"><span data-stu-id="dfccf-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="dfccf-197">Pentru acest exemplu, selectați **Lunar**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="dfccf-198">După examinarea tuturor detaliilor, selectați **Salvați și rulați**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="dfccf-199">Sarcina 4 - Examinați rezultatele modelului și explicațiile</span><span class="sxs-lookup"><span data-stu-id="dfccf-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="dfccf-200">Lăsați modelul să finalizeze pregătirea și notarea datelor.</span><span class="sxs-lookup"><span data-stu-id="dfccf-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="dfccf-201">Acum puteți revizui explicațiile modelului de recomandare a produsului.</span><span class="sxs-lookup"><span data-stu-id="dfccf-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="dfccf-202">Pentru mai multe informații, consultați [Examinați starea și rezultatele unei predicții](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="dfccf-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="dfccf-203">Activitatea 5 - Creați un segment de produse achiziționate</span><span class="sxs-lookup"><span data-stu-id="dfccf-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="dfccf-204">Rularea modelului de producție creează o nouă entitate pe care o puteți vedea în **Date** > **Entități**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="dfccf-205">Puteți crea un segment nou pe baza entității create de model.</span><span class="sxs-lookup"><span data-stu-id="dfccf-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="dfccf-206">Mergeți la **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-206">Go to **Segments**.</span></span> <span data-ttu-id="dfccf-207">Selectați **Nou** și alegeți **Creați din** > **Informații**.</span><span class="sxs-lookup"><span data-stu-id="dfccf-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Crearea unui segment cu rezultatul modelului.](media/segment-intelligence.png)

1. <span data-ttu-id="dfccf-209">Selectați punctul final **OOBProductRecommendationModelPrediction** și definiți segmentul:</span><span class="sxs-lookup"><span data-stu-id="dfccf-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="dfccf-210">Câmp: ID produs</span><span class="sxs-lookup"><span data-stu-id="dfccf-210">Field: ProductID</span></span>
   - <span data-ttu-id="dfccf-211">Operator: valoare</span><span class="sxs-lookup"><span data-stu-id="dfccf-211">Operator: Value</span></span>
   - <span data-ttu-id="dfccf-212">Valoare: selectați primele trei ID-uri de produs</span><span class="sxs-lookup"><span data-stu-id="dfccf-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Creați un segment din rezultatele modelului.":::

<span data-ttu-id="dfccf-214">Acum aveți un segment actualizat dinamic, care identifică clienții care sunt mai dispuși să achiziționeze cele mai recomandate trei produse</span><span class="sxs-lookup"><span data-stu-id="dfccf-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="dfccf-215">Pentru mai multe informații, consultați [Creați și gestionați segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="dfccf-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]