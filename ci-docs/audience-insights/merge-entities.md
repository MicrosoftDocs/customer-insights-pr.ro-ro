---
title: Îmbinați entitățile în unificarea datelor
description: Îmbinați entitățile pentru a crea profiluri de clienți unificate.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305668"
---
# <a name="merge-entities"></a><span data-ttu-id="782cf-103">Îmbinare entități</span><span class="sxs-lookup"><span data-stu-id="782cf-103">Merge entities</span></span>

<span data-ttu-id="782cf-104">Faza de îmbinare este ultima fază din procesul de unificare a datelor.</span><span class="sxs-lookup"><span data-stu-id="782cf-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="782cf-105">Scopul său este reconcilierea datelor conflictuale.</span><span class="sxs-lookup"><span data-stu-id="782cf-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="782cf-106">Exemple de date conflictuale ar putea include un nume de client care se găsește în două seturi de date, dar care apare puțin diferit în fiecare („Grant Marshall” față de „Grant Marshal”) sau un număr de telefon care diferă în format (617-803-091X versus 617803091X ).</span><span class="sxs-lookup"><span data-stu-id="782cf-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="782cf-107">Fuzionarea acelor puncte de date conflictuale se face pe baza atributelor.</span><span class="sxs-lookup"><span data-stu-id="782cf-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Pagina de îmbinare din procesul de unificare a datelor, afișând tabelul cu câmpuri îmbinate care definesc profilul de client unificat.":::

<span data-ttu-id="782cf-109">După completarea [fazei de potrivire](match-entities.md), începeți faza de îmbinare selectând dala **Îmbinare** pe pagina **Unificare**.</span><span class="sxs-lookup"><span data-stu-id="782cf-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="782cf-110">Revizuiți recomandările sistemului</span><span class="sxs-lookup"><span data-stu-id="782cf-110">Review system recommendations</span></span>

<span data-ttu-id="782cf-111">În secțiunea **Date** > **Unificare** > **Îmbinare**, alegeți și excludeți atributele de îmbinat cu entitatea de profil de client unificat.</span><span class="sxs-lookup"><span data-stu-id="782cf-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="782cf-112">Profilul de client unificat este rezultat al procesului de unificare a datelor.</span><span class="sxs-lookup"><span data-stu-id="782cf-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="782cf-113">Unele atribute sunt combinate automat de sistem.</span><span class="sxs-lookup"><span data-stu-id="782cf-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="782cf-114">Pentru a vedea atributele ce sunt incluse într-unul dintre atributele dvs. îmbinate automat, selectați acel atribut îmbinat în fila de tabel **Câmpurile clienților**.</span><span class="sxs-lookup"><span data-stu-id="782cf-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="782cf-115">Atributele care compun atributul îmbinat apar în două rânduri noi sub atributul îmbinat.</span><span class="sxs-lookup"><span data-stu-id="782cf-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="782cf-116">Separarea, redenumirea, excluderea și editarea câmpurilor îmbinate</span><span class="sxs-lookup"><span data-stu-id="782cf-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="782cf-117">Puteți să modificați modul în care sistemul procesează atributele îmbinate pentru a genera profilul de client unificat.</span><span class="sxs-lookup"><span data-stu-id="782cf-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="782cf-118">Selectați **Afișați mai multe** și alegeți ce vreți să schimbați.</span><span class="sxs-lookup"><span data-stu-id="782cf-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opțiuni din meniul derulant Afișați mai multe pentru a gestiona atributele combinate.":::

<span data-ttu-id="782cf-120">Pentru mai multe informații vedeți secțiunile următoare.</span><span class="sxs-lookup"><span data-stu-id="782cf-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="782cf-121">Câmpuri îmbinate separate</span><span class="sxs-lookup"><span data-stu-id="782cf-121">Separate merged fields</span></span>

<span data-ttu-id="782cf-122">Pentru a separa câmpurile îmbinate, găsiți atributul în tabel.</span><span class="sxs-lookup"><span data-stu-id="782cf-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="782cf-123">Câmpurile separate sunt afișate drept puncte de date individuale în profilul de client unificat.</span><span class="sxs-lookup"><span data-stu-id="782cf-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="782cf-124">Selectați câmpul îmbinat.</span><span class="sxs-lookup"><span data-stu-id="782cf-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="782cf-125">Selectați **Afișați mai multe** și alegeți **Câmpuri separate**.</span><span class="sxs-lookup"><span data-stu-id="782cf-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="782cf-126">Confirmați separarea.</span><span class="sxs-lookup"><span data-stu-id="782cf-126">Confirm the separation.</span></span>

1. <span data-ttu-id="782cf-127">Selectați **Salvare** și **Rulare** pentru a procesa modificările.</span><span class="sxs-lookup"><span data-stu-id="782cf-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="782cf-128">Redenumiți câmpurile îmbinate</span><span class="sxs-lookup"><span data-stu-id="782cf-128">Rename merged fields</span></span>

<span data-ttu-id="782cf-129">Schimbați numele afișat al atributelor combinate.</span><span class="sxs-lookup"><span data-stu-id="782cf-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="782cf-130">Nu puteți modifica numele entității de ieșire.</span><span class="sxs-lookup"><span data-stu-id="782cf-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="782cf-131">Selectați câmpul îmbinat.</span><span class="sxs-lookup"><span data-stu-id="782cf-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="782cf-132">Selectați **Afișați mai multe** și alegeți **Redenumire**.</span><span class="sxs-lookup"><span data-stu-id="782cf-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="782cf-133">Confirmați numele afișat modificat.</span><span class="sxs-lookup"><span data-stu-id="782cf-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="782cf-134">Selectați **Salvare** și **Rulare** pentru a procesa modificările.</span><span class="sxs-lookup"><span data-stu-id="782cf-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="782cf-135">Câmpuri îmbinate excluse</span><span class="sxs-lookup"><span data-stu-id="782cf-135">Exclude merged fields</span></span>

<span data-ttu-id="782cf-136">Excludeți un atribut din profilul de client unificat.</span><span class="sxs-lookup"><span data-stu-id="782cf-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="782cf-137">Dacă câmpul e utilizat în alte procese, de exemplu într-un segment, eliminați-l din aceste procese înainte de a-l exclude din profilul clientului.</span><span class="sxs-lookup"><span data-stu-id="782cf-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="782cf-138">Selectați câmpul îmbinat.</span><span class="sxs-lookup"><span data-stu-id="782cf-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="782cf-139">Selectați **Afișați mai multe** și alegeți **Excludere**.</span><span class="sxs-lookup"><span data-stu-id="782cf-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="782cf-140">Confirmați excluderea.</span><span class="sxs-lookup"><span data-stu-id="782cf-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="782cf-141">Selectați **Salvare** și **Rulare** pentru a procesa modificările.</span><span class="sxs-lookup"><span data-stu-id="782cf-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="782cf-142">Pe pagina **Îmbinare**, selectați **Câmpuri excluse** pentru a vedea lista tuturor câmpurilor excluse.</span><span class="sxs-lookup"><span data-stu-id="782cf-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="782cf-143">Acest panou vă permite să adăugați câmpuri excluse înapoi.</span><span class="sxs-lookup"><span data-stu-id="782cf-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="782cf-144">Îmbinați manual câmpurile</span><span class="sxs-lookup"><span data-stu-id="782cf-144">Manually combine fields</span></span>

<span data-ttu-id="782cf-145">Specificați manual un atribut îmbinat.</span><span class="sxs-lookup"><span data-stu-id="782cf-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="782cf-146">Pe pagina **Combinare**, selectați **Combinați câmpuri**.</span><span class="sxs-lookup"><span data-stu-id="782cf-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="782cf-147">Furnizați un **Nume** și un **Nume al câmpului de ieșire**.</span><span class="sxs-lookup"><span data-stu-id="782cf-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="782cf-148">Alegeți un câmp de adăugat.</span><span class="sxs-lookup"><span data-stu-id="782cf-148">Choose a field to add.</span></span> <span data-ttu-id="782cf-149">Selectați **Adăugați câmpuri** pentru combinarea mai multor câmpuri.</span><span class="sxs-lookup"><span data-stu-id="782cf-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="782cf-150">Confirmați excluderea.</span><span class="sxs-lookup"><span data-stu-id="782cf-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="782cf-151">Selectați **Salvare** și **Rulare** pentru a procesa modificările.</span><span class="sxs-lookup"><span data-stu-id="782cf-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="782cf-152">Modificarea ordinii câmpurilor</span><span class="sxs-lookup"><span data-stu-id="782cf-152">Change the order of fields</span></span>

<span data-ttu-id="782cf-153">Unele entități conțin mai multe detalii decât altele.</span><span class="sxs-lookup"><span data-stu-id="782cf-153">Some entities contain more details than others.</span></span> <span data-ttu-id="782cf-154">Dacă o entitate include cele mai recente date despre un câmp, le puteți oferi prioritate față de alte entități atunci când îmbinați valorile.</span><span class="sxs-lookup"><span data-stu-id="782cf-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="782cf-155">Selectați câmpul îmbinat.</span><span class="sxs-lookup"><span data-stu-id="782cf-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="782cf-156">Selectați **Afișați mai multe** și alegeți **Editare**.</span><span class="sxs-lookup"><span data-stu-id="782cf-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="782cf-157">În panoul **Combinați câmpurile**, selectați **Mutați în sus / în jos** pentru a seta ordinea sau glisați și fixați-le în poziția dorită.</span><span class="sxs-lookup"><span data-stu-id="782cf-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="782cf-158">Confirmați modificarea.</span><span class="sxs-lookup"><span data-stu-id="782cf-158">Confirm the change.</span></span>

1. <span data-ttu-id="782cf-159">Selectați **Salvare** și **Rulare** pentru a procesa modificările.</span><span class="sxs-lookup"><span data-stu-id="782cf-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="782cf-160">Executați-vă unificarea</span><span class="sxs-lookup"><span data-stu-id="782cf-160">Run your merge</span></span>

<span data-ttu-id="782cf-161">Indiferent dacă fuzionați manual atributele sau lăsați sistemul să le îmbine, puteți rula întotdeauna fuziunea.</span><span class="sxs-lookup"><span data-stu-id="782cf-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="782cf-162">Selectați **Executare** pe pagina **Îmbinare** pentru a porni procesul.</span><span class="sxs-lookup"><span data-stu-id="782cf-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="782cf-163">![Îmbinare date Salvați și rulați](media/configure-data-merge-save-run.png "Îmbinare date Salvați și rulați")</span><span class="sxs-lookup"><span data-stu-id="782cf-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="782cf-164">Alege **Rulați numai îmbinarea** dacă doriți doar să vedeți rezultatul reflectat în entitatea client unificată.</span><span class="sxs-lookup"><span data-stu-id="782cf-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="782cf-165">Procesele din aval vor fi reîmprospătate ca [definite în programul de reîmprospătare](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="782cf-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="782cf-166">Alegeți **Rulați procesele de îmbinare și flux spre aval** pentru a reîmprospăta sistemul cu modificările dvs.</span><span class="sxs-lookup"><span data-stu-id="782cf-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="782cf-167">Toate procesele, inclusiv îmbogățirea, segmentele și măsurile vor fi reluate automat.</span><span class="sxs-lookup"><span data-stu-id="782cf-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="782cf-168">După ce toate procesele din aval s-au finalizat, profilurile clienților reflectă orice modificare făcută.</span><span class="sxs-lookup"><span data-stu-id="782cf-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="782cf-169">Pentru a face mai multe modificări și a relua pasul, puteți anula o îmbinare în curs.</span><span class="sxs-lookup"><span data-stu-id="782cf-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="782cf-170">Selectați **Se reîmprospătează ...** și selectați **Anulare operațiune** în panoul lateral care apare.</span><span class="sxs-lookup"><span data-stu-id="782cf-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="782cf-171">Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese.</span><span class="sxs-lookup"><span data-stu-id="782cf-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="782cf-172">În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="782cf-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="782cf-173">Puteți selecta starea unui proces pentru a vedea detalii despre evoluția întregii lucrări.</span><span class="sxs-lookup"><span data-stu-id="782cf-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="782cf-174">După selectarea **Vizualizare detalii** pentru una dintre sarcinile jobului, găsiți informații suplimentare: timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate sarcinii.</span><span class="sxs-lookup"><span data-stu-id="782cf-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="782cf-175">Următorul pas</span><span class="sxs-lookup"><span data-stu-id="782cf-175">Next Step</span></span>

<span data-ttu-id="782cf-176">Configurați [Activități](activities.md), [Îmbogățire](enrichment-hub.md), sau [Relații](relationships.md) pentru a obține mai multe informații despre clienți.</span><span class="sxs-lookup"><span data-stu-id="782cf-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="782cf-177">Dacă ați configurat deja activități, îmbogățire sau segmente, acestea vor fi procesate automat pentru a utiliza cele mai recente date despre clienți.</span><span class="sxs-lookup"><span data-stu-id="782cf-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
