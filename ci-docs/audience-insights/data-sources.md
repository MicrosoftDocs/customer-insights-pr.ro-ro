---
title: Utilizați sursele de date pentru ingerarea datelor
description: Aflați cum să importați date din diverse surse.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643968"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="07ffe-103">Prezentare generală pentru surse de date</span><span class="sxs-lookup"><span data-stu-id="07ffe-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="07ffe-104">Capacitatea Detalii despre audiență din Dynamics 365 Customer Insights se conectează la date dintr-un set larg de surse.</span><span class="sxs-lookup"><span data-stu-id="07ffe-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="07ffe-105">Conectarea la un sursă de date este adesea denumită procesul de *ingerare de date*.</span><span class="sxs-lookup"><span data-stu-id="07ffe-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="07ffe-106">După ingerarea datelor, puteți [unifica](data-unification.md) și lua măsuri în legătură cu acestea.</span><span class="sxs-lookup"><span data-stu-id="07ffe-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="07ffe-107">Adăugați o sursă de date</span><span class="sxs-lookup"><span data-stu-id="07ffe-107">Add a data source</span></span>

<span data-ttu-id="07ffe-108">Consultați articolele detaliate despre cum să adăugați o sursă de date, în funcție de opțiunea pe care o alegeți.</span><span class="sxs-lookup"><span data-stu-id="07ffe-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="07ffe-109">Puteți adăuga o sursă de date în trei moduri principale:</span><span class="sxs-lookup"><span data-stu-id="07ffe-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="07ffe-110">Prin zeci de conectori Power Query</span><span class="sxs-lookup"><span data-stu-id="07ffe-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="07ffe-111">Dintr-un folder Common Data Model</span><span class="sxs-lookup"><span data-stu-id="07ffe-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="07ffe-112">Din propriul Common Data Service lake</span><span class="sxs-lookup"><span data-stu-id="07ffe-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="07ffe-113">Nu puteți adăuga încă date din sursele de date locale.</span><span class="sxs-lookup"><span data-stu-id="07ffe-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="07ffe-114">Examinați datele ingerate</span><span class="sxs-lookup"><span data-stu-id="07ffe-114">Review ingested data</span></span>

<span data-ttu-id="07ffe-115">Veți vedea numele fiecărei surse de date ingerate, starea acesteia și ultima dată când datele au fost actualizate pentru sursa respectivă.</span><span class="sxs-lookup"><span data-stu-id="07ffe-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="07ffe-116">Puteți sorta lista surselor de date după fiecare coloană.</span><span class="sxs-lookup"><span data-stu-id="07ffe-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="07ffe-117">![Sursă de date adăugată](media/configure-data-datasource-added.png "Sursă de date adăugată")</span><span class="sxs-lookup"><span data-stu-id="07ffe-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="07ffe-118">Stare</span><span class="sxs-lookup"><span data-stu-id="07ffe-118">Status</span></span>  |<span data-ttu-id="07ffe-119">Descriere</span><span class="sxs-lookup"><span data-stu-id="07ffe-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="07ffe-120">Reușit</span><span class="sxs-lookup"><span data-stu-id="07ffe-120">Successful</span></span>   |<span data-ttu-id="07ffe-121">Sursa de date a fost ingerată cu succes dacă este menționat un timp în coloana **Reîmprospătat**.</span><span class="sxs-lookup"><span data-stu-id="07ffe-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="07ffe-122">Neînceput</span><span class="sxs-lookup"><span data-stu-id="07ffe-122">Not started</span></span>   |<span data-ttu-id="07ffe-123">Sursa de date nu are încă date ingerate sau este încă în modul schiță.</span><span class="sxs-lookup"><span data-stu-id="07ffe-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="07ffe-124">Se reîmprospătează</span><span class="sxs-lookup"><span data-stu-id="07ffe-124">Refreshing</span></span>    |<span data-ttu-id="07ffe-125">Ingestia datelor este în curs.</span><span class="sxs-lookup"><span data-stu-id="07ffe-125">Data ingestion is in progress.</span></span> <span data-ttu-id="07ffe-126">Aveți posibilitatea de a revoca această operațiune selectând **Oprire reîmprospătare** în coloana **Acțiuni**.</span><span class="sxs-lookup"><span data-stu-id="07ffe-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="07ffe-127">Oprirea reîmprospătării unei surse de date o va readuce la ultima stare de reîmprospătare.</span><span class="sxs-lookup"><span data-stu-id="07ffe-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="07ffe-128">Nereuşit</span><span class="sxs-lookup"><span data-stu-id="07ffe-128">Failed</span></span>     |<span data-ttu-id="07ffe-129">Ingerarea de date s-a efectuat cu erori.</span><span class="sxs-lookup"><span data-stu-id="07ffe-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="07ffe-130">Selectați **Reîmprospătare stare** pentru a revizui mai multe detalii despre starea de reîmprospătare, inclusiv detalii despre erori și actualizări de proces descendent.</span><span class="sxs-lookup"><span data-stu-id="07ffe-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="07ffe-131">Încărcarea datelor ar putea lua ceva timp.</span><span class="sxs-lookup"><span data-stu-id="07ffe-131">Loading data can take some time.</span></span> <span data-ttu-id="07ffe-132">După o reîmprospătare reușită, datele ingerate pot fi revizuite din pagina **Entități**.</span><span class="sxs-lookup"><span data-stu-id="07ffe-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="07ffe-133">Pentru mai multe informații, consultați [Entități](entities.md).</span><span class="sxs-lookup"><span data-stu-id="07ffe-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="07ffe-134">Reîmprospătați o sursă de date</span><span class="sxs-lookup"><span data-stu-id="07ffe-134">Refresh a data source</span></span>

<span data-ttu-id="07ffe-135">Sursele de date pot fi reîmprospătate într-un program automat sau reîmprospătate manual la cerere.</span><span class="sxs-lookup"><span data-stu-id="07ffe-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="07ffe-136">Accesați **Administrator** > **Sistem** > [**Planificare**](system.md#schedule-tab) pentru a configura reîmprospătările planificate ale tuturor surselor de date ingerate.</span><span class="sxs-lookup"><span data-stu-id="07ffe-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="07ffe-137">Pentru a actualiza o sursă de date la cerere, urmați acești pași:</span><span class="sxs-lookup"><span data-stu-id="07ffe-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="07ffe-138">În Detalii despre audiență, accesați **Date** > **Surse de date**</span><span class="sxs-lookup"><span data-stu-id="07ffe-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="07ffe-139">Selectați elipsele verticale de lângă sursa de date pe care doriți să o reîmprospătați și selectați **Reîmprospătare** din lista verticală.</span><span class="sxs-lookup"><span data-stu-id="07ffe-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="07ffe-140">Sursa de date este acum declanșată pentru o reîmprospătare manuală.</span><span class="sxs-lookup"><span data-stu-id="07ffe-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="07ffe-141">Reîmprospătarea unei surse de date va actualiza atât schema entității, cât și datele pentru toate entitățile specificate în sursa de date.</span><span class="sxs-lookup"><span data-stu-id="07ffe-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="07ffe-142">Selectați **Oprire reîmprospătare** dacă doriți să anulați o reîmprospătare existentă iar sursa de date va reveni la ultima sa stare de reîmprospătare.</span><span class="sxs-lookup"><span data-stu-id="07ffe-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="07ffe-143">Ștergerea unei surse de date</span><span class="sxs-lookup"><span data-stu-id="07ffe-143">Delete a data source</span></span>

1. <span data-ttu-id="07ffe-144">În Detalii despre audiență, accesați **Date** > **Surse de date**.</span><span class="sxs-lookup"><span data-stu-id="07ffe-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="07ffe-145">Selectați elipsa verticală de lângă sursa de date pe care doriți să o eliminați și selectați **Ștergeți** din meniul cu selectare multiplă.</span><span class="sxs-lookup"><span data-stu-id="07ffe-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="07ffe-146">Confirmați ștergerea.</span><span class="sxs-lookup"><span data-stu-id="07ffe-146">Confirm your deletion.</span></span>
