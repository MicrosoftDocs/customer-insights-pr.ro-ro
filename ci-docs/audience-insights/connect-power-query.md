---
title: Ingerare date printr-un conector Power Query
description: Conectori pentru surse de date bazate pe Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d51a7efa5fd9f7336d1662500eb804a674738493
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267787"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="6dc48-103">Conectați-vă la o sursă de date Power Query</span><span class="sxs-lookup"><span data-stu-id="6dc48-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="6dc48-104">Power Query oferă un set larg de conectori pentru a ingera date.</span><span class="sxs-lookup"><span data-stu-id="6dc48-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="6dc48-105">Majoritatea acestor conectori sunt suportați de Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6dc48-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="6dc48-106">Adăugarea surselor de date pe baza conectorilor Power Query urmează în general pașii descriși în secțiunea următoare.</span><span class="sxs-lookup"><span data-stu-id="6dc48-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="6dc48-107">Cu toate acestea, în funcție de conectorul pe care îl utilizați, sunt necesare informații diferite.</span><span class="sxs-lookup"><span data-stu-id="6dc48-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="6dc48-108">Pentru mai multe informații, consultați documentația despre conectorii individuali din [Conectorul de referință Power Query](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="6dc48-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="6dc48-109">Creați o nouă sursă de date</span><span class="sxs-lookup"><span data-stu-id="6dc48-109">Create a new data source</span></span>

1. <span data-ttu-id="6dc48-110">În Detalii despre audiență, accesați **Date** > **Surse de date**.</span><span class="sxs-lookup"><span data-stu-id="6dc48-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="6dc48-111">Selectați **Adăugați sursa de date**.</span><span class="sxs-lookup"><span data-stu-id="6dc48-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="6dc48-112">Alegeți metoda **Importați date** și selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="6dc48-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="6dc48-113">Furnizați un **Nume** pentru sursa de date și selectați **Următorul** pentru a crea sursă de date.</span><span class="sxs-lookup"><span data-stu-id="6dc48-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="6dc48-114">Numire recomandări:</span><span class="sxs-lookup"><span data-stu-id="6dc48-114">Name guidelines:</span></span> 
   - <span data-ttu-id="6dc48-115">Începeți cu o literă.</span><span class="sxs-lookup"><span data-stu-id="6dc48-115">Start with a letter.</span></span>
   - <span data-ttu-id="6dc48-116">Folosiți numai litere și cifre.</span><span class="sxs-lookup"><span data-stu-id="6dc48-116">Use letters and numbers only.</span></span> <span data-ttu-id="6dc48-117">Nu sunt permise caracterele speciale și spațiile.</span><span class="sxs-lookup"><span data-stu-id="6dc48-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="6dc48-118">Folosiți între 3 și 64 de caractere.</span><span class="sxs-lookup"><span data-stu-id="6dc48-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="6dc48-119">Alegeți unul dintre [conectorii disponibili](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="6dc48-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="6dc48-120">Pentru acest exemplu, selectăm conectorul **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="6dc48-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="6dc48-121">Introduceți detaliile necesare în **Setări de conectare** pentru conectorul selectat și selectați **Următorul** pentru a vedea o previzualizare a datelor.</span><span class="sxs-lookup"><span data-stu-id="6dc48-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="6dc48-122">Selectați **Transformați datele**.</span><span class="sxs-lookup"><span data-stu-id="6dc48-122">Select **Transform data**.</span></span> <span data-ttu-id="6dc48-123">În acest pas, veți adăuga entități la sursă de date.</span><span class="sxs-lookup"><span data-stu-id="6dc48-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="6dc48-124">Entitățile sunt seturi de date.</span><span class="sxs-lookup"><span data-stu-id="6dc48-124">Entities are datasets.</span></span> <span data-ttu-id="6dc48-125">Dacă aveți o bază de date care include mai multe seturi de date, fiecare set de date este propria entitate.</span><span class="sxs-lookup"><span data-stu-id="6dc48-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="6dc48-126">Dialogul **Power Query - Editați interogările** vă permite să examinați și să rafinați datele.</span><span class="sxs-lookup"><span data-stu-id="6dc48-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="6dc48-127">Entitățile identificate de sisteme în sursa de date selectată apar în panoul din stânga.</span><span class="sxs-lookup"><span data-stu-id="6dc48-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6dc48-128">![Editați interogările de dialog](media/data-manager-configure-edit-queries.png "Editați interogările de dialog")</span><span class="sxs-lookup"><span data-stu-id="6dc48-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="6dc48-129">De asemenea, vă puteți transforma datele.</span><span class="sxs-lookup"><span data-stu-id="6dc48-129">You can also transform your data.</span></span> <span data-ttu-id="6dc48-130">Selectați o entitate de editat sau de transformat.</span><span class="sxs-lookup"><span data-stu-id="6dc48-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="6dc48-131">Utilizați opțiunile din fereastra Power Query pentru a aplica transformări.</span><span class="sxs-lookup"><span data-stu-id="6dc48-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="6dc48-132">Fiecare transformare este listată sub **Pași aplicați**.</span><span class="sxs-lookup"><span data-stu-id="6dc48-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="6dc48-133">Power Query oferă numeroase opțiuni de transformare pre-construite.</span><span class="sxs-lookup"><span data-stu-id="6dc48-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="6dc48-134">Pentru informații suplimentare, consultați [Transformări Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="6dc48-134">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="6dc48-135">Puteți adăuga entități suplimentare la sursa dvs. de date selectând **Preluare date** în dialogul **Editare interogări**.</span><span class="sxs-lookup"><span data-stu-id="6dc48-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="6dc48-136">Aceste transformări sunt foarte recomandate:</span><span class="sxs-lookup"><span data-stu-id="6dc48-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="6dc48-137">Dacă ingerați date dintr-un fișier CSV, primul rând conține adesea anteturi.</span><span class="sxs-lookup"><span data-stu-id="6dc48-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="6dc48-138">Accesați **Transformați tabelul** și selectați **Folosiți anteturi ca primul rând**.</span><span class="sxs-lookup"><span data-stu-id="6dc48-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="6dc48-139">Asigurați-vă că tipul de date este setat corespunzător.</span><span class="sxs-lookup"><span data-stu-id="6dc48-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="6dc48-140">Selectați **Salvare** din partea de jos a ferestrei Power Query pentru a vă salva transformările.</span><span class="sxs-lookup"><span data-stu-id="6dc48-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="6dc48-141">După salvare, veți găsi sursa de date la **Date** > **Surse de date**.</span><span class="sxs-lookup"><span data-stu-id="6dc48-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="6dc48-142">Pe pagina **Surse de date**, veți observa că noua sursă de date este în stare **Se reîmprospătează**.</span><span class="sxs-lookup"><span data-stu-id="6dc48-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="6dc48-143">Surse de date Power Query disponibile</span><span class="sxs-lookup"><span data-stu-id="6dc48-143">Available Power Query data sources</span></span>

<span data-ttu-id="6dc48-144">Consultați [Conectorul de referință Power Query](https://docs.microsoft.com/power-query/connectors/) pentru o listă actualizată de conectori pe care îi puteți selecta pentru a importa date în Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6dc48-144">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="6dc48-145">Conectori cu bifă în coloana **Customer Insights (fluxuri de date)** sunt disponibili pentru a crea noi surse de date bazate pe Power Query.</span><span class="sxs-lookup"><span data-stu-id="6dc48-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="6dc48-146">Consultați documentația unui conector specific pentru a afla mai multe despre cerințele preliminare, limitările și alte detalii.</span><span class="sxs-lookup"><span data-stu-id="6dc48-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="6dc48-147">Editați surse de date Power Query</span><span class="sxs-lookup"><span data-stu-id="6dc48-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="6dc48-148">Este posibil să nu fie posibilă modificarea surselor de date care sunt utilizate în prezent într-unul dintre procesele aplicației (*segmentare*, *potrivire* sau *îmbinare*, de exemplu).</span><span class="sxs-lookup"><span data-stu-id="6dc48-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="6dc48-149">Utilizând pagina **Setări**, puteți urmări progresul fiecărui proces activ.</span><span class="sxs-lookup"><span data-stu-id="6dc48-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="6dc48-150">Când se termină un proces, aveți posibilitatea să reveniți la pagina **Surse de date** și să efectuați modificările.</span><span class="sxs-lookup"><span data-stu-id="6dc48-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="6dc48-151">În Detalii despre audiență, accesați **Date** > **Surse de date**.</span><span class="sxs-lookup"><span data-stu-id="6dc48-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="6dc48-152">Selectați elipsa verticală de lângă sursa de date pe care doriți să o modificați și selectați **Editați** din meniul cu selectare multiplă.</span><span class="sxs-lookup"><span data-stu-id="6dc48-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6dc48-153">![Opțiunea editare](media/edit-option-data-sources.png "Opțiunea editare")</span><span class="sxs-lookup"><span data-stu-id="6dc48-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="6dc48-154">Aplicați modificările și transformările dvs. în **Power Query - Editați interogările** așa cum au fost descrise în secțiunea [Creați o nouă sursă de date](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="6dc48-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="6dc48-155">Selectați **Salvare** în Power Query după finalizarea modificărilor pentru a salva modificările.</span><span class="sxs-lookup"><span data-stu-id="6dc48-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]