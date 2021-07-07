---
title: Ghid eșantion de predicție pentru Valoarea ciclului de viață a clientului
description: Utilizați acest exemplu de ghid pentru a încerca modelul de predicție pentru Valoarea ciclului de viață a clientului.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 19c1fbadb79ba22c0dc11aa7c3b5b2415add70a7
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306364"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="c6647-103">Ghid eșantion de predicție pentru Valoarea ciclului de viață a clientului (CLV)</span><span class="sxs-lookup"><span data-stu-id="c6647-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="c6647-104">Acest ghid vă va explica un exemplu de la un capăt la altul al predicției valorii ciclului de viață al clientului (CLV) în Customer Insights, folosind date eșantion.</span><span class="sxs-lookup"><span data-stu-id="c6647-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="c6647-105">Scenariu</span><span class="sxs-lookup"><span data-stu-id="c6647-105">Scenario</span></span>

<span data-ttu-id="c6647-106">Contoso este o companie care produce cafea și aparate de cafea de înaltă calitate.</span><span class="sxs-lookup"><span data-stu-id="c6647-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="c6647-107">Ei vând produsele prin intermediul site-ului lor de cafea Contoso.</span><span class="sxs-lookup"><span data-stu-id="c6647-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="c6647-108">Compania dorește să înțeleagă valoarea (veniturile) pe care clienții lor o pot genera în următoarele 12 luni.</span><span class="sxs-lookup"><span data-stu-id="c6647-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="c6647-109">Cunoașterea valorii așteptate a clienților lor în următoarele 12 luni îi va ajuta să-și direcționeze eforturile de marketing către clienții cu valoare ridicată.</span><span class="sxs-lookup"><span data-stu-id="c6647-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c6647-110">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="c6647-110">Prerequisites</span></span>

- <span data-ttu-id="c6647-111">Cel puțin [Permisiuni de colaborare](permissions.md) în perspectivele publicului.</span><span class="sxs-lookup"><span data-stu-id="c6647-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="c6647-112">Vă recomandăm să implementați pașii următori [într-un mediu nou](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="c6647-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="c6647-113">Sarcina 1 - Ingerare date</span><span class="sxs-lookup"><span data-stu-id="c6647-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="c6647-114">Examinați articolele [despre ingestia de date](data-sources.md) și [importul surselor de date utilizând conectori Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="c6647-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="c6647-115">Următoarele informații presupun că v-ați familiarizat cu ingerarea datelor în general.</span><span class="sxs-lookup"><span data-stu-id="c6647-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="c6647-116">Ingerarea datelor clienților de pe platforma de comerț electronic</span><span class="sxs-lookup"><span data-stu-id="c6647-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="c6647-117">Creați un sursă de date numită **eCommerce**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="c6647-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c6647-118">Introduceți adresa de URL pentru contactele de comerț electronic [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="c6647-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="c6647-119">În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.</span><span class="sxs-lookup"><span data-stu-id="c6647-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c6647-120">Actualizați tipul de date pentru coloanele enumerate mai jos:</span><span class="sxs-lookup"><span data-stu-id="c6647-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="c6647-121">**DateOfBirth**: Dată</span><span class="sxs-lookup"><span data-stu-id="c6647-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="c6647-122">**CreatedOn**: Dată/Oră/Zonă</span><span class="sxs-lookup"><span data-stu-id="c6647-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformați data nașterii în dată.":::

1. <span data-ttu-id="c6647-124">În câmpul „Nume” din panoul din dreapta, redenumiți sursa de date din **Interogare** în **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="c6647-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="c6647-125">**Salvați** sursa de date.</span><span class="sxs-lookup"><span data-stu-id="c6647-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="c6647-126">Ingerați date de cumpărare online</span><span class="sxs-lookup"><span data-stu-id="c6647-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="c6647-127">Adăugați un alt set de date la aceeași sursă de date **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="c6647-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="c6647-128">Alegeți din nou conectorul **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="c6647-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="c6647-129">Introduceți adresa URL pentru datele de **Achiziții online** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="c6647-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="c6647-130">În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.</span><span class="sxs-lookup"><span data-stu-id="c6647-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c6647-131">Actualizați tipul de date pentru coloanele enumerate mai jos:</span><span class="sxs-lookup"><span data-stu-id="c6647-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="c6647-132">**PurchasedOn**: Dată/Oră</span><span class="sxs-lookup"><span data-stu-id="c6647-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="c6647-133">**TotalPrice**: Monedă</span><span class="sxs-lookup"><span data-stu-id="c6647-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="c6647-134">În câmpul **Nume** din panoul lateral, redenumiți sursa de date din **Interogare** în **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="c6647-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="c6647-135">**Salvați** sursa de date.</span><span class="sxs-lookup"><span data-stu-id="c6647-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="c6647-136">Ingerați datele clienților din schema de loialitate</span><span class="sxs-lookup"><span data-stu-id="c6647-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="c6647-137">Creați o sursă de date numită **LoyaltyScheme**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="c6647-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c6647-138">Introduceți adresa de URL pentru contactele de comerț electronic https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="c6647-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="c6647-139">În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.</span><span class="sxs-lookup"><span data-stu-id="c6647-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c6647-140">Actualizați tipul de date pentru coloanele enumerate mai jos:</span><span class="sxs-lookup"><span data-stu-id="c6647-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="c6647-141">**DateOfBirth**: Dată</span><span class="sxs-lookup"><span data-stu-id="c6647-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="c6647-142">**RewardsPoints**: Număr întreg</span><span class="sxs-lookup"><span data-stu-id="c6647-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="c6647-143">**CreatedOn**: Dată/Oră</span><span class="sxs-lookup"><span data-stu-id="c6647-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="c6647-144">În câmpul **Nume** din panoul din dreapta, redenumiți sursa de date din **Interogare** în **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="c6647-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="c6647-145">**Salvați** sursa de date.</span><span class="sxs-lookup"><span data-stu-id="c6647-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="c6647-146">Ingerați datele clienților din recenziile site-ului web</span><span class="sxs-lookup"><span data-stu-id="c6647-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="c6647-147">Creați o sursă de date numită **Website**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="c6647-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c6647-148">Introduceți adresa de URL pentru contactele de comerț electronic https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="c6647-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="c6647-149">În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.</span><span class="sxs-lookup"><span data-stu-id="c6647-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c6647-150">Actualizați tipul de date pentru coloanele enumerate mai jos:</span><span class="sxs-lookup"><span data-stu-id="c6647-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="c6647-151">**ReviewRating**: Număr decimal</span><span class="sxs-lookup"><span data-stu-id="c6647-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="c6647-152">**ReviewDate**: Dată</span><span class="sxs-lookup"><span data-stu-id="c6647-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="c6647-153">În câmpul „Nume” din panoul din dreapta, redenumiți sursa de date din **Interogare** la **Recenzii**.</span><span class="sxs-lookup"><span data-stu-id="c6647-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="c6647-154">**Salvați** sursa de date.</span><span class="sxs-lookup"><span data-stu-id="c6647-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="c6647-155">Sarcina 2 - Unificarea datelor</span><span class="sxs-lookup"><span data-stu-id="c6647-155">Task 2 - Data unification</span></span>

<span data-ttu-id="c6647-156">După ingerarea datelor, începem acum procesul de unificare a datelor pentru a crea un profil de client unificat.</span><span class="sxs-lookup"><span data-stu-id="c6647-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="c6647-157">Pentru informații suplimentare, consultați [Unificare date](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="c6647-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="c6647-158">Hartă</span><span class="sxs-lookup"><span data-stu-id="c6647-158">Map</span></span>

1. <span data-ttu-id="c6647-159">După ingerarea datelor, mapați contactele de la datele de comerț electronic și de loialitate la tipuri de date obișnuite.</span><span class="sxs-lookup"><span data-stu-id="c6647-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="c6647-160">Mergeți la **Date** > **Unificare** > **Mapare**.</span><span class="sxs-lookup"><span data-stu-id="c6647-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="c6647-161">Selectați entitățile care reprezintă profilul clientului - **eCommerceContacts** și **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="c6647-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="c6647-162">Apoi selectați **Se aplică**.</span><span class="sxs-lookup"><span data-stu-id="c6647-162">Then, select **Apply**.</span></span>

   ![unificați sursele de date privind comerțul electronic și loialitatea.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="c6647-164">Selectați **ContactId** ca cheie primară pentru **eCommerceContacts** și **LoyaltyID** ca cheie primară pentru **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="c6647-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Unificați LoyaltyId ca cheie principală.](media/unify-loyaltyid.png)

1. <span data-ttu-id="c6647-166">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="c6647-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="c6647-167">Corespondență</span><span class="sxs-lookup"><span data-stu-id="c6647-167">Match</span></span>

1. <span data-ttu-id="c6647-168">Accesați fila **Potrivire** și selectați **Setare ordine**.</span><span class="sxs-lookup"><span data-stu-id="c6647-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="c6647-169">În lista derulantă **Primar**, alegeți **eCommerceContacts: eCommerce** ca sursă principală și include toate înregistrările.</span><span class="sxs-lookup"><span data-stu-id="c6647-169">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="c6647-170">În lista derulantă **Entitate 2**, alegeți **loyCustomers: LoyaltyScheme** și include toate înregistrările.</span><span class="sxs-lookup"><span data-stu-id="c6647-170">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Potriviți unificarea de comerț electronic și loialitate.](media/unify-match-order.png)

1. <span data-ttu-id="c6647-172">Selectați **Adăugați regulă**</span><span class="sxs-lookup"><span data-stu-id="c6647-172">Select **Add rule**</span></span>

1. <span data-ttu-id="c6647-173">Adăugați prima condiție folosind FullName.</span><span class="sxs-lookup"><span data-stu-id="c6647-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="c6647-174">Pentru eCommerceContacts selectați **FullName** în meniul derulant.</span><span class="sxs-lookup"><span data-stu-id="c6647-174">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="c6647-175">Pentru loyCustomers selectați **FullName** în lista derulantă.</span><span class="sxs-lookup"><span data-stu-id="c6647-175">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="c6647-176">Selectați lista derulantă **Normalizare** și alegeți **Tip (Telefon, Nume, Adresă, ...)**.</span><span class="sxs-lookup"><span data-stu-id="c6647-176">Select the **Normalize** dropdown and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="c6647-177">Setați **Nivel de precizie**: **De bază** și **Valoare**: **Mare**.</span><span class="sxs-lookup"><span data-stu-id="c6647-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="c6647-178">Introduceți numele **FullName, Email** pentru noua regulă.</span><span class="sxs-lookup"><span data-stu-id="c6647-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="c6647-179">Adăugați o a doua condiție pentru adresa de e-mail selectând **Adăugați o condiție**</span><span class="sxs-lookup"><span data-stu-id="c6647-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="c6647-180">Pentru entitatea eCommerceContacts, alegeți **E-mail** în meniul derulant.</span><span class="sxs-lookup"><span data-stu-id="c6647-180">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="c6647-181">Pentru entitatea loyCustomers, alegeți **E-mail** în lista derulantă.</span><span class="sxs-lookup"><span data-stu-id="c6647-181">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="c6647-182">Lăsați Normalizarea necompletată.</span><span class="sxs-lookup"><span data-stu-id="c6647-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="c6647-183">Setați **Nivel de precizie**: **De bază** și **Valoare**: **Mare**.</span><span class="sxs-lookup"><span data-stu-id="c6647-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Unificați regula de potrivire pentru nume și e-mail.](media/unify-match-rule.png)

1. <span data-ttu-id="c6647-185">Selectați **Terminat**.</span><span class="sxs-lookup"><span data-stu-id="c6647-185">Select **Done**.</span></span>

1. <span data-ttu-id="c6647-186">Selectați **Salvare** și **Rulare**.</span><span class="sxs-lookup"><span data-stu-id="c6647-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="c6647-187">Îmbinare</span><span class="sxs-lookup"><span data-stu-id="c6647-187">Merge</span></span>

1. <span data-ttu-id="c6647-188">Accesați fila **Îmbinare**.</span><span class="sxs-lookup"><span data-stu-id="c6647-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="c6647-189">Pe **ContactId** pentru entitatea **loyCustomers**, schimbați numele afișat în **ContactIdLOYALTY** pentru a-l diferenția de celelalte ID-uri ingerate.</span><span class="sxs-lookup"><span data-stu-id="c6647-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![redenumiți contactid din ID-ul de loialitate.](media/unify-merge-contactid.png)

1. <span data-ttu-id="c6647-191">Selectați **Salvați** și **Executați procese de îmbinare și din aval**.</span><span class="sxs-lookup"><span data-stu-id="c6647-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="c6647-192">Sarcina 3 - Configurați predicția pentru Valoarea ciclului de viață a clientului</span><span class="sxs-lookup"><span data-stu-id="c6647-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="c6647-193">Cu profilurile de clienți unificate, putem acum să rulăm predicția pentru Valoarea ciclului de viață a clientului.</span><span class="sxs-lookup"><span data-stu-id="c6647-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="c6647-194">Pentru pași detaliați, consultați [Valoarea predicției pentru Valoarea ciclului de viață a clientului (previzualizare)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="c6647-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="c6647-195">Accesați **Inteligența**  > **Predicții** și selectați **Modelul pentru Valoarea ciclului de viață al clientului**.</span><span class="sxs-lookup"><span data-stu-id="c6647-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="c6647-196">Parcurgeți informațiile din panoul lateral și selectați **Începeți**.</span><span class="sxs-lookup"><span data-stu-id="c6647-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="c6647-197">Denumiți modelul **Predicție OOB eCommerce CLV** și entitatea de ieșire **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="c6647-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="c6647-198">Definiți preferințele modelului pentru modelul CLV:</span><span class="sxs-lookup"><span data-stu-id="c6647-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="c6647-199">**Predicția perioadei de timp**: **12 luni sau 1 an**.</span><span class="sxs-lookup"><span data-stu-id="c6647-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="c6647-200">Această setare definește cât de departe în viitor se poate prezice ciclul de viață al clientului.</span><span class="sxs-lookup"><span data-stu-id="c6647-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="c6647-201">**Clienți activi**: Specificați ce înseamnă clienții activi pentru afacerea dvs.</span><span class="sxs-lookup"><span data-stu-id="c6647-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="c6647-202">Setați intervalul de timp istoric în care un client trebuie să fi avut cel puțin o tranzacție pentru a fi considerat activ.</span><span class="sxs-lookup"><span data-stu-id="c6647-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="c6647-203">Modelul va prezice CLV numai pentru clienții activi.</span><span class="sxs-lookup"><span data-stu-id="c6647-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="c6647-204">Alegeți între a permite modelului să calculeze perioada de timp pe baza datelor istorice ale tranzacțiilor sau să furnizați un anumit interval de timp.</span><span class="sxs-lookup"><span data-stu-id="c6647-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="c6647-205">În acest exemplu de ghid, noi **lăsăm modelul să calculeze intervalul de cumpărare**, care este opțiunea implicită.</span><span class="sxs-lookup"><span data-stu-id="c6647-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="c6647-206">**Clienți cu valoare ridicată**: Definiți clienții cu valoare ridicată ca o percentilă a clienților cu plată superioară.</span><span class="sxs-lookup"><span data-stu-id="c6647-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="c6647-207">Modelul folosește această intrare pentru a oferi rezultate care se potrivesc definiției dvs. de afaceri a clienților cu valoare ridicată.</span><span class="sxs-lookup"><span data-stu-id="c6647-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="c6647-208">Puteți alege să lăsați modelul să definească clienți de mare valoare.</span><span class="sxs-lookup"><span data-stu-id="c6647-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="c6647-209">Folosește o regulă euristică din care derivă percentila.</span><span class="sxs-lookup"><span data-stu-id="c6647-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="c6647-210">De asemenea, puteți defini clienții cu valoare ridicată ca fiind o percentilă a celor mai buni viitori clienți plătitori.</span><span class="sxs-lookup"><span data-stu-id="c6647-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="c6647-211">În acest exemplu de ghid, definim manual clienții cu valoare ridicată ca **30% din cei mai activi clienți plătitori** și selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="c6647-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Preferințele intră în experiența ghidată pentru modelul CLV.":::

1. <span data-ttu-id="c6647-213">În pasul **Date necesare**, selectați **Adăugați date** pentru a furniza datele din istoricul tranzacțiilor.</span><span class="sxs-lookup"><span data-stu-id="c6647-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="c6647-214">Adăugați entitatea **Achiziții eCommerce: eCommerce** și maparea atributelor necesare modelului:</span><span class="sxs-lookup"><span data-stu-id="c6647-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="c6647-215">ID tranzacție: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="c6647-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="c6647-216">Data tranzacției: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="c6647-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="c6647-217">Valoarea tranzacției: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="c6647-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="c6647-218">ID produs: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="c6647-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="c6647-219">Selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="c6647-219">Select **Next**.</span></span>

1. <span data-ttu-id="c6647-220">Configurați relația dintre entitatea **Achiziții eCommerce: eCommerce** și **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="c6647-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="c6647-221">Pasul **Date suplimentare (opțional)** vă permite să adăugați mai multe date despre activitatea clienților.</span><span class="sxs-lookup"><span data-stu-id="c6647-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="c6647-222">Aceste date vă pot ajuta să obțineți mai multe informații despre interacțiunile clienților cu afacerea dvs., care pot contribui la CLV.</span><span class="sxs-lookup"><span data-stu-id="c6647-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="c6647-223">Adăugarea de interacțiuni cheie cu clienții, cum ar fi jurnalele web, jurnalele serviciu pentru relații cu clienții sau istoricul programului de recompense, poate îmbunătăți precizia predicțiilor.</span><span class="sxs-lookup"><span data-stu-id="c6647-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="c6647-224">Selectați **Adăugați date** pentru a include mai multe date despre activitatea clienților.</span><span class="sxs-lookup"><span data-stu-id="c6647-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="c6647-225">Adăugați entitatea de activitate client și asociați numele câmpurilor acesteia la câmpurile corespunzătoare cerute de model:</span><span class="sxs-lookup"><span data-stu-id="c6647-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="c6647-226">Entitatea de activitate client: Recenzii: Site web</span><span class="sxs-lookup"><span data-stu-id="c6647-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="c6647-227">Cheia principală: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="c6647-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="c6647-228">Marcă de timp: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="c6647-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="c6647-229">Eveniment (numele activității): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="c6647-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="c6647-230">Detalii (suma sau valoarea): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="c6647-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="c6647-231">Selectați **Următorul** și configurați activitatea și relația dintre datele tranzacției și datele clienților:</span><span class="sxs-lookup"><span data-stu-id="c6647-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="c6647-232">Tipul activității: Alegeți activitate existentă</span><span class="sxs-lookup"><span data-stu-id="c6647-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="c6647-233">Eticheta activității: Recenzie</span><span class="sxs-lookup"><span data-stu-id="c6647-233">Activity label: Review</span></span>
   - <span data-ttu-id="c6647-234">Etichetă corespondentă: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="c6647-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="c6647-235">Entitate client: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="c6647-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="c6647-236">Relație: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="c6647-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="c6647-237">Selectați **Următorul** pentru a seta planificarea modelului.</span><span class="sxs-lookup"><span data-stu-id="c6647-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="c6647-238">Modelul trebuie să se antreneze în mod regulat pentru a învăța noi modele atunci când sunt ingerate date noi.</span><span class="sxs-lookup"><span data-stu-id="c6647-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="c6647-239">Pentru acest exemplu, alegeți **Lunar**.</span><span class="sxs-lookup"><span data-stu-id="c6647-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="c6647-240">După examinarea tuturor detaliilor, selectați **Salvați și rulați**.</span><span class="sxs-lookup"><span data-stu-id="c6647-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="c6647-241">Sarcina 4 - Examinați rezultatele modelului și explicațiile</span><span class="sxs-lookup"><span data-stu-id="c6647-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="c6647-242">Lăsați modelul să finalizeze pregătirea și notarea datelor.</span><span class="sxs-lookup"><span data-stu-id="c6647-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="c6647-243">Apoi, puteți consulta rezultatele și explicațiile modelului CLV.</span><span class="sxs-lookup"><span data-stu-id="c6647-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="c6647-244">Pentru mai multe informații, consultați [Examinați starea și rezultatele unei predicții](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="c6647-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="c6647-245">Sarcina 5 - Creați un segment de clienți de mare valoare</span><span class="sxs-lookup"><span data-stu-id="c6647-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="c6647-246">Rularea modelului creează o nouă entitate, care este listată pe **Date** > **Entități**.</span><span class="sxs-lookup"><span data-stu-id="c6647-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="c6647-247">Puteți crea un nou segment de clienți pe baza entității create de model.</span><span class="sxs-lookup"><span data-stu-id="c6647-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="c6647-248">Mergeți la **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="c6647-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="c6647-249">Selectați **Nou** și alegeți **Creați din** > **Informații**.</span><span class="sxs-lookup"><span data-stu-id="c6647-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Crearea unui segment cu rezultatul modelului.](media/segment-intelligence.png)

1. <span data-ttu-id="c6647-251">Selectați entitatea **OOBeCommerceCLVPrediction** și definiți segmentul:</span><span class="sxs-lookup"><span data-stu-id="c6647-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="c6647-252">Câmp: CLVScore</span><span class="sxs-lookup"><span data-stu-id="c6647-252">Field: CLVScore</span></span>
  - <span data-ttu-id="c6647-253">Operator: mai mare decât</span><span class="sxs-lookup"><span data-stu-id="c6647-253">Operator: greater than</span></span>
  - <span data-ttu-id="c6647-254">Valoare: 1500</span><span class="sxs-lookup"><span data-stu-id="c6647-254">Value: 1500</span></span>

1. <span data-ttu-id="c6647-255">Selectați **Revizuiți** și **Salvați** segmentul.</span><span class="sxs-lookup"><span data-stu-id="c6647-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="c6647-256">Acum aveți un segment care identifică clienții despre care se estimează că vor genera mai mult de 1500$ în venituri în următoarele 12 luni.</span><span class="sxs-lookup"><span data-stu-id="c6647-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="c6647-257">Acest segment se actualizează dinamic dacă sunt ingerate mai multe date.</span><span class="sxs-lookup"><span data-stu-id="c6647-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="c6647-258">Pentru mai multe informații, consultați [Creați și gestionați segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c6647-258">For more information, see [Create and manage segments](segments.md).</span></span>
