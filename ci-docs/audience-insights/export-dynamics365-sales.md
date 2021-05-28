---
title: Exportați datele Customer Insights către Dynamics 365 Sales
description: Aflați cum să configurați conexiunea și să exportați la Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976241"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="3827e-103">Utilizarea segmentelor în Dynamics 365 Sales (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="3827e-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="3827e-104">Utilizați datele clienților pentru a crea liste de marketing, a urmări fluxuri de lucru și a trimite promoții cu Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="3827e-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="3827e-105">Cerință preliminară pentru conexiune</span><span class="sxs-lookup"><span data-stu-id="3827e-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="3827e-106">Înregistrările de contact trebuie să fie prezente în Dynamics 365 Sales înainte de a putea exporta un segment din Customer Insights în Sales.</span><span class="sxs-lookup"><span data-stu-id="3827e-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="3827e-107">Citiți mai multe despre cum să efectuați ingestia persoanelor de contact în [Dynamics 365 Sales folosind Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="3827e-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="3827e-108">Exportul de segmente din perspectivele publicului către Sales nu va crea noi înregistrări de contact în instanțele de Sales.</span><span class="sxs-lookup"><span data-stu-id="3827e-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="3827e-109">Înregistrările de contact din Sales trebuie să fie ingerate în statistici ale publicului și utilizate ca sursă de date.</span><span class="sxs-lookup"><span data-stu-id="3827e-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="3827e-110">De asemenea, trebuie să fie incluse în entitatea Client unificată pentru a identifica ID-urile clienților cu ID-urile de contact înainte ca segmentele să poată fi exportate.</span><span class="sxs-lookup"><span data-stu-id="3827e-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="3827e-111">Configurarea conexiunii la Sales</span><span class="sxs-lookup"><span data-stu-id="3827e-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="3827e-112">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="3827e-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3827e-113">Selectați **Adăugați conexiune** și alegeți **Dynamics 365 Sales** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="3827e-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="3827e-114">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="3827e-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3827e-115">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="3827e-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3827e-116">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="3827e-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3827e-117">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="3827e-117">Choose who can use this connection.</span></span> <span data-ttu-id="3827e-118">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="3827e-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="3827e-119">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="3827e-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="3827e-120">Introduceți adresa URL de vânzări a organizației dvs. în câmpul **Adresa serverului**.</span><span class="sxs-lookup"><span data-stu-id="3827e-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="3827e-121">În secțiunea **Cont administrator server**, selectați **Conectare** și alegeți un cont Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="3827e-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="3827e-122">Mapați un câmp ID client la ID-ul de contact Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="3827e-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="3827e-123">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="3827e-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="3827e-124">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="3827e-124">Configure an export</span></span>

<span data-ttu-id="3827e-125">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="3827e-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="3827e-126">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="3827e-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3827e-127">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="3827e-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3827e-128">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="3827e-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="3827e-129">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="3827e-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="3827e-130">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="3827e-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="3827e-131">Alegeți unul sau mai multe segmente.</span><span class="sxs-lookup"><span data-stu-id="3827e-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="3827e-132">Selectați **Salvare**</span><span class="sxs-lookup"><span data-stu-id="3827e-132">Select **Save**</span></span>

<span data-ttu-id="3827e-133">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="3827e-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="3827e-134">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3827e-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3827e-135">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="3827e-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
