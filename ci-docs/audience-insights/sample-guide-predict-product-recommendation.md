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
ms.openlocfilehash: a85ee598ec747d0594755314e83a127ce0f2af95
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306181"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="501a7-103">Eșantion de ghid pentru recomandarea produsului predicție (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="501a7-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="501a7-104">Vă vom explica un exemplu complet de predicție a recomandării de produs folosind datele eșantion furnizate mai jos.</span><span class="sxs-lookup"><span data-stu-id="501a7-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="501a7-105">Scenariu</span><span class="sxs-lookup"><span data-stu-id="501a7-105">Scenario</span></span>

<span data-ttu-id="501a7-106">Contoso este o companie care produce cafea și aparate de cafea de înaltă calitate, pe care le vând prin intermediul site-ului lor de cafea Contoso.</span><span class="sxs-lookup"><span data-stu-id="501a7-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="501a7-107">Scopul lor este să înțeleagă ce produse ar trebui să recomande clienților lor recurenti.</span><span class="sxs-lookup"><span data-stu-id="501a7-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="501a7-108">Știind ce sunt mai mulți clienți **probabil să cumpere**, îi poate ajuta să economisească eforturile de marketing concentrându-se pe anumite elemente.</span><span class="sxs-lookup"><span data-stu-id="501a7-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="501a7-109">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="501a7-109">Prerequisites</span></span>

- <span data-ttu-id="501a7-110">Cel puțin [Permisiuni de contributor](permissions.md) în Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="501a7-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="501a7-111">Vă recomandăm să implementați pașii următori [într-un mediu nou](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="501a7-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="501a7-112">Sarcina 1 - Ingerare date</span><span class="sxs-lookup"><span data-stu-id="501a7-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="501a7-113">Examinați articolele [despre ingestia de date](data-sources.md) și în mod specific [importul surselor de date utilizând conectori Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="501a7-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="501a7-114">Următoarele informații presupun că v-ați familiarizat cu ingerarea datelor în general.</span><span class="sxs-lookup"><span data-stu-id="501a7-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="501a7-115">Ingerarea datelor clienților de pe platforma de comerț electronic</span><span class="sxs-lookup"><span data-stu-id="501a7-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="501a7-116">Creați un sursă de date numită **eCommerce**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="501a7-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="501a7-117">Introduceți adresa de URL pentru contactele de comerț electronic https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="501a7-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="501a7-118">În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.</span><span class="sxs-lookup"><span data-stu-id="501a7-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="501a7-119">Actualizați tipul de date pentru coloanele enumerate mai jos:</span><span class="sxs-lookup"><span data-stu-id="501a7-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="501a7-120">**DateOfBirth**: Dată</span><span class="sxs-lookup"><span data-stu-id="501a7-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="501a7-121">**CreatedOn**: Dată/Oră/Zonă</span><span class="sxs-lookup"><span data-stu-id="501a7-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformați data nașterii în dată.":::

5. <span data-ttu-id="501a7-123">În câmpul „Nume” din panoul din dreapta, redenumiți sursa de date din **Interogare** în **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="501a7-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="501a7-124">**Salvați** sursa de date.</span><span class="sxs-lookup"><span data-stu-id="501a7-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="501a7-125">Ingerați date de cumpărare online</span><span class="sxs-lookup"><span data-stu-id="501a7-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="501a7-126">Adăugați un alt set de date la aceeași sursă de date **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="501a7-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="501a7-127">Alegeți din nou conectorul **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="501a7-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="501a7-128">Introduceți adresa URL pentru datele de **Achiziții online** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="501a7-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="501a7-129">În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.</span><span class="sxs-lookup"><span data-stu-id="501a7-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="501a7-130">Actualizați tipul de date pentru coloanele enumerate mai jos:</span><span class="sxs-lookup"><span data-stu-id="501a7-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="501a7-131">**PurchasedOn**: Dată/Oră</span><span class="sxs-lookup"><span data-stu-id="501a7-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="501a7-132">**TotalPrice**: Monedă</span><span class="sxs-lookup"><span data-stu-id="501a7-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="501a7-133">În câmpul **Nume** din panoul lateral, redenumiți sursa de date din **Interogare** în **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="501a7-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="501a7-134">**Salvați** sursa de date.</span><span class="sxs-lookup"><span data-stu-id="501a7-134">**Save** the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="501a7-135">Ingerați datele clienților din schema de loialitate</span><span class="sxs-lookup"><span data-stu-id="501a7-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="501a7-136">Creați o sursă de date numită **LoyaltyScheme**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="501a7-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="501a7-137">Introduceți adresa de URL pentru contactele de comerț electronic https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="501a7-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="501a7-138">În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.</span><span class="sxs-lookup"><span data-stu-id="501a7-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="501a7-139">Actualizați tipul de date pentru coloanele enumerate mai jos:</span><span class="sxs-lookup"><span data-stu-id="501a7-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="501a7-140">**DateOfBirth**: Dată</span><span class="sxs-lookup"><span data-stu-id="501a7-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="501a7-141">**RewardsPoints**: Număr întreg</span><span class="sxs-lookup"><span data-stu-id="501a7-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="501a7-142">**CreatedOn**: Dată/Oră</span><span class="sxs-lookup"><span data-stu-id="501a7-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="501a7-143">În câmpul **Nume** din panoul din dreapta, redenumiți sursa de date din **Interogare** în **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="501a7-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="501a7-144">**Salvați** sursa de date.</span><span class="sxs-lookup"><span data-stu-id="501a7-144">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="501a7-145">Sarcina 2 - Unificarea datelor</span><span class="sxs-lookup"><span data-stu-id="501a7-145">Task 2 - Data unification</span></span>

<span data-ttu-id="501a7-146">După ingerarea datelor, începem acum procesul de unificare a datelor pentru a crea un profil de client unificat.</span><span class="sxs-lookup"><span data-stu-id="501a7-146">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="501a7-147">Pentru informații suplimentare, consultați [Unificare date](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="501a7-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="501a7-148">Hartă</span><span class="sxs-lookup"><span data-stu-id="501a7-148">Map</span></span>

1. <span data-ttu-id="501a7-149">După ingerarea datelor, mapați contactele de la datele de comerț electronic și de loialitate la tipuri de date obișnuite.</span><span class="sxs-lookup"><span data-stu-id="501a7-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="501a7-150">Mergeți la **Date** > **Unificare** > **Mapare**.</span><span class="sxs-lookup"><span data-stu-id="501a7-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="501a7-151">Selectați entitățile care reprezintă profilul clientului - **eCommerceContacts** și **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="501a7-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![unificați sursele de date privind comerțul electronic și loialitatea.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="501a7-153">Selectați **ContactId** ca cheie primară pentru **eCommerceContacts** și **LoyaltyID** ca cheie primară pentru **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="501a7-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Unificați LoyaltyId ca cheie principală.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="501a7-155">Corespondență</span><span class="sxs-lookup"><span data-stu-id="501a7-155">Match</span></span>

1. <span data-ttu-id="501a7-156">Accesați fila **Potrivire** și selectați **Setare ordine**.</span><span class="sxs-lookup"><span data-stu-id="501a7-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="501a7-157">În lista derulantă **Primar**, alegeți **eCommerceContacts: eCommerce** ca sursă principală și include toate înregistrările.</span><span class="sxs-lookup"><span data-stu-id="501a7-157">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="501a7-158">În lista derulantă **Entitate 2**, alegeți **loyCustomers: LoyaltyScheme** și include toate înregistrările.</span><span class="sxs-lookup"><span data-stu-id="501a7-158">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Potriviți unificarea de comerț electronic și loialitate.](media/unify-match-order.png)

4. <span data-ttu-id="501a7-160">Selectați **Creare regulă nouă**</span><span class="sxs-lookup"><span data-stu-id="501a7-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="501a7-161">Adăugați prima condiție folosind FullName.</span><span class="sxs-lookup"><span data-stu-id="501a7-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="501a7-162">Pentru eCommerceContacts selectați **FullName** în meniul derulant.</span><span class="sxs-lookup"><span data-stu-id="501a7-162">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="501a7-163">Pentru loyCustomers selectați **FullName** în lista derulantă.</span><span class="sxs-lookup"><span data-stu-id="501a7-163">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="501a7-164">Selectați lista derulantă **Normalizare** și alegeți **Tip (telefon, nume, adresă, ...)**.</span><span class="sxs-lookup"><span data-stu-id="501a7-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="501a7-165">Setați **Nivel de precizie**: **De bază** și **Valoare**: **Mare**.</span><span class="sxs-lookup"><span data-stu-id="501a7-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="501a7-166">Introduceți numele **FullName, Email** pentru noua regulă.</span><span class="sxs-lookup"><span data-stu-id="501a7-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="501a7-167">Adăugați o a doua condiție pentru adresa de e-mail selectând **Adăugați o condiție**</span><span class="sxs-lookup"><span data-stu-id="501a7-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="501a7-168">Pentru entitatea eCommerceContacts, alegeți **E-mail** în meniul derulant.</span><span class="sxs-lookup"><span data-stu-id="501a7-168">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="501a7-169">Pentru entitatea loyCustomers, alegeți **E-mail** în lista derulantă.</span><span class="sxs-lookup"><span data-stu-id="501a7-169">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="501a7-170">Lăsați Normalizarea necompletată.</span><span class="sxs-lookup"><span data-stu-id="501a7-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="501a7-171">Setați **Nivel de precizie**: **De bază** și **Valoare**: **Mare**.</span><span class="sxs-lookup"><span data-stu-id="501a7-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Unificați regula de potrivire pentru nume și e-mail.](media/unify-match-rule.png)

7. <span data-ttu-id="501a7-173">Selectați **Salvare** și **Rulare**.</span><span class="sxs-lookup"><span data-stu-id="501a7-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="501a7-174">Îmbinare</span><span class="sxs-lookup"><span data-stu-id="501a7-174">Merge</span></span>

1. <span data-ttu-id="501a7-175">Accesați fila **Îmbinare**.</span><span class="sxs-lookup"><span data-stu-id="501a7-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="501a7-176">Pe **ContactId** pentru entitatea **loyCustomers**, schimbați numele afișat în **ContactIdLOYALTY** pentru a-l diferenția de celelalte ID-uri ingerate.</span><span class="sxs-lookup"><span data-stu-id="501a7-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![redenumiți contactid din ID-ul de loialitate.](media/unify-merge-contactid.png)

1. <span data-ttu-id="501a7-178">Selectați **Salvați** și **Rulați** pentru a porni procesul de îmbinare.</span><span class="sxs-lookup"><span data-stu-id="501a7-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="501a7-179">Sarcina 3 - Configurați recomandarea produsului predicție</span><span class="sxs-lookup"><span data-stu-id="501a7-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="501a7-180">Odată stabilite profilurile de clienți unificate, putem rula acum predicția de retragere a abonamentelor.</span><span class="sxs-lookup"><span data-stu-id="501a7-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="501a7-181">Accesați **Informații** > **Predicție** alegeți **Recomandarea produsului**.</span><span class="sxs-lookup"><span data-stu-id="501a7-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="501a7-182">Selectați **Începeți**.</span><span class="sxs-lookup"><span data-stu-id="501a7-182">Select **Get started**.</span></span>

1. <span data-ttu-id="501a7-183">Denumiți modelul **Modelul de recomandare pentru produsul OOB predicție** și entitatea de ieșire **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="501a7-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="501a7-184">Definiți trei condiții pentru model:</span><span class="sxs-lookup"><span data-stu-id="501a7-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="501a7-185">**Numărul de produse**: Setați această valoare la **5**.</span><span class="sxs-lookup"><span data-stu-id="501a7-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="501a7-186">Această setare definește câte produse doriți să le recomandați clienților dvs.</span><span class="sxs-lookup"><span data-stu-id="501a7-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="501a7-187">**Se așteaptă repetarea achizițiilor**: Selectați **Da** pentru a indica faptul că doriți să includeți produse în recomandarea pe care clienții dvs. au achiziționat-o anterior.</span><span class="sxs-lookup"><span data-stu-id="501a7-187">**Repeat purchases expected**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="501a7-188">**Fereastră de privire retrospectivă:** Selectați cel puțin **365 de zile**.</span><span class="sxs-lookup"><span data-stu-id="501a7-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="501a7-189">Această setare definește cât de departe va privi modelul înapoi spre activitatea clientului pentru a o utiliza drept intrare pentru recomandările sale.</span><span class="sxs-lookup"><span data-stu-id="501a7-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferințe de model pentru modelul de recomandare produs.":::

1. <span data-ttu-id="501a7-191">Selectați **Date necesare** și selectați **Adăugare date** pentru istoricul achizițiilor.</span><span class="sxs-lookup"><span data-stu-id="501a7-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="501a7-192">Adăugați entitatea **eCommercePurchases : eCommerce** și mapați câmpurile din eCommerce la câmpurile corespunzătoare cerute de model.</span><span class="sxs-lookup"><span data-stu-id="501a7-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="501a7-193">Conectați entitatea **eCommercePurchases : eCommerce** cu **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="501a7-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Conectați entitățile eCommerce.](media/model-purchase-join.png)

1. <span data-ttu-id="501a7-195">Selectați **Următorul** pentru a seta planificarea modelului.</span><span class="sxs-lookup"><span data-stu-id="501a7-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="501a7-196">Modelul trebuie să se antreneze în mod regulat pentru a învăța noi modele atunci când sunt ingerate date noi.</span><span class="sxs-lookup"><span data-stu-id="501a7-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="501a7-197">Pentru acest exemplu, selectați **Lunar**.</span><span class="sxs-lookup"><span data-stu-id="501a7-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="501a7-198">După examinarea tuturor detaliilor, selectați **Salvați și rulați**.</span><span class="sxs-lookup"><span data-stu-id="501a7-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="501a7-199">Sarcina 4 - Examinați rezultatele modelului și explicațiile</span><span class="sxs-lookup"><span data-stu-id="501a7-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="501a7-200">Lăsați modelul să finalizeze pregătirea și notarea datelor.</span><span class="sxs-lookup"><span data-stu-id="501a7-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="501a7-201">Acum puteți revizui explicațiile modelului de recomandare a produsului.</span><span class="sxs-lookup"><span data-stu-id="501a7-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="501a7-202">Pentru mai multe informații, consultați [Examinați starea și rezultatele unei predicții](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="501a7-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="501a7-203">Activitatea 5 - Creați un segment de produse achiziționate</span><span class="sxs-lookup"><span data-stu-id="501a7-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="501a7-204">Rularea modelului de producție creează o nouă entitate pe care o puteți vedea în **Date** > **Entități**.</span><span class="sxs-lookup"><span data-stu-id="501a7-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="501a7-205">Puteți crea un segment nou pe baza entității create de model.</span><span class="sxs-lookup"><span data-stu-id="501a7-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="501a7-206">Mergeți la **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="501a7-206">Go to **Segments**.</span></span> <span data-ttu-id="501a7-207">Selectați **Nou** și alegeți **Creați din** > **Informații**.</span><span class="sxs-lookup"><span data-stu-id="501a7-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Crearea unui segment cu rezultatul modelului.](media/segment-intelligence.png)

1. <span data-ttu-id="501a7-209">Selectați punctul final **OOBProductRecommendationModelPrediction** și definiți segmentul:</span><span class="sxs-lookup"><span data-stu-id="501a7-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="501a7-210">Câmp: ID produs</span><span class="sxs-lookup"><span data-stu-id="501a7-210">Field: ProductID</span></span>
   - <span data-ttu-id="501a7-211">Operator: valoare</span><span class="sxs-lookup"><span data-stu-id="501a7-211">Operator: Value</span></span>
   - <span data-ttu-id="501a7-212">Valoare: selectați primele trei ID-uri de produs</span><span class="sxs-lookup"><span data-stu-id="501a7-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Creați un segment din rezultatele modelului.":::

<span data-ttu-id="501a7-214">Acum aveți un segment actualizat dinamic, care identifică clienții care sunt mai dispuși să achiziționeze cele mai recomandate trei produse</span><span class="sxs-lookup"><span data-stu-id="501a7-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="501a7-215">Pentru mai multe informații, consultați [Creați și gestionați segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="501a7-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
