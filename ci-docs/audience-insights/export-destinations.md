---
title: Exportați date din Customer Insights
description: Gestionați exporturile către partajare date.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016651"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="e4843-103">Prezentare generală a exporturilor (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="e4843-103">Exports (preview) overview</span></span>

<span data-ttu-id="e4843-104">Pagina **Exporturi** vă arată toate exporturile configurate.</span><span class="sxs-lookup"><span data-stu-id="e4843-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="e4843-105">Exporturile partajează date specifice cu diferite aplicații.</span><span class="sxs-lookup"><span data-stu-id="e4843-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="e4843-106">Ele pot include profiluri sau entități ale clienților, scheme și detalii de mapare.</span><span class="sxs-lookup"><span data-stu-id="e4843-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="e4843-107">Fiecare export necesită o [conexiune, configurată de un administrator, pentru a gestiona autentificarea și accesul](connections.md).</span><span class="sxs-lookup"><span data-stu-id="e4843-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="e4843-108">Faceți salt la **Date** > **Exporturi** pentru a vizualiza pagina exporturilor.</span><span class="sxs-lookup"><span data-stu-id="e4843-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="e4843-109">Toate rolurile utilizatorilor au acces la vizualizarea exporturilor configurate.</span><span class="sxs-lookup"><span data-stu-id="e4843-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="e4843-110">Utilizarea câmpului de căutare din bara de comandă pentru a găsi exporturile după nume, numele conexiunii sau tipul conexiunii.</span><span class="sxs-lookup"><span data-stu-id="e4843-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="e4843-111">Configurați un nou export</span><span class="sxs-lookup"><span data-stu-id="e4843-111">Set up a new export</span></span>

<span data-ttu-id="e4843-112">Pentru a configura sau edita un export, trebuie să existe conexiuni disponibile pentru dvs.</span><span class="sxs-lookup"><span data-stu-id="e4843-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="e4843-113">Conexiunile depind de [rolul dvs. de utilizator](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="e4843-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="e4843-114">Administratorii au acces la toate conexiunile.</span><span class="sxs-lookup"><span data-stu-id="e4843-114">Administrators have access to all connections.</span></span> <span data-ttu-id="e4843-115">De asemenea, pot crea conexiuni noi atunci când configurează un export.</span><span class="sxs-lookup"><span data-stu-id="e4843-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="e4843-116">Contribuitorii pot avea acces la conexiuni specifice.</span><span class="sxs-lookup"><span data-stu-id="e4843-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="e4843-117">Acestea depind de administratori pentru a configura și partaja conexiuni.</span><span class="sxs-lookup"><span data-stu-id="e4843-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="e4843-118">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e4843-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="e4843-119">Spectatorii pot vizualiza doar exporturile existente, dar nu le pot crea.</span><span class="sxs-lookup"><span data-stu-id="e4843-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="e4843-120">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="e4843-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e4843-121">Selectați **Adăugare export** pentru a crea o nouă destinație de export.</span><span class="sxs-lookup"><span data-stu-id="e4843-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="e4843-122">În panoul **Configurați exportul**, selectați ce conexiune să utilizați.</span><span class="sxs-lookup"><span data-stu-id="e4843-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="e4843-123">[Conexiunile](connections.md) sunt gestionate de administratori.</span><span class="sxs-lookup"><span data-stu-id="e4843-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="e4843-124">Furnizați detaliile necesare și selectați **Salvare** pentru a crea exportul.</span><span class="sxs-lookup"><span data-stu-id="e4843-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="e4843-125">Editarea unui export</span><span class="sxs-lookup"><span data-stu-id="e4843-125">Edit an export</span></span>

1. <span data-ttu-id="e4843-126">Selectați elipsa verticală pentru destinația de export pe care doriți să o editați.</span><span class="sxs-lookup"><span data-stu-id="e4843-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="e4843-127">Selectați **Editați** din meniul derulant.</span><span class="sxs-lookup"><span data-stu-id="e4843-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="e4843-128">Schimbați valorile pe care doriți să le actualizați și selectați **Salvați**.</span><span class="sxs-lookup"><span data-stu-id="e4843-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="e4843-129">Vizualizați Exporturi și detalii despre export</span><span class="sxs-lookup"><span data-stu-id="e4843-129">View Exports and export details</span></span>

<span data-ttu-id="e4843-130">După crearea destinațiilor de export, acestea sunt listate pe **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="e4843-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="e4843-131">Toți utilizatorii pot vedea ce date sunt partajate și starea cea mai recentă a acestora.</span><span class="sxs-lookup"><span data-stu-id="e4843-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="e4843-132">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="e4843-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e4843-133">Utilizatorii fără permisiuni de editare selectează **Vizualizare** în loc de **Editare** pentru a vizualiza detaliile exportului.</span><span class="sxs-lookup"><span data-stu-id="e4843-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="e4843-134">Acest panou lateral arată configurarea acestui export.</span><span class="sxs-lookup"><span data-stu-id="e4843-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="e4843-135">Fără permisiuni de editare, nu puteți modifica valorile.</span><span class="sxs-lookup"><span data-stu-id="e4843-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="e4843-136">Selectați **Închidere** pentru a reveni la pagina de exporturi.</span><span class="sxs-lookup"><span data-stu-id="e4843-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="e4843-137">Executați exporturi la cerere</span><span class="sxs-lookup"><span data-stu-id="e4843-137">Run exports on demand</span></span>

<span data-ttu-id="e4843-138">După configurarea unui export, acesta va rula cu fiecare [reîmprospătare programată](system.md#schedule-tab) atâta timp cât are o conexiune care funcționează.</span><span class="sxs-lookup"><span data-stu-id="e4843-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="e4843-139">Pentru a exporta date fără a aștepta o reîmprospătare programată, accesați **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="e4843-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="e4843-140">Aveţi două opţiuni:</span><span class="sxs-lookup"><span data-stu-id="e4843-140">You have two options:</span></span>

- <span data-ttu-id="e4843-141">Pentru a rula toate exporturile, selectați **Executare totală** în bara de comandă.</span><span class="sxs-lookup"><span data-stu-id="e4843-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="e4843-142">Pentru a rula un singur export, selectați puncte de suspensie (...) pe un element din listă și apoi alegeți **Executare**.</span><span class="sxs-lookup"><span data-stu-id="e4843-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="e4843-143">Eliminați un export</span><span class="sxs-lookup"><span data-stu-id="e4843-143">Remove an Export</span></span>

1. <span data-ttu-id="e4843-144">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="e4843-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e4843-145">Selectați elipsa verticală pentru Exportul pe care doriți să-l eliminați.</span><span class="sxs-lookup"><span data-stu-id="e4843-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="e4843-146">Selectați **Eliminare** din meniul vertical.</span><span class="sxs-lookup"><span data-stu-id="e4843-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="e4843-147">Confirmați eliminarea selectând **Eliminare** pe ecranul de confirmare.</span><span class="sxs-lookup"><span data-stu-id="e4843-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
