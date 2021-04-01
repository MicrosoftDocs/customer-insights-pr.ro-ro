---
title: Exportați datele Customer Insights către Dynamics 365 Sales
description: Aflați cum puteți configura conexiunea la Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598124"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="49bec-103">Conector pentru Dynamics 365 Sales (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="49bec-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="49bec-104">Utilizați datele clienților pentru a crea liste de marketing, a urmări fluxuri de lucru și a trimite promoții cu Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="49bec-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="49bec-105">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="49bec-105">Prerequisite</span></span>

1. <span data-ttu-id="49bec-106">Înregistrările de contact trebuie să fie prezente în Dynamics 365 Sales înainte de a putea exporta un segment din Customer Insights în Sales.</span><span class="sxs-lookup"><span data-stu-id="49bec-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="49bec-107">Citiți mai multe despre cum să efectuați ingestia persoanelor de contact în [Dynamics 365 Sales folosind Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="49bec-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="49bec-108">Exportul de segmente din perspectivele publicului către Sales nu va crea noi înregistrări de contact în instanțele de Sales.</span><span class="sxs-lookup"><span data-stu-id="49bec-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="49bec-109">Înregistrările de contact din Sales trebuie să fie ingerate în statistici ale publicului și utilizate ca sursă de date.</span><span class="sxs-lookup"><span data-stu-id="49bec-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="49bec-110">De asemenea, trebuie să fie incluse în entitatea Client unificată pentru a identifica ID-urile clienților cu ID-urile de contact înainte ca segmentele să poată fi exportate.</span><span class="sxs-lookup"><span data-stu-id="49bec-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="49bec-111">Configurați conectorul pentru Vânzări</span><span class="sxs-lookup"><span data-stu-id="49bec-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="49bec-112">În Detalii despre audiență, accesați **Administrator** > **Destinații export**.</span><span class="sxs-lookup"><span data-stu-id="49bec-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="49bec-113">Sub **Dynamics 365 Sales**, selectați **Configurare**.</span><span class="sxs-lookup"><span data-stu-id="49bec-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="49bec-114">Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="49bec-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="49bec-115">Introduceți adresa URL de vânzări a organizației dvs. în câmpul **Adresa serverului**.</span><span class="sxs-lookup"><span data-stu-id="49bec-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="49bec-116">În secțiunea **Cont administrator server**, selectați **Conectare** și alegeți un cont Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="49bec-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="49bec-117">Mapați un câmp ID client la ID-ul de contact Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="49bec-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="49bec-118">Selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="49bec-118">Select **Next**.</span></span>

1. <span data-ttu-id="49bec-119">Alegeți unul sau mai multe segmente.</span><span class="sxs-lookup"><span data-stu-id="49bec-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="49bec-120">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="49bec-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="49bec-121">Exportați datele</span><span class="sxs-lookup"><span data-stu-id="49bec-121">Export the data</span></span>

<span data-ttu-id="49bec-122">Puteți [exporta date la cerere](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="49bec-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="49bec-123">Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="49bec-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]