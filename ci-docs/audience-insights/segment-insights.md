---
title: Detalii de segment pentru segmentele existente
description: Obțineți detalii despre segmentele existente pentru a vedea diferențele și punctele comune.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: d731d21462b5a31aba0653f87e299d98373bbf49
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270035"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="17b67-103">Detalii despre segment (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="17b67-103">Segment insights (preview)</span></span>

<span data-ttu-id="17b67-104">Descoperiți informații suplimentare și detalii despre segmentele dvs. existente.</span><span class="sxs-lookup"><span data-stu-id="17b67-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="17b67-105">Aflați ce diferențiază două segmente sau ce au în comun.</span><span class="sxs-lookup"><span data-stu-id="17b67-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="17b67-106">Suprapunere de segment</span><span class="sxs-lookup"><span data-stu-id="17b67-106">Segment overlap</span></span>

<span data-ttu-id="17b67-107">Analiza de suprapunere a segmentelor arată câți și care clienți sunt comuni pentru două sau mai multe segmente.</span><span class="sxs-lookup"><span data-stu-id="17b67-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="17b67-108">De exemplu, modul în care un segment de clienți frecvenți se suprapune cu un segment care conține clienți mulțumiți de serviciul sau produsul dvs.</span><span class="sxs-lookup"><span data-stu-id="17b67-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="17b67-109">De asemenea, puteți analiza modul în care se suprapun modificările pentru atribute specifice.</span><span class="sxs-lookup"><span data-stu-id="17b67-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="17b67-110">Executați o analiză de suprapunere</span><span class="sxs-lookup"><span data-stu-id="17b67-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="17b67-111">Accesați **Segmente** și selectați fila **Detalii (previzualizare)**.</span><span class="sxs-lookup"><span data-stu-id="17b67-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="17b67-112">Selectați **Nou** și alegeți opțiunea **Suprapune** în panoul **Alegeți tipul de Detaliu**.</span><span class="sxs-lookup"><span data-stu-id="17b67-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="17b67-113">Alegeți segmentele de interes și selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="17b67-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="17b67-114">Opțional, alegeți unul sau mai multe câmpuri de interes pentru a analiza suprapunerile pentru fiecare valoare posibilă a câmpului și selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="17b67-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="17b67-115">Furnizați un nume pentru analiza de suprapunere, un nume de afișare opțional și o descriere.</span><span class="sxs-lookup"><span data-stu-id="17b67-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="17b67-116">Selectați **Salvare** pentru a începe analiza.</span><span class="sxs-lookup"><span data-stu-id="17b67-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="17b67-117">Analiza de suprapunere este gata atunci când starea se schimbă de la Actualizare la Succes.</span><span class="sxs-lookup"><span data-stu-id="17b67-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="17b67-118">Vizualizați și optimizați o analiză de suprapunere</span><span class="sxs-lookup"><span data-stu-id="17b67-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="17b67-119">După finalizarea analizei, găsiți detalii despre acest detaliu despre **Segmente** > **Detalii (previzualizare)**.</span><span class="sxs-lookup"><span data-stu-id="17b67-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Detalii despre suprapunere pe segment":::

<span data-ttu-id="17b67-121">Selectați un detaliu pentru a vedea rezultatele analizei:</span><span class="sxs-lookup"><span data-stu-id="17b67-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="17b67-122">Numărul de membri care se suprapun segmentelor selectate pentru analiză.</span><span class="sxs-lookup"><span data-stu-id="17b67-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="17b67-123">Numărul de membri incluși într-unul dintre segmente, dar nu și în restul segmentelor.</span><span class="sxs-lookup"><span data-stu-id="17b67-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="17b67-124">Dacă ați selectat câmpuri în timp ce configurați analiza de suprapunere, le veți găsi în filele corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="17b67-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="17b67-125">Puteți utiliza funcția verticală a filtrului pentru a selecta orice nivel de interes al atributului, iar tabelul din partea de jos va afișa datele corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="17b67-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="17b67-126">Diferențiatori de segmente</span><span class="sxs-lookup"><span data-stu-id="17b67-126">Segment differentiators</span></span>

<span data-ttu-id="17b67-127">Diferențiatori de segmente vă ajută să aflați ce diferențiază un segment de restul clienților dvs. sau de un alt segment.</span><span class="sxs-lookup"><span data-stu-id="17b67-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="17b67-128">Trebuie doar să selectați un segment, iar sistemul va identifica atributele de profil și măsurile care disting segmentul selectat.</span><span class="sxs-lookup"><span data-stu-id="17b67-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="17b67-129">Efectuați o analiză de diferențiator</span><span class="sxs-lookup"><span data-stu-id="17b67-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="17b67-130">Accesați **Segmente** și selectați fila **Detalii (previzualizare)**.</span><span class="sxs-lookup"><span data-stu-id="17b67-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="17b67-131">Selectați **Nou** și alegeți opțiunea **Suprapune** în panoul **Alegeți tipul de Detaliu**.</span><span class="sxs-lookup"><span data-stu-id="17b67-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="17b67-132">Alegeți segmentul pe care doriți să îl analizați **Segmentul primar** și selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="17b67-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="17b67-133">Alegeți **Toți clienții** sau un **Segment secundar** pentru a compara segmentul principal cu și selecta **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="17b67-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="17b67-134">Opțional, alege unul sau mai multe câmpuri de interes pentru a concentra analiza pe atribute specifice și selectează **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="17b67-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="17b67-135">Furnizați un nume pentru analiza de suprapunere, un nume de afișare opțional și o descriere.</span><span class="sxs-lookup"><span data-stu-id="17b67-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="17b67-136">Selectați **Salvare** pentru a începe analiza.</span><span class="sxs-lookup"><span data-stu-id="17b67-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="17b67-137">Analiza de suprapunere este gata atunci când starea se schimbă de la Actualizare la Succes.</span><span class="sxs-lookup"><span data-stu-id="17b67-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="17b67-138">Vizualizați și optimizați o analiză a diferențiatorilor</span><span class="sxs-lookup"><span data-stu-id="17b67-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="17b67-139">După finalizarea analizei, găsiți detalii despre acest detaliu despre **Segmente** > **Detalii (previzualizare)**.</span><span class="sxs-lookup"><span data-stu-id="17b67-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Detalii despre diferențiator pe segment":::

<span data-ttu-id="17b67-141">Selectați un detaliu pentru a vedea rezultatele analizei.</span><span class="sxs-lookup"><span data-stu-id="17b67-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="17b67-142">O analiză a diferențiatorului include două file.</span><span class="sxs-lookup"><span data-stu-id="17b67-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="17b67-143">Fila **Atribute** listează atributele profilului considerate ca diferențiatori.</span><span class="sxs-lookup"><span data-stu-id="17b67-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="17b67-144">Fila **Măsuri** listează diferențiatori.</span><span class="sxs-lookup"><span data-stu-id="17b67-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="17b67-145">Fiecare filă include următoarele detalii:</span><span class="sxs-lookup"><span data-stu-id="17b67-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="17b67-146">Lista clasificată a diferențiatorilor, ordonată după scorul diferenței.</span><span class="sxs-lookup"><span data-stu-id="17b67-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="17b67-147">**Scorul de diferență** pentru fiecare diferențiator.</span><span class="sxs-lookup"><span data-stu-id="17b67-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="17b67-148">Scorul de diferență reprezintă gradul de diferență a unui atribut între două segmente.</span><span class="sxs-lookup"><span data-stu-id="17b67-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="17b67-149">Cu cât scorul de diferență este mai mare, cu atât atributele diferă între cele două segmente.</span><span class="sxs-lookup"><span data-stu-id="17b67-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="17b67-150">Selectați un scor pentru a deschide panoul **Scorul de diferență** cu distribuțiile de valori pentru acel atribut.</span><span class="sxs-lookup"><span data-stu-id="17b67-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="17b67-151">Gestionați detaliile de segment</span><span class="sxs-lookup"><span data-stu-id="17b67-151">Manage segment insights</span></span>

<span data-ttu-id="17b67-152">Puteți utiliza următoarele opțiuni pentru detaliile dvs. din bara de comenzi:</span><span class="sxs-lookup"><span data-stu-id="17b67-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="17b67-153">**Înapoi** pentru a returna lista de detalii</span><span class="sxs-lookup"><span data-stu-id="17b67-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="17b67-154">**Reîmprospăta** pentru a rula din nou analiza</span><span class="sxs-lookup"><span data-stu-id="17b67-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="17b67-155">**Ștergere** pentru a elimina acest detaliu</span><span class="sxs-lookup"><span data-stu-id="17b67-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]