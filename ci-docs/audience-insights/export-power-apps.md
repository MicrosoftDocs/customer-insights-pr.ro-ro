---
title: Conector Power Apps
description: Conectarea cu Power Apps și Power Automate.
ms.date: 01/19/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a8bbb9a09218d54228589d43c21c8894680b56e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268931"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="32c6f-103">Conector Microsoft Power Apps (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="32c6f-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="32c6f-104">Aduceți profilurile de clienți unificate în aplicațiile dvs. personalizate cu Power Apps.</span><span class="sxs-lookup"><span data-stu-id="32c6f-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="32c6f-105">Conectare Power Apps și Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="32c6f-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="32c6f-106">Customer Insights este unul dintre numeroasele [surse de date disponibile în Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="32c6f-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="32c6f-107">Consultați documentația Power Apps pentru a învăța cum să [adăugați o conexiune de date la o aplicație](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="32c6f-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="32c6f-108">Vă recomandăm să treceți în revistă [Cum Power Apps utilizează delegarea pentru a gestiona seturi de date mari în aplicațiile proiectate pe pânză](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="32c6f-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="32c6f-109">Entităţi disponibile</span><span class="sxs-lookup"><span data-stu-id="32c6f-109">Available entities</span></span>

<span data-ttu-id="32c6f-110">După adăugarea Customer Insights ca o conexiune de date, puteți alege următoarele entități în Power Apps:</span><span class="sxs-lookup"><span data-stu-id="32c6f-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="32c6f-111">Client: să utilizeze date din [profilul clientului unificat](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="32c6f-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="32c6f-112">UnifiedActivity: pentru a afișa [cronologia de activitate](activities.md) pe aplicație.</span><span class="sxs-lookup"><span data-stu-id="32c6f-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="32c6f-113">Limitări</span><span class="sxs-lookup"><span data-stu-id="32c6f-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="32c6f-114">Entități recuperabile</span><span class="sxs-lookup"><span data-stu-id="32c6f-114">Retrievable entities</span></span>

<span data-ttu-id="32c6f-115">Puteți regăsi numai entitățile **Client**, **UnifiedActivity** și **Segmente** i prin intermediul conectorului Power Apps.</span><span class="sxs-lookup"><span data-stu-id="32c6f-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="32c6f-116">Alte entități sunt afișate deoarece conectorul de bază le acceptă prin declanșatoare în Power Automate.</span><span class="sxs-lookup"><span data-stu-id="32c6f-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="32c6f-117">Delegare</span><span class="sxs-lookup"><span data-stu-id="32c6f-117">Delegation</span></span>

<span data-ttu-id="32c6f-118">Delegarea funcționează pentru entitatea Client și entitatea UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="32c6f-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="32c6f-119">Delegare pentru entitatea **Client**: pentru a utiliza delegarea pentru această entitate, câmpurile trebuie să fie indexate în [Index de căutare și filtrare](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="32c6f-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="32c6f-120">Delegația pentru **UnifiedActivity**: Delegația pentru această entitate funcționează numai pentru câmpuri **ActivityId** și **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="32c6f-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="32c6f-121">Pentru mai multe informații despre delegare, consultați [Funcții și operațiuni Power Apps delegabile](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="32c6f-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="32c6f-122">Exemplu de control al galeriei</span><span class="sxs-lookup"><span data-stu-id="32c6f-122">Example gallery control</span></span>

<span data-ttu-id="32c6f-123">De exemplu, adăugați profiluri de clienți la un [control al galeriei](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="32c6f-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="32c6f-124">Adăugați un control **Galerie** unei aplicații pe care o construiți.</span><span class="sxs-lookup"><span data-stu-id="32c6f-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="32c6f-125">![Adăugați un element galerie](media/connector-powerapps9.png "Adăugați un element galerie")</span><span class="sxs-lookup"><span data-stu-id="32c6f-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="32c6f-126">Selectați **Client** ca sursă de date pentru elemente.</span><span class="sxs-lookup"><span data-stu-id="32c6f-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="32c6f-127">![Selectați o sursă de date](media/choose-datasource-powerapps.png "Selectați o sursă de date")</span><span class="sxs-lookup"><span data-stu-id="32c6f-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="32c6f-128">Puteți schimba panoul de date din dreapta pentru a selecta ce câmp pentru entitatea Client să se afișeze în galerie.</span><span class="sxs-lookup"><span data-stu-id="32c6f-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="32c6f-129">Dacă doriți să afișați orice câmp de la clientul selectat în galerie, completați proprietatea Text a unei etichete: **{Name_of_the_gallery}.Selectate.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="32c6f-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="32c6f-130">Exemplu: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="32c6f-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="32c6f-131">Pentru a afișa cronologia unificată pentru un client, adăugați un element de galerie și adăugați proprietatea Elemente: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="32c6f-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="32c6f-132">Exemplu: Filtru ('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="32c6f-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]