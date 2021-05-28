---
title: Exportați datele Customer Insights către Azure Synapse Analytics
description: Aflați cum să configurați conexiunea și să exportați la Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977392"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="f4f2a-103">Exportați datele la Azure Synapse Analytics (versiune preliminară)</span><span class="sxs-lookup"><span data-stu-id="f4f2a-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="f4f2a-104">Azure Synapse este un serviciu de analize ce accelerează timpul de detaliere a depozitelor de date și a sistemelor de date mari.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="f4f2a-105">Puteți ingera și utiliza datele Customer Insights în [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="f4f2a-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f4f2a-106">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="f4f2a-106">Prerequisites</span></span>

<span data-ttu-id="f4f2a-107">Următoarele condiții preliminare trebuie îndeplinite pentru a configura conexiunea de la Customer Insights la Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="f4f2a-108">Asigurați-vă să setați toate **atribuirile de roluri** după cum este descris.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="f4f2a-109">Cerințe preliminare în Customer Insights</span><span class="sxs-lookup"><span data-stu-id="f4f2a-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="f4f2a-110">Aveți un rol **Administrator** în Detalii despre public.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="f4f2a-111">Aflați mai multe despre [setarea permisiunilor utilizatorilor în Detalii privind publicul](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="f4f2a-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="f4f2a-112">În Azure:</span><span class="sxs-lookup"><span data-stu-id="f4f2a-112">In Azure:</span></span> 

- <span data-ttu-id="f4f2a-113">Un abonament Azure activ.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-113">An active Azure subscription.</span></span>

- <span data-ttu-id="f4f2a-114">Dacă utilizați un nou cont Azure Data Lake Storage Gen2, *director principal de serviciu pentru detalii despre public* are nevoie de permisiune de **Contributor stocare data blob**.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="f4f2a-115">Aflați mai multe despre [conectarea la un cont Azure Data Lake Storage Gen2 cu contul principal de serviciu Azure pentru detalii despre public](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="f4f2a-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="f4f2a-116">Data Lake Storage Gen2 **trebuie să aibă** [spațiul de nume ierarhic](/azure/storage/blobs/data-lake-storage-namespace) activat.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="f4f2a-117">Pe grupul de resurse, unde se află spațiul de lucru Azure Synapse, *director principal de serviciu* și *utilizator pentru detalii despre public* trebuie să le fie atribuite cel puțin permisiuni **Cititor**.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="f4f2a-118">Pentru mai multe informații, consultați [Atribuirea de roluri Azure utilizând portalul Azure](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="f4f2a-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="f4f2a-119">Pentru *utilizator* este nevoie de permisiuni **Contribuitor stocare date blob** pentru contul Azure Data Lake Storage Gen2 unde sunt amplasate datele și conectate la spațiul de lucru Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="f4f2a-120">Aflați mai multe despre [utilizarea portalului Azure pentru a atribui un rol Azure pentru accesul la datele de blob și la coadă](/azure/storage/common/storage-auth-aad-rbac-portal) și [permisiuni de stocare pentru contribuitor date blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="f4f2a-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="f4f2a-121">Pentru utilizator *[identitatea gestionată de spațiu de lucru Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* este nevoie de permisiuni **Contribuitor stocare date blob** pentru contul Azure Data Lake Storage Gen2 unde sunt amplasate datele și conectate la spațiul de lucru Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="f4f2a-122">Aflați mai multe despre [utilizarea portalului Azure pentru a atribui un rol Azure pentru accesul la datele de blob și la coadă](/azure/storage/common/storage-auth-aad-rbac-portal) și [permisiuni de stocare pentru contribuitor date blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="f4f2a-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="f4f2a-123">Pentru spațiul de lucru Azure Synapse,*directorul principal de serviciu pentru detalii despre public* este nevoie să aibă atribuit rolul **Administrator Synapse**.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="f4f2a-124">Pentru mai multe informații, consultați [Cum să configurați controlul accesului pentru spațiul de lucru Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="f4f2a-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="f4f2a-125">Configurați conexiunea și exportul la Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="f4f2a-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="f4f2a-126">Configurați o conexiune</span><span class="sxs-lookup"><span data-stu-id="f4f2a-126">Configure a connection</span></span>

1. <span data-ttu-id="f4f2a-127">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f4f2a-128">Selectați **Adăugare conexiune** și alegeți **Azure Synapse Analytics** sau selectați **Configurare** pe dala **Azure Synapse Analytics** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="f4f2a-129">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul Nume afișat.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="f4f2a-130">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="f4f2a-131">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f4f2a-132">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-132">Choose who can use this connection.</span></span> <span data-ttu-id="f4f2a-133">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f4f2a-134">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f4f2a-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f4f2a-135">Selectați sau căutați abonamentul în care doriți să utilizați datele Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="f4f2a-136">De îndată ce este selectat un abonament, puteți selecta și **Spațiul de lucru**, **Contul de stocare** și **containerul**.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="f4f2a-137">Selectați **Salvare** pentru a salva conexiunea.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="f4f2a-138">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="f4f2a-138">Configure an export</span></span>

<span data-ttu-id="f4f2a-139">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f4f2a-140">Pentru mai multe informații, consultați [permisiunile necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f4f2a-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f4f2a-141">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f4f2a-142">Pentru a crea un nou export, selectați **Adăugare export**.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="f4f2a-143">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="f4f2a-144">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile [conexiuni](connections.md) de acest tip.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="f4f2a-145">Dați un **Nume afișat** pentru exportul dvs. și un **Nume al bazei de date**.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="f4f2a-146">Selectați ce entități doriți să exportați la Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="f4f2a-147">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-147">Select **Save**.</span></span>

<span data-ttu-id="f4f2a-148">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f4f2a-149">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f4f2a-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f4f2a-150">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f4f2a-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="f4f2a-151">Actualizați un export</span><span class="sxs-lookup"><span data-stu-id="f4f2a-151">Update an export</span></span>

1. <span data-ttu-id="f4f2a-152">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f4f2a-153">Selectați **Editare** pe exportul pe care doriți să îl actualizați.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="f4f2a-154">**Adăugați** sau **Eliminați** entități din selecție.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="f4f2a-155">Dacă entitățile sunt eliminate din selecție, ele nu sunt șterse și din baza de date Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="f4f2a-156">Cu toate acestea, reîmprospătările de date viitoare nu vor actualiza entitățile eliminate din baza de date respectivă.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="f4f2a-157">**Modificarea numelui bazei de date** creează o nouă bază de date Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="f4f2a-158">Baza de date cu numele ce a fost configurat înainte nu va primi actualizări în reîmprospătări viitoare.</span><span class="sxs-lookup"><span data-stu-id="f4f2a-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
