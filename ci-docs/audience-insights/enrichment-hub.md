---
title: Îmbogățire profiluri de clienți unificate
description: Folosiți capacitățile pentru a vă îmbogăți datele clienților.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667109"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="070c4-103">Îmbogățirea profilurilor clienților (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="070c4-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="070c4-104">Utilizați date din surse precum Microsoft și de la alți parteneri pentru a vă îmbogăți datele clienților.</span><span class="sxs-lookup"><span data-stu-id="070c4-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pagină hub de îmbogățire":::

<span data-ttu-id="070c4-106">În statisticile publicului, accesați **Date** > **Îmbogățire** pentru a lucra cu opțiuni de îmbogățire.</span><span class="sxs-lookup"><span data-stu-id="070c4-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="070c4-107">Trebuie să aveți permisiuni de Colaborator sau Administrator pentru a crea sau edita îmbogățirile.</span><span class="sxs-lookup"><span data-stu-id="070c4-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="070c4-108">Pentru mai multe informații, consultați [Permisiuni](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="070c4-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="070c4-109">Pe fila **Descoperire**, veți găsi următoarele îmbogățiri:</span><span class="sxs-lookup"><span data-stu-id="070c4-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="070c4-110">[Mărcile](enrichment-microsoft-graph.md) furnizate de Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="070c4-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="070c4-111">[Interesele](enrichment-microsoft-graph.md) furnizate de Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="070c4-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="070c4-112">[Datele companiei](enrichment-leadspace.md) furnizate de Leadspace</span><span class="sxs-lookup"><span data-stu-id="070c4-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="070c4-113">[Date demografice](enrichment-experian.md) furnizate de Experian</span><span class="sxs-lookup"><span data-stu-id="070c4-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="070c4-114">[Date despre locație](enrichment-here.md) furnizate de HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="070c4-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="070c4-115">[Date particularizate](enrichment-SFTP-custom-import.md) prin Protocol de transfer securizat al fișierelor (SFTP)</span><span class="sxs-lookup"><span data-stu-id="070c4-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="070c4-116">Pe fila **Îmbogățirile mele**, puteți vedea îmbogățirile pe care le-ați configurat și le puteți edita proprietățile.</span><span class="sxs-lookup"><span data-stu-id="070c4-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="070c4-117">Gestionarea îmbogățirilor existente</span><span class="sxs-lookup"><span data-stu-id="070c4-117">Manage existing enrichments</span></span>

<span data-ttu-id="070c4-118">Accesați **Îmbogățirile mele** pentru a vedea toate îmbogățirile configurate.</span><span class="sxs-lookup"><span data-stu-id="070c4-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="070c4-119">Fiecare îmbogățire este reprezentată ca un rând care include informații suplimentare despre îmbogățire.</span><span class="sxs-lookup"><span data-stu-id="070c4-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="070c4-120">Selectați o îmbogățire pentru a vedea opțiunile disponibile.</span><span class="sxs-lookup"><span data-stu-id="070c4-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="070c4-121">Alternativ, puteți selecta elipsele (...) de pe un element din listă pentru a vedea opțiunile.</span><span class="sxs-lookup"><span data-stu-id="070c4-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opțiuni de gestionare a îmbogățirilor din lista îmbogățirilor":::

- <span data-ttu-id="070c4-123">**Vizualizare** detalii de îmbogățire cu numărul de profiluri de clienți îmbogățite.</span><span class="sxs-lookup"><span data-stu-id="070c4-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="070c4-124">**Editați** configurația de îmbogățire.</span><span class="sxs-lookup"><span data-stu-id="070c4-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="070c4-125">**Rulați** îmbogățirea pentru actualizarea profilurilor clienților cu cele mai recente date.</span><span class="sxs-lookup"><span data-stu-id="070c4-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="070c4-126">**Dezactivați** o îmbogățire existentă pentru a o opri din actualizarea automată cu fiecare actualizare programată.</span><span class="sxs-lookup"><span data-stu-id="070c4-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="070c4-127">Datele din ultima actualizare reușită vor continua să fie disponibile.</span><span class="sxs-lookup"><span data-stu-id="070c4-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="070c4-128">**Activați** o îmbogățire inactivă pentru a reporni actualizarea automată cu fiecare actualizare programată.</span><span class="sxs-lookup"><span data-stu-id="070c4-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="070c4-129">**Ștergeți** o îmbogățire.</span><span class="sxs-lookup"><span data-stu-id="070c4-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="070c4-130">Puteți rula sau dezactiva mai multe îmbogățiri simultan selectându-le în listă.</span><span class="sxs-lookup"><span data-stu-id="070c4-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="070c4-131">Opțiunile de vizualizare și editare nu sunt disponibile ca acțiune în bloc și funcționează doar pentru câte o îmbogățire pe rând.</span><span class="sxs-lookup"><span data-stu-id="070c4-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>
