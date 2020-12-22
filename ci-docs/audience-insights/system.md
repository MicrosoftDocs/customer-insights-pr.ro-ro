---
title: Configurarea sistemului în Detalii despre public
description: Aflați despre setările sistemului în capabilitatea de detalii privind publicul Dynamics 365 Customer Insights.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406706"
---
# <a name="system-configuration"></a><span data-ttu-id="7aed8-103">Configurări sistem</span><span class="sxs-lookup"><span data-stu-id="7aed8-103">System configuration</span></span>

<span data-ttu-id="7aed8-104">Pagina **Sistem** include patru file: **Stare**, **Planificare**, **Despre** și **General**.</span><span class="sxs-lookup"><span data-stu-id="7aed8-104">The **System** page includes four tabs: **Status**, **Schedule**, **About**, and **General**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7aed8-105">![Pagina de sistem](media/system-tabs.png "Pagina de sistem")</span><span class="sxs-lookup"><span data-stu-id="7aed8-105">![System page](media/system-tabs.png "System page")</span></span>

## <a name="status-tab"></a><span data-ttu-id="7aed8-106">Fila Stare</span><span class="sxs-lookup"><span data-stu-id="7aed8-106">Status tab</span></span>

<span data-ttu-id="7aed8-107">Fila **Stare** vă permite să urmăriți progresul ingestiei de date, exporturile de date, și mai multe procese importante ale produsului.</span><span class="sxs-lookup"><span data-stu-id="7aed8-107">The **Status tab** lets you track the progress of data ingestion, data exports, and several important product processes.</span></span> <span data-ttu-id="7aed8-108">Consultați informațiile din această filă pentru a vă asigura că procesele active sunt complete.</span><span class="sxs-lookup"><span data-stu-id="7aed8-108">Review the information on this tab to ensure the completeness of active processes.</span></span>

<span data-ttu-id="7aed8-109">Această filă include tabele de stare pentru **Sursele de date**, **Procesele de sistem**, și **Pregătirea datelor**.</span><span class="sxs-lookup"><span data-stu-id="7aed8-109">This tab includes status tables for **Data sources**, **System processes**, and **Data preparation**.</span></span> <span data-ttu-id="7aed8-110">Fiecare tabel urmărește **Numele** activității și entitatea corespunzătoare, **Starea** celei mai recente rulări și când a fost **Ultima actualizare**.</span><span class="sxs-lookup"><span data-stu-id="7aed8-110">Each table tracks the **Name** of the task and its corresponding entity, the **Status** of its most recent run, and when it was **Last updated**.</span></span>

<span data-ttu-id="7aed8-111">Vizualizați detaliile ultimelor câteva rulări ale activității selectând numele acesteia.</span><span class="sxs-lookup"><span data-stu-id="7aed8-111">View the details of the tasks' last several runs by selecting its name.</span></span>

### <a name="status-types"></a><span data-ttu-id="7aed8-112">Tipuri de stări</span><span class="sxs-lookup"><span data-stu-id="7aed8-112">Status types</span></span>

<span data-ttu-id="7aed8-113">Sunt șase tipuri de stări pentru sarcini.</span><span class="sxs-lookup"><span data-stu-id="7aed8-113">There are six types of status for tasks.</span></span> <span data-ttu-id="7aed8-114">Următoarele tipuri de stare apar și pe paginile *Potrivire*, *Îmbinare*, *Surse de date*, *Segmente*, *Măsuri*, *Îmbogățire*, *Activități* și *Predicții*:</span><span class="sxs-lookup"><span data-stu-id="7aed8-114">The following status types also show on the *Match*, *Merge*, *Data sources*, *Segments*, *Measures*, *Enrichment*, *Activities*, and *Predictions* pages:</span></span>

- <span data-ttu-id="7aed8-115">**Se procesează:** Sarcina este în desfășurare.</span><span class="sxs-lookup"><span data-stu-id="7aed8-115">**Processing:** Task is in progress.</span></span> <span data-ttu-id="7aed8-116">Starea se poate schimba în Reușită sau Eșec.</span><span class="sxs-lookup"><span data-stu-id="7aed8-116">The status can change to Successful or Failure.</span></span>
- <span data-ttu-id="7aed8-117">**Reușită:** Sarcină finalizată cu succes.</span><span class="sxs-lookup"><span data-stu-id="7aed8-117">**Successful:** Task completed successfully.</span></span>
- <span data-ttu-id="7aed8-118">**Omis:** Sarcina a fost omisă.</span><span class="sxs-lookup"><span data-stu-id="7aed8-118">**Skipped:** Task got skipped.</span></span> <span data-ttu-id="7aed8-119">Unul sau mai multe dintre procesele din aval de care depinde această sarcină eșuează sau sunt omise.</span><span class="sxs-lookup"><span data-stu-id="7aed8-119">One or more of the downstream processes this task depends on are failing or got skipped.</span></span>
- <span data-ttu-id="7aed8-120">**Eșec:** Procesarea sarcinii a eșuat.</span><span class="sxs-lookup"><span data-stu-id="7aed8-120">**Failure:** Processing  of the task has failed.</span></span>
- <span data-ttu-id="7aed8-121">**Anulat:** Procesarea a fost anulată de către utilizator înainte de finalizarea acesteia.</span><span class="sxs-lookup"><span data-stu-id="7aed8-121">**Canceled:** Processing was canceled by the user before it finished.</span></span>
- <span data-ttu-id="7aed8-122">**În coadă:** Prelucrarea este pusă în coadă și va începe odată ce toate sarcinile din aval sunt finalizate.</span><span class="sxs-lookup"><span data-stu-id="7aed8-122">**Queued:** Processing is queued and will start once all the downstream tasks are completed.</span></span> <span data-ttu-id="7aed8-123">Pentru mai multe informații, consultați [politici reîmprospătare](#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="7aed8-123">For more information, see [Refresh policies](#refresh-policies).</span></span>

### <a name="refresh-policies"></a><span data-ttu-id="7aed8-124">Politici de reîmprospătare</span><span class="sxs-lookup"><span data-stu-id="7aed8-124">Refresh policies</span></span>

<span data-ttu-id="7aed8-125">Această listă prezintă politicile de reîmprospătare pentru fiecare dintre principalele procese:</span><span class="sxs-lookup"><span data-stu-id="7aed8-125">This list shows the refresh policies for each of the main processes:</span></span>

- <span data-ttu-id="7aed8-126">**Surse de date:** Se execută conform cu [planificarea configurată](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7aed8-126">**Data sources:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="7aed8-127">Nu depinde de niciun alt proces.</span><span class="sxs-lookup"><span data-stu-id="7aed8-127">Doesn't depend on any other process.</span></span> <span data-ttu-id="7aed8-128">Potrivirea depinde de finalizarea cu succes a acestui proces.</span><span class="sxs-lookup"><span data-stu-id="7aed8-128">Match depends on the successful completion of this process.</span></span>
- <span data-ttu-id="7aed8-129">**Potrivirea:** Se execută conform cu [planificarea configurată](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7aed8-129">**Match:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="7aed8-130">Depinde de procesarea surselor de date utilizate în definiția potrivirii.</span><span class="sxs-lookup"><span data-stu-id="7aed8-130">Depends on the processing of the data sources used in the match definition.</span></span> <span data-ttu-id="7aed8-131">Îmbinarea depinde de finalizarea cu succes a acestui proces.</span><span class="sxs-lookup"><span data-stu-id="7aed8-131">Merge depends on the successful completion of this process.</span></span>
- <span data-ttu-id="7aed8-132">**Îmbinarea**: Se execută conform cu [planificarea configurată](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7aed8-132">**Merge**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="7aed8-133">Depinde de finalizarea procesului de potrivire.</span><span class="sxs-lookup"><span data-stu-id="7aed8-133">Depends on the completion of the match process.</span></span> <span data-ttu-id="7aed8-134">Segmentele, măsurile, îmbogățirea, căutarea, activitățile, predicțiile și pregătirea datelor depind de finalizarea cu succes a acestui proces.</span><span class="sxs-lookup"><span data-stu-id="7aed8-134">Segments, measures, enrichment, search, activities, predictions, and data preparation depend on the successful completion of this process.</span></span>
- <span data-ttu-id="7aed8-135">**Segmente**: Se execută manual (reîmprospătare unică) și în funcție de [planificarea configurată](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7aed8-135">**Segments**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="7aed8-136">Depinde de Îmbinare.</span><span class="sxs-lookup"><span data-stu-id="7aed8-136">Depends on Merge.</span></span> <span data-ttu-id="7aed8-137">Detaliile depind de procesarea acestuia.</span><span class="sxs-lookup"><span data-stu-id="7aed8-137">Insights depend on its processing.</span></span>
- <span data-ttu-id="7aed8-138">**Măsuri**: Se execută manual (reîmprospătare unică) și în funcție de [planificarea configurată](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7aed8-138">**Measures**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="7aed8-139">Depinde de Îmbinare.</span><span class="sxs-lookup"><span data-stu-id="7aed8-139">Depends on Merge.</span></span>
- <span data-ttu-id="7aed8-140">**Activități**: Se execută manual (reîmprospătare unică) și în funcție de [planificarea configurată](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7aed8-140">**Activities**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="7aed8-141">Depinde de Îmbinare.</span><span class="sxs-lookup"><span data-stu-id="7aed8-141">Depends on Merge.</span></span>
- <span data-ttu-id="7aed8-142">**Îmbogățire**: Se execută manual (reîmprospătare unică) și în funcție de [planificarea configurată](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7aed8-142">**Enrichment**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="7aed8-143">Depinde de Îmbinare.</span><span class="sxs-lookup"><span data-stu-id="7aed8-143">Depends on Merge.</span></span>
- <span data-ttu-id="7aed8-144">**Căutarea**: Se execută manual (reîmprospătare unică) și în funcție de [planificarea configurată](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7aed8-144">**Search**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="7aed8-145">Depinde de Îmbinare.</span><span class="sxs-lookup"><span data-stu-id="7aed8-145">Depends on Merge.</span></span>
- <span data-ttu-id="7aed8-146">**Pregătire date:**: Se execută conform cu [planificarea configurată](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7aed8-146">**Data preparation**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="7aed8-147">Depinde de Îmbinare.</span><span class="sxs-lookup"><span data-stu-id="7aed8-147">Depends on Merge.</span></span>
- <span data-ttu-id="7aed8-148">**Detalii**: Se execută manual (reîmprospătare unică) și în funcție de [planificarea configurată](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7aed8-148">**Insights**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="7aed8-149">Depinde de segmente.</span><span class="sxs-lookup"><span data-stu-id="7aed8-149">Depends on Segments.</span></span>

<span data-ttu-id="7aed8-150">Selectați starea unei activități pentru a vedea detalii despre evoluția întregii lucrări în care a avut loc.</span><span class="sxs-lookup"><span data-stu-id="7aed8-150">Select the status of a task to see the progress details of the entire job it was in.</span></span> <span data-ttu-id="7aed8-151">Politicile de actualizare de mai sus vă pot ajuta să înțelegeți ce puteți face pentru a aborda o sarcină **Omisă** sau **În coadă**.</span><span class="sxs-lookup"><span data-stu-id="7aed8-151">The refresh policies above can help to understand what you can do to address a **Skipped** or **Queued** task.</span></span>

## <a name="schedule-tab"></a><span data-ttu-id="7aed8-152">Fila planificare</span><span class="sxs-lookup"><span data-stu-id="7aed8-152">Schedule tab</span></span>

<span data-ttu-id="7aed8-153">Folosiți fila **Planificare** pentru a planifica reîmprospătarea automată a tuturor [surselor de date ingerate](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="7aed8-153">Use the **Schedule** tab to schedule automatic refreshes of all your [ingested data sources](data-sources.md).</span></span> <span data-ttu-id="7aed8-154">Actualizările automate vă ajută să vă asigurați că actualizările din sursele de date sunt reflectate în profilurile dvs. de clienți unificate.</span><span class="sxs-lookup"><span data-stu-id="7aed8-154">Automatic refreshes help ensure that updates from your data sources are reflected in your unified customer profiles.</span></span>

1. <span data-ttu-id="7aed8-155">În detaliile despre public, accesați **Administrator** > **Sistem** și selectați fila **Planificare**.</span><span class="sxs-lookup"><span data-stu-id="7aed8-155">In audience insights, go to **Admin** > **System** and select the **Schedule** tab.</span></span>

2. <span data-ttu-id="7aed8-156">Starea implicită pentru reîmprospătarea programată este **Dezactivat**.</span><span class="sxs-lookup"><span data-stu-id="7aed8-156">The default state for the scheduled refresh is **Off**.</span></span> <span data-ttu-id="7aed8-157">Pentru a activa actualizarea programată, schimbați comutarea din partea de sus a ecranului la **Activat**.</span><span class="sxs-lookup"><span data-stu-id="7aed8-157">To enable scheduled refreshes, change the toggle at the top of the screen to **On**.</span></span>

3. <span data-ttu-id="7aed8-158">Alegeți între **Săptămânal** (implicit) și reîmprospătare **Zilnică**.</span><span class="sxs-lookup"><span data-stu-id="7aed8-158">Choose between **Weekly** (default) and **Daily** refreshes.</span></span> <span data-ttu-id="7aed8-159">Dacă intenționați să programați actualizări săptămânale, selectați una sau mai multe zile în care doriți să rulați actualizarea.</span><span class="sxs-lookup"><span data-stu-id="7aed8-159">If you intend to schedule weekly refreshes, select one or more days on which you want to run the refresh.</span></span>

4. <span data-ttu-id="7aed8-160">Setați-vă **Fusul orar**, apoi utilizați meniul vertical **Oră** pentru a seta temporizarea reîmprospătării.</span><span class="sxs-lookup"><span data-stu-id="7aed8-160">Set your **Time zone**, then use the **Time** dropdown to set your refresh timing.</span></span> <span data-ttu-id="7aed8-161">Când ați terminat, selectați **Setare**.</span><span class="sxs-lookup"><span data-stu-id="7aed8-161">When you're finished, select **Set**.</span></span> <span data-ttu-id="7aed8-162">Dacă doriți să programați mai multe actualizări într-o singură zi, selectați **Adăugați altă oră**.</span><span class="sxs-lookup"><span data-stu-id="7aed8-162">If you'd like to schedule multiple refreshes in a single day, select **Add another time**.</span></span>

5. <span data-ttu-id="7aed8-163">Selectați **Salvare** pentru a vă aplica modificările.</span><span class="sxs-lookup"><span data-stu-id="7aed8-163">Select **Save** to apply your changes.</span></span>

## <a name="about-tab"></a><span data-ttu-id="7aed8-164">Despre filă</span><span class="sxs-lookup"><span data-stu-id="7aed8-164">About tab</span></span>

<span data-ttu-id="7aed8-165">Fila **Despre** conține **Numele afișat** al organizației dvs., **ID de mediu** activ, **Regiunea**, și **ID sesiune**.</span><span class="sxs-lookup"><span data-stu-id="7aed8-165">The **About** tab contains your organization's **Display name**, the active **Environment ID**, the **Region**, and your **Session ID**.</span></span> <span data-ttu-id="7aed8-166">Dacă aveți mai multe medii de lucru, ar trebui să le dați fiecăruia un nume de afișare ușor de identificat.</span><span class="sxs-lookup"><span data-stu-id="7aed8-166">If you have more than one work environment, you should give each an easily identifiable display name.</span></span>

## <a name="general-tab"></a><span data-ttu-id="7aed8-167">Fila General</span><span class="sxs-lookup"><span data-stu-id="7aed8-167">General tab</span></span>

<span data-ttu-id="7aed8-168">Există două opțiuni pe fila **General**, **Limba** și **Format țară/regiune**.</span><span class="sxs-lookup"><span data-stu-id="7aed8-168">There are two options on the **General** tab, **Language** and **Country/Region format**.</span></span>

<span data-ttu-id="7aed8-169">Aplicația [acceptă mai multe limbi](supported-languages.md).</span><span class="sxs-lookup"><span data-stu-id="7aed8-169">The app [supports a number of languages](supported-languages.md).</span></span> <span data-ttu-id="7aed8-170">Pentru a schimba limba preferată, alegeți o **Limbă** din lista verticală.</span><span class="sxs-lookup"><span data-stu-id="7aed8-170">To change your preferred language, choose a **Language** from the dropdown.</span></span>

<span data-ttu-id="7aed8-171">Pentru a schimba formatarea dvs. preferată pentru date, oră și numere, utilizați lista verticală **Format țară/regiune**.</span><span class="sxs-lookup"><span data-stu-id="7aed8-171">To change your preferred formatting for dates, time, and numbers, use the **Country/Region format** dropdown.</span></span> <span data-ttu-id="7aed8-172">O previzualizare de formatare este afișată sub acest câmp.</span><span class="sxs-lookup"><span data-stu-id="7aed8-172">A formatting preview is displayed under this field.</span></span> <span data-ttu-id="7aed8-173">Sistemul va sugera automat o selecție atunci când alegeți o nouă limbă.</span><span class="sxs-lookup"><span data-stu-id="7aed8-173">The system will automatically suggest a selection when you choose a new language.</span></span>

<span data-ttu-id="7aed8-174">Selectați **Salvare** pentru a confirma selecțiile.</span><span class="sxs-lookup"><span data-stu-id="7aed8-174">Select **Save** to confirm your selections.</span></span>

## <a name="api-usage-tab"></a><span data-ttu-id="7aed8-175">Filă utilizare API</span><span class="sxs-lookup"><span data-stu-id="7aed8-175">API usage tab</span></span>

<span data-ttu-id="7aed8-176">Găsiți detalii despre utilizarea API în timp real și vedeți ce evenimente s-au întâmplat într-un interval de timp dat.</span><span class="sxs-lookup"><span data-stu-id="7aed8-176">Find details about the real-time API usage and see which events happened in a given time range.</span></span> <span data-ttu-id="7aed8-177">Pentru mai multe informații, consultați [Ingestie date în timp real](real-time-data-ingestion.md).</span><span class="sxs-lookup"><span data-stu-id="7aed8-177">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>