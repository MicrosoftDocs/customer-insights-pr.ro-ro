---
title: Exportați date din Customer Insights
description: Gestionați exporturile către partajare date.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896158"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="a1ad3-103">Prezentare generală a exporturilor (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="a1ad3-103">Exports (preview) overview</span></span>

<span data-ttu-id="a1ad3-104">Pagina **Exporturi** vă arată toate exporturile configurate.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="a1ad3-105">Exporturile partajează date specifice cu diferite aplicații.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="a1ad3-106">Ele pot include profiluri sau entități ale clienților, scheme și detalii de mapare.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="a1ad3-107">Fiecare export necesită o [conexiune, configurată de un administrator, pentru a gestiona autentificarea și accesul](connections.md).</span><span class="sxs-lookup"><span data-stu-id="a1ad3-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a1ad3-108">Până în martie 2021, exporturile au creat automat o conexiune la serviciul corespunzător.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="a1ad3-109">Exporturile necesită acum o [conexiune, creată și partajată de un administrator](connections.md) înainte de a le putea crea.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="a1ad3-110">Faceți salt la **Date** > **Exporturi** pentru a vizualiza pagina exporturilor.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="a1ad3-111">Toate rolurile utilizatorilor au acces la vizualizarea exporturilor configurate.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="a1ad3-112">Utilizarea câmpului de căutare din bara de comandă pentru a găsi exporturile după nume, numele conexiunii sau tipul conexiunii.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="a1ad3-113">Configurați un nou export</span><span class="sxs-lookup"><span data-stu-id="a1ad3-113">Set up a new export</span></span>

<span data-ttu-id="a1ad3-114">Pentru a configura sau edita un export, trebuie să existe conexiuni disponibile pentru dvs.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="a1ad3-115">Conexiunile depind de [rolul dvs. de utilizator](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="a1ad3-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="a1ad3-116">Administratorii au acces la toate conexiunile.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-116">Administrators have access to all connections.</span></span> <span data-ttu-id="a1ad3-117">De asemenea, pot crea conexiuni noi atunci când configurează un export.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="a1ad3-118">Contribuitorii pot avea acces la conexiuni specifice.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="a1ad3-119">Acestea depind de administratori pentru a configura și partaja conexiuni.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="a1ad3-120">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a1ad3-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="a1ad3-121">Spectatorii pot vizualiza doar exporturile existente, dar nu le pot crea.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="a1ad3-122">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a1ad3-123">Selectați **Adăugare export** pentru a crea o nouă destinație de export.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="a1ad3-124">În panoul **Configurați exportul**, selectați ce conexiune să utilizați.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="a1ad3-125">[Conexiunile](connections.md) sunt gestionate de administratori.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="a1ad3-126">Furnizați detaliile necesare și selectați **Salvare** pentru a crea exportul.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="a1ad3-127">Editarea unui export</span><span class="sxs-lookup"><span data-stu-id="a1ad3-127">Edit an export</span></span>

1. <span data-ttu-id="a1ad3-128">Selectați elipsa verticală pentru destinația de export pe care doriți să o editați.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="a1ad3-129">Selectați **Editați** din meniul derulant.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="a1ad3-130">Schimbați valorile pe care doriți să le actualizați și selectați **Salvați**.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="a1ad3-131">Vizualizați Exporturi și detalii despre export</span><span class="sxs-lookup"><span data-stu-id="a1ad3-131">View Exports and export details</span></span>

<span data-ttu-id="a1ad3-132">După crearea destinațiilor de export, acestea sunt listate pe **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="a1ad3-133">Toți utilizatorii pot vedea ce date sunt partajate și starea cea mai recentă a acestora.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="a1ad3-134">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a1ad3-135">Utilizatorii fără permisiuni de editare selectează **Vizualizare** în loc de **Editare** pentru a vizualiza detaliile exportului.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="a1ad3-136">Acest panou lateral arată configurarea acestui export.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="a1ad3-137">Fără permisiuni de editare, nu puteți modifica valorile.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="a1ad3-138">Selectați **Închidere** pentru a reveni la pagina de exporturi.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="a1ad3-139">Executați exporturi la cerere</span><span class="sxs-lookup"><span data-stu-id="a1ad3-139">Run exports on demand</span></span>

<span data-ttu-id="a1ad3-140">După configurarea unui export, acesta va rula cu fiecare [reîmprospătare programată](system.md#schedule-tab) atâta timp cât are o conexiune care funcționează.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="a1ad3-141">Pentru a exporta date fără a aștepta o reîmprospătare programată, accesați **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="a1ad3-142">Aveţi două opţiuni:</span><span class="sxs-lookup"><span data-stu-id="a1ad3-142">You have two options:</span></span>

- <span data-ttu-id="a1ad3-143">Pentru a rula toate exporturile, selectați **Executare totală** în bara de comandă.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="a1ad3-144">Pentru a rula un singur export, selectați puncte de suspensie (...) pe un element din listă și apoi alegeți **Executare**.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="a1ad3-145">Eliminați un export</span><span class="sxs-lookup"><span data-stu-id="a1ad3-145">Remove an Export</span></span>

1. <span data-ttu-id="a1ad3-146">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a1ad3-147">Selectați elipsa verticală pentru Exportul pe care doriți să-l eliminați.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="a1ad3-148">Selectați **Eliminare** din meniul vertical.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="a1ad3-149">Confirmați eliminarea selectând **Eliminare** pe ecranul de confirmare.</span><span class="sxs-lookup"><span data-stu-id="a1ad3-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
