---
title: Reîmprospătare incrementală pentru sursele de date bazate pe Power Query
description: Reîmprospătați date noi și actualizate pentru surse mari de date bazate pe Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406697"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="3fe4d-103">Reîmprospătare incrementală pentru sursele de date bazate pe Power Query</span><span class="sxs-lookup"><span data-stu-id="3fe4d-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="3fe4d-104">Reîmprospătarea incrementală pentru sursele de date oferă următoarele avantaje:</span><span class="sxs-lookup"><span data-stu-id="3fe4d-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="3fe4d-105">**Reîmprospătări mai rapide** - Numai datele care s-au schimbat se reîmprospătează.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="3fe4d-106">De exemplu, este posibil să reîmprospătați doar ultimele cinci zile ale unui set de date istoric.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="3fe4d-107">**Fiabilitate crescută** - Cu actualizări mai mici, nu trebuie să mențineți conexiunile la sisteme volatile pentru o perioadă lungă de timp, reducând riscul apariției problemelor de conectare.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="3fe4d-108">**Consum redus de resurse** - Reîmprospătarea doar a unui subset din datele dvs. totale duce la utilizarea mai eficientă a resurselor de calcul și reduce amprenta asupra mediului.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="3fe4d-109">Configurați reîmprospătarea incrementală</span><span class="sxs-lookup"><span data-stu-id="3fe4d-109">Configure incremental refresh</span></span>

<span data-ttu-id="3fe4d-110">Statisticile despre public permit reîmprospătarea incrementală pentru sursele de date importate prin Power Query care acceptă ingestia incrementală.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="3fe4d-111">De exemplu, bazele de date SQL Azure cu câmpuri de dată și oră, care indică momentul în care înregistrările de date au fost actualizate ultima dată.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="3fe4d-112">[Creați o nouă sursă de date bazată pe Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="3fe4d-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="3fe4d-113">Furnizați un nume pentru sursa de date.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="3fe4d-114">Selectați o sursă de date care acceptă actualizare incrementală, cum ar fi baza de date SQL Azure.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="3fe4d-115">Selectați entitățile sau tabelele de ingerat.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="3fe4d-116">Finalizați etapele de transformare și selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="3fe4d-117">În caseta de dialog **Configurați reîmprospătare incrementală**, selectați **Configurat** pentru a deschide **Setări de reîmprospătare incrementală**.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="3fe4d-118">Dacă selectați **Salt**, sursa de date va reîmprospăta întregul set de date.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="3fe4d-119">Puteți aplica, de asemenea, reîmprospătarea incrementală mai târziu prin editarea unei surse de date existente.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="3fe4d-120">Pe **Setări de reîmprospătare incrementală**, veți configura reîmprospătarea incrementală pentru toate entitățile pe care le-ați selectat la crearea sursei de date.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3fe4d-121">![Configurați entitățile dintr-o sursă de date pentru reîmprospătare incrementală](media/incremental-refresh-settings.png "Configurați entitățile dintr-o sursă de date pentru reîmprospătare incrementală")</span><span class="sxs-lookup"><span data-stu-id="3fe4d-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="3fe4d-122">Selectați o entitate și furnizați următoarele detalii:</span><span class="sxs-lookup"><span data-stu-id="3fe4d-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="3fe4d-123">**Definiți cheia principală**: Selectați o cheie primară pentru entitate sau tabel.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="3fe4d-124">**Definiți câmpul „ultima actualizare”**: Acest câmp va afișa doar atributele de tip dată sau oră.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="3fe4d-125">Selectați un atribut care indică momentul în care înregistrările au fost actualizate ultima dată.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="3fe4d-126">Acesta va fi utilizat pentru a identifica înregistrările care se încadrează în intervalul de timp de reîmprospătare incrementală.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="3fe4d-127">**Verificați dacă există actualizări la fiecare**: Specificați cât timp doriți să fie intervalul de timp de reîmprospătare incremental.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="3fe4d-128">Selectați **salvare** pentru a finaliza crearea sursei de date.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="3fe4d-129">Actualizarea inițială a datelor va fi o reîmprospătare completă.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="3fe4d-130">Ulterior, reîmprospătarea de date incrementală se întâmplă așa cum este configurat în pasul anterior.</span><span class="sxs-lookup"><span data-stu-id="3fe4d-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>