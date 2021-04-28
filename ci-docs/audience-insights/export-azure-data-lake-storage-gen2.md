---
title: Exportați datele Customer Insights către Azure Data Lake Storage Gen2
description: Aflați cum să configurați conexiunea la Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760066"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="13df5-103">Configurați conexiunea la Azure Data Lake Storage Gen2 (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="13df5-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="13df5-104">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="13df5-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="13df5-105">Selectați **Adăugați conexiune** și alegeți **Azure Data Lake Gen 2** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="13df5-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="13df5-106">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="13df5-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="13df5-107">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="13df5-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="13df5-108">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="13df5-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="13df5-109">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="13df5-109">Choose who can use this connection.</span></span> <span data-ttu-id="13df5-110">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="13df5-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="13df5-111">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="13df5-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="13df5-112">Introduceți **Nume de cont**, **Cheia contului**, și **Recipient** pentru Azure Data Lake Storage Gen2 dvs.</span><span class="sxs-lookup"><span data-stu-id="13df5-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="13df5-113">Pentru a afla cum să creați un cont de stocare cu care să utilizați Azure Data Lake Storage Gen2, consultați [Creați un cont de stocare](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="13df5-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="13df5-114">Pentru a afla mai multe despre numele contului de stocare Azure Data Lake Gen2 și cheia de cont, consultați [Gestionați setările contului de stocare în portalul Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="13df5-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="13df5-115">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="13df5-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="13df5-116">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="13df5-116">Configure an export</span></span>

<span data-ttu-id="13df5-117">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="13df5-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="13df5-118">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="13df5-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="13df5-119">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="13df5-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="13df5-120">Pentru a crea un nou export, selectați **Adăugare export**.</span><span class="sxs-lookup"><span data-stu-id="13df5-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="13df5-121">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="13df5-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="13df5-122">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="13df5-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="13df5-123">Selectați caseta de lângă fiecare dintre entitățile pe care doriți să le exportați la această destinație.</span><span class="sxs-lookup"><span data-stu-id="13df5-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="13df5-124">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="13df5-124">Select **Save**.</span></span>

<span data-ttu-id="13df5-125">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="13df5-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="13df5-126">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="13df5-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="13df5-127">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="13df5-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="13df5-128">Datele exportate sunt stocate în recipientul de stocare Azure Data Lake Gen 2 pe care l-ați configurat.</span><span class="sxs-lookup"><span data-stu-id="13df5-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
