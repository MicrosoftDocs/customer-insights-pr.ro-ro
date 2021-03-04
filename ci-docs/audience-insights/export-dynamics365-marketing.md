---
title: Exportați datele Customer Insights către Dynamics 365 Marketing
description: Aflați cum puteți configura conexiunea la Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269069"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="e1f23-103">Conector pentru Dynamics 365 Marketing (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="e1f23-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e1f23-104">Utilizați [segmentele](segments.md) pentru a genera campanii și a contacta anumite grupuri de clienți cu Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="e1f23-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="e1f23-105">Pentru mai multe informații, consultați [Utilizați segmente din Dynamics 365 Customer Insights cu Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="e1f23-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="e1f23-106">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="e1f23-106">Prerequisite</span></span>

- <span data-ttu-id="e1f23-107">Înregistrările de contact trebuie să fie prezente în Dynamics 365 Marketing înainte de a putea exporta un segment din Customer Insights în Marketing.</span><span class="sxs-lookup"><span data-stu-id="e1f23-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="e1f23-108">Citiți mai multe despre cum să efectuați ingestia persoanelor de contact în [Dynamics 365 Marketing folosind Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="e1f23-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="e1f23-109">Exportul de segmente din perspectivele publicului către Marketing nu va crea noi înregistrări de contact în instanțele de Marketing.</span><span class="sxs-lookup"><span data-stu-id="e1f23-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="e1f23-110">Înregistrările de contact din Marketing trebuie să fie ingerate în statistici ale publicului și utilizate ca sursă de date.</span><span class="sxs-lookup"><span data-stu-id="e1f23-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="e1f23-111">De asemenea, trebuie să fie incluse în entitatea Client unificată pentru a identifica ID-urile clienților cu ID-urile de contact înainte ca segmentele să poată fi exportate.</span><span class="sxs-lookup"><span data-stu-id="e1f23-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="e1f23-112">Configurați conectorul pentru marketing</span><span class="sxs-lookup"><span data-stu-id="e1f23-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="e1f23-113">În Detalii despre audiență, accesați **Administrator** > **Destinații export**.</span><span class="sxs-lookup"><span data-stu-id="e1f23-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e1f23-114">Sub **Dynamics 365 Marketing**, selectați **Configurare**.</span><span class="sxs-lookup"><span data-stu-id="e1f23-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="e1f23-115">Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="e1f23-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e1f23-116">Introduceți adresa URL de marketing a organizației dvs. în câmpul **Adresa serverului**.</span><span class="sxs-lookup"><span data-stu-id="e1f23-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="e1f23-117">În secțiunea **Cont administrator server**, selectați **Conectare** și alegeți un cont Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="e1f23-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="e1f23-118">Mapați un câmp ID client la ID-ul de contact Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e1f23-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="e1f23-119">Selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="e1f23-119">Select **Next**.</span></span>

1. <span data-ttu-id="e1f23-120">Alegeți unul sau mai multe segmente.</span><span class="sxs-lookup"><span data-stu-id="e1f23-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="e1f23-121">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="e1f23-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e1f23-122">Exportați datele</span><span class="sxs-lookup"><span data-stu-id="e1f23-122">Export the data</span></span>

<span data-ttu-id="e1f23-123">Puteți [exporta date la cerere](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e1f23-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="e1f23-124">Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e1f23-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]