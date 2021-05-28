---
title: Segmente sugerate bazate pe activitate.
description: Lăsați ca învățarea programată să vă ajute să găsiți segmente noi și interesante pe baza activității clienților.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034105"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="12b38-103">Segmente sugerate bazate pe datele de activitate (versiune preliminară)</span><span class="sxs-lookup"><span data-stu-id="12b38-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="12b38-104">Descoperiți segmente interesante ale clienților pe baza datelor despre activitatea clienților care sunt ingerate în Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="12b38-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="12b38-105">Ca exemple de date despre activitate ar fi tranzacțiile, durata apelului de asistență, achizițiile sau returnările.</span><span class="sxs-lookup"><span data-stu-id="12b38-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="12b38-106">Pentru a sugera segmente, datele de activitate sunt analizate din punct de vedere al caracterului recență, frecvență și valoare monetară (sau durată).</span><span class="sxs-lookup"><span data-stu-id="12b38-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="12b38-107">Ca alternativă, puteți genera [segmente sugerate pentru a îmbunătăți o măsură sau a înțelege mai bine ce anume influențează un atribut](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="12b38-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Fila Segmente sugerate ce prezintă sugestii de segmente pentru segmente bazate pe activitate și bazate pe atribute.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="12b38-109">Clasificați clienții după activitate</span><span class="sxs-lookup"><span data-stu-id="12b38-109">Categorize customers by activity</span></span>

<span data-ttu-id="12b38-110">Cu [datele despre activitate](activities.md) disponibile în Customer Insights, putem genera sugestii care reprezintă grupuri de clienți:</span><span class="sxs-lookup"><span data-stu-id="12b38-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="12b38-111">cei mai activi clienți</span><span class="sxs-lookup"><span data-stu-id="12b38-111">most active customers</span></span> 
- <span data-ttu-id="12b38-112">clienții care au făcut cele mai multe achiziții</span><span class="sxs-lookup"><span data-stu-id="12b38-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="12b38-113">clienții care au generat cele mai multe venituri</span><span class="sxs-lookup"><span data-stu-id="12b38-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="12b38-114">clienții care nu au fost activi în ultima perioadă</span><span class="sxs-lookup"><span data-stu-id="12b38-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="12b38-115">clienții care interacționează frecvent cu afacerea dvs.</span><span class="sxs-lookup"><span data-stu-id="12b38-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="12b38-116">Dacă aveți o afacere de retail, ați putea afla care clienți generează cele mai multe venituri și îi puteți recompensa cu un cupon.</span><span class="sxs-lookup"><span data-stu-id="12b38-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="12b38-117">Sau puteți să identificați clienții ocazionali și le puteți oferi posibilitatea să se alăture unui program de recompense, astfel încât să vă viziteze afacerea mai des.</span><span class="sxs-lookup"><span data-stu-id="12b38-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="12b38-118">Dacă vă ocupați de servicii medicale, oferind asistență medicală publică și obiectivul dvs. este de a reduce la minimum cheltuielile pentru pacienții individuali.</span><span class="sxs-lookup"><span data-stu-id="12b38-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="12b38-119">O modalitate de a face acest lucru ar fi reducerea vizitelor recurente, oferind cea mai bună îngrijire posibilă în cât mai puține vizite.</span><span class="sxs-lookup"><span data-stu-id="12b38-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="12b38-120">În acest caz, obiectivul dvs. este de a menține frecvența de vizitare scăzută și să reduceți costurile recurente pentru pacienți.</span><span class="sxs-lookup"><span data-stu-id="12b38-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="12b38-121">Sau puteți să identificați segmente de pacienți care au rezervări frecvente și costuri recurente ridicate și puteți analiza aceste cazuri pentru a îmbunătăți tratamentul persoanei.</span><span class="sxs-lookup"><span data-stu-id="12b38-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="12b38-122">Date necesare</span><span class="sxs-lookup"><span data-stu-id="12b38-122">Required data</span></span>

<span data-ttu-id="12b38-123">Sugestiile sunt generate pe baza datelor de intrare selectate.</span><span class="sxs-lookup"><span data-stu-id="12b38-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="12b38-124">Profiluri de clienți: toți clienții sau membri ai unui anumit segment.</span><span class="sxs-lookup"><span data-stu-id="12b38-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="12b38-125">Perioada de timp: luna trecută, anul trecut sau orice alt interval de timp particularizat.</span><span class="sxs-lookup"><span data-stu-id="12b38-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="12b38-126">Tipul de activitate: achiziții, tranzacții retail, tranzacții online, cazuri de asistență pentru clienți, abonamente etc.</span><span class="sxs-lookup"><span data-stu-id="12b38-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="12b38-127">Entitatea din Customer Insights care conține datele despre activitate: entitatea UnifiedActivity sau entitatea pentru o anumită activitate.</span><span class="sxs-lookup"><span data-stu-id="12b38-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="12b38-128">Dimensiuni care trebuie incluse: caracter recent, frecvență sau dimensiune monetară, în funcție de cerințele afacerii dvs.</span><span class="sxs-lookup"><span data-stu-id="12b38-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="12b38-129">Generați segmente sugerate</span><span class="sxs-lookup"><span data-stu-id="12b38-129">Generate suggested segments</span></span>

1. <span data-ttu-id="12b38-130">Mergeți la **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="12b38-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="12b38-131">Selectați fila **Sugestii (previzualizare)**.</span><span class="sxs-lookup"><span data-stu-id="12b38-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="12b38-132">Selectați **Găsiți noi sugestii** și alegeți **Vedeți sau anticipați comportamentul clienților**.</span><span class="sxs-lookup"><span data-stu-id="12b38-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="12b38-133">Selectați **Start** pentru a rula experiența ghidată.</span><span class="sxs-lookup"><span data-stu-id="12b38-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Primul pas al expertului de configurare pentru un segment sugerat pe baza activității.":::

1. <span data-ttu-id="12b38-135">Dați datele de intrare necesare și selectați **Următorul** pentru a continua.</span><span class="sxs-lookup"><span data-stu-id="12b38-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="12b38-136">Alegeți clienții: includeți toți clienții sau un anumit segment.</span><span class="sxs-lookup"><span data-stu-id="12b38-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="12b38-137">Alegeți activitatea: selectați tipul de activitate și entitățile care descriu activitatea.</span><span class="sxs-lookup"><span data-stu-id="12b38-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="12b38-138">Preferințe: setați perioada de timp de luat în considerare, factorii pentru sugestii și mapați atributele.</span><span class="sxs-lookup"><span data-stu-id="12b38-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="12b38-139">Revizuiți datele introduse și selectați **Rulare** pentru a rula modelul și a genera sugestii.</span><span class="sxs-lookup"><span data-stu-id="12b38-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="12b38-140">În funcție de numărul de profiluri ale clienților și de activitățile selectate, finalizarea poate dura câteva minute.</span><span class="sxs-lookup"><span data-stu-id="12b38-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="12b38-141">După generarea sugestiilor, puteți să le filtrați după dimensiune sau valoarea care vă interesează cel mai mult.</span><span class="sxs-lookup"><span data-stu-id="12b38-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="12b38-142">Vizualizați detaliile unui segment sugerat</span><span class="sxs-lookup"><span data-stu-id="12b38-142">View details of a suggested segment</span></span>

<span data-ttu-id="12b38-143">După ce sugestiile sunt generate, le veți găsi listate în **Segmente** > **Sugestii (previzualizare)** în secțiunea **Sugestii bazate pe activități**.</span><span class="sxs-lookup"><span data-stu-id="12b38-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Panou lateral extins care prezintă date detaliate ale unui segment sugerat.":::

<span data-ttu-id="12b38-145">Selectați **Vedeți sugestia** pentru un segment sugerat pentru a vedea detaliile acelui segment.</span><span class="sxs-lookup"><span data-stu-id="12b38-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="12b38-146">Panoul lateral oferă detalii precum extensia fiecărei dimensiuni în comparație cu grupul țintă.</span><span class="sxs-lookup"><span data-stu-id="12b38-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="12b38-147">De asemenea, evidențiază numărul de membri potențiali din segment și procentul corespunzător din totalul clienților.</span><span class="sxs-lookup"><span data-stu-id="12b38-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="12b38-148">Dacă doriți să păstrați sugestia drept segment, selectați **Creare segment**.</span><span class="sxs-lookup"><span data-stu-id="12b38-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="12b38-149">Salvați o sugestie ca segment</span><span class="sxs-lookup"><span data-stu-id="12b38-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="12b38-150">Accesați **Segmente** > **Sugestii (previzualizare)**.</span><span class="sxs-lookup"><span data-stu-id="12b38-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="12b38-151">Selectați segmentul pe care doriți să-l salvați.</span><span class="sxs-lookup"><span data-stu-id="12b38-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="12b38-152">În panoul lateral, selectați **Creare segment**.</span><span class="sxs-lookup"><span data-stu-id="12b38-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="12b38-153">După ce salvați segmentul, acesta se va afișa în lista de segmente de pe fila **Toate segmentele**. Acum poate fi [reîmprospătat sau șters ca orice alt segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="12b38-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="12b38-154">Nu puteți edita detaliile segmentului.</span><span class="sxs-lookup"><span data-stu-id="12b38-154">You can't edit the segment details.</span></span> <span data-ttu-id="12b38-155">Cu toate acestea, puteți modifica criteriile de intrare pentru sugestii și puteți genera sugestii diferite.</span><span class="sxs-lookup"><span data-stu-id="12b38-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="12b38-156">Reîmprospătați sau editați un set de sugestii</span><span class="sxs-lookup"><span data-stu-id="12b38-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="12b38-157">Accesați **Segmente** > **Sugestii (versiune preliminară)** și căutați segmentul în secțiunea **Sugestii bazate pe activități**.</span><span class="sxs-lookup"><span data-stu-id="12b38-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="12b38-158">Selectați **Reîmprospătați sugestiile** pentru a reîmprospăta sugestiile păstrând în același timp atributele configurate.</span><span class="sxs-lookup"><span data-stu-id="12b38-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="12b38-159">Sau selectați **Editați sugestiile** pentru a modifica atributele configurate.</span><span class="sxs-lookup"><span data-stu-id="12b38-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="12b38-160">Sistemul va relua procesul, va genera sugestii de segmente pe baza celor mai recente date și va înlocui sugestiile curente.</span><span class="sxs-lookup"><span data-stu-id="12b38-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
