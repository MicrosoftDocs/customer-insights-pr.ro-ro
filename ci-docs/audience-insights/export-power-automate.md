---
title: Conector Power Automate | Microsoft Docs
description: Creați fluxuri în Microsoft Power Automate din Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 57be0a204ef920b7a4bb31cf9a5b3a77f96eca0d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305079"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="fa034-103">Conector Power Automate (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="fa034-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="fa034-104">Declanșați evenimente specifice care să aibă loc automat atunci când datele se modifică și gestionați fluxurile mai complexe direct în [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="fa034-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="fa034-105">declanșatoare Power Automate</span><span class="sxs-lookup"><span data-stu-id="fa034-105">Power Automate triggers</span></span>

<span data-ttu-id="fa034-106">Utilizați declanșatoarele pentru a crea fluxuri cloud și pentru a automatiza sarcini repetitive, cum ar fi notificări sau acțiuni mai avansate.</span><span class="sxs-lookup"><span data-stu-id="fa034-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="fa034-107">Se declanșează atunci când o reîmprospătare pentru o sursă de date eșuează.</span><span class="sxs-lookup"><span data-stu-id="fa034-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="fa034-108">Se declanșează atunci când o reîmprospătare pentru o sursă de date reușește.</span><span class="sxs-lookup"><span data-stu-id="fa034-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="fa034-109">Se declanșează atunci când un prag este trecut pe un segment.</span><span class="sxs-lookup"><span data-stu-id="fa034-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="fa034-110">Declanșatorul se limitează la trecerea peste prag.</span><span class="sxs-lookup"><span data-stu-id="fa034-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="fa034-111">Se declanșează atunci când un prag este trecut pe o măsură de business.</span><span class="sxs-lookup"><span data-stu-id="fa034-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="fa034-112">Numai măsurile de business fără o dimensiune sunt acceptate.</span><span class="sxs-lookup"><span data-stu-id="fa034-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="fa034-113">Declanșatorul se limitează la trecerea peste prag.</span><span class="sxs-lookup"><span data-stu-id="fa034-113">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="fa034-114">Declanșați când se finalizează o reîmprospătare completă (surse de date, segmente, măsuri, ...).</span><span class="sxs-lookup"><span data-stu-id="fa034-114">Trigger when a full refresh of (data sources, segments, measures, ...) is completed.</span></span>
- <span data-ttu-id="fa034-115">Se declanșează când este finalizată o reîmprospătare a procesului de unificare (hartă, potrivire, îmbinare).</span><span class="sxs-lookup"><span data-stu-id="fa034-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

[<span data-ttu-id="fa034-116">Configurați declanșatoarele în Power Automate.</span><span class="sxs-lookup"><span data-stu-id="fa034-116">Configure your triggers in Power Automate.</span></span>](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a><span data-ttu-id="fa034-117">acțiuni Power Automate</span><span class="sxs-lookup"><span data-stu-id="fa034-117">Power Automate actions</span></span>

<span data-ttu-id="fa034-118">Conectorul Power Automate oferă alte acțiuni decât declanșatoarele disponibile.</span><span class="sxs-lookup"><span data-stu-id="fa034-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="fa034-119">Pentru mai multe informaţii, consultaţi [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="fa034-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="fa034-120">Creați un flux Power Automate</span><span class="sxs-lookup"><span data-stu-id="fa034-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="fa034-121">În Detalii despre audiență, accesați **Administrator** > **Destinații export**.</span><span class="sxs-lookup"><span data-stu-id="fa034-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="fa034-122">Pe dala **Power Automate**, selectați **Configurare**.</span><span class="sxs-lookup"><span data-stu-id="fa034-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="fa034-123">Se deschide conectorul Customer Insights (previzualizare) în Power Automate.</span><span class="sxs-lookup"><span data-stu-id="fa034-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="fa034-124">**Conectare** la Power Automate.</span><span class="sxs-lookup"><span data-stu-id="fa034-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="fa034-125">Alegeți unul dintre declanșatoarele disponibile și adăugați mai mulți pași la noul dvs. flux.</span><span class="sxs-lookup"><span data-stu-id="fa034-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="fa034-126">Pentru mai multe informații, consultați [Creați un flux pentru cloud în Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="fa034-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="fa034-127">Exemple de utilizare a fluxurilor:</span><span class="sxs-lookup"><span data-stu-id="fa034-127">Examples of how to use flows:</span></span> 
- <span data-ttu-id="fa034-128">Postează un mesaj către un canal Microsoft Teams dacă o reîmprospătare sursă de date eșuează.</span><span class="sxs-lookup"><span data-stu-id="fa034-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="fa034-129">Trimiteți un e-mail proprietarilor de date atunci când este trecut un prag pe un segment.</span><span class="sxs-lookup"><span data-stu-id="fa034-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
