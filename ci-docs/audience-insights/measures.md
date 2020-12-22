---
title: Creați și editați măsuri
description: Definiți măsurile legate de client pentru a analiza și reflecta performanța anumitor domenii de afaceri.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406705"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="80c07-103">Definiți și gestionați măsurile</span><span class="sxs-lookup"><span data-stu-id="80c07-103">Define and manage measures</span></span>

<span data-ttu-id="80c07-104">**Măsuri** reprezintă indicatori de performanță cheie (KPI) care reflectă performanța și sănătatea domeniilor de activitate specifice.</span><span class="sxs-lookup"><span data-stu-id="80c07-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="80c07-105">Detaliile despre public oferă o experiență intuitivă pentru crearea diferitelor tipuri de măsuri, utilizând un generator de interogări care nu necesită codare sau validarea manuală a măsurilor.</span><span class="sxs-lookup"><span data-stu-id="80c07-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="80c07-106">Aveți posibilitatea să urmăriți măsurile de afaceri pe pagina de **pornire**, să consultați măsuri pentru anumiți clienți din **cardul de client** și să utilizați măsuri pentru a defini segmentele de clienți din pagina **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="80c07-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="80c07-107">Crearea unei măsuri</span><span class="sxs-lookup"><span data-stu-id="80c07-107">Create a measure</span></span>

<span data-ttu-id="80c07-108">Această secțiune vă ajută apoi să parcurgeți prin crearea unei măsuri de la zero.</span><span class="sxs-lookup"><span data-stu-id="80c07-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="80c07-109">Puteți construi măsuri cu date din mai multe surse de date care sunt conectate prin entitatea Client.</span><span class="sxs-lookup"><span data-stu-id="80c07-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="80c07-110">Se aplică unele [limite ale serviciului](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="80c07-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="80c07-111">În Detalii despre public, accesați **Măsuri**.</span><span class="sxs-lookup"><span data-stu-id="80c07-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="80c07-112">Selectați **Măsură nouă**.</span><span class="sxs-lookup"><span data-stu-id="80c07-112">Select **New measure**.</span></span>

3. <span data-ttu-id="80c07-113">Alegeți **Tipul** de măsură:</span><span class="sxs-lookup"><span data-stu-id="80c07-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="80c07-114">**Atribut client**: Un singur câmp per client care reflectă un scor, o valoare sau o stare pentru client.</span><span class="sxs-lookup"><span data-stu-id="80c07-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="80c07-115">Atributele clientului sunt create ca atribute într-o nouă entitate generată de sistem numită **Customer_Measure**.</span><span class="sxs-lookup"><span data-stu-id="80c07-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="80c07-116">**Măsură client**: Statistici privind comportamentul clienților cu defalcarea în funcție de dimensiunile selectate.</span><span class="sxs-lookup"><span data-stu-id="80c07-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="80c07-117">O entitate nouă este generată pentru fiecare măsură, potențial cu mai multe înregistrări per client.</span><span class="sxs-lookup"><span data-stu-id="80c07-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="80c07-118">**Măsură de afaceri**: Urmărește performanța afacerii și sănătatea afacerii.</span><span class="sxs-lookup"><span data-stu-id="80c07-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="80c07-119">Măsurile de afaceri pot avea două rezultate diferite: o ieșire numerică care se afișează pe pagina **Acasă** sau o entitate nouă pe care o găsiți pe pagina **Entități**.</span><span class="sxs-lookup"><span data-stu-id="80c07-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="80c07-120">Oferiți un **Nume** și opțional **Nume afișat**, apoi selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="80c07-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="80c07-121">În secțiunea **Entități**, selectați prima entitate din lista derulantă.</span><span class="sxs-lookup"><span data-stu-id="80c07-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="80c07-122">În acest moment, ar trebui să decideți dacă sunt necesare entități suplimentare ca parte a definirii măsurii.</span><span class="sxs-lookup"><span data-stu-id="80c07-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="80c07-123">![Definiție măsură](media/measure-definition.png "Definiție măsură")</span><span class="sxs-lookup"><span data-stu-id="80c07-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="80c07-124">Pentru a adăuga mai multe entități, selectați **Adăugați entitatea** și selectați entitățile pe care doriți să le utilizați pentru măsură.</span><span class="sxs-lookup"><span data-stu-id="80c07-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="80c07-125">Puteți selecta numai entitățile care au relații cu entitatea dvs. de început.</span><span class="sxs-lookup"><span data-stu-id="80c07-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="80c07-126">Pentru informații suplimentare despre definirea relațiile, consultați [Relații](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="80c07-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="80c07-127">Opțional, puteți configura variabile.</span><span class="sxs-lookup"><span data-stu-id="80c07-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="80c07-128">În secțiunea **Variabile**, selectați **Variabilă nouă**.</span><span class="sxs-lookup"><span data-stu-id="80c07-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="80c07-129">Variabilele sunt calcule care se fac pe fiecare dintre înregistrările selectate.</span><span class="sxs-lookup"><span data-stu-id="80c07-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="80c07-130">De exemplu, însumarea punctului de vânzare (POS) și vânzările online pentru fiecare dintre înregistrările clienților.</span><span class="sxs-lookup"><span data-stu-id="80c07-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="80c07-131">Furnizați un **Nume** pentru variabile.</span><span class="sxs-lookup"><span data-stu-id="80c07-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="80c07-132">În zona **Expresie**, alegeți un câmp cu care să începeți calculul.</span><span class="sxs-lookup"><span data-stu-id="80c07-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="80c07-133">Introduceți o expresie în **Expresie** în timp ce alegeți mai multe câmpuri care vor fi incluse în calcul.</span><span class="sxs-lookup"><span data-stu-id="80c07-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="80c07-134">În prezent, sunt acceptate doar expresiile aritmetice.</span><span class="sxs-lookup"><span data-stu-id="80c07-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="80c07-135">În plus, calculul variabilelor nu este acceptat pentru entități din diferite [căi de entitate](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="80c07-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="80c07-136">Selectați **Terminat**.</span><span class="sxs-lookup"><span data-stu-id="80c07-136">Select **Done**.</span></span>

11. <span data-ttu-id="80c07-137">În secțiunea **Definiție măsură**, veți defini modul în care entitățile alese și variabilele calculate sunt agregate într-o nouă entitate sau atribut de măsură.</span><span class="sxs-lookup"><span data-stu-id="80c07-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="80c07-138">Selectați **Dimensiune nouă**.</span><span class="sxs-lookup"><span data-stu-id="80c07-138">Select **New dimension**.</span></span> <span data-ttu-id="80c07-139">Puteți da exemplu pentru o dimensiune ca funcție a *grupare după*.</span><span class="sxs-lookup"><span data-stu-id="80c07-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="80c07-140">Rezultatul de date al entității sau atributului dvs. de măsurare va fi grupat după toate dimensiunile dvs. definite.</span><span class="sxs-lookup"><span data-stu-id="80c07-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="80c07-141">![Alegeți ciclul agregat](media/measures-businessreport-measure-definition2.png "Alegeți ciclul agregat")</span><span class="sxs-lookup"><span data-stu-id="80c07-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="80c07-142">Selectați sau introduceți următoarele informații ca parte a definiției dimensiunii dvs.:</span><span class="sxs-lookup"><span data-stu-id="80c07-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="80c07-143">**Entitate**: Dacă definiți o entitate de măsurare, aceasta ar trebui să includă cel puțin un atribut.</span><span class="sxs-lookup"><span data-stu-id="80c07-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="80c07-144">Dacă definiți un atribut Măsură, acesta va include în mod implicit un singur atribut.</span><span class="sxs-lookup"><span data-stu-id="80c07-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="80c07-145">Această selecție se referă la alegerea entității care include acel atribut.</span><span class="sxs-lookup"><span data-stu-id="80c07-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="80c07-146">**Câmp**: Alegeți atributul specific care trebuie inclus fie în entitatea dvs. Măsură, fie în atributul dvs.</span><span class="sxs-lookup"><span data-stu-id="80c07-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="80c07-147">**Pachet**: Alegeți dacă doriți să agregați datele zilnic, lunar sau anual.</span><span class="sxs-lookup"><span data-stu-id="80c07-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="80c07-148">Este o selecție necesară numai dacă ați selectat un atribut de tip Date.</span><span class="sxs-lookup"><span data-stu-id="80c07-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="80c07-149">**Ca**: Definește numele noului câmp.</span><span class="sxs-lookup"><span data-stu-id="80c07-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="80c07-150">**Nume afișat**: Definește numele afișat al câmpului dvs.</span><span class="sxs-lookup"><span data-stu-id="80c07-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="80c07-151">Măsura dvs. de afaceri va fi salvată ca o entitate cu un singur număr și va apărea pe pagina **Acasă** dacă nu adăugați mai multe dimensiuni la măsura dvs.</span><span class="sxs-lookup"><span data-stu-id="80c07-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="80c07-152">După adăugarea mai multor dimensiuni, măsura va *nu* va apărea pe pagina **Acasă**.</span><span class="sxs-lookup"><span data-stu-id="80c07-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="80c07-153">Opțional, adăugați funcții de agregare.</span><span class="sxs-lookup"><span data-stu-id="80c07-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="80c07-154">Orice agregare pe care o creați are ca rezultat o nouă valoare în entitatea sau atributul dvs. Măsuri.</span><span class="sxs-lookup"><span data-stu-id="80c07-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="80c07-155">Funcțiile de agregare acceptate sunt: **Min**, **Max**, **În medie**, **Median**, **Sumă**, **Cont unic**, **Primul** (ia prima înregistrare a unei valori a dimensiunii) și **Ultimul** (ia ultima înregistrare la o valoare a dimensiunii).</span><span class="sxs-lookup"><span data-stu-id="80c07-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="80c07-156">Selectați **Salvare** pentru a aplica modificările la măsura dvs..</span><span class="sxs-lookup"><span data-stu-id="80c07-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="80c07-157">Gestionați-vă măsurile</span><span class="sxs-lookup"><span data-stu-id="80c07-157">Manage your measures</span></span>

<span data-ttu-id="80c07-158">După ce creați cel puțin o măsură, veți vedea o listă de măsuri pe pagina **Măsuri**.</span><span class="sxs-lookup"><span data-stu-id="80c07-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="80c07-159">Veți găsi informații despre tipul de măsură, creatorul, data și ora de creare, ultima dată și oră de modificare, starea (dacă măsura este activă, inactivă sau eșuată) și ultima dată și oră de actualizare.</span><span class="sxs-lookup"><span data-stu-id="80c07-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="80c07-160">Când selectați o măsură din listă, puteți vedea o previzualizare a rezultatului acesteia.</span><span class="sxs-lookup"><span data-stu-id="80c07-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="80c07-161">Pentru a vă reîmprospăta toate măsurile în același timp, selectați **Reîmprospătați tot** fără a selecta o anumită măsură.</span><span class="sxs-lookup"><span data-stu-id="80c07-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="80c07-162">![Acțiuni de gestionare a măsurilor unice](media/measure-actions.png "Acțiuni de gestionare a măsurilor unice")</span><span class="sxs-lookup"><span data-stu-id="80c07-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="80c07-163">Alternativ, selectați o măsură din listă și efectuați una dintre următoarele acțiuni:</span><span class="sxs-lookup"><span data-stu-id="80c07-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="80c07-164">Selectați numele măsurii pentru a vedea detaliile acesteia.</span><span class="sxs-lookup"><span data-stu-id="80c07-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="80c07-165">**Editați** configurația măsurii.</span><span class="sxs-lookup"><span data-stu-id="80c07-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="80c07-166">**Redenumiți** măsura.</span><span class="sxs-lookup"><span data-stu-id="80c07-166">**Rename** the measure.</span></span>
- <span data-ttu-id="80c07-167">**Ștergeți** măsura.</span><span class="sxs-lookup"><span data-stu-id="80c07-167">**Delete** the measure.</span></span>
- <span data-ttu-id="80c07-168">Selectați elipsele (...) și apoi **Reîmprospătați** pentru a începe procesul de reîmprospătare pentru măsură.</span><span class="sxs-lookup"><span data-stu-id="80c07-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="80c07-169">Selectați elipsele (...) și apoi **Descărcați** pentru a obține un fișier .CSV al măsurii.</span><span class="sxs-lookup"><span data-stu-id="80c07-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="80c07-170">Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese.</span><span class="sxs-lookup"><span data-stu-id="80c07-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="80c07-171">În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="80c07-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="80c07-172">Puteți selecta starea unui proces pentru a vedea detalii despre evoluția întregii lucrări.</span><span class="sxs-lookup"><span data-stu-id="80c07-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="80c07-173">După selectarea **Vizualizare detalii** pentru una dintre sarcinile jobului, găsiți informații suplimentare: timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate sarcinii.</span><span class="sxs-lookup"><span data-stu-id="80c07-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="80c07-174">Următorul pas</span><span class="sxs-lookup"><span data-stu-id="80c07-174">Next step</span></span>

<span data-ttu-id="80c07-175">Puteți utiliza măsuri existente pentru a crea primul segment de clienți pe pagina **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="80c07-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="80c07-176">Pentru mai multe informații, consultați [Segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="80c07-176">For more information, see [Segments](segments.md).</span></span>
