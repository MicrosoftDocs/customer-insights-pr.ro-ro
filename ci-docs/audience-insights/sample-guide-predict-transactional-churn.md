---
title: Ghid eșantion de predicție a retragerii tranzacționale
description: Utilizați acest exemplu de ghid pentru a încerca modelul preinstalat de predicție a retragerii tranzacționale.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 055708ed3f9f468cad83ecf976a460814bf05199
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643608"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="4f6b1-103">Ghid eșantion de predicție a retragerii tranzacționale (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="4f6b1-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="4f6b1-104">Acest ghid vă va explica un exemplu complet de predicție a retragerii tranzacționale în Customer Insights folosind datele furnizate mai jos.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="4f6b1-105">Toate datele utilizate în acest ghid nu sunt date reale ale clienților și fac parte din setul de date Contoso găsit în mediul *Demo* în cadrul abonamentului dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="4f6b1-106">Scenariu</span><span class="sxs-lookup"><span data-stu-id="4f6b1-106">Scenario</span></span>

<span data-ttu-id="4f6b1-107">Contoso este o companie care produce cafea și aparate de cafea de înaltă calitate, pe care le vinde prin intermediul site-ului web Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="4f6b1-108">Scopul lor este să știe care dintre clienții care le cumpără de obicei produsele nu vor mai fi clienți activi în următoarele 60 de zile.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="4f6b1-109">Știind care dintre clienții lor este **susceptibil să se retragă**, îi poate ajuta să economisească eforturile de marketing concentrându-se pe păstrarea lor.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4f6b1-110">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="4f6b1-110">Prerequisites</span></span>

- <span data-ttu-id="4f6b1-111">Cel puțin [Permisiuni de contributor](permissions.md) în Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="4f6b1-112">Vă recomandăm să implementați pașii următori [într-un mediu nou](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="4f6b1-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="4f6b1-113">Sarcina 1 - Ingerare date</span><span class="sxs-lookup"><span data-stu-id="4f6b1-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="4f6b1-114">Examinați articolele [despre ingestia de date](data-sources.md) și în mod specific [importul surselor de date utilizând conectori Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="4f6b1-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="4f6b1-115">Următoarele informații presupun că v-ați familiarizat cu ingerarea datelor în general.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="4f6b1-116">Ingerarea datelor clienților de pe platforma de comerț electronic</span><span class="sxs-lookup"><span data-stu-id="4f6b1-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="4f6b1-117">Creați un sursă de date numită **eCommerce**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="4f6b1-118">Introduceți adresa de URL pentru contactele de comerț electronic https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="4f6b1-119">În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="4f6b1-120">Actualizați tipul de date pentru coloanele enumerate mai jos:</span><span class="sxs-lookup"><span data-stu-id="4f6b1-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="4f6b1-121">**DateOfBirth**: Dată</span><span class="sxs-lookup"><span data-stu-id="4f6b1-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="4f6b1-122">**CreatedOn**: Dată/Oră/Zonă</span><span class="sxs-lookup"><span data-stu-id="4f6b1-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="4f6b1-123">![Transformați data nașterii în dată](media/ecommerce-dob-date.PNG "transformare data nașterii în dată")</span><span class="sxs-lookup"><span data-stu-id="4f6b1-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="4f6b1-124">În câmpul „Nume” din panoul din dreapta, redenumiți sursa de date din **Interogare** în **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="4f6b1-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="4f6b1-125">Salvați sursa de date.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="4f6b1-126">Ingerați date de cumpărare online</span><span class="sxs-lookup"><span data-stu-id="4f6b1-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="4f6b1-127">Adăugați un alt set de date la aceeași sursă de date **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="4f6b1-128">Alegeți din nou conectorul **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="4f6b1-129">Introduceți adresa URL pentru datele de **Achiziții online** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="4f6b1-130">În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="4f6b1-131">Actualizați tipul de date pentru coloanele enumerate mai jos:</span><span class="sxs-lookup"><span data-stu-id="4f6b1-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="4f6b1-132">**PurchasedOn**: Dată/Oră</span><span class="sxs-lookup"><span data-stu-id="4f6b1-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="4f6b1-133">**TotalPrice**: Monedă</span><span class="sxs-lookup"><span data-stu-id="4f6b1-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="4f6b1-134">În câmpul „Nume” din panoul din dreapta, redenumiți sursa de date din **Interogare** în **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="4f6b1-135">Salvați sursa de date.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="4f6b1-136">Ingerați datele clienților din schema de loialitate</span><span class="sxs-lookup"><span data-stu-id="4f6b1-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="4f6b1-137">Creați o sursă de date numită **LoyaltyScheme**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="4f6b1-138">Introduceți adresa de URL pentru contactele de comerț electronic https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="4f6b1-139">În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="4f6b1-140">Actualizați tipul de date pentru coloanele enumerate mai jos:</span><span class="sxs-lookup"><span data-stu-id="4f6b1-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="4f6b1-141">**DateOfBirth**: Dată</span><span class="sxs-lookup"><span data-stu-id="4f6b1-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="4f6b1-142">**RewardsPoints**: Număr întreg</span><span class="sxs-lookup"><span data-stu-id="4f6b1-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="4f6b1-143">**CreatedOn**: Dată/Oră</span><span class="sxs-lookup"><span data-stu-id="4f6b1-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="4f6b1-144">În câmpul „Nume” din panoul din dreapta, redenumiți sursa de date din **Interogare** în **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-144">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="4f6b1-145">Salvați sursa de date.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="4f6b1-146">Sarcina 2 - Unificarea datelor</span><span class="sxs-lookup"><span data-stu-id="4f6b1-146">Task 2 - Data unification</span></span>

<span data-ttu-id="4f6b1-147">După ingerarea datelor, începem acum procesul de **Mapare, potrivire, îmbinare** pentru a crea un profil de client unificat.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="4f6b1-148">Pentru informații suplimentare, consultați [Unificare date](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="4f6b1-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="4f6b1-149">Hartă</span><span class="sxs-lookup"><span data-stu-id="4f6b1-149">Map</span></span>

1. <span data-ttu-id="4f6b1-150">După ingerarea datelor, mapați contactele de la datele de comerț electronic și de loialitate la tipuri de date obișnuite.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="4f6b1-151">Mergeți la **Date** > **Unificare** > **Mapare**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="4f6b1-152">Selectați entitățile care reprezintă profilul clientului - **eCommerceContacts** și **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="unificați sursele de date privind comerțul electronic și loialitatea.":::

1. <span data-ttu-id="4f6b1-154">Selectați **ContactId** ca cheie primară pentru **eCommerceContacts** și **LoyaltyID** ca cheie primară pentru **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unificați LoyaltyId ca cheie principală.":::

### <a name="match"></a><span data-ttu-id="4f6b1-156">Corespondență</span><span class="sxs-lookup"><span data-stu-id="4f6b1-156">Match</span></span>

1. <span data-ttu-id="4f6b1-157">Accesați fila **Potrivire** și selectați **Setare ordine**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="4f6b1-158">În lista derulantă **Primar**, alegeți **eCommerceContacts: eCommerce** ca sursă principală și includeți toate înregistrările.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="4f6b1-159">În lista derulantă **Entitate 2**, alegeți **loyCustomers: LoyaltyScheme** și includeți toate înregistrările.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Potriviți unificarea de comerț electronic și loialitate.":::

1. <span data-ttu-id="4f6b1-161">Selectați **Creare regulă nouă**</span><span class="sxs-lookup"><span data-stu-id="4f6b1-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="4f6b1-162">Adăugați prima condiție folosind FullName.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="4f6b1-163">Pentru eCommerceContacts selectați **FullName** din meniul derulant.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="4f6b1-164">Pentru loyCustomers selectați **FullName** din meniul derulant.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="4f6b1-165">Selectați lista derulantă **Normalizare** și alegeți **Tip (telefon, nume, adresă, ...)**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="4f6b1-166">Setați **Nivel de precizie**: **De bază** și **Valoare**: **Mare**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="4f6b1-167">Introduceți numele **FullName, Email** pentru noua regulă.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="4f6b1-168">Adăugați o a doua condiție pentru adresa de e-mail selectând **Adăugați o condiție**</span><span class="sxs-lookup"><span data-stu-id="4f6b1-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="4f6b1-169">Pentru entitatea eCommerceContacts, alegeți **E-mail** din meniul derulant.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="4f6b1-170">Pentru entitatea loyCustomers, alegeți **E-mail** din meniul derulant.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="4f6b1-171">Lăsați Normalizarea necompletată.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="4f6b1-172">Setați **Nivel de precizie**: **De bază** și **Valoare**: **Mare**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Unificați regula de potrivire pentru nume și e-mail.":::

7. <span data-ttu-id="4f6b1-174">Selectați **Salvare** și **Rulare**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="4f6b1-175">Îmbinare</span><span class="sxs-lookup"><span data-stu-id="4f6b1-175">Merge</span></span>

1. <span data-ttu-id="4f6b1-176">Accesați fila **Îmbinare**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="4f6b1-177">Pe **ContactId** pentru entitatea **loyCustomers**, schimbați numele afișat în **ContactIdLOYALTY** pentru a-l diferenția de celelalte ID-uri ingerate.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="redenumiți contactid din ID-ul de loialitate.":::

1. <span data-ttu-id="4f6b1-179">Selectați **Salvați** și **Rulați** pentru a porni procesul de îmbinare.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="4f6b1-180">Sarcina 3 - Configurați predicția de retragere tranzacțională</span><span class="sxs-lookup"><span data-stu-id="4f6b1-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="4f6b1-181">Odată stabilite profilurile de clienți unificate, putem rula acum predicția de retragere a abonamentelor.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="4f6b1-182">Pentru pași detaliați, consultați articolul [Predicția retragerii abonamentelor (previzualizare)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="4f6b1-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="4f6b1-183">Mergeți la **Informații** > **Descoperiți** și selectați pentru a utiliza **Modelul de retragere a clienților**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="4f6b1-184">Selectați opțiunea **Tranzacțional** și selectați **Începeți**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="4f6b1-185">Denumiți modelul **OOB eCommerce Transaction Churn Prediction** și entitatea de ieșire **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="4f6b1-186">Definiți două condiții pentru modelul de retragere:</span><span class="sxs-lookup"><span data-stu-id="4f6b1-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="4f6b1-187">**Fereastra de predicție**: **cel puțin 60** de zile.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="4f6b1-188">Această setare definește cât de departe în viitor vrem să prezicem retragerea clienților.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="4f6b1-189">**Definiție retragere**: **cel puțin 60** de zile.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="4f6b1-190">Durata fără cumpărare, după care un client este considerat retras.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Selectați pârghiile model Fereastră de predicție și Definiție retragere.":::

1. <span data-ttu-id="4f6b1-192">Selectați **Istoricul achizițiilor (obligatoriu)** și selectați **Adăugare date** pentru istoricul abonamentelor.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-192">Select **Purchase History (required)** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="4f6b1-193">Adăugați entitatea **eCommercePurchases : eCommerce** și mapați câmpurile din eCommerce la câmpurile corespunzătoare cerute de model.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="4f6b1-194">Conectați entitatea **eCommercePurchases : eCommerce** cu **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Conectați entitățile eCommerce.":::

1. <span data-ttu-id="4f6b1-196">Selectați **Următorul** pentru a seta planificarea modelului.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="4f6b1-197">Modelul trebuie să se antreneze în mod regulat pentru a învăța noi modele atunci când sunt ingerate date noi.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="4f6b1-198">Pentru acest exemplu, selectați **Lunar**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="4f6b1-199">După examinarea tuturor detaliilor, selectați **Salvați și rulați**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="4f6b1-200">Sarcina 4 - Examinați rezultatele modelului și explicațiile</span><span class="sxs-lookup"><span data-stu-id="4f6b1-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="4f6b1-201">Lăsați modelul să finalizeze pregătirea și notarea datelor.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="4f6b1-202">Acum puteți revizui explicațiile modelului de retragere a abonamentelor.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="4f6b1-203">Pentru mai multe informații, consultați [Examinați starea și rezultatele unei predicții](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="4f6b1-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="4f6b1-204">Sarcina 5 - Creați un segment de clienți cu risc de retragere ridicat</span><span class="sxs-lookup"><span data-stu-id="4f6b1-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="4f6b1-205">Rularea modelului de producție creează o nouă entitate pe care o puteți vedea în **Date** > **Entități**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="4f6b1-206">Puteți crea un segment nou pe baza entității create de model.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="4f6b1-207">Mergeți la **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-207">Go to **Segments**.</span></span> <span data-ttu-id="4f6b1-208">Selectați **Nou** și alegeți **Creați din** > **Informații**.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Crearea unui segment cu rezultatul modelului.":::

1. <span data-ttu-id="4f6b1-210">Selectați punctul final **OOBSubscriptionChurnPrediction** și definiți segmentul:</span><span class="sxs-lookup"><span data-stu-id="4f6b1-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="4f6b1-211">Câmp: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="4f6b1-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="4f6b1-212">Operator: mai mare decât</span><span class="sxs-lookup"><span data-stu-id="4f6b1-212">Operator: greater than</span></span>
   - <span data-ttu-id="4f6b1-213">Valoare: 0,6</span><span class="sxs-lookup"><span data-stu-id="4f6b1-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configurați un segment de retragere a abonamentului.":::

<span data-ttu-id="4f6b1-215">Acum aveți un segment actualizat dinamic, care identifică clienții cu risc ridicat de retragere pentru această activitate de abonamente.</span><span class="sxs-lookup"><span data-stu-id="4f6b1-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="4f6b1-216">Pentru mai multe informații, consultați [Creați și gestionați segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="4f6b1-216">For more information, see [Create and manage segments](segments.md).</span></span>
