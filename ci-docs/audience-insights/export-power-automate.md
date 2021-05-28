---
title: Conector Power Automate | Microsoft Docs
description: Creați fluxuri în Microsoft Power Automate din Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976103"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="1a42c-103">Conector Power Automate (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="1a42c-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="1a42c-104">Declanșați evenimente specifice care să aibă loc automat atunci când datele se modifică și gestionați fluxurile mai complexe direct în [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="1a42c-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="1a42c-105">declanșatoare Power Automate</span><span class="sxs-lookup"><span data-stu-id="1a42c-105">Power Automate triggers</span></span>

<span data-ttu-id="1a42c-106">Utilizați declanșatoarele pentru a crea fluxuri cloud și pentru a automatiza sarcini repetitive, cum ar fi notificări sau acțiuni mai avansate.</span><span class="sxs-lookup"><span data-stu-id="1a42c-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="1a42c-107">Se declanșează atunci când o reîmprospătare pentru o sursă de date eșuează.</span><span class="sxs-lookup"><span data-stu-id="1a42c-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="1a42c-108">Se declanșează atunci când o reîmprospătare pentru o sursă de date reușește.</span><span class="sxs-lookup"><span data-stu-id="1a42c-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="1a42c-109">Se declanșează atunci când un prag este trecut pe un segment.</span><span class="sxs-lookup"><span data-stu-id="1a42c-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="1a42c-110">Declanșatorul se limitează la trecerea peste prag.</span><span class="sxs-lookup"><span data-stu-id="1a42c-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="1a42c-111">Se declanșează atunci când un prag este trecut pe o măsură de business.</span><span class="sxs-lookup"><span data-stu-id="1a42c-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="1a42c-112">Numai măsurile de business fără o dimensiune sunt acceptate.</span><span class="sxs-lookup"><span data-stu-id="1a42c-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="1a42c-113">Declanșatorul se limitează la trecerea peste prag.</span><span class="sxs-lookup"><span data-stu-id="1a42c-113">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="1a42c-114">Declanșați când se finalizează o reîmprospătare completă (surse de date, segmente, măsuri,...).</span><span class="sxs-lookup"><span data-stu-id="1a42c-114">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="1a42c-115">Se declanșează când este finalizată o reîmprospătare a procesului de unificare (hartă, potrivire, îmbinare).</span><span class="sxs-lookup"><span data-stu-id="1a42c-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="1a42c-116">[Configurați declanșatoarele în Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="1a42c-116">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="1a42c-117">acțiuni Power Automate</span><span class="sxs-lookup"><span data-stu-id="1a42c-117">Power Automate actions</span></span>
<span data-ttu-id="1a42c-118">Conectorul Power Automate oferă alte acțiuni decât declanșatoarele disponibile.</span><span class="sxs-lookup"><span data-stu-id="1a42c-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="1a42c-119">Pentru mai multe informaţii, consultaţi [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="1a42c-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="1a42c-120">Creați un flux Power Automate</span><span class="sxs-lookup"><span data-stu-id="1a42c-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="1a42c-121">În Detalii despre audiență, accesați **Administrator** > **Destinații export**.</span><span class="sxs-lookup"><span data-stu-id="1a42c-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1a42c-122">Pe dala **Power Automate**, selectați **Configurare**.</span><span class="sxs-lookup"><span data-stu-id="1a42c-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="1a42c-123">Se deschide conectorul Customer Insights (previzualizare) în Power Automate.</span><span class="sxs-lookup"><span data-stu-id="1a42c-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="1a42c-124">**Conectare** la Power Automate.</span><span class="sxs-lookup"><span data-stu-id="1a42c-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="1a42c-125">Alegeți unul dintre declanșatoarele disponibile și adăugați mai mulți pași la noul dvs. flux.</span><span class="sxs-lookup"><span data-stu-id="1a42c-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="1a42c-126">Pentru mai multe informații, consultați [Creați un flux pentru cloud în Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="1a42c-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="1a42c-127">Exemple de utilizare a fluxurilor:</span><span class="sxs-lookup"><span data-stu-id="1a42c-127">Examples how to use flows:</span></span> 
- <span data-ttu-id="1a42c-128">Postează un mesaj către un canal Microsoft Teams dacă o reîmprospătare sursă de date eșuează.</span><span class="sxs-lookup"><span data-stu-id="1a42c-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="1a42c-129">Trimiteți un e-mail proprietarilor de date atunci când este trecut un prag pe un segment.</span><span class="sxs-lookup"><span data-stu-id="1a42c-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
