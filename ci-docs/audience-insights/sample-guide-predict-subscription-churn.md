---
title: Ghid eșantion de predicție a retragerii abonamentelor
description: Utilizați acest exemplu de ghid pentru a încerca modelul preinstalat de predicție a retragerii abonamentelor.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2537cfb5dde0d1ce1af16f585f0bf91d15ea1870
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653995"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="674d1-103">Ghid eșantion de predicție a retragerii abonamentelor (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="674d1-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="674d1-104">Vă vom explica un exemplu complet de predicție a retragerii de abonamente folosind datele eșantion furnizate mai jos.</span><span class="sxs-lookup"><span data-stu-id="674d1-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="674d1-105">Scenariu</span><span class="sxs-lookup"><span data-stu-id="674d1-105">Scenario</span></span>

<span data-ttu-id="674d1-106">Contoso este o companie care produce cafea și aparate de cafea de înaltă calitate, pe care le vinde prin intermediul site-ului web Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="674d1-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="674d1-107">Recent, au început o afacere cu abonamente pentru ca clienții lor să poată obține cafea în mod regulat.</span><span class="sxs-lookup"><span data-stu-id="674d1-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="674d1-108">Obiectivul lor este să înțeleagă care clienți abonați ar putea anula abonamentul în următoarele câteva luni.</span><span class="sxs-lookup"><span data-stu-id="674d1-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="674d1-109">Știind care dintre clienții lor este **susceptibil să se retragă**, îi poate ajuta să economisească eforturile de marketing concentrându-se pe păstrarea lor.</span><span class="sxs-lookup"><span data-stu-id="674d1-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="674d1-110">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="674d1-110">Prerequisites</span></span>

- <span data-ttu-id="674d1-111">Cel puțin [Permisiuni de contributor](permissions.md) în Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="674d1-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="674d1-112">Vă recomandăm să implementați pașii următori [într-un mediu nou](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="674d1-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="674d1-113">Sarcina 1 - Ingerare date</span><span class="sxs-lookup"><span data-stu-id="674d1-113">Task 1 - Ingest Data</span></span>

<span data-ttu-id="674d1-114">Examinați articolele [despre ingestia de date](data-sources.md) și în mod specific [importul surselor de date utilizând conectori Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="674d1-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="674d1-115">Următoarele informații presupun că v-ați familiarizat cu ingerarea datelor în general.</span><span class="sxs-lookup"><span data-stu-id="674d1-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="674d1-116">Ingerarea datelor clienților de pe platforma de comerț electronic</span><span class="sxs-lookup"><span data-stu-id="674d1-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="674d1-117">Creați un sursă de date numită **eCommerce**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="674d1-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="674d1-118">Introduceți adresa de URL pentru contactele de comerț electronic https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="674d1-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="674d1-119">În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.</span><span class="sxs-lookup"><span data-stu-id="674d1-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="674d1-120">Actualizați tipul de date pentru coloanele enumerate mai jos:</span><span class="sxs-lookup"><span data-stu-id="674d1-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="674d1-121">**DateOfBirth**: Dată</span><span class="sxs-lookup"><span data-stu-id="674d1-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="674d1-122">**CreatedOn**: Dată/Oră/Zonă</span><span class="sxs-lookup"><span data-stu-id="674d1-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="674d1-123">![Transformați data nașterii în dată](media/ecommerce-dob-date.PNG "transformare data nașterii în dată")</span><span class="sxs-lookup"><span data-stu-id="674d1-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="674d1-124">În câmpul „Nume” din panoul din dreapta, redenumiți sursa de date din **Interogare** în **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="674d1-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="674d1-125">Salvați sursa de date.</span><span class="sxs-lookup"><span data-stu-id="674d1-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="674d1-126">Ingerați datele clienților din schema de loialitate</span><span class="sxs-lookup"><span data-stu-id="674d1-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="674d1-127">Creați o sursă de date numită **LoyaltyScheme**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="674d1-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="674d1-128">Introduceți adresa de URL pentru contactele de comerț electronic https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="674d1-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="674d1-129">În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.</span><span class="sxs-lookup"><span data-stu-id="674d1-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="674d1-130">Actualizați tipul de date pentru coloanele enumerate mai jos:</span><span class="sxs-lookup"><span data-stu-id="674d1-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="674d1-131">**DateOfBirth**: Dată</span><span class="sxs-lookup"><span data-stu-id="674d1-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="674d1-132">**RewardsPoints**: Număr întreg</span><span class="sxs-lookup"><span data-stu-id="674d1-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="674d1-133">**CreatedOn**: Dată/Oră</span><span class="sxs-lookup"><span data-stu-id="674d1-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="674d1-134">În câmpul „Nume” din panoul din dreapta, redenumiți sursa de date din **Interogare** în **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="674d1-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="674d1-135">Salvați sursa de date.</span><span class="sxs-lookup"><span data-stu-id="674d1-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="674d1-136">Ingerare informații abonamente</span><span class="sxs-lookup"><span data-stu-id="674d1-136">Ingest subscription information</span></span>

1. <span data-ttu-id="674d1-137">Creați o sursă de date numită **SubscriptionHistory**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="674d1-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="674d1-138">Introduceți adresa de URL pentru contactele de comerț electronic https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="674d1-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="674d1-139">În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.</span><span class="sxs-lookup"><span data-stu-id="674d1-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="674d1-140">Actualizați tipul de date pentru coloanele enumerate mai jos:</span><span class="sxs-lookup"><span data-stu-id="674d1-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="674d1-141">**SubscriptioID**: Număr întreg</span><span class="sxs-lookup"><span data-stu-id="674d1-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="674d1-142">**SubscriptionAmount**: Monedă</span><span class="sxs-lookup"><span data-stu-id="674d1-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="674d1-143">**SubscriptionEndDate**: Dată/Oră</span><span class="sxs-lookup"><span data-stu-id="674d1-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="674d1-144">**SubscriptionStartDate**: Dată/Oră</span><span class="sxs-lookup"><span data-stu-id="674d1-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="674d1-145">**TransactionDate**: Dată/Oră</span><span class="sxs-lookup"><span data-stu-id="674d1-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="674d1-146">**IsRecurring**: Adevărat/Fals</span><span class="sxs-lookup"><span data-stu-id="674d1-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="674d1-147">**Is_auto_renew**: Adevărat/Fals</span><span class="sxs-lookup"><span data-stu-id="674d1-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="674d1-148">**RecurringFrequencyInMonths**: Număr întreg</span><span class="sxs-lookup"><span data-stu-id="674d1-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="674d1-149">În câmpul „Nume” din panoul din dreapta, redenumiți sursa de date din **Interogare** în **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="674d1-149">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="674d1-150">Salvați sursa de date.</span><span class="sxs-lookup"><span data-stu-id="674d1-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="674d1-151">Ingerați datele clienților din recenziile site-ului web</span><span class="sxs-lookup"><span data-stu-id="674d1-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="674d1-152">Creați o sursă de date numită **Website**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="674d1-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="674d1-153">Introduceți adresa de URL pentru contactele de comerț electronic https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="674d1-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="674d1-154">În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.</span><span class="sxs-lookup"><span data-stu-id="674d1-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="674d1-155">Actualizați tipul de date pentru coloanele enumerate mai jos:</span><span class="sxs-lookup"><span data-stu-id="674d1-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="674d1-156">**ReviewRating**: Număr întreg</span><span class="sxs-lookup"><span data-stu-id="674d1-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="674d1-157">**ReviewDate**: Dată</span><span class="sxs-lookup"><span data-stu-id="674d1-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="674d1-158">În câmpul „Nume” din panoul din dreapta, redenumiți sursa de date din **Interogare** în **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="674d1-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="674d1-159">Sarcina 2 - Unificarea datelor</span><span class="sxs-lookup"><span data-stu-id="674d1-159">Task 2 - Data unification</span></span>

<span data-ttu-id="674d1-160">După ingerarea datelor, începem acum procesul de **Mapare, potrivire, îmbinare** pentru a crea un profil de client unificat.</span><span class="sxs-lookup"><span data-stu-id="674d1-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="674d1-161">Pentru informații suplimentare, consultați [Unificare date](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="674d1-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="674d1-162">Hartă</span><span class="sxs-lookup"><span data-stu-id="674d1-162">Map</span></span>

1. <span data-ttu-id="674d1-163">După ingerarea datelor, mapați contactele de la datele de comerț electronic și de loialitate la tipuri de date obișnuite.</span><span class="sxs-lookup"><span data-stu-id="674d1-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="674d1-164">Mergeți la **Date** > **Unificare** > **Mapare**.</span><span class="sxs-lookup"><span data-stu-id="674d1-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="674d1-165">Selectați entitățile care reprezintă profilul clientului - **eCommerceContacts** și **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="674d1-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="unificați sursele de date privind comerțul electronic și loialitatea.":::

1. <span data-ttu-id="674d1-167">Selectați **ContactId** ca cheie primară pentru **eCommerceContacts** și **LoyaltyID** ca cheie primară pentru **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="674d1-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unificați LoyaltyId ca cheie principală.":::

### <a name="match"></a><span data-ttu-id="674d1-169">Corespondență</span><span class="sxs-lookup"><span data-stu-id="674d1-169">Match</span></span>

1. <span data-ttu-id="674d1-170">Accesați fila **Potrivire** și selectați **Setare ordine**.</span><span class="sxs-lookup"><span data-stu-id="674d1-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="674d1-171">În lista derulantă **Primar**, alegeți **eCommerceContacts: eCommerce** ca sursă principală și includeți toate înregistrările.</span><span class="sxs-lookup"><span data-stu-id="674d1-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="674d1-172">În lista derulantă **Entitate 2**, alegeți **loyCustomers: LoyaltyScheme** și includeți toate înregistrările.</span><span class="sxs-lookup"><span data-stu-id="674d1-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Potriviți unificarea de comerț electronic și loialitate.":::

1. <span data-ttu-id="674d1-174">Selectați **Creare regulă nouă**</span><span class="sxs-lookup"><span data-stu-id="674d1-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="674d1-175">Adăugați prima condiție folosind FullName.</span><span class="sxs-lookup"><span data-stu-id="674d1-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="674d1-176">Pentru eCommerceContacts selectați **FullName** din meniul derulant.</span><span class="sxs-lookup"><span data-stu-id="674d1-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="674d1-177">Pentru loyCustomers selectați **FullName** din meniul derulant.</span><span class="sxs-lookup"><span data-stu-id="674d1-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="674d1-178">Selectați lista derulantă **Normalizare** și alegeți **Tip (telefon, nume, adresă, ...)**.</span><span class="sxs-lookup"><span data-stu-id="674d1-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="674d1-179">Setați **Nivel de precizie**: **De bază** și **Valoare**: **Mare**.</span><span class="sxs-lookup"><span data-stu-id="674d1-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="674d1-180">Introduceți numele **FullName, Email** pentru noua regulă.</span><span class="sxs-lookup"><span data-stu-id="674d1-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="674d1-181">Adăugați o a doua condiție pentru adresa de e-mail selectând **Adăugați o condiție**</span><span class="sxs-lookup"><span data-stu-id="674d1-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="674d1-182">Pentru entitatea eCommerceContacts, alegeți **E-mail** din meniul derulant.</span><span class="sxs-lookup"><span data-stu-id="674d1-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="674d1-183">Pentru entitatea loyCustomers, alegeți **E-mail** din meniul derulant.</span><span class="sxs-lookup"><span data-stu-id="674d1-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="674d1-184">Lăsați Normalizarea necompletată.</span><span class="sxs-lookup"><span data-stu-id="674d1-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="674d1-185">Setați **Nivel de precizie**: **De bază** și **Valoare**: **Mare**.</span><span class="sxs-lookup"><span data-stu-id="674d1-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Unificați regula de potrivire pentru nume și e-mail.":::

7. <span data-ttu-id="674d1-187">Selectați **Salvare** și **Rulare**.</span><span class="sxs-lookup"><span data-stu-id="674d1-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="674d1-188">Îmbinare</span><span class="sxs-lookup"><span data-stu-id="674d1-188">Merge</span></span>

1. <span data-ttu-id="674d1-189">Accesați fila **Îmbinare**.</span><span class="sxs-lookup"><span data-stu-id="674d1-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="674d1-190">Pe **ContactId** pentru entitatea **loyCustomers**, schimbați numele afișat în **ContactIdLOYALTY** pentru a-l diferenția de celelalte ID-uri ingerate.</span><span class="sxs-lookup"><span data-stu-id="674d1-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="redenumiți contactid din ID-ul de loialitate.":::

1. <span data-ttu-id="674d1-192">Selectați **Salvați** și **Rulați** pentru a porni procesul de îmbinare.</span><span class="sxs-lookup"><span data-stu-id="674d1-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="674d1-193">Sarcina 3 - Configurați predicția de retragere a abonamentelor</span><span class="sxs-lookup"><span data-stu-id="674d1-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="674d1-194">Odată stabilite profilurile de clienți unificate, putem rula acum predicția de retragere a abonamentelor.</span><span class="sxs-lookup"><span data-stu-id="674d1-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="674d1-195">Pentru pași detaliați, consultați articolul [Predicția retragerii abonamentelor (previzualizare)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="674d1-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="674d1-196">Mergeți la **Informații** > **Descoperiți** și selectați pentru a utiliza **Modelul de retragere a clienților**.</span><span class="sxs-lookup"><span data-stu-id="674d1-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="674d1-197">Selectați opțiunea **Abonament** și selectați **Începeți**.</span><span class="sxs-lookup"><span data-stu-id="674d1-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="674d1-198">Denumiți modelul **OOB Subscription Churn Prediction** și entitatea de ieșire **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="674d1-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="674d1-199">Definiți două condiții pentru modelul de retragere:</span><span class="sxs-lookup"><span data-stu-id="674d1-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="674d1-200">**Zile de la terminarea abonamentului**: **cel puțin 60** de zile.</span><span class="sxs-lookup"><span data-stu-id="674d1-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="674d1-201">Dacă un client nu își reînnoiește abonamentul în această perioadă după încheierea abonamentului, atunci este considerat retras.</span><span class="sxs-lookup"><span data-stu-id="674d1-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="674d1-202">**Definiție retragere**: **cel puțin 93** de zile.</span><span class="sxs-lookup"><span data-stu-id="674d1-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="674d1-203">Durata pentru care modelul prezice ce clienți s-ar putea retrage.</span><span class="sxs-lookup"><span data-stu-id="674d1-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="674d1-204">Cu cât priviți mai departe în viitor, cu atât rezultatele sunt mai puțin precise.</span><span class="sxs-lookup"><span data-stu-id="674d1-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Selectați pârghiile model Fereastră de predicție și Definiție retragere.":::

1. <span data-ttu-id="674d1-206">Selectați **Adăugare date necesare** și selectați **Adăugare date** pentru istoricul abonamentelor.</span><span class="sxs-lookup"><span data-stu-id="674d1-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="674d1-207">Adăugați entitatea **Subscription : SubscriptionHistory** și mapați câmpurile din eCommerce la câmpurile corespunzătoare cerute de model.</span><span class="sxs-lookup"><span data-stu-id="674d1-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="674d1-208">Asociați entitatea **Subscription : SubscriptionHistory** cu **eCommerceContacts: eCommerce**, denumiți relația **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="674d1-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Conectați entitățile eCommerce.":::

1. <span data-ttu-id="674d1-210">Sub Activități clienți, adăugați entitatea **webReviews : Website** și mapați câmpurile din webReviews la câmpurile corespunzătoare cerute de model.</span><span class="sxs-lookup"><span data-stu-id="674d1-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="674d1-211">Cheie primară: ReviewId</span><span class="sxs-lookup"><span data-stu-id="674d1-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="674d1-212">Marcă de timp: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="674d1-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="674d1-213">Eveniment: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="674d1-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="674d1-214">Configurați o activitate pentru recenziile site-urilor web.</span><span class="sxs-lookup"><span data-stu-id="674d1-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="674d1-215">Selectați activitatea **Revizuire** și asociați entitatea **webReviews : Website** cu **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="674d1-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="674d1-216">Selectați **Următorul** pentru a seta planificarea modelului.</span><span class="sxs-lookup"><span data-stu-id="674d1-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="674d1-217">Modelul trebuie să se antreneze în mod regulat pentru a învăța noi modele atunci când sunt ingerate date noi.</span><span class="sxs-lookup"><span data-stu-id="674d1-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="674d1-218">Pentru acest exemplu, selectați **Lunar**.</span><span class="sxs-lookup"><span data-stu-id="674d1-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="674d1-219">După examinarea tuturor detaliilor, selectați **Salvați și rulați**.</span><span class="sxs-lookup"><span data-stu-id="674d1-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="674d1-220">Sarcina 4 - Examinați rezultatele modelului și explicațiile</span><span class="sxs-lookup"><span data-stu-id="674d1-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="674d1-221">Lăsați modelul să finalizeze pregătirea și notarea datelor.</span><span class="sxs-lookup"><span data-stu-id="674d1-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="674d1-222">Acum puteți revizui explicațiile modelului de retragere a abonamentelor.</span><span class="sxs-lookup"><span data-stu-id="674d1-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="674d1-223">Pentru mai multe informații, consultați [Examinați starea și rezultatele unei predicții](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="674d1-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="674d1-224">Sarcina 5 - Creați un segment de clienți cu risc de retragere ridicat</span><span class="sxs-lookup"><span data-stu-id="674d1-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="674d1-225">Rularea modelului de producție creează o nouă entitate pe care o puteți vedea în **Date** > **Entități**.</span><span class="sxs-lookup"><span data-stu-id="674d1-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="674d1-226">Puteți crea un segment nou pe baza entității create de model.</span><span class="sxs-lookup"><span data-stu-id="674d1-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="674d1-227">Mergeți la **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="674d1-227">Go to **Segments**.</span></span> <span data-ttu-id="674d1-228">Selectați **Nou** și alegeți **Creați din** > **Informații**.</span><span class="sxs-lookup"><span data-stu-id="674d1-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Crearea unui segment cu rezultatul modelului.":::

1. <span data-ttu-id="674d1-230">Selectați punctul final **OOBSubscriptionChurnPrediction** și definiți segmentul:</span><span class="sxs-lookup"><span data-stu-id="674d1-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="674d1-231">Câmp: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="674d1-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="674d1-232">Operator: mai mare decât</span><span class="sxs-lookup"><span data-stu-id="674d1-232">Operator: greater than</span></span>
   - <span data-ttu-id="674d1-233">Valoare: 0,6</span><span class="sxs-lookup"><span data-stu-id="674d1-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configurați un segment de retragere a abonamentului.":::

<span data-ttu-id="674d1-235">Acum aveți un segment actualizat dinamic, care identifică clienții cu risc ridicat de retragere pentru această activitate de abonamente.</span><span class="sxs-lookup"><span data-stu-id="674d1-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="674d1-236">Pentru mai multe informații, consultați [Creați și gestionați segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="674d1-236">For more information, see [Create and manage segments](segments.md).</span></span>
