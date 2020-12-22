---
title: Relații între entități și căi de entități
description: Creați și gestionați relații între entități din mai multe surse de date.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406708"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="76797-103">Relații între entități</span><span class="sxs-lookup"><span data-stu-id="76797-103">Relationships between entities</span></span>

<span data-ttu-id="76797-104">Relațiile vă ajută să conectați entități și să generați un grafic al datelor dvs. atunci când entitățile partajează un identificator comun (cheie străină) la care se poate face referire de la o entitate la alta.</span><span class="sxs-lookup"><span data-stu-id="76797-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="76797-105">Entitățile conectate vă permit să definiți segmente și măsuri pe baza mai multor surse de date.</span><span class="sxs-lookup"><span data-stu-id="76797-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="76797-106">Există două tipuri de relații.</span><span class="sxs-lookup"><span data-stu-id="76797-106">There are two types of relationships.</span></span> <span data-ttu-id="76797-107">Relațiile de sistem care nu pot fi modificate, care sunt create automat și relațiile personalizate create și configurate de utilizatori.</span><span class="sxs-lookup"><span data-stu-id="76797-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="76797-108">În timpul proceselor de potrivire și îmbinare, relațiile de sistem sunt create în culise bazate pe potrivire inteligentă.</span><span class="sxs-lookup"><span data-stu-id="76797-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="76797-109">Aceste relații ajută la corelarea înregistrărilor profilului clienților cu înregistrările altor entități corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="76797-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="76797-110">Următoarea diagramă ilustrează crearea a trei relații de sistem atunci când entitatea client este asociată cu entități suplimentare pentru a produce entitatea de profil final pentru clienți.</span><span class="sxs-lookup"><span data-stu-id="76797-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="76797-111">![Se creează relația](media/relationships-entities-merge.png "Se creează relația")</span><span class="sxs-lookup"><span data-stu-id="76797-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="76797-112">**Relația *CustomerToContact*** a fost creată între entitatea Client și entitatea de contact.</span><span class="sxs-lookup"><span data-stu-id="76797-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="76797-113">Entitatea Client face ca câmpul cheie **Contact_contactId** să se raporteze la câmpul cheie al entității de contact **contactId**.</span><span class="sxs-lookup"><span data-stu-id="76797-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="76797-114">**Relația _CustomerToAccount_** a fost creată între entitatea Client și entitatea de cont.</span><span class="sxs-lookup"><span data-stu-id="76797-114">**_CustomerToAccount_ relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="76797-115">Entitatea Client face ca câmpul cheie **Account_accountId** să se raporteze la câmpul cheie al entității de cont **accountId**.</span><span class="sxs-lookup"><span data-stu-id="76797-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="76797-116">**Relația _CustomerToWebAccount_** a fost creată între entitatea Client și entitatea WebAccount.</span><span class="sxs-lookup"><span data-stu-id="76797-116">**_CustomerToWebAccount_ relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="76797-117">Entitatea Client face ca câmpul cheie **WebAccount_webaccountId** să se raporteze la câmpul cheie al entității WebAccount **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="76797-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="76797-118">Creați o relație</span><span class="sxs-lookup"><span data-stu-id="76797-118">Create a relationship</span></span>

<span data-ttu-id="76797-119">Definiți relațiile particularizate pe pagina **Relații**.</span><span class="sxs-lookup"><span data-stu-id="76797-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="76797-120">Fiecare relație constă dintr-o entitate sursă (entitatea care deține cheia străină) și o entitate țintă (entitatea la care face referire cheia străină a entității sursă).</span><span class="sxs-lookup"><span data-stu-id="76797-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="76797-121">În detalii despre public, accesați **Date** > **Relații**.</span><span class="sxs-lookup"><span data-stu-id="76797-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="76797-122">Selectați **Relație nouă**.</span><span class="sxs-lookup"><span data-stu-id="76797-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="76797-123">Pe panoul **Adăugați relație**, furnizați următoarele informații:</span><span class="sxs-lookup"><span data-stu-id="76797-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="76797-124">![Introduceți detaliile relației](media/relationships-add.png "Introduceți detaliile relației")</span><span class="sxs-lookup"><span data-stu-id="76797-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="76797-125">**Numele relației**: Nume care reflectă scopul relației (de exemplu, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="76797-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="76797-126">**Descriere**: Descrierea relației.</span><span class="sxs-lookup"><span data-stu-id="76797-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="76797-127">**Entitatea sursă**: Selectați entitatea care este utilizată ca sursă în relație (de exemplu, WebLog).</span><span class="sxs-lookup"><span data-stu-id="76797-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="76797-128">**Cardinalitate**: Selectați cardinalitatea înregistrărilor entității sursă.</span><span class="sxs-lookup"><span data-stu-id="76797-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="76797-129">De exemplu, „multe” înseamnă că mai multe înregistrări Weblog sunt legate de un WebAccount.</span><span class="sxs-lookup"><span data-stu-id="76797-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="76797-130">**Câmpul cheie sursă**: Acesta reprezintă câmpul cheie străină din entitatea sursă.</span><span class="sxs-lookup"><span data-stu-id="76797-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="76797-131">De exemplu, WebLog are **accountId** drept câmp de cheie străină.</span><span class="sxs-lookup"><span data-stu-id="76797-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="76797-132">**Entitatea țintă**: Selectați entitatea care este utilizată ca țintă în relație (de exemplu, WebAccount).</span><span class="sxs-lookup"><span data-stu-id="76797-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="76797-133">**Cardinalitate țintă**: Selectați cardinalitatea înregistrărilor entității țintă.</span><span class="sxs-lookup"><span data-stu-id="76797-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="76797-134">De exemplu, „una” înseamnă că mai multe înregistrări Weblog sunt legate de un WebAccount.</span><span class="sxs-lookup"><span data-stu-id="76797-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="76797-135">**Câmpul cheie țintă**: Acest câmp reprezintă câmpul cheie al entității țintă.</span><span class="sxs-lookup"><span data-stu-id="76797-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="76797-136">De exemplu, WebAccount are **accountId** drept câmp de cheie.</span><span class="sxs-lookup"><span data-stu-id="76797-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="76797-137">Sunt acceptate doar relații mulți-la-unu și unu-la-unu.</span><span class="sxs-lookup"><span data-stu-id="76797-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="76797-138">Relațiile de mulți la mulți pot fi create folosind două relații mulți-la-unu și o entitate de legătură (o entitate care este utilizată pentru a conecta entitatea sursă și entitatea țintă).</span><span class="sxs-lookup"><span data-stu-id="76797-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="76797-139">Ștergeți o relație</span><span class="sxs-lookup"><span data-stu-id="76797-139">Delete a relationship</span></span>

1. <span data-ttu-id="76797-140">În detalii despre public, accesați **Date** > **Relații**.</span><span class="sxs-lookup"><span data-stu-id="76797-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="76797-141">Bifați caseta de selectare pentru relațiile pe care doriți să le eliminați.</span><span class="sxs-lookup"><span data-stu-id="76797-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="76797-142">Selectați **Ștergere** în partea de sus a tabelului **Relații**.</span><span class="sxs-lookup"><span data-stu-id="76797-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="76797-143">Confirmați ștergerea.</span><span class="sxs-lookup"><span data-stu-id="76797-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="76797-144">Următorul pas</span><span class="sxs-lookup"><span data-stu-id="76797-144">Next step</span></span>

<span data-ttu-id="76797-145">Relațiile de sistem și personalizate sunt utilizate pentru a crea segmente bazate pe mai multe surse de date care nu mai sunt izolate.</span><span class="sxs-lookup"><span data-stu-id="76797-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="76797-146">Pentru mai multe informații, consultați [Segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="76797-146">For more information, see [Segments](segments.md).</span></span>
