---
title: Exportați datele Customer Insights către Dynamics 365 Sales
description: Aflați cum puteți configura conexiunea la Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643833"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="4d98d-103">Conector pentru Dynamics 365 Sales (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="4d98d-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="4d98d-104">Utilizați datele clienților pentru a crea liste de marketing, a urmări fluxuri de lucru și a trimite promoții cu Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="4d98d-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="4d98d-105">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="4d98d-105">Prerequisite</span></span>

<span data-ttu-id="4d98d-106">Înregistrări de contact [din Dynamics 365 Sales ingerate folosind Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="4d98d-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="4d98d-107">Configurați conectorul pentru Vânzări</span><span class="sxs-lookup"><span data-stu-id="4d98d-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="4d98d-108">În Detalii despre audiență, accesați **Administrator** > **Destinații export**.</span><span class="sxs-lookup"><span data-stu-id="4d98d-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="4d98d-109">Sub **Dynamics 365 Sales**, selectați **Configurare**.</span><span class="sxs-lookup"><span data-stu-id="4d98d-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="4d98d-110">Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="4d98d-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="4d98d-111">Introduceți adresa URL de vânzări a organizației dvs. în câmpul **Adresa serverului**.</span><span class="sxs-lookup"><span data-stu-id="4d98d-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="4d98d-112">În secțiunea **Cont administrator server**, selectați **Conectare** și alegeți un cont Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="4d98d-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="4d98d-113">Mapați un câmp ID client la ID-ul de contact Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="4d98d-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="4d98d-114">Selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="4d98d-114">Select **Next**.</span></span>

1. <span data-ttu-id="4d98d-115">Alegeți unul sau mai multe segmente.</span><span class="sxs-lookup"><span data-stu-id="4d98d-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="4d98d-116">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="4d98d-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="4d98d-117">Exportați datele</span><span class="sxs-lookup"><span data-stu-id="4d98d-117">Export the data</span></span>

<span data-ttu-id="4d98d-118">Puteți [exporta date la cerere](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="4d98d-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="4d98d-119">Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4d98d-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
