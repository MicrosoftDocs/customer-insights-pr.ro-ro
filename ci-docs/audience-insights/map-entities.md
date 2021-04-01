---
title: Mapați entitățile pentru unificarea datelor
description: Mapați datele pentru a crea profiluri de clienți unificate.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 36b7f7b2fac9497245cf6759506c53753972f173
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596008"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="700a7-103">Entități de hartă și atribute</span><span class="sxs-lookup"><span data-stu-id="700a7-103">Map entities and attributes</span></span>

<span data-ttu-id="700a7-104">**Maparea** este prima etapă a procesului de unificare a datelor din detaliile despre public.</span><span class="sxs-lookup"><span data-stu-id="700a7-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="700a7-105">Maparea constă din trei faze:</span><span class="sxs-lookup"><span data-stu-id="700a7-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="700a7-106">*Selectare entitate*: Identificați entitățile combinabile care duc la un set de date cu informații mai complete despre clienții dvs.</span><span class="sxs-lookup"><span data-stu-id="700a7-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="700a7-107">*Selectarea atributelor*: Pentru fiecare entitate, identificați coloanele pe care doriți să le combinați și să le reconciliați în fazele de *Potrivire* și *Combinare*.</span><span class="sxs-lookup"><span data-stu-id="700a7-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="700a7-108">Aceste coloane sunt numite *Atribute*.</span><span class="sxs-lookup"><span data-stu-id="700a7-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="700a7-109">*Selectarea cheii primare și a tipului semantic*: Pentru fiecare entitate, identificați un atribut pe care doriți să îl definiți ca cheie primară pentru acea entitate și, pentru fiecare atribut, identificați un tip semantic care descrie cel mai bine acel atribut.</span><span class="sxs-lookup"><span data-stu-id="700a7-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="700a7-110">Pentru mai multe informații despre fluxul general de unificare a datelor, consultați [Unificare](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="700a7-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="700a7-111">Selectați primele entități</span><span class="sxs-lookup"><span data-stu-id="700a7-111">Select the first entities</span></span>

1. <span data-ttu-id="700a7-112">În Detalii despre public, accesați **Date** > **Unificare** > **Mapare**.</span><span class="sxs-lookup"><span data-stu-id="700a7-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="700a7-113">Începeți faza de mapare selectând **Selectați entități**.</span><span class="sxs-lookup"><span data-stu-id="700a7-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="700a7-114">Selectați entitățile și atributele pe care doriți să le utilizați în fazele *potrivire* și *îmbinare*.</span><span class="sxs-lookup"><span data-stu-id="700a7-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="700a7-115">Puteți selecta atributele necesare individual dintr-o entitate sau puteți include toate atributele dintr-o entitate selectând caseta de selectare **Includeți toate câmpurile** de la nivelul entității.</span><span class="sxs-lookup"><span data-stu-id="700a7-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="700a7-116">Vă recomandăm să selectați cel puțin două entități pentru a beneficia de procesul de unificare a datelor.</span><span class="sxs-lookup"><span data-stu-id="700a7-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="700a7-117">![Adăugați exemple de entități](media/data-manager-configure-map-add-entities-example.png "Adăugați exemple de entități")</span><span class="sxs-lookup"><span data-stu-id="700a7-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="700a7-118">În acest exemplu, adăugăm entitățile **eCommerceContacts** și **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="700a7-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="700a7-119">Alegând aceste entități, puteți obține informații despre care dintre clienții de afaceri online sunt membri ai programului de loialitate.</span><span class="sxs-lookup"><span data-stu-id="700a7-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="700a7-120">Puteți căuta cuvinte cheie în toate atributele și entitățile pentru a selecta atributele necesare pe care doriți să le mapați.</span><span class="sxs-lookup"><span data-stu-id="700a7-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="700a7-121">![Exemplu de câmpuri de căutare](media/data-manager-configure-map-search-fields-example.png "Exemplu de câmpuri de căutare")</span><span class="sxs-lookup"><span data-stu-id="700a7-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="700a7-122">Selectați **Aplicare** pentru a vă confirma selecțiile.</span><span class="sxs-lookup"><span data-stu-id="700a7-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="700a7-123">Selectați cheia primară și tipul semantic pentru atribute</span><span class="sxs-lookup"><span data-stu-id="700a7-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="700a7-124">După selectarea entităților dvs., pagina **Hartă** listează entitățile selectate pentru examinare.</span><span class="sxs-lookup"><span data-stu-id="700a7-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="700a7-125">Definiți cheia primară pentru o entitate și identificați tipul semantic pentru un atribut din entitate.</span><span class="sxs-lookup"><span data-stu-id="700a7-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="700a7-126">**Cheia primară**: Selectați un atribut ca cheie primară pentru fiecare entitate.</span><span class="sxs-lookup"><span data-stu-id="700a7-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="700a7-127">Pentru ca un atribut să fie o cheie primară validă, nu ar trebui să includă valori duplicate, valori lipsă sau valori nule.</span><span class="sxs-lookup"><span data-stu-id="700a7-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="700a7-128">Atributele tipului de date șir, întreg și GUID sunt acceptate ca chei primare și vor fi afișate într-un câmp din care puteți selecta.</span><span class="sxs-lookup"><span data-stu-id="700a7-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="700a7-129">**Tip de atribut semantic**: Categorii de atribute, cum ar fi adresa de e-mail sau numele.</span><span class="sxs-lookup"><span data-stu-id="700a7-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="700a7-130">Pentru a utiliza modele de inteligență artificială pentru predicție inteligentă de semantică, economie de timp și îmbunătățirea preciziei, setați **Mapare inteligentă** la **PORNITĂ**.</span><span class="sxs-lookup"><span data-stu-id="700a7-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="700a7-131">Maparea inteligentă evidențiază recomandările semantice bazate pe inteligență artificială în câmpul **Tip**.</span><span class="sxs-lookup"><span data-stu-id="700a7-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="700a7-132">Dacă o setați la **OPRIT**, veți vedea recomandările noastre regulate de mapare.</span><span class="sxs-lookup"><span data-stu-id="700a7-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="700a7-133">Puteți selecta orice tip semantic din lista de opțiuni disponibile și puteți înlocui selecția sugerată.</span><span class="sxs-lookup"><span data-stu-id="700a7-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="700a7-134">![Tipul de atribut și predicție semantică](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Tipul de atribut și predicție semantică")</span><span class="sxs-lookup"><span data-stu-id="700a7-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="700a7-135">Adăugarea unui tip semantic particularizat este de asemenea posibilă.</span><span class="sxs-lookup"><span data-stu-id="700a7-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="700a7-136">Selectați câmpul tip pentru un atribut și introduceți numele dvs. de tip semantic particularizat.</span><span class="sxs-lookup"><span data-stu-id="700a7-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="700a7-137">Astfel, puteți modifica tipurile de atribute care au fost identificate automat de sistem.</span><span class="sxs-lookup"><span data-stu-id="700a7-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="700a7-138">Toate atributele pentru care un tip semantic este identificat automat sunt grupate în secțiunea **Examinați câmpurile mapate**.</span><span class="sxs-lookup"><span data-stu-id="700a7-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="700a7-139">Examinați aceste atribute și tipurile lor semantice, deoarece acestea vor fi utilizate pentru a combina entitățile dvs. în etapa de îmbinare a unificării datelor.</span><span class="sxs-lookup"><span data-stu-id="700a7-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="700a7-140">Atributele care nu sunt mapate automat la un tip semantic sunt grupate în secțiunea **Definiți datele în câmpurile nemapate**.</span><span class="sxs-lookup"><span data-stu-id="700a7-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="700a7-141">Selectați câmpul de tip semantic pentru atributele nemapate sau introduceți numele tipului de atribut personalizat.</span><span class="sxs-lookup"><span data-stu-id="700a7-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="700a7-142">![Cheie primară și tip de atribut](media/data-manager-configure-map-add-attributes.png "Cheie primară și tip de atribut")</span><span class="sxs-lookup"><span data-stu-id="700a7-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="700a7-143">Un câmp ar trebui să fie mapat la tipul semantic Person.FullName pentru a completa numele clientului pe cardul clientului.</span><span class="sxs-lookup"><span data-stu-id="700a7-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="700a7-144">În caz contrar, cărțile client vor apărea fără nume.</span><span class="sxs-lookup"><span data-stu-id="700a7-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="700a7-145">Adăugați și eliminați atribute și entități</span><span class="sxs-lookup"><span data-stu-id="700a7-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="700a7-146">Pe **Unificare** > **Mapare**, selectați **Editați câmpurile**.</span><span class="sxs-lookup"><span data-stu-id="700a7-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="700a7-147">În panoul **Editați câmpurile**, adăugați sau eliminați atribute și entități.</span><span class="sxs-lookup"><span data-stu-id="700a7-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="700a7-148">Folosiți căutarea sau derulați pentru a găsi și selecta atributele și entitățile de interes.</span><span class="sxs-lookup"><span data-stu-id="700a7-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="700a7-149">Nu puteți elimina un atribut sau o entitate dacă au fost deja potrivite.</span><span class="sxs-lookup"><span data-stu-id="700a7-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="700a7-150">![Adăugare sau eliminare atribute](media/configure-data-map-edit.png "Adăugare sau eliminare atribute")</span><span class="sxs-lookup"><span data-stu-id="700a7-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="700a7-151">Selectați **Se aplică**.</span><span class="sxs-lookup"><span data-stu-id="700a7-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="700a7-152">Adăugați imagini la profiluri</span><span class="sxs-lookup"><span data-stu-id="700a7-152">Add images to profiles</span></span>

<span data-ttu-id="700a7-153">Dacă o entitate conține URL-uri pentru imagini de profil sau logo-uri disponibile public, le puteți adăuga la profilul de client unificat.</span><span class="sxs-lookup"><span data-stu-id="700a7-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="700a7-154">Selectați entitatea și găsiți câmpul care conține adresa URL a imaginii de profil.</span><span class="sxs-lookup"><span data-stu-id="700a7-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="700a7-155">În câmpul de intrare **Tip**, introduceți manual valoarea următoare:</span><span class="sxs-lookup"><span data-stu-id="700a7-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="700a7-156">Pentru o persoană: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="700a7-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="700a7-157">Pentru o organizație: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="700a7-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="700a7-158">Continuați cu pașii de unificare și asigurați-vă că atributul care conține adresa URL a imaginii este, de asemenea, adăugat în pasul [Îmbinare](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="700a7-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="700a7-159">Setați atribute pentru organizații</span><span class="sxs-lookup"><span data-stu-id="700a7-159">Set attributes for organizations</span></span>

<span data-ttu-id="700a7-160">Pentru organizații (previzualizare), tipul de atribut ar trebui să fie asociat cu „Organization.Name”</span><span class="sxs-lookup"><span data-stu-id="700a7-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="700a7-161">![Cheie primară și tip de atribut B2B](media/configure-data-map-edit-b2b.png "Cheie primară și tip de atribut B2B")</span><span class="sxs-lookup"><span data-stu-id="700a7-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="700a7-162">Următorul pas</span><span class="sxs-lookup"><span data-stu-id="700a7-162">Next step</span></span>

<span data-ttu-id="700a7-163">Ca parte a procesului de unificare a datelor, accesați pagina **Potrivire**.</span><span class="sxs-lookup"><span data-stu-id="700a7-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="700a7-164">Vizita [**Potrivire**](match-entities.md) pentru a vă informa cu privire la această fază.</span><span class="sxs-lookup"><span data-stu-id="700a7-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="700a7-165">Consultați videoclipul următor: [Introducere: Crearea unui profil de client unificat](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="700a7-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]