---
title: Activități ale clienților
description: Definiți activitățile clienților și vizualizați-le în cronologia clienților.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267447"
---
# <a name="customer-activities"></a><span data-ttu-id="86bb5-103">Activități ale clienților</span><span class="sxs-lookup"><span data-stu-id="86bb5-103">Customer activities</span></span>

<span data-ttu-id="86bb5-104">Combinați activitățile clienților din [diverse surse de date](data-sources.md) în Dynamics 365 Customer Insights pentru a crea o cronologie a clienților care listează activitățile în ordine cronologică.</span><span class="sxs-lookup"><span data-stu-id="86bb5-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="86bb5-105">Puteți include cronologia în aplicațiile de Customer Engagement în Dynamics 365 prin intermediul [Program de completare card client](customer-card-add-in.md), sau într-un tablou de bord Power BI.</span><span class="sxs-lookup"><span data-stu-id="86bb5-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="86bb5-106">Definiți o activitate</span><span class="sxs-lookup"><span data-stu-id="86bb5-106">Define an activity</span></span>

<span data-ttu-id="86bb5-107">Sursele dvs. de date includ entități cu date tranzacționale și de activitate din mai multe surse de date.</span><span class="sxs-lookup"><span data-stu-id="86bb5-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="86bb5-108">Identificați aceste entități și selectați activitățile pe care doriți să le vizualizați în cronologia clientului.</span><span class="sxs-lookup"><span data-stu-id="86bb5-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="86bb5-109">Alegeți entitatea care include activitatea sau activitățile dvs. țintă.</span><span class="sxs-lookup"><span data-stu-id="86bb5-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="86bb5-110">În Detalii despre audiență, accesați **Date** > **Activități**.</span><span class="sxs-lookup"><span data-stu-id="86bb5-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="86bb5-111">Selectați **Adăugați o activitate**.</span><span class="sxs-lookup"><span data-stu-id="86bb5-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="86bb5-112">O entitate trebuie să aibă cel puțin un atribut de tip **Date** pentru a fi inclus într-o cronologie a clienților și nu puteți adăuga entități fără câmpuri **Date**.</span><span class="sxs-lookup"><span data-stu-id="86bb5-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="86bb5-113">Controlul **Adăugați activitate** este dezactivat dacă nu se găsește o astfel de entitate.</span><span class="sxs-lookup"><span data-stu-id="86bb5-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="86bb5-114">În panoul **Adăugați activitate**, setați valorile pentru următoarele câmpuri:</span><span class="sxs-lookup"><span data-stu-id="86bb5-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="86bb5-115">**Entitate**: Selectați o entitate care include date de tranzacție sau de activitate.</span><span class="sxs-lookup"><span data-stu-id="86bb5-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="86bb5-116">**Cheie primară**: Selectați câmpul care identifică în mod unic o înregistrare.</span><span class="sxs-lookup"><span data-stu-id="86bb5-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="86bb5-117">Nu ar trebui să conțină valori duplicate, valori goale sau valori lipsă.</span><span class="sxs-lookup"><span data-stu-id="86bb5-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="86bb5-118">**Marcă de timp**: Selectați câmpul care reprezintă ora de început a activității dvs.</span><span class="sxs-lookup"><span data-stu-id="86bb5-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="86bb5-119">**Eveniment**: Selectați câmpul care este evenimentul pentru activitate.</span><span class="sxs-lookup"><span data-stu-id="86bb5-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="86bb5-120">**Adresă web**: Selectați câmpul care reprezintă o adresă URL care furnizează informații suplimentare despre această activitate.</span><span class="sxs-lookup"><span data-stu-id="86bb5-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="86bb5-121">De exemplu, sistemul tranzacțional care furnizează această activitate.</span><span class="sxs-lookup"><span data-stu-id="86bb5-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="86bb5-122">Această adresă URL poate fi orice câmp din sursa de date sau poate fi construită ca un câmp nou folosind o transformare Power Query.</span><span class="sxs-lookup"><span data-stu-id="86bb5-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="86bb5-123">Aceste date URL vor fi stocate în entitatea Activitate unificată, care poate fi consumată în aval folosind API-uri.</span><span class="sxs-lookup"><span data-stu-id="86bb5-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="86bb5-124">**Detalii**: Opțional, selectați câmpul care este adăugat pentru detalii suplimentare.</span><span class="sxs-lookup"><span data-stu-id="86bb5-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="86bb5-125">**Pictogramă**: Opțional, selectați pictograma care reprezintă această activitate.</span><span class="sxs-lookup"><span data-stu-id="86bb5-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="86bb5-126">**Tip de activitate**: Definiți referința de tip de activitate la Common Data Model care descrie cel mai bine definiția semantică a activității.</span><span class="sxs-lookup"><span data-stu-id="86bb5-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="86bb5-127">În secțiunee **Configurați relația**, configurați detaliile pentru a conecta datele activității dvs. cu clientul corespunzător.</span><span class="sxs-lookup"><span data-stu-id="86bb5-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="86bb5-128">**Câmpul entității Activitate**: Selectați câmpul din entitatea dvs. de activitate care va fi utilizat pentru a stabili o relație cu o altă entitate.</span><span class="sxs-lookup"><span data-stu-id="86bb5-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="86bb5-129">**Entitate client**: Selectați entitatea clientului sursă corespunzătoare cu care entitatea dvs. de activitate va fi în relație.</span><span class="sxs-lookup"><span data-stu-id="86bb5-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="86bb5-130">Vă puteți raporta doar la acele entități de clienți sursă care sunt utilizate în procesul de unificare a datelor.</span><span class="sxs-lookup"><span data-stu-id="86bb5-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="86bb5-131">**Câmpul entității clienților**: Acest câmp arată cheia principală a entității clientului sursă, așa cum este selectată în procesul de mapare.</span><span class="sxs-lookup"><span data-stu-id="86bb5-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="86bb5-132">Acest câmp cheie principal în entitatea client sursă este utilizat pentru a stabili o relație cu entitatea de activitate.</span><span class="sxs-lookup"><span data-stu-id="86bb5-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="86bb5-133">**Nume**: Dacă există deja o relație între această entitate de activitate și entitatea client sursă selectată, numele relației va fi în modul numai în citire.</span><span class="sxs-lookup"><span data-stu-id="86bb5-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="86bb5-134">Dacă nu există o astfel de relație, se va crea o nouă relație cu numele furnizat aici.</span><span class="sxs-lookup"><span data-stu-id="86bb5-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="86bb5-135">![Definiți relația dintre entități](media/activities-entities-define.png "Definiți relația dintre entități")</span><span class="sxs-lookup"><span data-stu-id="86bb5-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="86bb5-136">Selectați **Salvare** pentru a vă aplica modificările.</span><span class="sxs-lookup"><span data-stu-id="86bb5-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="86bb5-137">În pagina **Activități**, selectați **Executare**.</span><span class="sxs-lookup"><span data-stu-id="86bb5-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="86bb5-138">Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese.</span><span class="sxs-lookup"><span data-stu-id="86bb5-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="86bb5-139">În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="86bb5-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="86bb5-140">Puteți selecta starea unui proces pentru a vedea detalii despre evoluția întregii lucrări.</span><span class="sxs-lookup"><span data-stu-id="86bb5-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="86bb5-141">După selectarea **Vizualizare detalii** pentru una dintre sarcinile jobului, găsiți informații suplimentare: timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate sarcinii.</span><span class="sxs-lookup"><span data-stu-id="86bb5-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="86bb5-142">Editați o activitate</span><span class="sxs-lookup"><span data-stu-id="86bb5-142">Edit an activity</span></span>

1. <span data-ttu-id="86bb5-143">În Detalii despre audiență, accesați **Date** > **Activități**.</span><span class="sxs-lookup"><span data-stu-id="86bb5-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="86bb5-144">Selectați entitatea de activitate pe care doriți să o editați și selectați **Editați**.</span><span class="sxs-lookup"><span data-stu-id="86bb5-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="86bb5-145">Sau puteți trece deasupra rândului de entitate și selectați pictograma **Editați**.</span><span class="sxs-lookup"><span data-stu-id="86bb5-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="86bb5-146">Faceți clic pe pictograma **Editați**.</span><span class="sxs-lookup"><span data-stu-id="86bb5-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="86bb5-147">În panoul **Editare activitate**, actualizați valorile și selectați **Salvați**.</span><span class="sxs-lookup"><span data-stu-id="86bb5-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="86bb5-148">În pagina **Activități**, selectați **Executare**.</span><span class="sxs-lookup"><span data-stu-id="86bb5-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="86bb5-149">Ștergeți o activitate</span><span class="sxs-lookup"><span data-stu-id="86bb5-149">Delete an activity</span></span>

1. <span data-ttu-id="86bb5-150">În Detalii despre audiență, accesați **Date** > **Activități**.</span><span class="sxs-lookup"><span data-stu-id="86bb5-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="86bb5-151">Selectați entitatea de activitate pe care doriți să o eliminați și selectați **Ștergeți**.</span><span class="sxs-lookup"><span data-stu-id="86bb5-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="86bb5-152">Sau puteți trece deasupra rândului de entitate și selectați pictograma **Ștergeți**.</span><span class="sxs-lookup"><span data-stu-id="86bb5-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="86bb5-153">În plus, puteți selecta mai multe entități de activitate pentru a fi șterse simultan.</span><span class="sxs-lookup"><span data-stu-id="86bb5-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="86bb5-154">![Editarea sau ștergerea relației de entitate](media/activities-entities-edit-delete.png "Editarea sau ștergerea relației de entitate")</span><span class="sxs-lookup"><span data-stu-id="86bb5-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="86bb5-155">Selectați pictograma **Ștergeți**.</span><span class="sxs-lookup"><span data-stu-id="86bb5-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="86bb5-156">Confirmați ștergerea.</span><span class="sxs-lookup"><span data-stu-id="86bb5-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]