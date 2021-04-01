---
title: Exportați datele Customer Insights către Azure Data Lake Storage Gen2
description: Aflați cum să configurați conexiunea la Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596653"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="d0098-103">Conector pentru Azure Data Lake Storage Gen2 (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="d0098-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="d0098-104">Stocați datele Customer Insights în Azure Data Lake Storage Gen2 sau utilizați-le pentru a transfera datele către alte aplicații.</span><span class="sxs-lookup"><span data-stu-id="d0098-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="d0098-105">Configurați conectorul pentru Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="d0098-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="d0098-106">În Detalii despre audiență, accesați **Administrator** > **Destinații export**.</span><span class="sxs-lookup"><span data-stu-id="d0098-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d0098-107">Sub **Azure Data Lake Storage Gen2**, selectați **Configurare**.</span><span class="sxs-lookup"><span data-stu-id="d0098-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="d0098-108">Dați destinației dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="d0098-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="d0098-109">Introduceți **Nume de cont**, **Cheia contului**, și **Recipient** pentru Azure Data Lake Storage Gen2 dvs.</span><span class="sxs-lookup"><span data-stu-id="d0098-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="d0098-110">Pentru a afla cum să creați un cont de stocare cu care să utilizați Azure Data Lake Storage Gen2, consultați [Creați un cont de stocare](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="d0098-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="d0098-111">Pentru a afla mai multe despre cum să găsiți numele contului și cheia de cont de stocare Azure Data Lake Gen2, consultați [Gestionați setările contului de stocare în portalul Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="d0098-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="d0098-112">Selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="d0098-112">Select **Next**.</span></span>

1. <span data-ttu-id="d0098-113">Selectați caseta de lângă fiecare dintre entitățile pe care doriți să le exportați la această destinație.</span><span class="sxs-lookup"><span data-stu-id="d0098-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="d0098-114">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="d0098-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="d0098-115">Exportați datele</span><span class="sxs-lookup"><span data-stu-id="d0098-115">Export the data</span></span>

<span data-ttu-id="d0098-116">Puteți [exporta date la cerere](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d0098-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="d0098-117">Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d0098-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>