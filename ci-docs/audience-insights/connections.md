---
title: Conexiuni la alte servicii de la Customer Insights.
description: Partajați date către alte servicii.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 106dbc26f95b309821d738e1484b1eaa79dd225b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896112"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="907a4-103">Prezentare generală a conexiunilor (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="907a4-103">Connections (preview) overview</span></span>

<span data-ttu-id="907a4-104">Conexiunile sunt cheia pentru a permite partajarea datelor către și de la Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="907a4-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="907a4-105">Fiecare conexiune stabilește partajarea datelor cu un anumit serviciu.</span><span class="sxs-lookup"><span data-stu-id="907a4-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="907a4-106">Conexiunile stau la baza [configurare îmbogățiri terțe](enrichment-hub.md) și [configurare exporturi](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="907a4-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="907a4-107">Aceeași conexiune poate fi utilizată de mai multe ori.</span><span class="sxs-lookup"><span data-stu-id="907a4-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="907a4-108">De exemplu, o conexiune la Dynamics 365 Marketing funcționează pentru exporturi multiple și o conexiune Leadspace poate fi utilizată pentru mai multe îmbogățiri.</span><span class="sxs-lookup"><span data-stu-id="907a4-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="907a4-109">Salt la **Administrator** > **Conexiuni** pentru a crea și vizualiza conexiuni.</span><span class="sxs-lookup"><span data-stu-id="907a4-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="907a4-110">Fila **Conexiuni** vă arată toate conexiunile active.</span><span class="sxs-lookup"><span data-stu-id="907a4-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="907a4-111">Lista arată un rând pentru fiecare conexiune.</span><span class="sxs-lookup"><span data-stu-id="907a4-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="907a4-112">Obțineți o prezentare rapidă, o descriere și aflați ce puteți face cu fiecare opțiune de extensibilitate de pe fila **Descoperire**.</span><span class="sxs-lookup"><span data-stu-id="907a4-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="907a4-113">Exporturi</span><span class="sxs-lookup"><span data-stu-id="907a4-113">Exports</span></span>

<span data-ttu-id="907a4-114">Numai administratorii pot configura conexiuni noi, dar pot acorda acces contribuitorilor pentru a utiliza conexiunile existente.</span><span class="sxs-lookup"><span data-stu-id="907a4-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="907a4-115">Administratorii controlează unde pot merge datele, contribuitorii definesc sarcina utilă și frecvența potrivită nevoilor lor.</span><span class="sxs-lookup"><span data-stu-id="907a4-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="907a4-116">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="907a4-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="907a4-117">Îmbogățiri</span><span class="sxs-lookup"><span data-stu-id="907a4-117">Enrichments</span></span>

<span data-ttu-id="907a4-118">Numai administratorii pot configura conexiuni noi, dar conexiunile create sunt întotdeauna disponibile atât pentru administratori, cât și pentru contribuitori.</span><span class="sxs-lookup"><span data-stu-id="907a4-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="907a4-119">Administratorii gestionează acreditările și își dau consimțământul transferurilor de date.</span><span class="sxs-lookup"><span data-stu-id="907a4-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="907a4-120">Conexiunile pot fi apoi utilizate pentru îmbogățiri atât de administratori, cât și de contribuitori.</span><span class="sxs-lookup"><span data-stu-id="907a4-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="907a4-121">Adăugați o conexiune nouă</span><span class="sxs-lookup"><span data-stu-id="907a4-121">Add a new connection</span></span>

<span data-ttu-id="907a4-122">Pentru a adăuga conexiuni, trebuie să aveți [permisiuni de administrator](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="907a4-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="907a4-123">Dacă vă conectați la alte servicii Microsoft, presupunem că ambele servicii se află în aceeași organizație.</span><span class="sxs-lookup"><span data-stu-id="907a4-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="907a4-124">Salt la **Administrator** > **Conexiuni (previzualizare)**.</span><span class="sxs-lookup"><span data-stu-id="907a4-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="907a4-125">Mergeți la fila **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="907a4-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="907a4-126">Selectați **Adăugare conexiune** pentru a crea o nouă conexiune.</span><span class="sxs-lookup"><span data-stu-id="907a4-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="907a4-127">Alegeți din meniul derulant ce tip de conexiune doriți să creați.</span><span class="sxs-lookup"><span data-stu-id="907a4-127">Choose from the drop-down menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="907a4-128">În panoul **Configurarea conexiunii**, furnizați detaliile necesare.</span><span class="sxs-lookup"><span data-stu-id="907a4-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="907a4-129">**Numele afișat** și tipul conexiunii descriu o conexiune.</span><span class="sxs-lookup"><span data-stu-id="907a4-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="907a4-130">Vă recomandăm să alegeți un nume care să explice scopul și ținta acestei conexiuni.</span><span class="sxs-lookup"><span data-stu-id="907a4-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="907a4-131">Câmpurile exacte depind de serviciul la care vă conectați.</span><span class="sxs-lookup"><span data-stu-id="907a4-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="907a4-132">Puteți afla detalii despre un anumit tip de conexiune din articolul despre serviciul țintă.</span><span class="sxs-lookup"><span data-stu-id="907a4-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="907a4-133">Pentru a crea conexiunea, selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="907a4-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="907a4-134">Puteți selecta, de asemenea **Configurare** pe o dală de pe fila **Descoperire**.</span><span class="sxs-lookup"><span data-stu-id="907a4-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="907a4-135">Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi</span><span class="sxs-lookup"><span data-stu-id="907a4-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="907a4-136">Când configurați sau editați o conexiune de export, alegeți căror utilizatori le este permis să utilizeze această conexiune specifică pentru a defini [exporturi](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="907a4-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="907a4-137">În mod implicit, o conexiune este disponibilă pentru utilizatorii cu rol de administrator.</span><span class="sxs-lookup"><span data-stu-id="907a4-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="907a4-138">Puteți modifica această setare în **Alegeți cine poate utiliza această conexiune** și puteți permite utilizatorilor cu rol de contribuitor să utilizeze această conexiune.</span><span class="sxs-lookup"><span data-stu-id="907a4-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="907a4-139">Contribuitorii nu vor putea vizualiza sau edita conexiunea.</span><span class="sxs-lookup"><span data-stu-id="907a4-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="907a4-140">Vor vedea numele afișat și tipul acestuia numai atunci când creați un export.</span><span class="sxs-lookup"><span data-stu-id="907a4-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="907a4-141">Prin partajarea unei conexiuni, permiteți colaboratorilor să utilizeze o conexiune.</span><span class="sxs-lookup"><span data-stu-id="907a4-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="907a4-142">Contribuitorii vor vedea conexiuni partajate atunci când configurează exporturile.</span><span class="sxs-lookup"><span data-stu-id="907a4-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="907a4-143">Ei pot gestiona fiecare export care utilizează această conexiune specifică.</span><span class="sxs-lookup"><span data-stu-id="907a4-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="907a4-144">Puteți modifica această setare păstrând în același timp exporturile care au fost deja definite de contribuitori.</span><span class="sxs-lookup"><span data-stu-id="907a4-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="907a4-145">Editarea unei conexiuni</span><span class="sxs-lookup"><span data-stu-id="907a4-145">Edit a connection</span></span>

1. <span data-ttu-id="907a4-146">Salt la **Administrator** > **Conexiuni (previzualizare)**.</span><span class="sxs-lookup"><span data-stu-id="907a4-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="907a4-147">Mergeți la fila **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="907a4-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="907a4-148">Selectați elipsa verticală pentru conexiunea pe care doriți să o editați.</span><span class="sxs-lookup"><span data-stu-id="907a4-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="907a4-149">Selectați **Editare**.</span><span class="sxs-lookup"><span data-stu-id="907a4-149">Select **Edit**.</span></span>

1. <span data-ttu-id="907a4-150">Schimbați valorile pe care doriți să le actualizați și selectați **Salvați**.</span><span class="sxs-lookup"><span data-stu-id="907a4-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="907a4-151">Eliminați o conexiune</span><span class="sxs-lookup"><span data-stu-id="907a4-151">Remove a connection</span></span>

<span data-ttu-id="907a4-152">Dacă conexiunea pe care o eliminați este utilizată de îmbogățiri sau exporturi, trebuie mai întâi să le detașați sau să le eliminați.</span><span class="sxs-lookup"><span data-stu-id="907a4-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="907a4-153">Dialogul de eliminare vă va ghida către îmbogățirea sau exporturile relevante.</span><span class="sxs-lookup"><span data-stu-id="907a4-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> <span data-ttu-id="907a4-154">Îmbogățirile și exporturile detașate devin inactive.</span><span class="sxs-lookup"><span data-stu-id="907a4-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="907a4-155">Le reactivați adăugându-le o altă conexiune pe pagina [Îmbogățiri](enrichment-hub.md) sau [Exporturi](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="907a4-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="907a4-156">Salt la **Administrator** > **Conexiuni (previzualizare)**.</span><span class="sxs-lookup"><span data-stu-id="907a4-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="907a4-157">Mergeți la fila **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="907a4-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="907a4-158">Selectați elipsa verticală pentru conexiunea pe care doriți să o ștergeți.</span><span class="sxs-lookup"><span data-stu-id="907a4-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="907a4-159">Selectați **Eliminare** din meniul vertical.</span><span class="sxs-lookup"><span data-stu-id="907a4-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="907a4-160">Apare un dialog de confirmare.</span><span class="sxs-lookup"><span data-stu-id="907a4-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="907a4-161">Dacă există îmbogățiri sau exporturi care utilizează această conexiune, selectați butonul pentru a vedea ce folosește conexiunea.</span><span class="sxs-lookup"><span data-stu-id="907a4-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="907a4-162">**Exporturi:** Puteți alege să eliminați sau să deconectați exporturile pentru a putea elimina conexiunea.</span><span class="sxs-lookup"><span data-stu-id="907a4-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="907a4-163">Pentru a deconecta un export, administratorii pot utiliza acțiunea **Deconectat**.</span><span class="sxs-lookup"><span data-stu-id="907a4-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="907a4-164">Această acțiune este disponibilă pentru exporturile individuale și multiple selectate.</span><span class="sxs-lookup"><span data-stu-id="907a4-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="907a4-165">Prin deconectare, păstrați configurația de export, dar nu va fi rulată până când nu i se adaugă o altă conexiune.</span><span class="sxs-lookup"><span data-stu-id="907a4-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="907a4-166">**Îmbogățiri:** Puteți alege să eliminați sau să dezactivați îmbogățirile pentru a putea elimina conexiunea.</span><span class="sxs-lookup"><span data-stu-id="907a4-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="907a4-167">Odată ce conexiunea nu mai are dependențe, reveniți la **Administrator** > **Conexiuni** și încercați să eliminați din nou conexiunea.</span><span class="sxs-lookup"><span data-stu-id="907a4-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="907a4-168">Pentru a confirma ștergerea, selectați **Ștergere**.</span><span class="sxs-lookup"><span data-stu-id="907a4-168">To confirm the deletion select **Remove**.</span></span>

