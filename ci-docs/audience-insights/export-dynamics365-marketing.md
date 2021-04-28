---
title: Exportați datele Customer Insights către Dynamics 365 Marketing
description: Aflați cum să configurați conexiunea și să exportați la Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759652"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="dd518-103">Utilizarea segmentelor în Dynamics 365 Marketing (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="dd518-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="dd518-104">Utilizați [segmentele](segments.md) pentru a genera campanii și a contacta anumite grupuri de clienți cu Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="dd518-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="dd518-105">Pentru mai multe informații, consultați [Utilizați segmente din Dynamics 365 Customer Insights cu Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="dd518-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="dd518-106">Cerință preliminară pentru o conexiune</span><span class="sxs-lookup"><span data-stu-id="dd518-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="dd518-107">Înregistrările de contact trebuie să fie prezente în Dynamics 365 Marketing înainte de a putea exporta un segment din Customer Insights în Marketing.</span><span class="sxs-lookup"><span data-stu-id="dd518-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="dd518-108">Citiți mai multe despre cum să efectuați ingestia persoanelor de contact în [Dynamics 365 Marketing folosind Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="dd518-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="dd518-109">Exportul de segmente din perspectivele publicului către Marketing nu va crea noi înregistrări de contact în instanțele de Marketing.</span><span class="sxs-lookup"><span data-stu-id="dd518-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="dd518-110">Înregistrările de contact din Marketing trebuie să fie ingerate în statistici ale publicului și utilizate ca sursă de date.</span><span class="sxs-lookup"><span data-stu-id="dd518-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="dd518-111">De asemenea, trebuie să fie incluse în entitatea Client unificată pentru a identifica ID-urile clienților cu ID-urile de contact înainte ca segmentele să poată fi exportate.</span><span class="sxs-lookup"><span data-stu-id="dd518-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="dd518-112">Configurarea conexiunii la Marketing</span><span class="sxs-lookup"><span data-stu-id="dd518-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="dd518-113">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="dd518-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="dd518-114">Selectați **Adăugați conexiune** și alegeți **Dynamics 365 Marketing** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="dd518-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="dd518-115">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="dd518-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="dd518-116">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="dd518-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="dd518-117">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="dd518-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="dd518-118">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="dd518-118">Choose who can use this connection.</span></span> <span data-ttu-id="dd518-119">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="dd518-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="dd518-120">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="dd518-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="dd518-121">Introduceți adresa URL de marketing a organizației dvs. în câmpul **Adresa serverului**.</span><span class="sxs-lookup"><span data-stu-id="dd518-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="dd518-122">În secțiunea **Cont administrator server**, selectați **Conectare** și alegeți un cont Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="dd518-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="dd518-123">Mapați un câmp ID client la ID-ul de contact Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="dd518-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="dd518-124">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="dd518-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="dd518-125">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="dd518-125">Configure an export</span></span>

<span data-ttu-id="dd518-126">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="dd518-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="dd518-127">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="dd518-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="dd518-128">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="dd518-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="dd518-129">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="dd518-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="dd518-130">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="dd518-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="dd518-131">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="dd518-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="dd518-132">Alegeți unul sau mai multe segmente.</span><span class="sxs-lookup"><span data-stu-id="dd518-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="dd518-133">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="dd518-133">Select **Save**.</span></span>

<span data-ttu-id="dd518-134">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="dd518-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="dd518-135">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dd518-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dd518-136">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="dd518-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
