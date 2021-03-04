---
title: Îmbinați entitățile în unificarea datelor
description: Îmbinați entitățile pentru a crea profiluri de clienți unificate.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 5d5ff4c6f091d1b50d0f6c8366bbe4f0e6428dac
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268517"
---
# <a name="merge-entities"></a><span data-ttu-id="616ab-103">Îmbinare entități</span><span class="sxs-lookup"><span data-stu-id="616ab-103">Merge entities</span></span>

<span data-ttu-id="616ab-104">Faza de îmbinare este ultima fază din procesul de unificare a datelor.</span><span class="sxs-lookup"><span data-stu-id="616ab-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="616ab-105">Scopul său este reconcilierea datelor conflictuale.</span><span class="sxs-lookup"><span data-stu-id="616ab-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="616ab-106">Exemple de date conflictuale ar putea include un nume de client care se găsește în două seturi de date, dar care apare puțin diferit în fiecare („Grant Marshall” față de „Grant Marshal”) sau un număr de telefon care diferă în format (617-803-091X versus 617803091X ).</span><span class="sxs-lookup"><span data-stu-id="616ab-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="616ab-107">Fuzionarea acelor puncte de date conflictuale se face pe baza atributelor.</span><span class="sxs-lookup"><span data-stu-id="616ab-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="616ab-108">După completarea [fazei de potrivire](match-entities.md), începeți faza de îmbinare selectând dala **Îmbinare** pe pagina **Unificare**.</span><span class="sxs-lookup"><span data-stu-id="616ab-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="616ab-109">Revizuiți recomandările sistemului</span><span class="sxs-lookup"><span data-stu-id="616ab-109">Review system recommendations</span></span>

<span data-ttu-id="616ab-110">Pe pagina **Îmbinare**, alegeți și excludeți atributele de îmbinat în cadrul entității dvs. de profil de client unificat (rezultatul procesului de configurare).</span><span class="sxs-lookup"><span data-stu-id="616ab-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="616ab-111">Unele atribute sunt combinate automat de sistem.</span><span class="sxs-lookup"><span data-stu-id="616ab-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="616ab-112">Vizualizare atribute îmbinate</span><span class="sxs-lookup"><span data-stu-id="616ab-112">View merged attributes</span></span>

<span data-ttu-id="616ab-113">Pentru a vizualiza atributele care sunt incluse într-unul dintre atributele combinate automat, selectați acel atribut combinat.</span><span class="sxs-lookup"><span data-stu-id="616ab-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="616ab-114">Cele două atribute care compun acel atribut combinat apar în două rânduri noi sub atributul îmbinat.</span><span class="sxs-lookup"><span data-stu-id="616ab-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="616ab-115">![Selectați atributul îmbinat](media/configure-data-merge-profile-attributes.png "Selectați atributul îmbinat")</span><span class="sxs-lookup"><span data-stu-id="616ab-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="616ab-116">Separați atribute îmbinate</span><span class="sxs-lookup"><span data-stu-id="616ab-116">Separate merged attributes</span></span>

<span data-ttu-id="616ab-117">Pentru a separa sau a despărți oricare dintre atributele combinate automat, găsiți atributul în tabelul **Atribute profil**.</span><span class="sxs-lookup"><span data-stu-id="616ab-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="616ab-118">Selectați butonul elipsă (...).</span><span class="sxs-lookup"><span data-stu-id="616ab-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="616ab-119">În lista verticală, selectați **Câmpuri separate**.</span><span class="sxs-lookup"><span data-stu-id="616ab-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="616ab-120">Eliminați atribute îmbinate</span><span class="sxs-lookup"><span data-stu-id="616ab-120">Remove merged attributes</span></span>

<span data-ttu-id="616ab-121">Pentru a exclude un atribut de la entitatea profilului de client final, găsiți-l în tabelul **Atribute profil**.</span><span class="sxs-lookup"><span data-stu-id="616ab-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="616ab-122">Selectați butonul elipsă (...).</span><span class="sxs-lookup"><span data-stu-id="616ab-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="616ab-123">În lista verticală, selectați **Nu îmbinați**.</span><span class="sxs-lookup"><span data-stu-id="616ab-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="616ab-124">Atributul este mutat la secțiunea **Eliminat din înregistrarea client**.</span><span class="sxs-lookup"><span data-stu-id="616ab-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="616ab-125">Adăugați manual un atribut combinat</span><span class="sxs-lookup"><span data-stu-id="616ab-125">Manually add a merged attribute</span></span>

<span data-ttu-id="616ab-126">Pentru a adăuga un atribut combinat, accesați pagina **Îmbinare**.</span><span class="sxs-lookup"><span data-stu-id="616ab-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="616ab-127">Selectați **Adăugați atributul îmbinat**.</span><span class="sxs-lookup"><span data-stu-id="616ab-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="616ab-128">Furnizați un **Nume** pentru a-l identifica mai târziu pe pagina **Îmbinare**.</span><span class="sxs-lookup"><span data-stu-id="616ab-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="616ab-129">Opțional, furnizați un **Numele afișat** ce apare în entitatea de profil a clientului unificată.</span><span class="sxs-lookup"><span data-stu-id="616ab-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="616ab-130">Configurare **Selectați atributele dublate** pentru a selecta atributele pe care doriți să le îmbinați dintre entitățile potrivite.</span><span class="sxs-lookup"><span data-stu-id="616ab-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="616ab-131">De asemenea, puteți căuta atribute.</span><span class="sxs-lookup"><span data-stu-id="616ab-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="616ab-132">Configurați **Clasificare după importanță** pentru a acorda prioritate unui atribut asupra celorlalte.</span><span class="sxs-lookup"><span data-stu-id="616ab-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="616ab-133">De exemplu, dacă entitatea *WebAccountCSV* include cele mai precise date despre atribute *Nume complete*, puteți acorda prioritate acestei entități *ContactCSV* prin selectarea *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="616ab-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="616ab-134">Ca urmare, *WebAccountCSV* trece la prima prioritate, în timp ce *ContactCSV* trece la a doua prioritate atunci când asamblați valori pentru atributul *Numele complet*.</span><span class="sxs-lookup"><span data-stu-id="616ab-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="616ab-135">Executați-vă unificarea</span><span class="sxs-lookup"><span data-stu-id="616ab-135">Run your merge</span></span>

<span data-ttu-id="616ab-136">Indiferent dacă fuzionați manual atributele sau lăsați sistemul să le îmbine, puteți rula întotdeauna fuziunea.</span><span class="sxs-lookup"><span data-stu-id="616ab-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="616ab-137">Selectați **Executare** pe pagina **Îmbinare** pentru a porni procesul.</span><span class="sxs-lookup"><span data-stu-id="616ab-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="616ab-138">![Îmbinare date Salvați și rulați](media/configure-data-merge-save-run.png "Îmbinare date Salvați și rulați")</span><span class="sxs-lookup"><span data-stu-id="616ab-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="616ab-139">Pentru a face modificări suplimentare și a relua pasul, puteți anula o îmbinare în curs.</span><span class="sxs-lookup"><span data-stu-id="616ab-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="616ab-140">Selectați **Se reîmprospătează ...** și selectați **Anulare operațiune** în panoul lateral care apare.</span><span class="sxs-lookup"><span data-stu-id="616ab-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="616ab-141">După schimbarea textului de la **Se reîmprospătează ...** la **Reușit**, îmbinarea s-a finalizat și a rezolvat contradicțiile din datele dvs. în conformitate cu politicile pe care le-ați definit.</span><span class="sxs-lookup"><span data-stu-id="616ab-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="616ab-142">Atributele îmbinate și neîmbinate sunt incluse în entitatea de profil unificat.</span><span class="sxs-lookup"><span data-stu-id="616ab-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="616ab-143">Atributele excluse nu sunt incluse în entitatea de profil unificat.</span><span class="sxs-lookup"><span data-stu-id="616ab-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="616ab-144">Dacă nu a fost prima dată când ați executat o îmbinare cu succes, toate procesele din aval, inclusiv îmbogățirea, segmentarea și măsurile se vor repeta în mod automat.</span><span class="sxs-lookup"><span data-stu-id="616ab-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="616ab-145">După ce toate procesele din aval au fost reluate, profilurile clienților reflectă orice modificări pe care le-ați efectuat.</span><span class="sxs-lookup"><span data-stu-id="616ab-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="616ab-146">Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese.</span><span class="sxs-lookup"><span data-stu-id="616ab-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="616ab-147">În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="616ab-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="616ab-148">Puteți selecta starea unui proces pentru a vedea detalii despre evoluția întregii lucrări.</span><span class="sxs-lookup"><span data-stu-id="616ab-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="616ab-149">După selectarea **Vizualizare detalii** pentru una dintre sarcinile jobului, găsiți informații suplimentare: timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate sarcinii.</span><span class="sxs-lookup"><span data-stu-id="616ab-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="616ab-150">Următorul pas</span><span class="sxs-lookup"><span data-stu-id="616ab-150">Next Step</span></span>

<span data-ttu-id="616ab-151">Configurați [Activități](activities.md), [Îmbogățire](enrichment-microsoft-graph.md), sau [Relații](relationships.md) pentru a obține mai multe informații despre clienți.</span><span class="sxs-lookup"><span data-stu-id="616ab-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="616ab-152">Dacă ați configurat deja activități, îmbogățire sau relații sau dacă ați definit segmente, acestea vor fi procesate automat pentru a utiliza cele mai recente date despre clienți.</span><span class="sxs-lookup"><span data-stu-id="616ab-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]