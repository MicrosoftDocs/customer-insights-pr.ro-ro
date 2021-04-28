---
title: Utilizați sursele de date pentru ingerarea datelor
description: Aflați cum să importați date din diverse surse.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887909"
---
# <a name="data-sources-overview"></a><span data-ttu-id="fd59c-103">Prezentare generală surse de date</span><span class="sxs-lookup"><span data-stu-id="fd59c-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="fd59c-104">Capacitatea Detalii despre audiență din Dynamics 365 Customer Insights se conectează la date dintr-un set larg de surse.</span><span class="sxs-lookup"><span data-stu-id="fd59c-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="fd59c-105">Conectarea la un sursă de date este adesea denumită procesul de *ingerare de date*.</span><span class="sxs-lookup"><span data-stu-id="fd59c-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="fd59c-106">După ingerarea datelor, puteți [unifica](data-unification.md) și lua măsuri în legătură cu acestea.</span><span class="sxs-lookup"><span data-stu-id="fd59c-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="fd59c-107">Adăugați o sursă de date</span><span class="sxs-lookup"><span data-stu-id="fd59c-107">Add a data source</span></span>

<span data-ttu-id="fd59c-108">Consultați articolele detaliate despre cum să adăugați o sursă de date, în funcție de opțiunea pe care o alegeți.</span><span class="sxs-lookup"><span data-stu-id="fd59c-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="fd59c-109">Puteți adăuga o sursă de date în trei moduri principale:</span><span class="sxs-lookup"><span data-stu-id="fd59c-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="fd59c-110">Prin zeci de conectori Power Query</span><span class="sxs-lookup"><span data-stu-id="fd59c-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="fd59c-111">Dintr-un folder Common Data Model</span><span class="sxs-lookup"><span data-stu-id="fd59c-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="fd59c-112">Din propriul Common Data Service lake</span><span class="sxs-lookup"><span data-stu-id="fd59c-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="fd59c-113">Adăugați date din sursele de date locale</span><span class="sxs-lookup"><span data-stu-id="fd59c-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="fd59c-114">Ingerarea datelor din sursele de date locale în Detalii despre audiență este acceptată pe baza de fluxuri de date Power Platform.</span><span class="sxs-lookup"><span data-stu-id="fd59c-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="fd59c-115">Fluxurile de date pot fi activate în Customer Insights prin [furnizarea adresei URL a mediului Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) la configurarea mediului.</span><span class="sxs-lookup"><span data-stu-id="fd59c-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="fd59c-116">Sursele de date care sunt create după asocierea unui mediu Dataverse cu Customer Insights vor utiliza [fluxuri de date Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) în mod implicit.</span><span class="sxs-lookup"><span data-stu-id="fd59c-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="fd59c-117">Fluxurile de date acceptă conectivitate locală folosind gateway-urile de date.</span><span class="sxs-lookup"><span data-stu-id="fd59c-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="fd59c-118">Eliminați și recreați sursele de date care existau înainte ca mediul Dataverse să fi fost asociat pentru a utiliza gateway-urile de date locale.</span><span class="sxs-lookup"><span data-stu-id="fd59c-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="fd59c-119">Gateway-urile de date de la un mediu existent Power BI sau Power Apps vor fi vizibile și le puteți reutiliza în Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fd59c-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="fd59c-120">Pagina surselor de date afișează linkuri pentru a accesa mediul Power Platform în care puteți vizualiza și configura gateway-urile de date locale.</span><span class="sxs-lookup"><span data-stu-id="fd59c-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Captură de ecran a paginii surselor de date care prezintă link-uri care indică spre mediul Power Platform.":::

## <a name="review-ingested-data"></a><span data-ttu-id="fd59c-122">Examinați datele ingerate</span><span class="sxs-lookup"><span data-stu-id="fd59c-122">Review ingested data</span></span>

<span data-ttu-id="fd59c-123">Veți vedea numele fiecărei surse de date ingerate, starea acesteia și ultima dată când datele au fost actualizate pentru sursa respectivă.</span><span class="sxs-lookup"><span data-stu-id="fd59c-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="fd59c-124">Puteți sorta lista surselor de date după fiecare coloană.</span><span class="sxs-lookup"><span data-stu-id="fd59c-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fd59c-125">![Sursă de date adăugată](media/configure-data-datasource-added.png "Sursă de date adăugată")</span><span class="sxs-lookup"><span data-stu-id="fd59c-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="fd59c-126">Stare</span><span class="sxs-lookup"><span data-stu-id="fd59c-126">Status</span></span>  |<span data-ttu-id="fd59c-127">Descriere</span><span class="sxs-lookup"><span data-stu-id="fd59c-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="fd59c-128">Reușit</span><span class="sxs-lookup"><span data-stu-id="fd59c-128">Successful</span></span>   |<span data-ttu-id="fd59c-129">Sursa de date a fost ingerată cu succes dacă este menționat un timp în coloana **Reîmprospătat**.</span><span class="sxs-lookup"><span data-stu-id="fd59c-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="fd59c-130">Neînceput</span><span class="sxs-lookup"><span data-stu-id="fd59c-130">Not started</span></span>   |<span data-ttu-id="fd59c-131">Sursa de date nu are încă date ingerate sau este încă în modul schiță.</span><span class="sxs-lookup"><span data-stu-id="fd59c-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="fd59c-132">Se reîmprospătează</span><span class="sxs-lookup"><span data-stu-id="fd59c-132">Refreshing</span></span>    |<span data-ttu-id="fd59c-133">Ingestia datelor este în curs.</span><span class="sxs-lookup"><span data-stu-id="fd59c-133">Data ingestion is in progress.</span></span> <span data-ttu-id="fd59c-134">Aveți posibilitatea de a revoca această operațiune selectând **Oprire reîmprospătare** în coloana **Acțiuni**.</span><span class="sxs-lookup"><span data-stu-id="fd59c-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="fd59c-135">Oprirea reîmprospătării unei surse de date o va readuce la ultima stare de reîmprospătare.</span><span class="sxs-lookup"><span data-stu-id="fd59c-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="fd59c-136">Nereușite</span><span class="sxs-lookup"><span data-stu-id="fd59c-136">Failed</span></span>     |<span data-ttu-id="fd59c-137">Ingerarea de date s-a efectuat cu erori.</span><span class="sxs-lookup"><span data-stu-id="fd59c-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="fd59c-138">Selectați valoarea în coloana **Stare** a oricărei sursă de date pentru a revizui mai multe detalii.</span><span class="sxs-lookup"><span data-stu-id="fd59c-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="fd59c-139">În panoul **Detalii despre progres**, extindeți **Surse de date**.</span><span class="sxs-lookup"><span data-stu-id="fd59c-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="fd59c-140">Selectați **Consultați detalii** pentru mai multe informații despre starea de reîmprospătare, inclusiv detalii despre erori și actualizări de proces descendent.</span><span class="sxs-lookup"><span data-stu-id="fd59c-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="fd59c-141">Încărcarea datelor ar putea lua ceva timp.</span><span class="sxs-lookup"><span data-stu-id="fd59c-141">Loading data can take some time.</span></span> <span data-ttu-id="fd59c-142">După o reîmprospătare reușită, datele ingerate pot fi revizuite din pagina **Entități**.</span><span class="sxs-lookup"><span data-stu-id="fd59c-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="fd59c-143">Pentru mai multe informații, consultați [Entități](entities.md).</span><span class="sxs-lookup"><span data-stu-id="fd59c-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="fd59c-144">Reîmprospătați o sursă de date</span><span class="sxs-lookup"><span data-stu-id="fd59c-144">Refresh a data source</span></span>

<span data-ttu-id="fd59c-145">Sursele de date pot fi reîmprospătate într-un program automat sau reîmprospătate manual la cerere.</span><span class="sxs-lookup"><span data-stu-id="fd59c-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="fd59c-146">Accesați **Administrator** > **Sistem** > [**Planificare**](system.md#schedule-tab) pentru a configura reîmprospătările planificate ale tuturor surselor de date ingerate.</span><span class="sxs-lookup"><span data-stu-id="fd59c-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="fd59c-147">Pentru a actualiza o sursă de date la cerere, urmați acești pași:</span><span class="sxs-lookup"><span data-stu-id="fd59c-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="fd59c-148">În Detalii despre audiență, accesați **Date** > **Surse de date**</span><span class="sxs-lookup"><span data-stu-id="fd59c-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="fd59c-149">Selectați elipsele verticale de lângă sursa de date pe care doriți să o reîmprospătați și selectați **Reîmprospătare** din lista verticală.</span><span class="sxs-lookup"><span data-stu-id="fd59c-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="fd59c-150">Sursa de date este acum declanșată pentru o reîmprospătare manuală.</span><span class="sxs-lookup"><span data-stu-id="fd59c-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="fd59c-151">Reîmprospătarea unei surse de date va actualiza atât schema entității, cât și datele pentru toate entitățile specificate în sursa de date.</span><span class="sxs-lookup"><span data-stu-id="fd59c-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="fd59c-152">Selectați **Oprire reîmprospătare** dacă doriți să anulați o reîmprospătare existentă iar sursa de date va reveni la ultima sa stare de reîmprospătare.</span><span class="sxs-lookup"><span data-stu-id="fd59c-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="fd59c-153">Ștergerea unei surse de date</span><span class="sxs-lookup"><span data-stu-id="fd59c-153">Delete a data source</span></span>

1. <span data-ttu-id="fd59c-154">În Detalii despre audiență, accesați **Date** > **Surse de date**.</span><span class="sxs-lookup"><span data-stu-id="fd59c-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="fd59c-155">Selectați elipsa verticală de lângă sursa de date pe care doriți să o eliminați și selectați **Ștergeți** din meniul cu selectare multiplă.</span><span class="sxs-lookup"><span data-stu-id="fd59c-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="fd59c-156">Confirmați ștergerea.</span><span class="sxs-lookup"><span data-stu-id="fd59c-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
