---
title: Îmbogățire profiluri de clienți unificate
description: Folosiți capacitățile pentru a vă îmbogăți datele clienților.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305263"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="914b1-103">Îmbogățirea profilurilor clienților (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="914b1-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="914b1-104">Utilizați date din surse precum Microsoft și de la alți parteneri pentru a vă îmbogăți datele clienților.</span><span class="sxs-lookup"><span data-stu-id="914b1-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pagină hub de îmbogățire":::

<span data-ttu-id="914b1-106">În statisticile publicului, accesați **Date** > **Îmbogățire** pentru a lucra cu opțiuni de îmbogățire.</span><span class="sxs-lookup"><span data-stu-id="914b1-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>  

<span data-ttu-id="914b1-107">Trebuie să aveți permisiuni de Colaborator sau Administrator pentru a crea sau edita îmbogățirile.</span><span class="sxs-lookup"><span data-stu-id="914b1-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="914b1-108">Pentru mai multe informații, consultați [Permisiuni](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="914b1-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="914b1-109">Pe fila **Descoperire**, veți găsi următoarele îmbogățiri:</span><span class="sxs-lookup"><span data-stu-id="914b1-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="914b1-110">[Branduri](enrichment-microsoft.md) furnizate de Microsoft</span><span class="sxs-lookup"><span data-stu-id="914b1-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="914b1-111">[Interese](enrichment-microsoft.md) furnizate de Microsoft</span><span class="sxs-lookup"><span data-stu-id="914b1-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="914b1-112">[Adrese îmbunătățite](enrichment-enhanced-addresses.md) furnizate de Microsoft</span><span class="sxs-lookup"><span data-stu-id="914b1-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="914b1-113">[Datele companiei](enrichment-leadspace.md) furnizate de Leadspace</span><span class="sxs-lookup"><span data-stu-id="914b1-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="914b1-114">[Date demografice](enrichment-experian.md) furnizate de Experian</span><span class="sxs-lookup"><span data-stu-id="914b1-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="914b1-115">[Date despre locație](enrichment-here.md) furnizate de HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="914b1-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="914b1-116">[Date particularizate](enrichment-SFTP-custom-import.md) prin Protocol de transfer securizat al fișierelor (SFTP)</span><span class="sxs-lookup"><span data-stu-id="914b1-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="914b1-117">Pe fila **Îmbogățirile mele**, puteți vedea îmbogățirile pe care le-ați configurat și le puteți edita proprietățile.</span><span class="sxs-lookup"><span data-stu-id="914b1-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="914b1-118">Gestionarea îmbogățirilor existente</span><span class="sxs-lookup"><span data-stu-id="914b1-118">Manage existing enrichments</span></span>

<span data-ttu-id="914b1-119">Accesați fila **Îmbogățirile mele** pentru a vedea toate îmbogățirile configurate.</span><span class="sxs-lookup"><span data-stu-id="914b1-119">Go to the **My enrichments** tab to see all configured enrichments.</span></span> <span data-ttu-id="914b1-120">Fiecare îmbogățire este reprezentată ca un rând care include informații suplimentare despre îmbogățire.</span><span class="sxs-lookup"><span data-stu-id="914b1-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="914b1-121">Selectați o îmbogățire pentru a vedea opțiunile disponibile.</span><span class="sxs-lookup"><span data-stu-id="914b1-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="914b1-122">De asemenea, puteți selecta punctele de suspensie (...) pe un element din listă pentru a vedea opțiunile.</span><span class="sxs-lookup"><span data-stu-id="914b1-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opțiuni de gestionare a îmbogățirilor din lista îmbogățirilor":::

- <span data-ttu-id="914b1-124">**Vizualizare** detalii de îmbogățire cu numărul de profiluri de clienți îmbogățite.</span><span class="sxs-lookup"><span data-stu-id="914b1-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="914b1-125">**Editați** configurația de îmbogățire.</span><span class="sxs-lookup"><span data-stu-id="914b1-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="914b1-126">**Rulați** îmbogățirea pentru actualizarea profilurilor clienților cu cele mai recente date.</span><span class="sxs-lookup"><span data-stu-id="914b1-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="914b1-127">**Dezactivați** o îmbogățire existentă pentru a o opri din actualizarea automată cu fiecare actualizare programată.</span><span class="sxs-lookup"><span data-stu-id="914b1-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="914b1-128">Datele din ultima actualizare reușită vor continua să fie disponibile.</span><span class="sxs-lookup"><span data-stu-id="914b1-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="914b1-129">**Activați** o îmbogățire inactivă pentru a reporni actualizarea automată cu fiecare actualizare programată.</span><span class="sxs-lookup"><span data-stu-id="914b1-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="914b1-130">**Ștergeți** o îmbogățire.</span><span class="sxs-lookup"><span data-stu-id="914b1-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="914b1-131">Puteți rula sau dezactiva mai multe îmbogățiri simultan selectându-le în listă.</span><span class="sxs-lookup"><span data-stu-id="914b1-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="914b1-132">Opțiunile de vizualizare și editare nu sunt disponibile ca acțiune în bloc și funcționează doar pentru câte o îmbogățire pe rând.</span><span class="sxs-lookup"><span data-stu-id="914b1-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="914b1-133">Îmbogățiri și conexiuni</span><span class="sxs-lookup"><span data-stu-id="914b1-133">Enrichments and connections</span></span>

<span data-ttu-id="914b1-134">Îmbogățirile terților sunt configurate folosind [conexiuni](connections.md), pe care un administrator le înființează cu acreditări și oferă consimțământul pentru transferurile de date.</span><span class="sxs-lookup"><span data-stu-id="914b1-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="914b1-135">Conexiunea poate fi utilizată de administratori și contribuitori pentru a configura îmbogățiri.</span><span class="sxs-lookup"><span data-stu-id="914b1-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="914b1-136">Îmbogățiri multiple de același tip</span><span class="sxs-lookup"><span data-stu-id="914b1-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="914b1-137">Entitatea care urmează să fie îmbogățită este specificată în timpul configurației de îmbogățire, care vă permite să îmbogățiți doar un subset de profiluri.</span><span class="sxs-lookup"><span data-stu-id="914b1-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="914b1-138">De exemplu, îmbogățiți datele numai pentru un anumit segment.</span><span class="sxs-lookup"><span data-stu-id="914b1-138">For example, enrich data only for a specific segment.</span></span> <span data-ttu-id="914b1-139">Puteți configura mai multe îmbogățiri de același tip și reutiliza aceeași conexiune.</span><span class="sxs-lookup"><span data-stu-id="914b1-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="914b1-140">Unele îmbogățiri vor avea limite la numărul de îmbogățiri de același tip care pot fi create.</span><span class="sxs-lookup"><span data-stu-id="914b1-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="914b1-141">Limitele și utilizarea curentă pot fi văzute pe pagina **Îmbogățire**.</span><span class="sxs-lookup"><span data-stu-id="914b1-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
