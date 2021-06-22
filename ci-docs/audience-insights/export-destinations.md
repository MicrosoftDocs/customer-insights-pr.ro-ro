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
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253055"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="1b682-103">Prezentare generală a exporturilor (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="1b682-103">Exports (preview) overview</span></span>

<span data-ttu-id="1b682-104">Pagina **Exporturi** vă arată toate exporturile configurate.</span><span class="sxs-lookup"><span data-stu-id="1b682-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="1b682-105">Exporturile partajează date specifice cu diferite aplicații.</span><span class="sxs-lookup"><span data-stu-id="1b682-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="1b682-106">Ele pot include profiluri sau entități ale clienților, scheme și detalii de mapare.</span><span class="sxs-lookup"><span data-stu-id="1b682-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="1b682-107">Fiecare export necesită o [conexiune, configurată de un administrator, pentru a gestiona autentificarea și accesul](connections.md).</span><span class="sxs-lookup"><span data-stu-id="1b682-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="1b682-108">Faceți salt la **Date** > **Exporturi** pentru a vizualiza pagina exporturilor.</span><span class="sxs-lookup"><span data-stu-id="1b682-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="1b682-109">Toate rolurile utilizatorilor au acces la vizualizarea exporturilor configurate.</span><span class="sxs-lookup"><span data-stu-id="1b682-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="1b682-110">Utilizarea câmpului de căutare din bara de comandă pentru a găsi exporturile după nume, numele conexiunii sau tipul conexiunii.</span><span class="sxs-lookup"><span data-stu-id="1b682-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="1b682-111">Configurați un nou export</span><span class="sxs-lookup"><span data-stu-id="1b682-111">Set up a new export</span></span>

<span data-ttu-id="1b682-112">Pentru a configura sau edita un export, trebuie să existe conexiuni disponibile pentru dvs.</span><span class="sxs-lookup"><span data-stu-id="1b682-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="1b682-113">Conexiunile depind de [rolul dvs. de utilizator](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="1b682-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="1b682-114">Administratorii au acces la toate conexiunile.</span><span class="sxs-lookup"><span data-stu-id="1b682-114">Administrators have access to all connections.</span></span> <span data-ttu-id="1b682-115">De asemenea, pot crea conexiuni noi atunci când configurează un export.</span><span class="sxs-lookup"><span data-stu-id="1b682-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="1b682-116">Contribuitorii pot avea acces la conexiuni specifice.</span><span class="sxs-lookup"><span data-stu-id="1b682-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="1b682-117">Acestea depind de administratori pentru a configura și partaja conexiuni.</span><span class="sxs-lookup"><span data-stu-id="1b682-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="1b682-118">Lista exporturilor afișează contribuabili dacă pot edita sau vizualiza doar un export în coloana **Permisiuni**.</span><span class="sxs-lookup"><span data-stu-id="1b682-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="1b682-119">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1b682-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="1b682-120">Spectatorii pot vizualiza doar exporturile existente, dar nu le pot crea.</span><span class="sxs-lookup"><span data-stu-id="1b682-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="1b682-121">Definiți un nou export</span><span class="sxs-lookup"><span data-stu-id="1b682-121">Define a new export</span></span>

1. <span data-ttu-id="1b682-122">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="1b682-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1b682-123">Pentru a crea un nou export, selectați **Adăugare export**.</span><span class="sxs-lookup"><span data-stu-id="1b682-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="1b682-124">În panoul **Configurați exportul**, selectați ce conexiune să utilizați.</span><span class="sxs-lookup"><span data-stu-id="1b682-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="1b682-125">[Conexiunile](connections.md) sunt gestionate de administratori.</span><span class="sxs-lookup"><span data-stu-id="1b682-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="1b682-126">Furnizați detaliile necesare și selectați **Salvare** pentru a crea exportul.</span><span class="sxs-lookup"><span data-stu-id="1b682-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="1b682-127">Definiți un nou export pe baza unui export existent</span><span class="sxs-lookup"><span data-stu-id="1b682-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="1b682-128">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="1b682-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1b682-129">În lista de exporturi, selectați exportul pe care doriți să îl duplicați.</span><span class="sxs-lookup"><span data-stu-id="1b682-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="1b682-130">Selectați **Creați duplicat** în bara de comandă pentru a deschide panoul **Configurați exportul** cu detaliile exportului selectat.</span><span class="sxs-lookup"><span data-stu-id="1b682-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="1b682-131">Examinați și adaptați exportul și selectați **Salvați** pentru a crea un nou export.</span><span class="sxs-lookup"><span data-stu-id="1b682-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="1b682-132">Editarea unui export</span><span class="sxs-lookup"><span data-stu-id="1b682-132">Edit an export</span></span>

1. <span data-ttu-id="1b682-133">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="1b682-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1b682-134">În lista de exporturi, selectați exportul pe care doriți să îl editați.</span><span class="sxs-lookup"><span data-stu-id="1b682-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="1b682-135">Pe bara de comenzi, selectați **Editare**.</span><span class="sxs-lookup"><span data-stu-id="1b682-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="1b682-136">Schimbați valorile pe care doriți să le actualizați și selectați **Salvați**.</span><span class="sxs-lookup"><span data-stu-id="1b682-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="1b682-137">Vizualizați exporturi și detalii despre export</span><span class="sxs-lookup"><span data-stu-id="1b682-137">View exports and export details</span></span>

<span data-ttu-id="1b682-138">După crearea destinațiilor de export, acestea sunt listate pe **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="1b682-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="1b682-139">Toți utilizatorii pot vedea ce date sunt partajate și starea cea mai recentă a acestora.</span><span class="sxs-lookup"><span data-stu-id="1b682-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="1b682-140">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="1b682-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1b682-141">Utilizatorii fără permisiuni de editare selectează **Vizualizare** în loc de **Editare** pentru a vizualiza detaliile exportului.</span><span class="sxs-lookup"><span data-stu-id="1b682-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="1b682-142">Panoul lateral arată configurația unui export.</span><span class="sxs-lookup"><span data-stu-id="1b682-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="1b682-143">Fără permisiuni de editare, nu puteți modifica valorile.</span><span class="sxs-lookup"><span data-stu-id="1b682-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="1b682-144">Selectați **Închidere** pentru a reveni la pagina de exporturi.</span><span class="sxs-lookup"><span data-stu-id="1b682-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="1b682-145">Planificați și rulați exporturile</span><span class="sxs-lookup"><span data-stu-id="1b682-145">Schedule and run exports</span></span>

<span data-ttu-id="1b682-146">Fiecare export pe care îl configurați are o planificare de reîmprospătare.</span><span class="sxs-lookup"><span data-stu-id="1b682-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="1b682-147">În timpul unei reîmprospătări, sistemul caută date noi sau actualizate pentru a le include într-un export.</span><span class="sxs-lookup"><span data-stu-id="1b682-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="1b682-148">În mod implicit, exporturile sunt executate ca parte a fiecărui [reîmprospătare planificată a sistemului](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1b682-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1b682-149">Puteți particulariza planificarea de reîmprospătare sau îl puteți dezactiva pentru a rula manual exporturile.</span><span class="sxs-lookup"><span data-stu-id="1b682-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="1b682-150">Planificările de export depind de starea mediului dvs.</span><span class="sxs-lookup"><span data-stu-id="1b682-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="1b682-151">Dacă există actualizări pe [dependențele](system.md#refresh-policies) în curs când ar trebui să înceapă un export planificat, sistemul va finaliza mai întâi dependențele și apoi va rula exportul.</span><span class="sxs-lookup"><span data-stu-id="1b682-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="1b682-152">Puteți vedea când a fost actualizat ultima oară exportul în coloana **Reîmprospătat**.</span><span class="sxs-lookup"><span data-stu-id="1b682-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="1b682-153">Planificare export</span><span class="sxs-lookup"><span data-stu-id="1b682-153">Schedule exports</span></span>

<span data-ttu-id="1b682-154">Puteți defini planificări de reîmprospătare particularizate pentru exporturi individuale sau mai multe exporturi simultan.</span><span class="sxs-lookup"><span data-stu-id="1b682-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="1b682-155">Planificarea definită în prezent este listată în coloana listei de export **Planificare**.</span><span class="sxs-lookup"><span data-stu-id="1b682-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="1b682-156">Permisiunea de a schimba planificarea este aceeași ca și pentru [editarea și definirea exporturilor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1b682-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="1b682-157">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="1b682-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1b682-158">Selectați exportul pe care doriți să-l planificați.</span><span class="sxs-lookup"><span data-stu-id="1b682-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="1b682-159">Pe bara de comenzi, selectați **Planificare**.</span><span class="sxs-lookup"><span data-stu-id="1b682-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="1b682-160">În **Planificarea exportului**, setați **Planificarea executării** la **Pornit** pentru a rula automat exportul.</span><span class="sxs-lookup"><span data-stu-id="1b682-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="1b682-161">Setați-l la **Dezactivat** pentru a-l reîmprospăta manual.</span><span class="sxs-lookup"><span data-stu-id="1b682-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="1b682-162">Pentru exporturile actualizate automat, alegeți o valoare **Recurență** și specificați detaliile pentru aceasta.</span><span class="sxs-lookup"><span data-stu-id="1b682-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="1b682-163">Timpul definit se aplică tuturor cazurilor de recurență.</span><span class="sxs-lookup"><span data-stu-id="1b682-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="1b682-164">Este momentul în care un export ar trebui să înceapă reîmprospătarea.</span><span class="sxs-lookup"><span data-stu-id="1b682-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="1b682-165">Aplicați și activați modificările selectând **Salvați**.</span><span class="sxs-lookup"><span data-stu-id="1b682-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="1b682-166">Când editați planificarea pentru mai multe exporturi, trebuie să faceți o selecție în **Păstrați sau înlocuiți planificările**:</span><span class="sxs-lookup"><span data-stu-id="1b682-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="1b682-167">**Păstrați planificările individuale**: Persistați planificarea definită anterior pentru exporturile selectate și dezactivați-le sau numai activați-le.</span><span class="sxs-lookup"><span data-stu-id="1b682-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="1b682-168">**Definiți o planificare nouă pentru toate exporturile selectate**: Înlocuiți planificările existente ale exporturilor selectate.</span><span class="sxs-lookup"><span data-stu-id="1b682-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="1b682-169">Executați exporturi la cerere</span><span class="sxs-lookup"><span data-stu-id="1b682-169">Run exports on demand</span></span>

<span data-ttu-id="1b682-170">Pentru a exporta date fără a aștepta o reîmprospătare programată, accesați **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="1b682-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="1b682-171">Pentru a rula toate exporturile, selectați **Executare totală** în bara de comandă.</span><span class="sxs-lookup"><span data-stu-id="1b682-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="1b682-172">Această acțiune va executa numai exporturi care au o planificare activă.</span><span class="sxs-lookup"><span data-stu-id="1b682-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="1b682-173">Pentru a rula un singur export, selectați-l în listă și selectați **Executare** în bara de comandă.</span><span class="sxs-lookup"><span data-stu-id="1b682-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="1b682-174">Așa executați exporturile fără planificare activă.</span><span class="sxs-lookup"><span data-stu-id="1b682-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="1b682-175">Eliminați un export</span><span class="sxs-lookup"><span data-stu-id="1b682-175">Remove an Export</span></span>

1. <span data-ttu-id="1b682-176">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="1b682-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1b682-177">Selectați exportul de eliminat.</span><span class="sxs-lookup"><span data-stu-id="1b682-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="1b682-178">Pe bara de comenzi, selectați **Eliminare**.</span><span class="sxs-lookup"><span data-stu-id="1b682-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="1b682-179">Confirmați eliminarea selectând **Eliminare** pe ecranul de confirmare.</span><span class="sxs-lookup"><span data-stu-id="1b682-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
