---
title: Exportați date din Customer Insights
description: Gestionați exporturile către partajare date.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305493"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="70bb4-103">Prezentare generală a exporturilor (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="70bb4-103">Exports (preview) overview</span></span>

<span data-ttu-id="70bb4-104">Pagina **Exporturi** vă arată toate exporturile configurate.</span><span class="sxs-lookup"><span data-stu-id="70bb4-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="70bb4-105">Exporturile partajează date specifice cu diferite aplicații.</span><span class="sxs-lookup"><span data-stu-id="70bb4-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="70bb4-106">Ele pot include profiluri sau entități ale clienților, scheme și detalii de mapare.</span><span class="sxs-lookup"><span data-stu-id="70bb4-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="70bb4-107">Fiecare export necesită o [conexiune, configurată de un administrator, pentru a gestiona autentificarea și accesul](connections.md).</span><span class="sxs-lookup"><span data-stu-id="70bb4-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="70bb4-108">Faceți salt la **Date** > **Exporturi** pentru a vizualiza pagina exporturilor.</span><span class="sxs-lookup"><span data-stu-id="70bb4-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="70bb4-109">Toate rolurile de utilizatori pot vizualiza exporturile configurate.</span><span class="sxs-lookup"><span data-stu-id="70bb4-109">All user roles can view configured exports.</span></span> <span data-ttu-id="70bb4-110">Utilizați câmpul de căutare din bara de comenzi pentru a găsi exporturile după numele, numele conexiunii sau tipul conexiunii.</span><span class="sxs-lookup"><span data-stu-id="70bb4-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="70bb4-111">Configurați un nou export</span><span class="sxs-lookup"><span data-stu-id="70bb4-111">Set up a new export</span></span>

<span data-ttu-id="70bb4-112">Pentru a configura sau edita un export, trebuie să existe conexiuni disponibile pentru dvs.</span><span class="sxs-lookup"><span data-stu-id="70bb4-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="70bb4-113">Conexiunile depind de [rolul dvs. de utilizator](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="70bb4-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="70bb4-114">Administratorii au acces la toate conexiunile.</span><span class="sxs-lookup"><span data-stu-id="70bb4-114">Administrators have access to all connections.</span></span> <span data-ttu-id="70bb4-115">De asemenea, pot crea conexiuni noi atunci când configurează un export.</span><span class="sxs-lookup"><span data-stu-id="70bb4-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="70bb4-116">Contribuitorii pot avea acces la conexiuni specifice.</span><span class="sxs-lookup"><span data-stu-id="70bb4-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="70bb4-117">Acestea depind de administratori pentru a configura și partaja conexiuni.</span><span class="sxs-lookup"><span data-stu-id="70bb4-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="70bb4-118">Lista exporturilor afișează contribuabili dacă pot edita sau vizualiza doar un export în coloana **Permisiuni**.</span><span class="sxs-lookup"><span data-stu-id="70bb4-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="70bb4-119">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="70bb4-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="70bb4-120">Spectatorii pot vizualiza doar exporturile existente, dar nu le pot crea.</span><span class="sxs-lookup"><span data-stu-id="70bb4-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="70bb4-121">Definiți un nou export</span><span class="sxs-lookup"><span data-stu-id="70bb4-121">Define a new export</span></span>

1. <span data-ttu-id="70bb4-122">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="70bb4-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="70bb4-123">Pentru a crea un nou export, selectați **Adăugare export**.</span><span class="sxs-lookup"><span data-stu-id="70bb4-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="70bb4-124">În panoul **Configurați exportul**, selectați ce conexiune să utilizați.</span><span class="sxs-lookup"><span data-stu-id="70bb4-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="70bb4-125">[Conexiunile](connections.md) sunt gestionate de administratori.</span><span class="sxs-lookup"><span data-stu-id="70bb4-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="70bb4-126">Furnizați detaliile necesare și selectați **Salvare** pentru a crea exportul.</span><span class="sxs-lookup"><span data-stu-id="70bb4-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="70bb4-127">Definiți un nou export pe baza unui export existent</span><span class="sxs-lookup"><span data-stu-id="70bb4-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="70bb4-128">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="70bb4-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="70bb4-129">În lista de exporturi, selectați exportul pe care doriți să îl duplicați.</span><span class="sxs-lookup"><span data-stu-id="70bb4-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="70bb4-130">Selectați **Creați duplicat** în bara de comandă pentru a deschide panoul **Configurați exportul** cu detaliile exportului selectat.</span><span class="sxs-lookup"><span data-stu-id="70bb4-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="70bb4-131">Examinați și adaptați exportul și selectați **Salvați** pentru a crea un nou export.</span><span class="sxs-lookup"><span data-stu-id="70bb4-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="70bb4-132">Editarea unui export</span><span class="sxs-lookup"><span data-stu-id="70bb4-132">Edit an export</span></span>

1. <span data-ttu-id="70bb4-133">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="70bb4-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="70bb4-134">În lista de exporturi, selectați exportul pe care doriți să îl editați.</span><span class="sxs-lookup"><span data-stu-id="70bb4-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="70bb4-135">Pe bara de comenzi, selectați **Editare**.</span><span class="sxs-lookup"><span data-stu-id="70bb4-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="70bb4-136">Schimbați valorile pe care doriți să le actualizați și selectați **Salvați**.</span><span class="sxs-lookup"><span data-stu-id="70bb4-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="70bb4-137">Vizualizați exporturi și detalii despre export</span><span class="sxs-lookup"><span data-stu-id="70bb4-137">View exports and export details</span></span>

<span data-ttu-id="70bb4-138">După crearea destinațiilor de export, acestea sunt listate pe **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="70bb4-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="70bb4-139">Toți utilizatorii pot vedea ce date sunt partajate și starea cea mai recentă a acestora.</span><span class="sxs-lookup"><span data-stu-id="70bb4-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="70bb4-140">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="70bb4-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="70bb4-141">Utilizatorii fără permisiuni de editare selectează **Vizualizare** în loc de **Editați** pentru a vedea detaliile exportului.</span><span class="sxs-lookup"><span data-stu-id="70bb4-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="70bb4-142">Panoul lateral arată configurația unui export.</span><span class="sxs-lookup"><span data-stu-id="70bb4-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="70bb4-143">Fără permisiuni de editare, nu puteți modifica valorile.</span><span class="sxs-lookup"><span data-stu-id="70bb4-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="70bb4-144">Selectați **Închidere** pentru a reveni la pagina de exporturi.</span><span class="sxs-lookup"><span data-stu-id="70bb4-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="70bb4-145">Planificați și rulați exporturile</span><span class="sxs-lookup"><span data-stu-id="70bb4-145">Schedule and run exports</span></span>

<span data-ttu-id="70bb4-146">Fiecare export pe care îl configurați are o planificare de reîmprospătare.</span><span class="sxs-lookup"><span data-stu-id="70bb4-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="70bb4-147">În timpul unei reîmprospătări, sistemul caută date noi sau actualizate pentru a le include într-un export.</span><span class="sxs-lookup"><span data-stu-id="70bb4-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="70bb4-148">În mod implicit, exporturile sunt executate ca parte a fiecărui [reîmprospătare planificată a sistemului](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="70bb4-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="70bb4-149">Puteți particulariza planificarea de reîmprospătare sau îl puteți dezactiva pentru a rula manual exporturile.</span><span class="sxs-lookup"><span data-stu-id="70bb4-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="70bb4-150">Planificările de export depind de starea mediului dvs.</span><span class="sxs-lookup"><span data-stu-id="70bb4-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="70bb4-151">Dacă există actualizări în curs pe [dependențe](system.md#refresh-policies) când ar trebui să înceapă un export planificat, sistemul va finaliza mai întâi actualizările și apoi va rula exportul.</span><span class="sxs-lookup"><span data-stu-id="70bb4-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="70bb4-152">Puteți vedea când a fost actualizat ultima oară exportul în coloana **Reîmprospătat**.</span><span class="sxs-lookup"><span data-stu-id="70bb4-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="70bb4-153">Planificare export</span><span class="sxs-lookup"><span data-stu-id="70bb4-153">Schedule exports</span></span>

<span data-ttu-id="70bb4-154">Puteți defini planificări de reîmprospătare particularizate pentru exporturi individuale sau mai multe exporturi simultan.</span><span class="sxs-lookup"><span data-stu-id="70bb4-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="70bb4-155">Planificarea definită în prezent este listată în coloana listei de export **Planificare**.</span><span class="sxs-lookup"><span data-stu-id="70bb4-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="70bb4-156">Permisiunea de a schimba planificarea este aceeași ca și pentru [editarea și definirea exporturilor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="70bb4-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="70bb4-157">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="70bb4-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="70bb4-158">Selectați exportul pe care doriți să-l planificați.</span><span class="sxs-lookup"><span data-stu-id="70bb4-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="70bb4-159">Pe bara de comenzi, selectați **Planificare**.</span><span class="sxs-lookup"><span data-stu-id="70bb4-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="70bb4-160">În **Planificarea exportului**, setați **Planificarea executării** la **Pornit** pentru a rula automat exportul.</span><span class="sxs-lookup"><span data-stu-id="70bb4-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="70bb4-161">Setați-l la **Dezactivat** pentru a-l reîmprospăta manual.</span><span class="sxs-lookup"><span data-stu-id="70bb4-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="70bb4-162">Pentru exporturile actualizate automat, alegeți o valoare **Recurență** și specificați detaliile pentru aceasta.</span><span class="sxs-lookup"><span data-stu-id="70bb4-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="70bb4-163">Timpul definit se aplică tuturor cazurilor de recurență.</span><span class="sxs-lookup"><span data-stu-id="70bb4-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="70bb4-164">Este momentul în care un export ar trebui să înceapă reîmprospătarea.</span><span class="sxs-lookup"><span data-stu-id="70bb4-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="70bb4-165">Aplicați și activați modificările selectând **Salvați**.</span><span class="sxs-lookup"><span data-stu-id="70bb4-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="70bb4-166">Când editați planificarea pentru mai multe exporturi, trebuie să faceți o selecție în **Păstrați sau înlocuiți planificările**:</span><span class="sxs-lookup"><span data-stu-id="70bb4-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="70bb4-167">**Păstrați planificările individuale**: Persistați planificarea definită anterior pentru exporturile selectate și dezactivați-le sau numai activați-le.</span><span class="sxs-lookup"><span data-stu-id="70bb4-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="70bb4-168">**Definiți o planificare nouă pentru toate exporturile selectate**: Înlocuiți planificările existente ale exporturilor selectate.</span><span class="sxs-lookup"><span data-stu-id="70bb4-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="70bb4-169">Executați exporturi la cerere</span><span class="sxs-lookup"><span data-stu-id="70bb4-169">Run exports on demand</span></span>

<span data-ttu-id="70bb4-170">Pentru a exporta date fără a aștepta o reîmprospătare programată, accesați **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="70bb4-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="70bb4-171">Pentru a rula toate exporturile, selectați **Executare totală** în bara de comandă.</span><span class="sxs-lookup"><span data-stu-id="70bb4-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="70bb4-172">Această acțiune va executa numai exporturi care au o planificare activă.</span><span class="sxs-lookup"><span data-stu-id="70bb4-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="70bb4-173">Pentru a rula un singur export, selectați-l în listă și selectați **Executare** în bara de comandă.</span><span class="sxs-lookup"><span data-stu-id="70bb4-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="70bb4-174">Așa executați exporturile fără planificare activă.</span><span class="sxs-lookup"><span data-stu-id="70bb4-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="70bb4-175">Eliminați un export</span><span class="sxs-lookup"><span data-stu-id="70bb4-175">Remove an Export</span></span>

1. <span data-ttu-id="70bb4-176">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="70bb4-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="70bb4-177">Selectați exportul de eliminat.</span><span class="sxs-lookup"><span data-stu-id="70bb4-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="70bb4-178">Pe bara de comenzi, selectați **Eliminare**.</span><span class="sxs-lookup"><span data-stu-id="70bb4-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="70bb4-179">Confirmați eliminarea selectând **Eliminare** pe ecranul de confirmare.</span><span class="sxs-lookup"><span data-stu-id="70bb4-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
