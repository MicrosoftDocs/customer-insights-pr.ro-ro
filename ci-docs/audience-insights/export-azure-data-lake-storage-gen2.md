---
title: Exportați datele Customer Insights către Azure Data Lake Storage Gen2
description: Aflați cum să configurați conexiunea la Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477194"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="62056-103">Conector pentru Azure Data Lake Storage Gen2 (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="62056-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="62056-104">Stocați datele Customer Insights în Azure Data Lake Storage Gen2 sau utilizați-le pentru a transfera datele către alte aplicații.</span><span class="sxs-lookup"><span data-stu-id="62056-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="62056-105">Configurați conectorul pentru Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="62056-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="62056-106">În Detalii despre audiență, accesați **Administrator** > **Destinații export**.</span><span class="sxs-lookup"><span data-stu-id="62056-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="62056-107">Sub **Azure Data Lake Storage Gen2**, selectați **Configurare**.</span><span class="sxs-lookup"><span data-stu-id="62056-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="62056-108">Dați destinației dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="62056-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="62056-109">Introduceți **Nume de cont**, **Cheia contului**, și **Recipient** pentru Azure Data Lake Storage Gen2 dvs.</span><span class="sxs-lookup"><span data-stu-id="62056-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="62056-110">Pentru a afla cum să creați un cont de stocare cu care să utilizați Azure Data Lake Storage Gen2, consultați [Creați un cont de stocare](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="62056-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="62056-111">Pentru a afla mai multe despre cum să găsiți numele contului și cheia de cont de stocare Azure Data Lake Gen2, consultați [Gestionați setările contului de stocare în portalul Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="62056-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="62056-112">Selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="62056-112">Select **Next**.</span></span>

1. <span data-ttu-id="62056-113">Selectați caseta de lângă fiecare dintre entitățile pe care doriți să le exportați la această destinație.</span><span class="sxs-lookup"><span data-stu-id="62056-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="62056-114">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="62056-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="62056-115">Exportați datele</span><span class="sxs-lookup"><span data-stu-id="62056-115">Export the data</span></span>

<span data-ttu-id="62056-116">Puteți [exporta date la cerere](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="62056-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="62056-117">Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="62056-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
