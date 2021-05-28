---
title: Crearea și gestionarea segmentelor
description: Creați segmente de clienți pentru a îi grupa pe baza diferitelor atribute.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064952"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="79176-103">Crearea și gestionarea segmentelor</span><span class="sxs-lookup"><span data-stu-id="79176-103">Create and manage segments</span></span>

<span data-ttu-id="79176-104">Definiți filtre complexe pe baza entității client unificate și a entităților conexe.</span><span class="sxs-lookup"><span data-stu-id="79176-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="79176-105">Fiecare segment, după procesare, creează un set de înregistrări ale clienților pe care le puteți exporta și pe care puteți acționa.</span><span class="sxs-lookup"><span data-stu-id="79176-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="79176-106">Segmentele sunt gestionate pe pagina **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="79176-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="79176-107">Următorul exemplu ilustrează capabilitatea de segmentare.</span><span class="sxs-lookup"><span data-stu-id="79176-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="79176-108">Am definit un segment pentru clienții care au comandat cel puțin $500 de bunuri în ultimele 90 de zile *și* care au fost implicați într-un apel serviciu pentru relații cu clienții care a fost escaladat.</span><span class="sxs-lookup"><span data-stu-id="79176-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Captură de ecran a interfeței UI a generatorului de segmente cu două grupuri care specifică un segment de clienți.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="79176-110">Crearea unui nou segment</span><span class="sxs-lookup"><span data-stu-id="79176-110">Create a new segment</span></span>

<span data-ttu-id="79176-111">Sunt mai multe moduri de a crea un segment nou.</span><span class="sxs-lookup"><span data-stu-id="79176-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="79176-112">Această secțiune descrie modul de a crea un *segment necompletat* de la zero.</span><span class="sxs-lookup"><span data-stu-id="79176-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="79176-113">De asemenea, puteți să creați un *segment rapid* pe baza entităților existente sau să valorificați modelele de învățare programată pentru a obține *segmente sugerate*.</span><span class="sxs-lookup"><span data-stu-id="79176-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="79176-114">Mai multe informații: [Prezentare generală a segmentelor](segments.md).</span><span class="sxs-lookup"><span data-stu-id="79176-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="79176-115">Când creați un segment, puteți salva o schiță.</span><span class="sxs-lookup"><span data-stu-id="79176-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="79176-116">Aceasta va fi salvată ca segment inactiv și nu se poate activa, se va termina cu o configurație validă.</span><span class="sxs-lookup"><span data-stu-id="79176-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="79176-117">Salt la pagina **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="79176-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="79176-118">Selectați **Nou** > **Segment necompletat**.</span><span class="sxs-lookup"><span data-stu-id="79176-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="79176-119">În panoul **Segment nou**, alegeți un tip de segment:</span><span class="sxs-lookup"><span data-stu-id="79176-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="79176-120">**Segmente dinamice** [reîmprospătați](segments.md#refresh-segments) după o Planificare recurentă.</span><span class="sxs-lookup"><span data-stu-id="79176-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="79176-121">**Segmente statice** se rulează o dată când le creați.</span><span class="sxs-lookup"><span data-stu-id="79176-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="79176-122">Dați un **Numele al entității de ieșire** pentru segment.</span><span class="sxs-lookup"><span data-stu-id="79176-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="79176-123">Opțional, furnizați un nume afișat și o descriere care ajută la identificarea segmentului.</span><span class="sxs-lookup"><span data-stu-id="79176-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="79176-124">Selectați **Următorul** pentru a ajunge la pagina **Generator de segmente** unde definiți un grup.</span><span class="sxs-lookup"><span data-stu-id="79176-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="79176-125">Un grup este un grup de clienți.</span><span class="sxs-lookup"><span data-stu-id="79176-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="79176-126">Alegeți entitatea care include atributul pe care doriți să îl segmentați.</span><span class="sxs-lookup"><span data-stu-id="79176-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="79176-127">Alegeți atributul pentru care utilizați segmentul.</span><span class="sxs-lookup"><span data-stu-id="79176-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="79176-128">Acest atribut poate avea unul dintre cele patru tipuri de valori: numeric, șir, dată sau boolean.</span><span class="sxs-lookup"><span data-stu-id="79176-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="79176-129">Alegeți un operator și o valoare pentru atributul selectat.</span><span class="sxs-lookup"><span data-stu-id="79176-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79176-130">![Particularizați filtrul de grup](media/customer-group-numbers.png "Filtrul de grup de clienți")</span><span class="sxs-lookup"><span data-stu-id="79176-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="79176-131">Număr</span><span class="sxs-lookup"><span data-stu-id="79176-131">Number</span></span> |<span data-ttu-id="79176-132">Definiție</span><span class="sxs-lookup"><span data-stu-id="79176-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="79176-133">1</span><span class="sxs-lookup"><span data-stu-id="79176-133">1</span></span>     |<span data-ttu-id="79176-134">Entity</span><span class="sxs-lookup"><span data-stu-id="79176-134">Entity</span></span>          |
   |<span data-ttu-id="79176-135">2</span><span class="sxs-lookup"><span data-stu-id="79176-135">2</span></span>     |<span data-ttu-id="79176-136">Atribut</span><span class="sxs-lookup"><span data-stu-id="79176-136">Attribute</span></span>          |
   |<span data-ttu-id="79176-137">3</span><span class="sxs-lookup"><span data-stu-id="79176-137">3</span></span>    |<span data-ttu-id="79176-138">Operator</span><span class="sxs-lookup"><span data-stu-id="79176-138">Operator</span></span>         |
   |<span data-ttu-id="79176-139">4</span><span class="sxs-lookup"><span data-stu-id="79176-139">4</span></span>    |<span data-ttu-id="79176-140">Valoare</span><span class="sxs-lookup"><span data-stu-id="79176-140">Value</span></span>         |

   1. <span data-ttu-id="79176-141">Pentru a adăuga mai multe condiții unui grup, puteți utiliza doi operatori logici:</span><span class="sxs-lookup"><span data-stu-id="79176-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="79176-142">Operator **ȘI**: Ambele condiții trebuie îndeplinite ca parte a procesului de segmentare.</span><span class="sxs-lookup"><span data-stu-id="79176-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="79176-143">Această opțiune este cea mai utilă atunci când definiți condiții pentru diferite entități.</span><span class="sxs-lookup"><span data-stu-id="79176-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="79176-144">Operatorul **SAU**: Fiecare dintre condiții trebuie îndeplinită ca parte a procesului de segmentare.</span><span class="sxs-lookup"><span data-stu-id="79176-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="79176-145">Această opțiune este cea mai utilă atunci când definiți condiții multiple pentru aceeași entitate.</span><span class="sxs-lookup"><span data-stu-id="79176-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="79176-146">![Operatorul SAU unde fiecare condiție trebuie îndeplinită](media/segmentation-either-condition.png "Operatorul SAU unde fiecare condiție trebuie îndeplinită")</span><span class="sxs-lookup"><span data-stu-id="79176-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="79176-147">În prezent este posibil să imbricați un operator **SAU** sub unul **ȘI**, dar nu și invers.</span><span class="sxs-lookup"><span data-stu-id="79176-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="79176-148">Fiecare grup se potrivește cu un set de clienți.</span><span class="sxs-lookup"><span data-stu-id="79176-148">Each group matches set of customers.</span></span> <span data-ttu-id="79176-149">Puteți combina mai multe grupuri pentru a include clienții necesari pentru cazul dvs. de afaceri.</span><span class="sxs-lookup"><span data-stu-id="79176-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="79176-150">Selectați **Adăugați un grup**.</span><span class="sxs-lookup"><span data-stu-id="79176-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="79176-151">![Grup Adăugare grup de clienți](media/customer-group-add-group.png "Grup Adăugare grup de clienți")</span><span class="sxs-lookup"><span data-stu-id="79176-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="79176-152">Selectați unul dintre operatorii de mulțimi: **Reuniune**, **Intersecție** sau **Cu excepția**.</span><span class="sxs-lookup"><span data-stu-id="79176-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79176-153">![Uniune Adăugare grup de clienți](media/customer-group-union.png "Uniune Adăugare grup de clienți")</span><span class="sxs-lookup"><span data-stu-id="79176-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="79176-154">**Uniune** unește cele două grupuri.</span><span class="sxs-lookup"><span data-stu-id="79176-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="79176-155">**Intersectare** suprapune cele două grupuri.</span><span class="sxs-lookup"><span data-stu-id="79176-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="79176-156">Doar datele care *sunt comune* pentru ambele grupuri sunt reținute în grupul unificat.</span><span class="sxs-lookup"><span data-stu-id="79176-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="79176-157">**Excepție** combină cele două grupuri.</span><span class="sxs-lookup"><span data-stu-id="79176-157">**Except** combines the two groups.</span></span> <span data-ttu-id="79176-158">Doar datele din grupul A care *nu sunt comune* cu datele din grupul B sunt reținute.</span><span class="sxs-lookup"><span data-stu-id="79176-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="79176-159">Dacă entitatea este conectată la entitatea client unificată prin [relații](relationships.md), trebuie să definiți calea relației pentru a crea un segment valid.</span><span class="sxs-lookup"><span data-stu-id="79176-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="79176-160">Adăugați entitățile din calea relației până când puteți selecta entitatea **Client: CustomerInsights** din meniul listă verticală.</span><span class="sxs-lookup"><span data-stu-id="79176-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="79176-161">Apoi alegeți **Toate înregistrările** pentru fiecare pas.</span><span class="sxs-lookup"><span data-stu-id="79176-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79176-162">![Calea relației în timpul creării segmentului](media/segments-multiple-relationships.png "Calea relației în timpul creării segmentului")</span><span class="sxs-lookup"><span data-stu-id="79176-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="79176-163">În mod implicit, segmentele generează o entitate de ieșire care conține toate atributele profilurilor clienților care se potrivesc cu filtrele definite.</span><span class="sxs-lookup"><span data-stu-id="79176-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="79176-164">Dacă un segment se bazează pe alte entități decât entitatea *Client*, puteți adăuga mai multe atribute de la aceste entități la entitatea de ieșire.</span><span class="sxs-lookup"><span data-stu-id="79176-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="79176-165">Selectați **Atributele proiectului** pentru a alege atributele care vor fi anexate entității de ieșire.</span><span class="sxs-lookup"><span data-stu-id="79176-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="79176-166">Exemplu: un segment se bazează pe o entitate care conține date despre activitatea clienților care sunt legate de entitatea *Client*.</span><span class="sxs-lookup"><span data-stu-id="79176-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="79176-167">Segmentul caută toți clienții care au apelat la serviciul de asistență în ultimele 60 de zile.</span><span class="sxs-lookup"><span data-stu-id="79176-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="79176-168">Puteți alege să adăugați durata apelului și numărul de apeluri la toate înregistrările de clienți care se potrivesc în entitatea de ieșire.</span><span class="sxs-lookup"><span data-stu-id="79176-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="79176-169">Aceste informații ar putea fi utile pentru a trimite un e-mail cu linkuri utile către articole de ajutor online și întrebări frecvente către clienții care au sunat frecvent.</span><span class="sxs-lookup"><span data-stu-id="79176-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="79176-170">Atributele proiectate vor funcționa doar pentru entitățile care au o relație unu-la-mulți cu entitatea client.</span><span class="sxs-lookup"><span data-stu-id="79176-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="79176-171">De exemplu, un client poate avea mai multe abonamente.</span><span class="sxs-lookup"><span data-stu-id="79176-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="79176-172">Puteți să proiectați atribute numai de la o entitate care este utilizată în fiecare grup de interogări de segmente creat.</span><span class="sxs-lookup"><span data-stu-id="79176-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="79176-173">Atributele proiectate sunt luate în calcul atunci când se utilizează operatori de mulțimi.</span><span class="sxs-lookup"><span data-stu-id="79176-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="79176-174">Selectați **Salvare** pentru a vă salva segmentul.</span><span class="sxs-lookup"><span data-stu-id="79176-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="79176-175">Segmentul dvs. va fi salvat și procesat dacă toate cerințele sunt validate.</span><span class="sxs-lookup"><span data-stu-id="79176-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="79176-176">În caz contrar, acesta va fi salvat ca schiță.</span><span class="sxs-lookup"><span data-stu-id="79176-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="79176-177">Selectați **Înapoi la segmente** pentru a reveni la pagina **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="79176-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="79176-178">Segmente rapide</span><span class="sxs-lookup"><span data-stu-id="79176-178">Quick segments</span></span>

<span data-ttu-id="79176-179">Segmentele rapide permit crearea de segmente simple cu un singur operator rapid pentru informații mai rapide.</span><span class="sxs-lookup"><span data-stu-id="79176-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="79176-180">Pe pagina **Segmente**, selectați **Nou** > **Creare din**.</span><span class="sxs-lookup"><span data-stu-id="79176-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="79176-181">Selectați opțiunea **Profiluri** pentru a construi un segment care se bazează pe entitatea *Client unificat*.</span><span class="sxs-lookup"><span data-stu-id="79176-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="79176-182">Selectați opțiunea **Măsuri** pentru a construi un segment în jurul măsurilor pe care le-ați creat anterior.</span><span class="sxs-lookup"><span data-stu-id="79176-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="79176-183">Selectați opțiunea **Inteligență** pentru a construi un segment în jurul uneia dintre entitățile de ieșire pe care le-ați generat folosind fie capabilități **Predicții** sau **Modele particularizate**.</span><span class="sxs-lookup"><span data-stu-id="79176-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="79176-184">În caseta de dialog **Segment rapid nou**, selectați un atribut din lista verticală **Câmp**.</span><span class="sxs-lookup"><span data-stu-id="79176-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="79176-185">Sistemul va oferi câteva informații suplimentare care vă vor ajuta să creați segmente mai bune de clienți.</span><span class="sxs-lookup"><span data-stu-id="79176-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="79176-186">Pentru câmpurile categorice, vom afișa 10 numere de clienți de top.</span><span class="sxs-lookup"><span data-stu-id="79176-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="79176-187">Alegeți o **Valoare** și selectați **Revizuire**.</span><span class="sxs-lookup"><span data-stu-id="79176-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="79176-188">Pentru un atribut numeric, sistemul va arăta ce valoare a atributului se încadrează sub percentila fiecărui client.</span><span class="sxs-lookup"><span data-stu-id="79176-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="79176-189">Alegeți un **Operator** și o **Valoare**, apoi selectați **Revizuire**.</span><span class="sxs-lookup"><span data-stu-id="79176-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="79176-190">Sistemul vă va oferi o **Dimensiunea estimată segment**.</span><span class="sxs-lookup"><span data-stu-id="79176-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="79176-191">Puteți alege dacă vreți să generați segmentul pe care l-ați definit sau să îl revizuiți mai întâi pentru a obține o dimensiune diferită a segmentului.</span><span class="sxs-lookup"><span data-stu-id="79176-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="79176-192">![Numele și estimarea pentru un segment rapid](media/quick-segment-name.png "Numele și estimarea pentru un segment rapid")</span><span class="sxs-lookup"><span data-stu-id="79176-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="79176-193">Furnizați un **Nume** pentru segmentul dvs.</span><span class="sxs-lookup"><span data-stu-id="79176-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="79176-194">Opțional, furnizați un **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="79176-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="79176-195">Selectați **Salvare** pentru a crea segmentul.</span><span class="sxs-lookup"><span data-stu-id="79176-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="79176-196">După ce segmentul a terminat procesarea, îl puteți vizualiza ca orice alt segment creat.</span><span class="sxs-lookup"><span data-stu-id="79176-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="79176-197">Pașii următori</span><span class="sxs-lookup"><span data-stu-id="79176-197">Next steps</span></span>

<span data-ttu-id="79176-198">[Exportați un segment](export-destinations.md) și explorați [Card client](customer-card-add-in.md) și [Conectori](export-power-bi.md) pentru a obține informații despre nivelul clientului.</span><span class="sxs-lookup"><span data-stu-id="79176-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
