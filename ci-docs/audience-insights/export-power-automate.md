---
title: Conector Power Automate | Microsoft Docs
description: Creați fluxuri în Microsoft Power Automate din Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406662"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="bd2e1-103">Conector Power Automate (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="bd2e1-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="bd2e1-104">Declanșați evenimente specifice care să aibă loc automat atunci când datele se modifică și gestionați fluxurile mai complexe direct în [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="bd2e1-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="bd2e1-105">declanșatoare Power Automate</span><span class="sxs-lookup"><span data-stu-id="bd2e1-105">Power Automate triggers</span></span>

<span data-ttu-id="bd2e1-106">Puteți utiliza o varietate de declanșatoare care vă permit să creați fluxuri pentru a automatiza sarcini repetitive, cum ar fi notificări sau acțiuni mai avansate.</span><span class="sxs-lookup"><span data-stu-id="bd2e1-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="bd2e1-107">Se declanșează atunci când o reîmprospătare pentru o sursă de date eșuează.</span><span class="sxs-lookup"><span data-stu-id="bd2e1-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="bd2e1-108">Se declanșează atunci când o reîmprospătare pentru o sursă de date reușește.</span><span class="sxs-lookup"><span data-stu-id="bd2e1-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="bd2e1-109">Se declanșează atunci când un prag este trecut pe un segment.</span><span class="sxs-lookup"><span data-stu-id="bd2e1-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="bd2e1-110">Declanșatorul se limitează la trecerea peste prag.</span><span class="sxs-lookup"><span data-stu-id="bd2e1-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="bd2e1-111">Se declanșează atunci când un prag este trecut pe o măsură de business.</span><span class="sxs-lookup"><span data-stu-id="bd2e1-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="bd2e1-112">Declanșatorul se limitează la trecerea peste prag.</span><span class="sxs-lookup"><span data-stu-id="bd2e1-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="bd2e1-113">Declanșați când se finalizează o reîmprospătare completă (surse de date, segmente, măsuri,...).</span><span class="sxs-lookup"><span data-stu-id="bd2e1-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="bd2e1-114">Se declanșează când este finalizată o reîmprospătare a procesului de unificare (hartă, potrivire, îmbinare).</span><span class="sxs-lookup"><span data-stu-id="bd2e1-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="bd2e1-115">[Configurați declanșatoarele în Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="bd2e1-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="bd2e1-116">acțiuni Power Automate</span><span class="sxs-lookup"><span data-stu-id="bd2e1-116">Power Automate actions</span></span>
<span data-ttu-id="bd2e1-117">Conectorul Power Automate oferă alte acțiuni decât declanșatoarele disponibile.</span><span class="sxs-lookup"><span data-stu-id="bd2e1-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="bd2e1-118">Pentru mai multe informaţii, consultaţi [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="bd2e1-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="bd2e1-119">Creează un flux Power Automate în Detalii despre audiență</span><span class="sxs-lookup"><span data-stu-id="bd2e1-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="bd2e1-120">În Detalii despre audiență, accesați **Administrator** > **Sistem**.</span><span class="sxs-lookup"><span data-stu-id="bd2e1-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="bd2e1-121">Pe pagina **Sistem**, selectați fila **Stare**.</span><span class="sxs-lookup"><span data-stu-id="bd2e1-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="bd2e1-122">În secțiunea **Surse de date**, selectați **Fluxuri** și selectați **Creați un flux** din lista verticală.</span><span class="sxs-lookup"><span data-stu-id="bd2e1-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bd2e1-123">Conectorul ![Power Automate care arată Crearea unei acțiuni de flux](media/power-automate-connector-create-flow.png "Conectorul Power Automate care arată Crearea unei acțiuni de flux")</span><span class="sxs-lookup"><span data-stu-id="bd2e1-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="bd2e1-124">În Power Automate, selectați unul dintre declanșatorii disponibili pentru a crea fluxul preferat.</span><span class="sxs-lookup"><span data-stu-id="bd2e1-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="bd2e1-125">Când creați primul flux, trebuie să vă autentificați cu mai întâi cu conectorul Power Automate.</span><span class="sxs-lookup"><span data-stu-id="bd2e1-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
