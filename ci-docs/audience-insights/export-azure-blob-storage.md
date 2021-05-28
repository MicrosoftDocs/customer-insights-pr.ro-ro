---
title: Exportați datele Customer Insights într-un spațiu de stocare de bloburi Azure
description: Aflați cum să configurați conexiunea și să exportați într-un spațiu de stocare de bloburi.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976196"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="c82b6-103">Exportați lista segmentelor și alte date către Stocare de bloburi Azure (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="c82b6-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="c82b6-104">Stocați datele Customer Insights într-o stocare de bloburi sau utilizați-le pentru a transfera datele către alte aplicații.</span><span class="sxs-lookup"><span data-stu-id="c82b6-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="c82b6-105">Configurați conexiunea la spațiul de stocare de bloburi</span><span class="sxs-lookup"><span data-stu-id="c82b6-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="c82b6-106">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="c82b6-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c82b6-107">Selectați **Adăugați conexiune** și alegeți **Stocare bloburi Azure** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="c82b6-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="c82b6-108">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="c82b6-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c82b6-109">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="c82b6-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c82b6-110">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="c82b6-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c82b6-111">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="c82b6-111">Choose who can use this connection.</span></span> <span data-ttu-id="c82b6-112">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="c82b6-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c82b6-113">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c82b6-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c82b6-114">Introduceți **Nume de cont**, **Cheie de cont** și **Recipient** pentru contul dvs. de stocare de bloburi.</span><span class="sxs-lookup"><span data-stu-id="c82b6-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="c82b6-115">Pentru a afla mai multe despre cum să aflați numele contului de stocare de bloburi și cheia de cont, consultați [Gestionați setările contului de stocare în portalul Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="c82b6-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="c82b6-116">Pentru a afla cum să creați un container, consultați [Creați un container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="c82b6-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="c82b6-117">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="c82b6-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="c82b6-118">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="c82b6-118">Configure an export</span></span>

<span data-ttu-id="c82b6-119">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="c82b6-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c82b6-120">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c82b6-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c82b6-121">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="c82b6-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c82b6-122">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="c82b6-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c82b6-123">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Stocare bloburi Azure.</span><span class="sxs-lookup"><span data-stu-id="c82b6-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="c82b6-124">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="c82b6-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c82b6-125">Selectați caseta de lângă fiecare dintre entitățile pe care doriți să le exportați la această destinație.</span><span class="sxs-lookup"><span data-stu-id="c82b6-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="c82b6-126">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="c82b6-126">Select **Save**.</span></span>

<span data-ttu-id="c82b6-127">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="c82b6-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c82b6-128">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c82b6-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="c82b6-129">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c82b6-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="c82b6-130">Datele exportate sunt stocate în recipientul de stocare de bloburi pe care l-ați configurat.</span><span class="sxs-lookup"><span data-stu-id="c82b6-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="c82b6-131">Următoarele căi de foldere sunt create automat în containerul dvs.:</span><span class="sxs-lookup"><span data-stu-id="c82b6-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="c82b6-132">Pentru entitățile sursă și entitățile generate de sistem: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="c82b6-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="c82b6-133">Exemplu: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="c82b6-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="c82b6-134">Model.json pentru entitățile exportate va fi la nivel %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="c82b6-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="c82b6-135">Exemplu: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="c82b6-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
