---
title: Conector Power Automate | Microsoft Docs
description: Creați fluxuri în Microsoft Power Automate din Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597940"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="73fbc-103">Conector Power Automate (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="73fbc-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="73fbc-104">Declanșați evenimente specifice care să aibă loc automat atunci când datele se modifică și gestionați fluxurile mai complexe direct în [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="73fbc-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="73fbc-105">declanșatoare Power Automate</span><span class="sxs-lookup"><span data-stu-id="73fbc-105">Power Automate triggers</span></span>

<span data-ttu-id="73fbc-106">Utilizați declanșatoarele pentru a crea fluxuri cloud și pentru a automatiza sarcini repetitive, cum ar fi notificări sau acțiuni mai avansate.</span><span class="sxs-lookup"><span data-stu-id="73fbc-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="73fbc-107">Se declanșează atunci când o reîmprospătare pentru o sursă de date eșuează.</span><span class="sxs-lookup"><span data-stu-id="73fbc-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="73fbc-108">Se declanșează atunci când o reîmprospătare pentru o sursă de date reușește.</span><span class="sxs-lookup"><span data-stu-id="73fbc-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="73fbc-109">Se declanșează atunci când un prag este trecut pe un segment.</span><span class="sxs-lookup"><span data-stu-id="73fbc-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="73fbc-110">Declanșatorul se limitează la trecerea peste prag.</span><span class="sxs-lookup"><span data-stu-id="73fbc-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="73fbc-111">Se declanșează atunci când un prag este trecut pe o măsură de business.</span><span class="sxs-lookup"><span data-stu-id="73fbc-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="73fbc-112">Declanșatorul se limitează la trecerea peste prag.</span><span class="sxs-lookup"><span data-stu-id="73fbc-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="73fbc-113">Declanșați când se finalizează o reîmprospătare completă (surse de date, segmente, măsuri,...).</span><span class="sxs-lookup"><span data-stu-id="73fbc-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="73fbc-114">Se declanșează când este finalizată o reîmprospătare a procesului de unificare (hartă, potrivire, îmbinare).</span><span class="sxs-lookup"><span data-stu-id="73fbc-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="73fbc-115">[Configurați declanșatoarele în Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="73fbc-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="73fbc-116">acțiuni Power Automate</span><span class="sxs-lookup"><span data-stu-id="73fbc-116">Power Automate actions</span></span>
<span data-ttu-id="73fbc-117">Conectorul Power Automate oferă alte acțiuni decât declanșatoarele disponibile.</span><span class="sxs-lookup"><span data-stu-id="73fbc-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="73fbc-118">Pentru mai multe informaţii, consultaţi [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="73fbc-118">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="73fbc-119">Creați un flux Power Automate</span><span class="sxs-lookup"><span data-stu-id="73fbc-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="73fbc-120">În Detalii despre audiență, accesați **Administrator** > **Destinații export**.</span><span class="sxs-lookup"><span data-stu-id="73fbc-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="73fbc-121">Pe dala **Power Automate**, selectați **Configurare**.</span><span class="sxs-lookup"><span data-stu-id="73fbc-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="73fbc-122">Se deschide conectorul Customer Insights (previzualizare) în Power Automate.</span><span class="sxs-lookup"><span data-stu-id="73fbc-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="73fbc-123">**Conectare** la Power Automate.</span><span class="sxs-lookup"><span data-stu-id="73fbc-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="73fbc-124">Alegeți unul dintre declanșatoarele disponibile și adăugați mai mulți pași la noul dvs. flux.</span><span class="sxs-lookup"><span data-stu-id="73fbc-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="73fbc-125">Pentru mai multe informații, consultați [Creați un flux pentru cloud în Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="73fbc-125">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="73fbc-126">Exemple de utilizare a fluxurilor:</span><span class="sxs-lookup"><span data-stu-id="73fbc-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="73fbc-127">Postează un mesaj către un canal Microsoft Teams dacă o reîmprospătare sursă de date eșuează.</span><span class="sxs-lookup"><span data-stu-id="73fbc-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="73fbc-128">Trimiteți un e-mail proprietarilor de date atunci când este trecut un prag pe un segment.</span><span class="sxs-lookup"><span data-stu-id="73fbc-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]