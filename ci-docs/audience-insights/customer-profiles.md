---
title: Vizualizare profiluri de client
description: Obțineți o vizualizare combinată a datelor unificate ale clienților.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: d6a9e7872a488b6d68afce35b547f93cc4a7c652
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596882"
---
# <a name="customer-profiles"></a><span data-ttu-id="5058e-103">Profiluri de client</span><span class="sxs-lookup"><span data-stu-id="5058e-103">Customer profiles</span></span>

<span data-ttu-id="5058e-104">Pagina **Clienți** arată o vizualizare combinată a clienților dvs., pe baza datelor de profil colectate de la [toate sursele de date](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="5058e-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="5058e-105">Profilele clienților sunt disponibile odată ce [creați entitatea Client unificat](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="5058e-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="5058e-106">Asigurați-vă că finalizați procesul de unificare a datelor pentru a obține vizualizări mai bogate ale clienților.</span><span class="sxs-lookup"><span data-stu-id="5058e-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="5058e-107">Pagina vă permite, de asemenea, să căutați clienți.</span><span class="sxs-lookup"><span data-stu-id="5058e-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="5058e-108">Clienții pot fi persoane fizice sau organizații (previzualizare).</span><span class="sxs-lookup"><span data-stu-id="5058e-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="5058e-109">Fiecare profil de client sau organizație este reprezentat printr-o dală.</span><span class="sxs-lookup"><span data-stu-id="5058e-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="5058e-110">Selectați o dală pentru a vedea informații suplimentare despre respectivul client sau organizație.</span><span class="sxs-lookup"><span data-stu-id="5058e-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="5058e-111">Utilizați controalele de paginare din partea de jos a paginii pentru a vedea înregistrări suplimentare.</span><span class="sxs-lookup"><span data-stu-id="5058e-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="5058e-112">![Profiluri de clienți B2C](media/profiles-customers.png "Profiluri de clienți B2C")</span><span class="sxs-lookup"><span data-stu-id="5058e-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="5058e-113">Organizații (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="5058e-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="5058e-114">![Profiluri de clienți B2B](media/profile-customers-b2b.png "Profiluri de clienți B2B")</span><span class="sxs-lookup"><span data-stu-id="5058e-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="5058e-115">Dacă nu puteți vedea dalele când selectați **Clienți** în meniul de navigare, administratorul dvs. trebuie să [definească cel puțin un atribut care poate fi căutat](search-filter-index.md) în **Index de căutare și filtrare**.</span><span class="sxs-lookup"><span data-stu-id="5058e-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="5058e-116">Căutare clienți</span><span class="sxs-lookup"><span data-stu-id="5058e-116">Search for customers</span></span>

<span data-ttu-id="5058e-117">Căutați clienți introducând un nume sau alt atribut în caseta de căutare.</span><span class="sxs-lookup"><span data-stu-id="5058e-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="5058e-118">Căutarea funcționează numai în cadrul entității Profilul Clientului creat în timpul procesului de unificare a datelor.</span><span class="sxs-lookup"><span data-stu-id="5058e-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="5058e-119">Ca administrator, puteți configura atributele care pot fi căutate folosind pagina **Indice de căutare și filtrare**.</span><span class="sxs-lookup"><span data-stu-id="5058e-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="5058e-120">Pentru mai multe informații, consultați [Gestionați indicele de căutare și filtrare](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="5058e-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="5058e-121">Filtrați clienți</span><span class="sxs-lookup"><span data-stu-id="5058e-121">Filter customers</span></span>

<span data-ttu-id="5058e-122">Puteți filtra clienții după câmpurile entității Profilul clienților.</span><span class="sxs-lookup"><span data-stu-id="5058e-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="5058e-123">Similar cu căutarea, administratorul dvs. va trebui mai întâi să definească câmpurile ca fiind filtrabile folosind pagina **Indice de căutare și filtrare**.</span><span class="sxs-lookup"><span data-stu-id="5058e-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="5058e-124">Selectați **Filtru** în pagina **Clienți**.</span><span class="sxs-lookup"><span data-stu-id="5058e-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="5058e-125">Bifați casetele de lângă atributele prin care doriți să filtrați clienții.</span><span class="sxs-lookup"><span data-stu-id="5058e-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="5058e-126">![Profiluri de client](media/profiles-customers3.png "Profiluri de client")</span><span class="sxs-lookup"><span data-stu-id="5058e-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="5058e-127">Eliminați filtrele selectând **Ștergere filtre** pe pagina **Clienți**.</span><span class="sxs-lookup"><span data-stu-id="5058e-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="5058e-128">Pagină detalii client</span><span class="sxs-lookup"><span data-stu-id="5058e-128">Customer details page</span></span>

<span data-ttu-id="5058e-129">Selectați oricare dintre dalele clientului pentru a deschide **Pagina cu detalii despre client**.</span><span class="sxs-lookup"><span data-stu-id="5058e-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="5058e-130">Această vizualizare conține informații unificate pentru clientul selectat.</span><span class="sxs-lookup"><span data-stu-id="5058e-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="5058e-131">Detaliile clientului includ:</span><span class="sxs-lookup"><span data-stu-id="5058e-131">Customer details include:</span></span>

-   <span data-ttu-id="5058e-132">**Dală profil client:** Această dală arată diferitele valori din entitatea de profil client unificat.</span><span class="sxs-lookup"><span data-stu-id="5058e-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="5058e-133">Aceste detalii pot include adresa de e-mail, numele, orașul și așa mai departe.</span><span class="sxs-lookup"><span data-stu-id="5058e-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="5058e-134">**Interese potențiale, mărci potențiale:** Arată dacă ați configurat o îmbogățire primară.</span><span class="sxs-lookup"><span data-stu-id="5058e-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="5058e-135">Reprezintă potențiale interese și afinități pentru mărci pe care le poate avea un client cu un profil similar cu acest client.</span><span class="sxs-lookup"><span data-stu-id="5058e-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="5058e-136">Pentru mai multe informații, consultați [Îmbogățiți profilurile clienților cu afinități de brand și interes](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="5058e-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="5058e-137">**Măsuri:** Arată dacă ați configurat una sau mai multe măsuri de un anumit tip: măsuri de atribut client.</span><span class="sxs-lookup"><span data-stu-id="5058e-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="5058e-138">Acestea includ indicatorii KPI calculați în jurul clienților dvs. la nivel de client individual.</span><span class="sxs-lookup"><span data-stu-id="5058e-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="5058e-139">Pentru mai multe informații, consultați [Definire și gestionare măsuri](measures.md).</span><span class="sxs-lookup"><span data-stu-id="5058e-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="5058e-140">**Cronologia activității:** Arată dacă ați configurat activități.</span><span class="sxs-lookup"><span data-stu-id="5058e-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="5058e-141">Vizualizarea cronologiei conține activități sortate cronologic ale acestui client, începând cu cea mai recentă activitate.</span><span class="sxs-lookup"><span data-stu-id="5058e-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="5058e-142">Pentru mai multe informații, consultați [Activități Client](activities.md).</span><span class="sxs-lookup"><span data-stu-id="5058e-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="5058e-143">Selectați **Înapoi la clienți** pentru a reveni la pagina de căutare a clienților.</span><span class="sxs-lookup"><span data-stu-id="5058e-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5058e-144">Pașii următori</span><span class="sxs-lookup"><span data-stu-id="5058e-144">Next steps</span></span>

<span data-ttu-id="5058e-145">[Adăugați mai multe surse de date](data-sources.md) sau [creați segmente de clienți](segments.md).</span><span class="sxs-lookup"><span data-stu-id="5058e-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]