---
title: Conector Power Apps
description: Conectarea cu Power Apps și Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598170"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="de5de-103">Conector Microsoft Power Apps (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="de5de-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="de5de-104">Aduceți profilurile de clienți unificate în aplicațiile dvs. personalizate cu Power Apps.</span><span class="sxs-lookup"><span data-stu-id="de5de-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="de5de-105">Conectare Power Apps și Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="de5de-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="de5de-106">Customer Insights este unul dintre numeroasele [surse de date disponibile în Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="de5de-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="de5de-107">Consultați documentația Power Apps pentru a învăța cum să [adăugați o conexiune de date la o aplicație](/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="de5de-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="de5de-108">Vă recomandăm să treceți în revistă [Cum Power Apps utilizează delegarea pentru a gestiona seturi de date mari în aplicațiile proiectate pe pânză](/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="de5de-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="de5de-109">Entităţi disponibile</span><span class="sxs-lookup"><span data-stu-id="de5de-109">Available entities</span></span>

<span data-ttu-id="de5de-110">După adăugarea Customer Insights ca o conexiune de date, puteți alege următoarele entități în Power Apps:</span><span class="sxs-lookup"><span data-stu-id="de5de-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="de5de-111">Client: să utilizeze date din [profilul clientului unificat](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="de5de-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="de5de-112">UnifiedActivity: pentru a afișa [cronologia de activitate](activities.md) pe aplicație.</span><span class="sxs-lookup"><span data-stu-id="de5de-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="de5de-113">Limitări</span><span class="sxs-lookup"><span data-stu-id="de5de-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="de5de-114">Entități recuperabile</span><span class="sxs-lookup"><span data-stu-id="de5de-114">Retrievable entities</span></span>

<span data-ttu-id="de5de-115">Puteți regăsi numai entitățile **Client**, **UnifiedActivity** și **Segmente** i prin intermediul conectorului Power Apps.</span><span class="sxs-lookup"><span data-stu-id="de5de-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="de5de-116">Alte entități sunt afișate deoarece conectorul de bază le acceptă prin declanșatoare în Power Automate.</span><span class="sxs-lookup"><span data-stu-id="de5de-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="de5de-117">Delegare</span><span class="sxs-lookup"><span data-stu-id="de5de-117">Delegation</span></span>

<span data-ttu-id="de5de-118">Delegarea funcționează pentru entitatea Client și entitatea UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="de5de-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="de5de-119">Delegare pentru entitatea **Client**: pentru a utiliza delegarea pentru această entitate, câmpurile trebuie să fie indexate în [Index de căutare și filtrare](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="de5de-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="de5de-120">Delegația pentru **UnifiedActivity**: Delegația pentru această entitate funcționează numai pentru câmpuri **ActivityId** și **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="de5de-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="de5de-121">Pentru mai multe informații despre delegare, consultați [Funcții și operațiuni Power Apps delegabile](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="de5de-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="de5de-122">Exemplu de control al galeriei</span><span class="sxs-lookup"><span data-stu-id="de5de-122">Example gallery control</span></span>

<span data-ttu-id="de5de-123">De exemplu, adăugați profiluri de clienți la un [control al galeriei](/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="de5de-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="de5de-124">Adăugați un control **Galerie** unei aplicații pe care o construiți.</span><span class="sxs-lookup"><span data-stu-id="de5de-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="de5de-125">![Adăugați un element galerie](media/connector-powerapps9.png "Adăugați un element galerie")</span><span class="sxs-lookup"><span data-stu-id="de5de-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="de5de-126">Selectați **Client** ca sursă de date pentru elemente.</span><span class="sxs-lookup"><span data-stu-id="de5de-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="de5de-127">![Selectați o sursă de date](media/choose-datasource-powerapps.png "Selectați o sursă de date")</span><span class="sxs-lookup"><span data-stu-id="de5de-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="de5de-128">Puteți schimba panoul de date din dreapta pentru a selecta ce câmp pentru entitatea Client să se afișeze în galerie.</span><span class="sxs-lookup"><span data-stu-id="de5de-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="de5de-129">Dacă doriți să afișați orice câmp de la clientul selectat în galerie, completați proprietatea Text a unei etichete: **{Name_of_the_gallery}.Selectate.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="de5de-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="de5de-130">Exemplu: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="de5de-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="de5de-131">Pentru a afișa cronologia unificată pentru un client, adăugați un element de galerie și adăugați proprietatea Elemente: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="de5de-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="de5de-132">Exemplu: Filtru ('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="de5de-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]