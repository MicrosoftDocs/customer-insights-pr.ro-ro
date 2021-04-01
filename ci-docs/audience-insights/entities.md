---
title: Entități și seturi de date
description: Vizualizați datele pe pagina Entități.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 383523bad5105e08e57758838e90a49e805b5f9b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596422"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="ba55d-103">Entități în Detalii despre audiență</span><span class="sxs-lookup"><span data-stu-id="ba55d-103">Entities in audience insights</span></span>

<span data-ttu-id="ba55d-104">După [configurarea surselor de date](data-sources.md), accesați pagina **Entități** pentru a evalua calitatea datelor ingerate.</span><span class="sxs-lookup"><span data-stu-id="ba55d-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="ba55d-105">Entitățile sunt considerate seturi de date.</span><span class="sxs-lookup"><span data-stu-id="ba55d-105">Entities are considered datasets.</span></span> <span data-ttu-id="ba55d-106">Capacități multiple ale Dynamics 365 Customer Insights sunt construite în jurul acestor entități.</span><span class="sxs-lookup"><span data-stu-id="ba55d-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="ba55d-107">Revizuirea acestora îndeaproape vă poate ajuta să validați rezultatele acestor funcții.</span><span class="sxs-lookup"><span data-stu-id="ba55d-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="ba55d-108">Pagina **Entități** listează entitățile și include mai multe coloane:</span><span class="sxs-lookup"><span data-stu-id="ba55d-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="ba55d-109">**Nume**: Numele entității dvs. de date.</span><span class="sxs-lookup"><span data-stu-id="ba55d-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="ba55d-110">Dacă vedeți un simbol de avertizare lângă un nume de entitate, înseamnă că datele pentru acea entitate nu s-au încărcat cu succes.</span><span class="sxs-lookup"><span data-stu-id="ba55d-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="ba55d-111">**Sursa**: tipul sursei de date care au ingerat entitatea</span><span class="sxs-lookup"><span data-stu-id="ba55d-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="ba55d-112">**Creat de**: numele persoanei care a creat entitatea</span><span class="sxs-lookup"><span data-stu-id="ba55d-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="ba55d-113">**Creată**: Data și ora creării entității</span><span class="sxs-lookup"><span data-stu-id="ba55d-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="ba55d-114">**Actualizată de**: numele persoanei care a actualizat entitatea</span><span class="sxs-lookup"><span data-stu-id="ba55d-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="ba55d-115">**Ultima actualizare**: Data și ora ultimei actualizări a entității</span><span class="sxs-lookup"><span data-stu-id="ba55d-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="ba55d-116">**Ultima actualizare**: Data și ora ultimei actualizări de date</span><span class="sxs-lookup"><span data-stu-id="ba55d-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="ba55d-117">Explorarea datelor unei entități specifice</span><span class="sxs-lookup"><span data-stu-id="ba55d-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="ba55d-118">Selectați o entitate pentru a explora diferitele câmpuri și înregistrări incluse în acea entitate.</span><span class="sxs-lookup"><span data-stu-id="ba55d-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ba55d-119">![Selectați o entitate](media/data-manager-entities-data.png "Selectați o entitate")</span><span class="sxs-lookup"><span data-stu-id="ba55d-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="ba55d-120">Fila **Date** este selectată implicit și arată un tabel cu detalii despre înregistrările individuale ale entității.</span><span class="sxs-lookup"><span data-stu-id="ba55d-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ba55d-121">![Tabelul câmpurilor](media/data-manager-entities-fields.PNG "Tabelul câmpurilor")</span><span class="sxs-lookup"><span data-stu-id="ba55d-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="ba55d-122">Fila **Câmpuri** arată un tabel pentru a revizui detaliile pentru entitatea selectată, cum ar fi numele câmpurilor, tipurile de date și tipurile.</span><span class="sxs-lookup"><span data-stu-id="ba55d-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="ba55d-123">Coloana **Tip** prezintă tipurile asociate Common Data Model, care sunt fie identificate automat de sistem sau [mapate manual](map-entities.md) de către utilizatori.</span><span class="sxs-lookup"><span data-stu-id="ba55d-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="ba55d-124">Acestea sunt tipuri semantice care pot diferi de tipurile de date ale atributelor - de exemplu, câmpul *E-mail* de mai jos are un tip de date *Text* dar tipul său (semantic) de Common Data Model ar putea fi *E-mail* sau *EmailAddress*.</span><span class="sxs-lookup"><span data-stu-id="ba55d-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="ba55d-125">Ambele tabele prezintă doar un eșantion de date ale entității dvs.</span><span class="sxs-lookup"><span data-stu-id="ba55d-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="ba55d-126">Pentru a vizualiza setul complet de date, accesați pagina **Surse de date**, selectați o entitate, selectați **Editați**, apoi vizualizați datele acestei entități cu editorul Power Query, așa cum este explicat în [Surse de date](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="ba55d-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="ba55d-127">Pentru a afla mai multe despre datele ingerate în entitate, coloana **Rezumat** vă oferă câteva caracteristici importante ale datelor, cum ar fi valorile Null, valori lipsă, valori unice, numărări și distribuții, după cum se aplică datelor dumneavoastră.</span><span class="sxs-lookup"><span data-stu-id="ba55d-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="ba55d-128">Selectați pictograma diagramă pentru a vedea rezumatul datelor.</span><span class="sxs-lookup"><span data-stu-id="ba55d-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ba55d-129">![Simbol rezumat](media/data-manager-entities-summary.png "Tabel Rezumat date")</span><span class="sxs-lookup"><span data-stu-id="ba55d-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="ba55d-130">Următorul pas</span><span class="sxs-lookup"><span data-stu-id="ba55d-130">Next step</span></span>

<span data-ttu-id="ba55d-131">Consultați subiectul [Unificare](data-unification.md) pentru a afla despre cum să *mapați*, *potriviți*, și *combinați* datele ingerate.</span><span class="sxs-lookup"><span data-stu-id="ba55d-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]