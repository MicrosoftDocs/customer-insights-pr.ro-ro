---
title: Relații între entități și căi de entități
description: Creați și gestionați relații între entități din mai multe surse de date.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171179"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="f8ef0-103">Relații între entități</span><span class="sxs-lookup"><span data-stu-id="f8ef0-103">Relationships between entities</span></span>

<span data-ttu-id="f8ef0-104">Relațiile conectează entități și definesc un grafic al datelor dvs. atunci când entitățile partajează un identificator comun, o cheie străină.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="f8ef0-105">La această cheie străină se poate face referire de la o entitate la alta.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="f8ef0-106">Entitățile conectate vă permit definirea de segmente și măsuri pe baza mai multor surse de date.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="f8ef0-107">Există trei tipuri de relații:</span><span class="sxs-lookup"><span data-stu-id="f8ef0-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="f8ef0-108">Relații de sistem needitable, create de sistem ca parte a procesului de unificare a datelor</span><span class="sxs-lookup"><span data-stu-id="f8ef0-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="f8ef0-109">Relații moștenite non-editabile, care sunt create automat din ingerarea surselor de date</span><span class="sxs-lookup"><span data-stu-id="f8ef0-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="f8ef0-110">Relații particularizate editabile, create și configurate de utilizatori</span><span class="sxs-lookup"><span data-stu-id="f8ef0-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="f8ef0-111">Relații de sistem non-editabile</span><span class="sxs-lookup"><span data-stu-id="f8ef0-111">Non-editable system relationships</span></span>

<span data-ttu-id="f8ef0-112">În timpul unificării datelor, relațiile de sistem sunt create automat pe baza potrivirii inteligente.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="f8ef0-113">Aceste relații ajută la corelarea înregistrărilor profilului clienților cu înregistrările corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="f8ef0-114">Următoarea diagramă ilustrează crearea a trei relații bazate pe sistem.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="f8ef0-115">Entitatea client este asociată cu alte entități pentru a produce entitatea unificată *Client*.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagramă cu căi de relație pentru entitatea client cu trei relații 1-n.":::

- <span data-ttu-id="f8ef0-117">**Relația *CustomerToContact*** a fost creată între entitatea *Client* și entitatea de *contact*.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="f8ef0-118">Entitatea *Client* face ca câmpul cheie **Contact_contactID** să se raporteze la câmpul cheie al entității de *Contact* **contactID**.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="f8ef0-119">**Relația *CustomerToAccount*** a fost creată între entitatea *Client* și entitatea de *Cont*.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="f8ef0-120">Entitatea *Client* face ca câmpul cheie **Account_accountID** să se raporteze la câmpul cheie al entității de *cont* **accountID**.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="f8ef0-121">**Relația *CustomerToWebAccount*** a fost creată între entitatea *Client* și entitatea *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="f8ef0-122">Entitatea *Client* face ca câmpul cheie **WebAccount_webaccountID** să se raporteze la câmpul cheie al entității *WebAccount* **webaccountID**.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="f8ef0-123">Relații moștenite non-editabile</span><span class="sxs-lookup"><span data-stu-id="f8ef0-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="f8ef0-124">În timpul procesului de ingestie de date, sistemul verifică sursele de date pentru relațiile existente.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="f8ef0-125">Dacă nu există nicio relație, sistemul le creează automat.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="f8ef0-126">Aceste relații sunt utilizate și în procesele din aval.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="f8ef0-127">Crearea unei relații particularizate</span><span class="sxs-lookup"><span data-stu-id="f8ef0-127">Create a custom relationship</span></span>

<span data-ttu-id="f8ef0-128">Relația constă dintr-o *entitate sursă* care conține cheia străină și o *entitate țintă* pe care o indică cheia externă a entității sursă.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="f8ef0-129">În detalii despre public, accesați **Date** > **Relații**.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="f8ef0-130">Selectați **Relație nouă**.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="f8ef0-131">Pe panoul **Relație nouă**, furnizați următoarele informații:</span><span class="sxs-lookup"><span data-stu-id="f8ef0-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Panou lateral de relație nouă, cu câmpuri de intrare necompletate.":::

   - <span data-ttu-id="f8ef0-133">**Numele relației**: Numele care reflectă scopul relației.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="f8ef0-134">Exemplu: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="f8ef0-135">**Descriere**: Descrierea relației.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="f8ef0-136">**Entitate sursă**: Entitate care este utilizată ca sursă în relație.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="f8ef0-137">Exemplu: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="f8ef0-138">**Entitate țintă**: Entitate care este utilizată ca țintă în relație.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="f8ef0-139">Exemplu: Client.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-139">Example: Customer.</span></span>
   - <span data-ttu-id="f8ef0-140">**Cardinalitatea sursă**: Specificați cardinalitatea entității sursă.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="f8ef0-141">Cardinalitatea descrie numărul de elemente posibile dintr-un set.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="f8ef0-142">Se referă întotdeauna la cardinalitatea țintă.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="f8ef0-143">Puteți alege între **Unu** și **Mulți**.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="f8ef0-144">Sunt acceptate doar relații mulți-la-unu și unu-la-unu.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="f8ef0-145">Mai-multe-la-una: Mai multe înregistrări sursă se pot referi la o înregistrare țintă.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="f8ef0-146">Exemplu: Mai multe cazuri de asistență de la un singur client.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="f8ef0-147">Una-la-una: O singură înregistrare sursă se referă la o singură înregistrare țintă.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="f8ef0-148">Exemplu: Un ID de loialitate pentru un singur client.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="f8ef0-149">Relațiile mulți-la-mai-mulți pot fi create folosind două relații multe-la-una și o entitate care leagă, care conectează entitatea sursă și entitatea țintă.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="f8ef0-150">**Cardinalitate țintă**: Selectați cardinalitatea înregistrărilor entității țintă.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="f8ef0-151">**Câmpul cheie sursă**: Câmpul cheie străină din entitatea sursă.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="f8ef0-152">Exemplu: SupportCase ar putea utiliza CaseID ca un câmp cu cheie străină.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="f8ef0-153">**Câmpul cheie țintă**: Câmpul cheie al entității țintă.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="f8ef0-154">Exemplu Clientul ar putea folosi câmpul cheie **Număr de înregistrare client**.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="f8ef0-155">Pentru a crea conexiunea particularizată, selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="f8ef0-156">Vizualizare relații</span><span class="sxs-lookup"><span data-stu-id="f8ef0-156">View relationships</span></span>

<span data-ttu-id="f8ef0-157">Pagina Relații listează toate relațiile care au fost create.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="f8ef0-158">Fiecare rând reprezintă o relație, care include, de asemenea, detalii despre entitatea sursă, entitatea țintă și cardinalitatea.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Lista relațiilor și opțiunilor din bara de acțiuni a paginii Relații.":::

<span data-ttu-id="f8ef0-160">Această pagină oferă un set de opțiuni pentru relațiile existente și noi:</span><span class="sxs-lookup"><span data-stu-id="f8ef0-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="f8ef0-161">**Nouă relație**: [Creați o relație particularizată](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="f8ef0-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="f8ef0-162">**Vizualizator**: [Explorați vizualizatorul relației](#explore-the-relationship-visualizer) pentru a vedea o diagramă de rețea a relațiilor existente și cardinalitatea acestora.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="f8ef0-163">**Filtrați după**: Alegeți tipul de relații de afișat în listă.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="f8ef0-164">**Căutați relații**: Utilizați o căutare bazată pe text pe proprietățile relațiilor.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="f8ef0-165">Explorați vizualizatorul de relații</span><span class="sxs-lookup"><span data-stu-id="f8ef0-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="f8ef0-166">Vizualizatorul de relații arată o diagramă de rețea a relațiilor existente între entitățile conectate și cardinalitatea acestora.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="f8ef0-167">Pentru a personaliza vizualizarea, puteți schimba poziția casetelor glisându-le pe pânză.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Captură de ecran a diagramei de rețea a vizualizatorului de relații cu conexiuni între entități conexe.":::

<span data-ttu-id="f8ef0-169">Opțiuni disponibile:</span><span class="sxs-lookup"><span data-stu-id="f8ef0-169">Available options:</span></span> 
- <span data-ttu-id="f8ef0-170">**Exportați ca imagine**: Salvați vizualizarea curentă ca fișier imagine.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="f8ef0-171">**Treceți la aspectul orizontal/vertical**: Schimbați alinierea entităților și a relațiilor.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="f8ef0-172">**Editați**: Actualizați proprietățile relațiilor particularizate în panoul de editare și salvați modificările.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="f8ef0-173">Gestionați relațiile existente</span><span class="sxs-lookup"><span data-stu-id="f8ef0-173">Manage existing relationships</span></span> 

<span data-ttu-id="f8ef0-174">În pagina Relații, fiecare relație este reprezentată de un rând.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="f8ef0-175">Selectați o relație și alegeți una dintre următoarele opțiuni:</span><span class="sxs-lookup"><span data-stu-id="f8ef0-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="f8ef0-176">**Editați**: Actualizați proprietățile relațiilor particularizate în panoul de editare și salvați modificările.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="f8ef0-177">**Ștergeți**: Ștergeți relațiile particularizate.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="f8ef0-178">**Vizualizare**: Vizualizați relațiile create și moștenite de sistem.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="f8ef0-179">Următorul pas</span><span class="sxs-lookup"><span data-stu-id="f8ef0-179">Next step</span></span>

<span data-ttu-id="f8ef0-180">Relațiile de sistem și particularizate sunt utilizate pentru [a crea segmente](segments.md) bazate pe mai multe surse de date care nu mai sunt izolate.</span><span class="sxs-lookup"><span data-stu-id="f8ef0-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
