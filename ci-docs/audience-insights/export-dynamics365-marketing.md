---
title: Exportați datele Customer Insights către Dynamics 365 Marketing
description: Aflați cum puteți configura conexiunea la Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643788"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="f8707-103">Conector pentru Dynamics 365 Marketing (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="f8707-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="f8707-104">Utilizați [segmentele](segments.md) pentru a genera campanii și a contacta anumite grupuri de clienți cu Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="f8707-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="f8707-105">Pentru mai multe informații, consultați [Utilizați segmente din Dynamics 365 Customer Insights cu Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="f8707-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="f8707-106">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="f8707-106">Prerequisite</span></span>

<span data-ttu-id="f8707-107">Înregistrări de contact [din Dynamics 365 Marketing ingerate Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="f8707-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="f8707-108">Configurați conectorul pentru marketing</span><span class="sxs-lookup"><span data-stu-id="f8707-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="f8707-109">În Detalii despre audiență, accesați **Administrator** > **Destinații export**.</span><span class="sxs-lookup"><span data-stu-id="f8707-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f8707-110">Sub **Dynamics 365 Marketing**, selectați **Configurare**.</span><span class="sxs-lookup"><span data-stu-id="f8707-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="f8707-111">Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="f8707-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f8707-112">Introduceți adresa URL de marketing a organizației dvs. în câmpul **Adresa serverului**.</span><span class="sxs-lookup"><span data-stu-id="f8707-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="f8707-113">În secțiunea **Cont administrator server**, selectați **Conectare** și alegeți un cont Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="f8707-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="f8707-114">Mapați un câmp ID client la ID-ul de contact Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="f8707-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="f8707-115">Selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="f8707-115">Select **Next**.</span></span>

1. <span data-ttu-id="f8707-116">Alegeți unul sau mai multe segmente.</span><span class="sxs-lookup"><span data-stu-id="f8707-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="f8707-117">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="f8707-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f8707-118">Exportați datele</span><span class="sxs-lookup"><span data-stu-id="f8707-118">Export the data</span></span>

<span data-ttu-id="f8707-119">Puteți [exporta date la cerere](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f8707-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f8707-120">Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f8707-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
