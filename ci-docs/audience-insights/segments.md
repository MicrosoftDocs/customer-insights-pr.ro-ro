---
title: Crearea și gestionarea segmentelor
description: Creați segmente de clienți pentru a îi grupa pe baza diferitelor atribute.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597071"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="849e5-103">Crearea și gestionarea segmentelor</span><span class="sxs-lookup"><span data-stu-id="849e5-103">Create and manage segments</span></span>

<span data-ttu-id="849e5-104">Segmentele vă permit să vă grupați clienții pe baza atributelor demografice, tranzacționale sau comportamentale.</span><span class="sxs-lookup"><span data-stu-id="849e5-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="849e5-105">Puteți utiliza segmentele pentru a viza campanii promoționale, activități de vânzare și acțiuni de asistență pentru clienți pentru a vă atinge obiectivele de business.</span><span class="sxs-lookup"><span data-stu-id="849e5-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="849e5-106">Puteți defini filtre complexe în jurul entității de profil pentru clienți și entitățile sale asociate.</span><span class="sxs-lookup"><span data-stu-id="849e5-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="849e5-107">Fiecare segment, după procesare, creează un set de înregistrări ale clienților pe care le puteți exporta și pe care puteți acționa.</span><span class="sxs-lookup"><span data-stu-id="849e5-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="849e5-108">Se aplică unele [limite ale serviciului](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="849e5-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="849e5-109">Dacă nu se specifică altfel, toate segmentele sunt **Segmente dinamice**, care sunt actualizate într-o planificare recurentă.</span><span class="sxs-lookup"><span data-stu-id="849e5-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="849e5-110">Următorul exemplu ilustrează capabilitatea de segmentare.</span><span class="sxs-lookup"><span data-stu-id="849e5-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="849e5-111">Am definit un segment pentru clienții care au comandat cel puțin $500 de bunuri în ultimele 90 de zile *și* care au fost implicați într-un apel serviciu pentru relații cu clienții care a fost escaladat.</span><span class="sxs-lookup"><span data-stu-id="849e5-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="849e5-112">![Mai multe grupuri](media/segmentation-group1-2.png "Mai multe grupuri")</span><span class="sxs-lookup"><span data-stu-id="849e5-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="849e5-113">Crearea unui nou segment</span><span class="sxs-lookup"><span data-stu-id="849e5-113">Create a new segment</span></span>

<span data-ttu-id="849e5-114">Segmentele sunt gestionate pe pagina **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="849e5-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="849e5-115">În Detalii despre public, accesați pagina **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="849e5-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="849e5-116">Selectați **Nou** > **Segment necompletat**.</span><span class="sxs-lookup"><span data-stu-id="849e5-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="849e5-117">În panoul **Segment nou**, alegeți un tip de segment și furnizați un **Nume**.</span><span class="sxs-lookup"><span data-stu-id="849e5-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="849e5-118">Opțional, furnizați un nume afișat și o descriere care ajută la identificarea segmentului.</span><span class="sxs-lookup"><span data-stu-id="849e5-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="849e5-119">Selectați **Următorul** pentru a ajunge la pagina **Generator de segmente** unde definiți un grup.</span><span class="sxs-lookup"><span data-stu-id="849e5-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="849e5-120">Un grup este un grup de clienți.</span><span class="sxs-lookup"><span data-stu-id="849e5-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="849e5-121">Alegeți entitatea care include atributul pe care doriți să îl segmentați.</span><span class="sxs-lookup"><span data-stu-id="849e5-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="849e5-122">Alegeți atributul pentru care utilizați segmentul.</span><span class="sxs-lookup"><span data-stu-id="849e5-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="849e5-123">Acest atribut poate avea unul dintre cele patru tipuri de valori: numeric, șir, dată sau boolean.</span><span class="sxs-lookup"><span data-stu-id="849e5-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="849e5-124">Alegeți un operator și o valoare pentru atributul selectat.</span><span class="sxs-lookup"><span data-stu-id="849e5-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="849e5-125">![Particularizați filtrul de grup](media/customer-group-numbers.png "Filtrul de grup de clienți")</span><span class="sxs-lookup"><span data-stu-id="849e5-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="849e5-126">Număr</span><span class="sxs-lookup"><span data-stu-id="849e5-126">Number</span></span> |<span data-ttu-id="849e5-127">Definiție</span><span class="sxs-lookup"><span data-stu-id="849e5-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="849e5-128">1</span><span class="sxs-lookup"><span data-stu-id="849e5-128">1</span></span>     |<span data-ttu-id="849e5-129">Entity</span><span class="sxs-lookup"><span data-stu-id="849e5-129">Entity</span></span>          |
   |<span data-ttu-id="849e5-130">2</span><span class="sxs-lookup"><span data-stu-id="849e5-130">2</span></span>     |<span data-ttu-id="849e5-131">Atribut</span><span class="sxs-lookup"><span data-stu-id="849e5-131">Attribute</span></span>          |
   |<span data-ttu-id="849e5-132">3</span><span class="sxs-lookup"><span data-stu-id="849e5-132">3</span></span>    |<span data-ttu-id="849e5-133">Operator</span><span class="sxs-lookup"><span data-stu-id="849e5-133">Operator</span></span>         |
   |<span data-ttu-id="849e5-134">4</span><span class="sxs-lookup"><span data-stu-id="849e5-134">4</span></span>    |<span data-ttu-id="849e5-135">Valoare</span><span class="sxs-lookup"><span data-stu-id="849e5-135">Value</span></span>         |

8. <span data-ttu-id="849e5-136">Dacă entitatea este conectată la entitatea client unificată prin [relații](relationships.md), trebuie să definiți calea relației pentru a crea un segment valid.</span><span class="sxs-lookup"><span data-stu-id="849e5-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="849e5-137">Adăugați entitățile din calea relației până când puteți selecta entitatea **Client: CustomerInsights** din meniul listă verticală.</span><span class="sxs-lookup"><span data-stu-id="849e5-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="849e5-138">Atunci alegeți **Toate înregistrările** pentru fiecare condiție.</span><span class="sxs-lookup"><span data-stu-id="849e5-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="849e5-139">![Calea relației în timpul creării segmentului](media/segments-multiple-relationships.png "Calea relației în timpul creării segmentului")</span><span class="sxs-lookup"><span data-stu-id="849e5-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="849e5-140">În mod implicit, segmentele generează o entitate de ieșire care conține toate atributele profilurilor clienților care se potrivesc cu filtrele definite.</span><span class="sxs-lookup"><span data-stu-id="849e5-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="849e5-141">Dacă un segment se bazează pe alte entități decât entitatea *Client*, puteți adăuga mai multe atribute de la aceste entități la entitatea de ieșire.</span><span class="sxs-lookup"><span data-stu-id="849e5-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="849e5-142">Selectați **Atributele proiectului** pentru a alege atributele care vor fi anexate entității de ieșire.</span><span class="sxs-lookup"><span data-stu-id="849e5-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="849e5-143">Exemplu: un segment se bazează pe o entitate care conține date despre activitatea clienților care sunt legate de entitatea *Client*.</span><span class="sxs-lookup"><span data-stu-id="849e5-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="849e5-144">Segmentul caută toți clienții care au apelat la serviciul de asistență în ultimele 60 de zile.</span><span class="sxs-lookup"><span data-stu-id="849e5-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="849e5-145">Puteți alege să adăugați durata apelului și numărul de apeluri la toate înregistrările de clienți care se potrivesc în entitatea de ieșire.</span><span class="sxs-lookup"><span data-stu-id="849e5-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="849e5-146">Aceste informații ar putea fi utile pentru a trimite un e-mail cu linkuri utile către articole de ajutor online și întrebări frecvente către clienții care au sunat frecvent.</span><span class="sxs-lookup"><span data-stu-id="849e5-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="849e5-147">Selectați **Salvare** pentru a vă salva segmentul.</span><span class="sxs-lookup"><span data-stu-id="849e5-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="849e5-148">Segmentul dvs. va fi salvat și procesat dacă toate cerințele sunt validate.</span><span class="sxs-lookup"><span data-stu-id="849e5-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="849e5-149">În caz contrar, acesta va fi salvat ca schiță.</span><span class="sxs-lookup"><span data-stu-id="849e5-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="849e5-150">Selectați **Înapoi la segmente** pentru a reveni la pagina **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="849e5-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="849e5-151">Gestionarea segmentelor existente</span><span class="sxs-lookup"><span data-stu-id="849e5-151">Manage existing segments</span></span>

<span data-ttu-id="849e5-152">Pe pagina **Segmente**, puteți vedea toate segmentele salvate și le puteți gestiona.</span><span class="sxs-lookup"><span data-stu-id="849e5-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="849e5-153">Fiecare segment este reprezentat de un rând care include informații suplimentare despre segment.</span><span class="sxs-lookup"><span data-stu-id="849e5-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="849e5-154">Puteți sorta segmentele într-o coloană selectând titlul coloanei.</span><span class="sxs-lookup"><span data-stu-id="849e5-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="849e5-155">Folosiți caseta **Căutare** din colțul din dreapta sus pentru a filtra segmentele.</span><span class="sxs-lookup"><span data-stu-id="849e5-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="849e5-156">![Opțiuni de gestionare a unui segment existent](media/segments-selected-segment.png "Opțiuni de gestionare a unui segment existent")</span><span class="sxs-lookup"><span data-stu-id="849e5-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="849e5-157">Următoarea acțiune este disponibilă când selectați un segment:</span><span class="sxs-lookup"><span data-stu-id="849e5-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="849e5-158">**Vizualizați** detaliile segmentului, incluzând tendința numărului de membri o previzualizare a membrilor segmentului.</span><span class="sxs-lookup"><span data-stu-id="849e5-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="849e5-159">**Editați** segmentul pentru a-i schimba proprietățile.</span><span class="sxs-lookup"><span data-stu-id="849e5-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="849e5-160">**Creați duplicat** pentru un segment.</span><span class="sxs-lookup"><span data-stu-id="849e5-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="849e5-161">Puteți alege să editați proprietățile imediat sau pur și simplu să salvați duplicatul.</span><span class="sxs-lookup"><span data-stu-id="849e5-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="849e5-162">**Reîmprospătați** segmentul pentru a include cele mai recente date.</span><span class="sxs-lookup"><span data-stu-id="849e5-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="849e5-163">**Activarea** sau **Dezactivarea** segmentului.</span><span class="sxs-lookup"><span data-stu-id="849e5-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="849e5-164">Segmentele au două stări posibile - active sau inactive.</span><span class="sxs-lookup"><span data-stu-id="849e5-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="849e5-165">Aceste stări sunt utile la editarea unui segment.</span><span class="sxs-lookup"><span data-stu-id="849e5-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="849e5-166">Pentru segmentele inactive, definiția segmentului există, dar nu conține încă clienți.</span><span class="sxs-lookup"><span data-stu-id="849e5-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="849e5-167">Când activați un segment, starea acestuia se schimbă din „inactiv” în „activ” și începe să caute clienți care se potrivesc cu definiția segmentului.</span><span class="sxs-lookup"><span data-stu-id="849e5-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="849e5-168">În cazul în care o [reîmprospătare programată](system.md#schedule-tab) este configurată, segmentele inactive au **Starea** listată drept **Omis**, indicând că nici măcar nu a fost încercată o reîmprospătare.</span><span class="sxs-lookup"><span data-stu-id="849e5-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="849e5-169">Când este activat un segment inactiv, acesta se va reîmprospăta și va fi inclus în reîmprospătările programate.</span><span class="sxs-lookup"><span data-stu-id="849e5-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="849e5-170">Alternativ, puteți utiliza funcționalitatea **Planifică mai târziu** în lista derulantă **Activare/Dezactivare** pentru a specifica data și ora viitoare pentru activarea și dezactivarea unui anumit segment.</span><span class="sxs-lookup"><span data-stu-id="849e5-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="849e5-171">**Redenumire** segment.</span><span class="sxs-lookup"><span data-stu-id="849e5-171">**Rename** the segment.</span></span>
- <span data-ttu-id="849e5-172">**Descarcați** lista membrilor ca fișier .CSV.</span><span class="sxs-lookup"><span data-stu-id="849e5-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="849e5-173">Opțiunea **Adăugare la** trimite lista ID-urilor de clienți din segment pentru procesare într-o altă aplicație.</span><span class="sxs-lookup"><span data-stu-id="849e5-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="849e5-174">**Se șterge** segmentul.</span><span class="sxs-lookup"><span data-stu-id="849e5-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="849e5-175">Se reîmprospătează segmentele</span><span class="sxs-lookup"><span data-stu-id="849e5-175">Refresh segments</span></span>

<span data-ttu-id="849e5-176">Puteți reîmprospăta toate segmentele simultan, selectând **Reîmprospătați toate** pe pagina **Segmente** sau puteți reîmprospăta unul sau mai multe segmente atunci când le selectați și alegeți **Reîmprospătare** din opțiuni.</span><span class="sxs-lookup"><span data-stu-id="849e5-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="849e5-177">În mod alternativ, puteți configura o actualizare recurentă în **Administrator** > **Sistem** > **Planificare**.</span><span class="sxs-lookup"><span data-stu-id="849e5-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="849e5-178">Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese.</span><span class="sxs-lookup"><span data-stu-id="849e5-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="849e5-179">În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="849e5-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="849e5-180">Puteți selecta starea unui proces pentru a vedea detalii despre evoluția întregii lucrări.</span><span class="sxs-lookup"><span data-stu-id="849e5-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="849e5-181">După selectarea **Vizualizare detalii** pentru una dintre sarcinile jobului, găsiți informații suplimentare: timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate sarcinii.</span><span class="sxs-lookup"><span data-stu-id="849e5-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="849e5-182">Descărcați și exportați segmente</span><span class="sxs-lookup"><span data-stu-id="849e5-182">Download and export segments</span></span>

<span data-ttu-id="849e5-183">Puteți descărca segmentele dvs. într-un fișier CSV sau le puteți exporta către Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="849e5-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="849e5-184">Descărcați segmente într-un fișier CSV</span><span class="sxs-lookup"><span data-stu-id="849e5-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="849e5-185">În Detalii despre public, accesați pagina **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="849e5-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="849e5-186">Selectați elipsele din dala unui segment specific.</span><span class="sxs-lookup"><span data-stu-id="849e5-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="849e5-187">Selectați **Descărcați ca CSV** din lista derulantă de acțiuni.</span><span class="sxs-lookup"><span data-stu-id="849e5-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="849e5-188">Exportare segmente în Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="849e5-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="849e5-189">Înainte de a exporta segmente către Dynamics 365 Sales, un administrator trebuie să [creeze destinația de export](export-destinations.md) pentru Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="849e5-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="849e5-190">În Detalii despre public, accesați pagina **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="849e5-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="849e5-191">Selectați elipsele din dala unui segment specific.</span><span class="sxs-lookup"><span data-stu-id="849e5-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="849e5-192">Selectați **Adăugați la** din lista de acțiuni verticală și selectați destinația de export la care doriți să trimiteți datele.</span><span class="sxs-lookup"><span data-stu-id="849e5-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="849e5-193">Modul de schiță pentru segmente</span><span class="sxs-lookup"><span data-stu-id="849e5-193">Draft mode for segments</span></span>

<span data-ttu-id="849e5-194">Dacă nu sunt îndeplinite toate cerințele pentru procesarea unui segment, puteți salva segmentul ca schiță și să îl accesați din pagina **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="849e5-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="849e5-195">Acesta va fi salvat ca un segment inactiv și nu poate fi activat până când nu este valabil.</span><span class="sxs-lookup"><span data-stu-id="849e5-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="849e5-196">Adăugați mai multe condiții unui grup</span><span class="sxs-lookup"><span data-stu-id="849e5-196">Add more conditions to a group</span></span>

<span data-ttu-id="849e5-197">Pentru a adăuga mai multe condiții unui grup, puteți utiliza doi operatori logici:</span><span class="sxs-lookup"><span data-stu-id="849e5-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="849e5-198">Operator **ȘI**: Ambele condiții trebuie îndeplinite ca parte a procesului de segmentare.</span><span class="sxs-lookup"><span data-stu-id="849e5-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="849e5-199">Această opțiune este cea mai utilă atunci când definiți condiții pentru diferite entități.</span><span class="sxs-lookup"><span data-stu-id="849e5-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="849e5-200">Operatorul **SAU**: Fiecare dintre condiții trebuie îndeplinită ca parte a procesului de segmentare.</span><span class="sxs-lookup"><span data-stu-id="849e5-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="849e5-201">Această opțiune este cea mai utilă atunci când definiți condiții multiple pentru aceeași entitate.</span><span class="sxs-lookup"><span data-stu-id="849e5-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="849e5-202">![Operatorul SAU unde fiecare condiție trebuie îndeplinită](media/segmentation-either-condition.png "Operatorul SAU unde fiecare condiție trebuie îndeplinită")</span><span class="sxs-lookup"><span data-stu-id="849e5-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="849e5-203">În prezent este posibil să imbricați un operator **SAU** sub unul **ȘI**, dar nu și invers.</span><span class="sxs-lookup"><span data-stu-id="849e5-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="849e5-204">Combinarea mai multor grupuri</span><span class="sxs-lookup"><span data-stu-id="849e5-204">Combine multiple groups</span></span>

<span data-ttu-id="849e5-205">Fiecare grup produce un set specific de clienți.</span><span class="sxs-lookup"><span data-stu-id="849e5-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="849e5-206">Puteți combina aceste grupuri pentru a include clienții necesari pentru cazul dvs. de afaceri.</span><span class="sxs-lookup"><span data-stu-id="849e5-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="849e5-207">În detaliile despre public, accesați pagina **Segmente** și selectați un segment.</span><span class="sxs-lookup"><span data-stu-id="849e5-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="849e5-208">Selectați **Adăugați un grup**.</span><span class="sxs-lookup"><span data-stu-id="849e5-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="849e5-209">![Grup Adăugare grup de clienți](media/customer-group-add-group.png "Grup Adăugare grup de clienți")</span><span class="sxs-lookup"><span data-stu-id="849e5-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="849e5-210">Selectați unul dintre următorii operatori de set: **Reuniune**, **Intersectare** sau **Excepție**.</span><span class="sxs-lookup"><span data-stu-id="849e5-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="849e5-211">![Uniune Adăugare grup de clienți](media/customer-group-union.png "Uniune Adăugare grup de clienți")</span><span class="sxs-lookup"><span data-stu-id="849e5-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="849e5-212">Selectați unui grop de operator vă permite să definiți un nou grup.</span><span class="sxs-lookup"><span data-stu-id="849e5-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="849e5-213">Salvarea diferitelor grupuri pentru a determina ce date sunt menținute:</span><span class="sxs-lookup"><span data-stu-id="849e5-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="849e5-214">**Uniune** unește cele două grupuri.</span><span class="sxs-lookup"><span data-stu-id="849e5-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="849e5-215">**Intersectare** suprapune cele două grupuri.</span><span class="sxs-lookup"><span data-stu-id="849e5-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="849e5-216">Doar datele care *sunt comune* pentru ambele grupuri sunt reținute în grupul unificat.</span><span class="sxs-lookup"><span data-stu-id="849e5-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="849e5-217">**Excepție** combină cele două grupuri.</span><span class="sxs-lookup"><span data-stu-id="849e5-217">**Except** combines the two groups.</span></span> <span data-ttu-id="849e5-218">Doar datele din grupul A care *nu sunt comune* cu datele din grupul B sunt reținute.</span><span class="sxs-lookup"><span data-stu-id="849e5-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="849e5-219">Vizualizați istoricul procesării și membrii segmentului</span><span class="sxs-lookup"><span data-stu-id="849e5-219">View processing history and segment members</span></span>

<span data-ttu-id="849e5-220">Puteți vedea date consolidate despre un segment trecând în revistă detaliile acestuia.</span><span class="sxs-lookup"><span data-stu-id="849e5-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="849e5-221">În pagina **Segmente**, selectați segmentul pe care doriți să-l revizuiți.</span><span class="sxs-lookup"><span data-stu-id="849e5-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="849e5-222">Partea superioară a paginii include un grafic de tendințe care vizualizează modificările numărului de membri.</span><span class="sxs-lookup"><span data-stu-id="849e5-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="849e5-223">Treceți peste punctele de date pentru a vedea numărul de membri la o anumită dată.</span><span class="sxs-lookup"><span data-stu-id="849e5-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="849e5-224">Puteți actualiza intervalul de timp al vizualizării.</span><span class="sxs-lookup"><span data-stu-id="849e5-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="849e5-225">![Intervalul de timp al segmentului](media/segment-time-range.png "Intervalul de timp al segmentului")</span><span class="sxs-lookup"><span data-stu-id="849e5-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="849e5-226">Partea inferioară conține o listă a membrilor segmentului.</span><span class="sxs-lookup"><span data-stu-id="849e5-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="849e5-227">Câmpurile care apar în această listă se bazează pe atributele entităților segmentului dvs.</span><span class="sxs-lookup"><span data-stu-id="849e5-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="849e5-228">Lista este o previzualizare a membrilor segmentului care se potrivesc și arată primele 100 de înregistrări ale segmentului dvs., astfel încât să puteți evalua rapid și să revizuiți definițiile, dacă este necesar.</span><span class="sxs-lookup"><span data-stu-id="849e5-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="849e5-229">Pentru a vedea toate înregistrările potrivite, trebuie să [Exportați segmentul](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="849e5-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="849e5-230">Segmente rapide</span><span class="sxs-lookup"><span data-stu-id="849e5-230">Quick segments</span></span>

<span data-ttu-id="849e5-231">În plus față de generatorul de segmente, există o altă cale pentru crearea de segmente.</span><span class="sxs-lookup"><span data-stu-id="849e5-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="849e5-232">Segmentele rapide vă permit să construiți segmente simple cu un singur operator rapid și cu detalii instantanee.</span><span class="sxs-lookup"><span data-stu-id="849e5-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="849e5-233">Pe pagina **Segmente**, selectați **Nou** > **Creați rapid din**.</span><span class="sxs-lookup"><span data-stu-id="849e5-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="849e5-234">Selectați opțiunea **Profiluri** de a construi un segment care se bazează pe entitatea Client unificat.</span><span class="sxs-lookup"><span data-stu-id="849e5-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="849e5-235">Selectați opțiunea **Măsuri** pentru a construi un segment în jurul fiecăruia dintre tipurile de măsuri pe care le-ați creat anterior pe pagina **Măsuri**.</span><span class="sxs-lookup"><span data-stu-id="849e5-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="849e5-236">Selectați opțiunea **Inteligență** pentru a construi un segment în jurul uneia dintre entitățile de ieșire pe care le-ați generat folosind fie capabilități **Predicții** sau **Modele particularizate**.</span><span class="sxs-lookup"><span data-stu-id="849e5-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="849e5-237">În caseta de dialog **Segment rapid nou**, selectați un atribut din lista verticală **Câmp**.</span><span class="sxs-lookup"><span data-stu-id="849e5-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="849e5-238">Sistemul va oferi câteva informații suplimentare care vă vor ajuta să creați segmente mai bune de clienți.</span><span class="sxs-lookup"><span data-stu-id="849e5-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="849e5-239">Pentru câmpurile categorice, vom afișa 10 numere de clienți de top.</span><span class="sxs-lookup"><span data-stu-id="849e5-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="849e5-240">Alegeți o **Valoare** și selectați **Revizuire**.</span><span class="sxs-lookup"><span data-stu-id="849e5-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="849e5-241">Pentru un atribut numeric, sistemul va arăta ce valoare a atributului se încadrează sub percentila fiecărui client.</span><span class="sxs-lookup"><span data-stu-id="849e5-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="849e5-242">Alegeți un **Operator** și o **Valoare**, apoi selectați **Revizuire**.</span><span class="sxs-lookup"><span data-stu-id="849e5-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="849e5-243">Sistemul vă va oferi o **Dimensiunea estimată segment**.</span><span class="sxs-lookup"><span data-stu-id="849e5-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="849e5-244">Puteți alege dacă vreți să generați segmentul pe care l-ați definit sau să îl revizuiți mai întâi pentru a obține o dimensiune diferită a segmentului.</span><span class="sxs-lookup"><span data-stu-id="849e5-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="849e5-245">![Numele și estimarea pentru un segment rapid](media/quick-segment-name.png "Numele și estimarea pentru un segment rapid")</span><span class="sxs-lookup"><span data-stu-id="849e5-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="849e5-246">Furnizați un **Nume** pentru segmentul dvs.</span><span class="sxs-lookup"><span data-stu-id="849e5-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="849e5-247">Opțional, furnizați un **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="849e5-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="849e5-248">Selectați **Salvare** pentru a crea segmentul.</span><span class="sxs-lookup"><span data-stu-id="849e5-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="849e5-249">După ce segmentul a terminat procesarea, îl puteți vizualiza ca orice alt segment creat.</span><span class="sxs-lookup"><span data-stu-id="849e5-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="849e5-250">Pentru scenariile următoare, vă recomandăm să folosiți constructorul de segmente și nu capacitatea de segmente recomandată:</span><span class="sxs-lookup"><span data-stu-id="849e5-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="849e5-251">Crearea de segmente cu filtre pe câmpuri categorice în care operatorul este diferit de operatorul **Este**</span><span class="sxs-lookup"><span data-stu-id="849e5-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="849e5-252">Crearea de segmente cu filtre pe câmpuri numerice în care operatorul este diferit de operatorii **Între**, **Mai mare decât**, și **Mai puțin decât**</span><span class="sxs-lookup"><span data-stu-id="849e5-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="849e5-253">Crearea de segmente cu filtre pe câmpurile de tip de date</span><span class="sxs-lookup"><span data-stu-id="849e5-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="849e5-254">Următorii pași</span><span class="sxs-lookup"><span data-stu-id="849e5-254">Next steps</span></span>

<span data-ttu-id="849e5-255">[Exportați un segment](export-destinations.md) și explorați [Card client](customer-card-add-in.md) și [Conectori](export-power-bi.md) pentru a obține informații despre nivelul clientului.</span><span class="sxs-lookup"><span data-stu-id="849e5-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]