---
title: Ingerarea și limitările datelor în timp real
description: Informații generale despre capacitățile în timp real în detalii despre public.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270295"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="514e8-103">Ingestie date în timp real (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="514e8-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="514e8-104">Funcționalitatea aproape în timp real vă permite să vedeți, în câteva secunde, cele mai recente interacțiuni pe care clienții dvs. le-au făcut cu produsele sau serviciile dvs.</span><span class="sxs-lookup"><span data-stu-id="514e8-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="514e8-105">[Reîmprospătări programate](system.md#schedule-tab) includ un număr mare de înregistrări și mai multe operațiuni complexe.</span><span class="sxs-lookup"><span data-stu-id="514e8-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="514e8-106">În primul rând, datele sunt extrase din sursa de date.</span><span class="sxs-lookup"><span data-stu-id="514e8-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="514e8-107">În continuare, datele sunt unificate, apoi îmbogățite cu informații suplimentare.</span><span class="sxs-lookup"><span data-stu-id="514e8-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="514e8-108">Fiecare rulare a acestui proces poate dura de la câteva minute la câteva ore.</span><span class="sxs-lookup"><span data-stu-id="514e8-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="514e8-109">Funcționalitatea în timp real oferă date imediat pentru consum, până când actualizarea planificată ulterioară extrage aceste date din sursa de date.</span><span class="sxs-lookup"><span data-stu-id="514e8-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="514e8-110">Actualizările în timp real au un termen de expirare, după care nu mai suprascriu valoarea din sursă de date:</span><span class="sxs-lookup"><span data-stu-id="514e8-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="514e8-111">Actualizările profilului vor fi păstrate timp de 4 ore</span><span class="sxs-lookup"><span data-stu-id="514e8-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="514e8-112">Activitățile se vor păstra timp de 30 de zile</span><span class="sxs-lookup"><span data-stu-id="514e8-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="514e8-113">Aceste valori sunt parametrii de apel API pe care îi puteți modifica.</span><span class="sxs-lookup"><span data-stu-id="514e8-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="514e8-114">Ei urmăresc să se asigure că datele dvs. sursă rămân sursa de adevăr.</span><span class="sxs-lookup"><span data-stu-id="514e8-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="514e8-115">Dacă doriți ca actualizările în timp real să fie incluse mai mult timp, trebuie să le adăugați la o sursă de date, astfel încât să fie trase în timpul următoarei reîmprospătări programate.</span><span class="sxs-lookup"><span data-stu-id="514e8-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="514e8-116">Actualizarea în timp real a câmpurilor unificate de profil ale clientului</span><span class="sxs-lookup"><span data-stu-id="514e8-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="514e8-117">Profilurile actualizate vor fi afișate în vizualizarea cardului clientului sau în orice altă vizualizare, în câteva secunde.</span><span class="sxs-lookup"><span data-stu-id="514e8-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="514e8-118">Deoarece operațiunile în timp real au loc după unificarea datelor, acestea se aplică numai profilurilor de clienți unificate.</span><span class="sxs-lookup"><span data-stu-id="514e8-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="514e8-119">În consecință, modificările profilului în timp real nu vor actualiza măsurile, apartenența la segment sau îmbogățirile.</span><span class="sxs-lookup"><span data-stu-id="514e8-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="514e8-120">Limitări</span><span class="sxs-lookup"><span data-stu-id="514e8-120">Limitations</span></span>

- <span data-ttu-id="514e8-121">Profilurile clienților pot fi actualizate, dar nu pot fi create sau șterse.</span><span class="sxs-lookup"><span data-stu-id="514e8-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="514e8-122">Exportul actualizărilor în timp real către sisteme externe, de exemplu Power BI, nu este posibilă în acest moment.</span><span class="sxs-lookup"><span data-stu-id="514e8-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="514e8-123">Crearea în timp real a activităților</span><span class="sxs-lookup"><span data-stu-id="514e8-123">Real-time creation of activities</span></span>

<span data-ttu-id="514e8-124">API-ul în timp real vă permite să publicați o activitate nouă din sistemul dvs. sursă (o înregistrare sursă individuală) într-un profil de client unificat.</span><span class="sxs-lookup"><span data-stu-id="514e8-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="514e8-125">Noua activitate va fi disponibilă ca activitate unificată în cronologia profilului de client unificat în câteva secunde.</span><span class="sxs-lookup"><span data-stu-id="514e8-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="514e8-126">Puteți vedea cronologia în vizualizarea cardului clientului sau orice altă integrare cronologică pe care ați configurat-o.</span><span class="sxs-lookup"><span data-stu-id="514e8-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="514e8-127">Activitățile nu se pot muta.</span><span class="sxs-lookup"><span data-stu-id="514e8-127">Activities are immutable.</span></span> <span data-ttu-id="514e8-128">Nu se schimbă odată ce au fost create.</span><span class="sxs-lookup"><span data-stu-id="514e8-128">They don't change once created.</span></span>
> - <span data-ttu-id="514e8-129">În prezent, segmentele și măsurile nu se vor actualiza în funcție de noua activitate.</span><span class="sxs-lookup"><span data-stu-id="514e8-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="514e8-130">Activitățile adăugate doar prin API-ul în timp real nu fac parte din exporturi și nu vor fi afișate în PowerBI.</span><span class="sxs-lookup"><span data-stu-id="514e8-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="514e8-131">Există două moduri de conectare la API-ul în timp real:</span><span class="sxs-lookup"><span data-stu-id="514e8-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="514e8-132">[indirect ](#connect-via-the-dynamics-365-customer-insights-connector), folosind [conectorul Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="514e8-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="514e8-133">[direct](#connect-directly-to-the-real-time-api), cu cod</span><span class="sxs-lookup"><span data-stu-id="514e8-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="514e8-134">Ambele moduri au în comun următoarele condiții preliminare:</span><span class="sxs-lookup"><span data-stu-id="514e8-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="514e8-135">Un mediu Customer Insights</span><span class="sxs-lookup"><span data-stu-id="514e8-135">A Customer Insights environment</span></span>
- <span data-ttu-id="514e8-136">Profiluri de client unificate</span><span class="sxs-lookup"><span data-stu-id="514e8-136">Unified customer profiles</span></span>
- <span data-ttu-id="514e8-137">Activități configurate și rulate</span><span class="sxs-lookup"><span data-stu-id="514e8-137">Activities configured and run</span></span>
- <span data-ttu-id="514e8-138">Permisiuni de Contribuitor sau Administrator pentru autentificarea contului</span><span class="sxs-lookup"><span data-stu-id="514e8-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="514e8-139">Conectare prin intermediul conectorului Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="514e8-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="514e8-140">API-ul în timp real poate ingera date dintr-un conector dedicat Power Platform, [conectorul Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/), fără a fi nevoie să scrieți și să implementați niciun cod.</span><span class="sxs-lookup"><span data-stu-id="514e8-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="514e8-141">Conectorul poate efectua aceleași acțiuni în timp real ca API-ul.</span><span class="sxs-lookup"><span data-stu-id="514e8-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="514e8-142">Aveți nevoie de o licență validă pentru conectori premium.</span><span class="sxs-lookup"><span data-stu-id="514e8-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="514e8-143">Pentru mai multe informații, consultați [întrebările frecvente despre licențierea Power Apps și Power Automate](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="514e8-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="514e8-144">Power Platform [Power Apps și/sau Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="514e8-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="514e8-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="514e8-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="514e8-146">Pentru detalii despre crearea fluxurilor, consultați secțiunea [documentație Power Automate](https://docs.microsoft.com/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="514e8-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="514e8-147">Conectare direct la API-ul în timp real</span><span class="sxs-lookup"><span data-stu-id="514e8-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="514e8-148">Puteți utiliza capabilitățile în timp real construindu-vă propriul canal și conectându-vă direct la API-ul în timp real.</span><span class="sxs-lookup"><span data-stu-id="514e8-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="514e8-149">Puteți posta o activitate în formatul sistemului sursă sau în formatul UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="514e8-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="514e8-150">Obțineți formatul făcând un apel API către /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="514e8-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="514e8-151">Detalii despre acest API, inclusiv parametrii și răspunsurile, pot fi găsite în secțiunea **EntityData** de pe [Referința API-urilor Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="514e8-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="514e8-152">Pentru informații suplimentare, consultați [Lucrul cu API-uri Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="514e8-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="514e8-153">Înțelegeți utilizarea dvs. în timp real cu telemetria</span><span class="sxs-lookup"><span data-stu-id="514e8-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="514e8-154">Obțineți o prezentare generală a volumului de solicitări către API-ul în timp real și informații despre problemele pe care le poate întâmpina sistemul.</span><span class="sxs-lookup"><span data-stu-id="514e8-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="514e8-155">Puteți [accesa telemetria în timp real](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="514e8-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]