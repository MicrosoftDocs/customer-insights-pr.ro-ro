---
title: Crearea și gestionarea măsurilor
description: Definiți măsuri pentru a analiza și reflecta performanța afacerii dvs.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654747"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="9a290-103">Definiți și gestionați măsurile</span><span class="sxs-lookup"><span data-stu-id="9a290-103">Define and manage measures</span></span>

<span data-ttu-id="9a290-104">Măsurile vă ajută să înțelegeți mai bine comportamentele clienților și performanța afacerii prin recuperarea valorilor relevante din [profiluri unificate](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="9a290-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="9a290-105">De exemplu, o companie vrea să vadă *cheltuieli totale per client* pentru a înțelege istoricul achizițiilor clientului individual.</span><span class="sxs-lookup"><span data-stu-id="9a290-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="9a290-106">Sau măsurați *vânzările totale ale companiei* pentru a înțelege veniturile la nivel agregat din întreaga afacere.</span><span class="sxs-lookup"><span data-stu-id="9a290-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="9a290-107">Măsurile sunt create folosind generatorul de măsuri, o platformă de interogare a datelor cu diverși operatori și opțiuni simple de mapare.</span><span class="sxs-lookup"><span data-stu-id="9a290-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="9a290-108">Vă permite să filtrați datele, să grupați rezultatele, să detectați [căile relației entității](relationships.md), și previzualizați ieșirea.</span><span class="sxs-lookup"><span data-stu-id="9a290-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="9a290-109">Utilizați instrumentul de măsurare pentru a planifica activități comerciale prin interogarea datelor despre clienți și extragerea de informații.</span><span class="sxs-lookup"><span data-stu-id="9a290-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="9a290-110">De exemplu, crearea unei măsuri de *cheltuieli totale per client* și *returnare totală per client* ajută la identificarea unui grup de clienți cu cheltuieli mari, dar cu randament ridicat.</span><span class="sxs-lookup"><span data-stu-id="9a290-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="9a290-111">Puteți [crea un segment](segments.md) pentru a conduce următoarele cele mai bune acțiuni.</span><span class="sxs-lookup"><span data-stu-id="9a290-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="9a290-112">Crearea unei măsuri</span><span class="sxs-lookup"><span data-stu-id="9a290-112">Create a measure</span></span>

<span data-ttu-id="9a290-113">Această secțiune vă ajută să creați o nouă măsură de la zero.</span><span class="sxs-lookup"><span data-stu-id="9a290-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="9a290-114">Puteți construi o măsură cu atribute de date de la entități de date care au o relație configurată pentru a se conecta cu entitatea Client.</span><span class="sxs-lookup"><span data-stu-id="9a290-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="9a290-115">În Detalii despre public, accesați **Măsuri**.</span><span class="sxs-lookup"><span data-stu-id="9a290-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="9a290-116">Selectați **Nou**.</span><span class="sxs-lookup"><span data-stu-id="9a290-116">Select **New**.</span></span>

1. <span data-ttu-id="9a290-117">Selectați **Editează nume** și furnizați un **Nume** pentru măsură.</span><span class="sxs-lookup"><span data-stu-id="9a290-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="9a290-118">Dacă noua dvs. configurație de măsurare are doar două câmpuri, de exemplu, CustomerID și un singur calcul, rezultatul va fi adăugat ca o nouă coloană la entitatea generată de sistem numită Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="9a290-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="9a290-119">Și veți putea vedea valoarea măsurii în profilul de client unificat.</span><span class="sxs-lookup"><span data-stu-id="9a290-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="9a290-120">Alte măsuri își vor genera propriile entități.</span><span class="sxs-lookup"><span data-stu-id="9a290-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="9a290-121">În zona de configurare, alegeți funcția de agregare din meniul derulant **Selectați Funcție**.</span><span class="sxs-lookup"><span data-stu-id="9a290-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="9a290-122">Funcțiile de agregare includ:</span><span class="sxs-lookup"><span data-stu-id="9a290-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="9a290-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="9a290-123">**Sum**</span></span>
   - <span data-ttu-id="9a290-124">**Medie**</span><span class="sxs-lookup"><span data-stu-id="9a290-124">**Average**</span></span>
   - <span data-ttu-id="9a290-125">**Contor**</span><span class="sxs-lookup"><span data-stu-id="9a290-125">**Count**</span></span>
   - <span data-ttu-id="9a290-126">**Număr unic**</span><span class="sxs-lookup"><span data-stu-id="9a290-126">**Count Unique**</span></span>
   - <span data-ttu-id="9a290-127">**Max**</span><span class="sxs-lookup"><span data-stu-id="9a290-127">**Max**</span></span>
   - <span data-ttu-id="9a290-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="9a290-128">**Min**</span></span>
   - <span data-ttu-id="9a290-129">**Primul**: ia prima valoare a înregistrării de date</span><span class="sxs-lookup"><span data-stu-id="9a290-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="9a290-130">**Ultimul**: ia ultima valoare care a fost adăugată la înregistrarea de date</span><span class="sxs-lookup"><span data-stu-id="9a290-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatori pentru calcule de măsură.":::

1. <span data-ttu-id="9a290-132">Selectați **Adăugați un atribut** pentru a selecta datele de care aveți nevoie pentru a crea această măsură.</span><span class="sxs-lookup"><span data-stu-id="9a290-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="9a290-133">Selectați fila **Atribute**.</span><span class="sxs-lookup"><span data-stu-id="9a290-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="9a290-134">Entitate de date: alegeți entitatea care include atributul pe care doriți să îl măsurați.</span><span class="sxs-lookup"><span data-stu-id="9a290-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="9a290-135">Atribut de date: alegeți atributul pe care doriți să îl utilizați în funcția de agregare pentru a calcula măsura.</span><span class="sxs-lookup"><span data-stu-id="9a290-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="9a290-136">Puteți selecta doar un singur atribut o dată.</span><span class="sxs-lookup"><span data-stu-id="9a290-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="9a290-137">De asemenea, puteți selecta un atribut de date dintr-o măsură existentă selectând fila **Măsuri**. Sau puteți căuta o entitate sau un nume de măsură.</span><span class="sxs-lookup"><span data-stu-id="9a290-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="9a290-138">Selectați **Adăuga** pentru a adăuga atributul selectat la măsură.</span><span class="sxs-lookup"><span data-stu-id="9a290-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Selectați un atribut de utilizat în calcule.":::

1. <span data-ttu-id="9a290-140">Pentru a construi măsuri mai complexe, puteți adăuga mai multe atribute sau puteți utiliza operatori matematici în funcția de măsurare.</span><span class="sxs-lookup"><span data-stu-id="9a290-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Creați o măsură complexă cu operatori matematici.":::

1. <span data-ttu-id="9a290-142">Pentru a adăuga filtre, selectați **Filtru** în zona de configurare.</span><span class="sxs-lookup"><span data-stu-id="9a290-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="9a290-143">În secțiunea **Adăugați un atribut** din panoul **Filtre**, selectați atributul pe care doriți să îl utilizați pentru a crea filtre.</span><span class="sxs-lookup"><span data-stu-id="9a290-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="9a290-144">Setați operatorii de filtrare să definească filtrul pentru fiecare atribut selectat.</span><span class="sxs-lookup"><span data-stu-id="9a290-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="9a290-145">Selectați **Aplicare** pentru a adăuga filtrele la măsură.</span><span class="sxs-lookup"><span data-stu-id="9a290-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="9a290-146">Pentru a adăuga dimensiuni, selectați **Dimensiune** în zona de configurare.</span><span class="sxs-lookup"><span data-stu-id="9a290-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="9a290-147">Dimensiunile vor fi afișate ca coloane în entitatea de ieșire de măsurare.</span><span class="sxs-lookup"><span data-stu-id="9a290-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="9a290-148">Selectați **Editați dimensiunile** pentru a adăuga atribute de date pe care doriți să le grupați valorile măsurate.</span><span class="sxs-lookup"><span data-stu-id="9a290-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="9a290-149">De exemplu, oraș sau sex.</span><span class="sxs-lookup"><span data-stu-id="9a290-149">For example, city or gender.</span></span> <span data-ttu-id="9a290-150">În mod implicit, dimensiunea *CustomerID* este selectată pentru a crea *măsuri la nivel de client*.</span><span class="sxs-lookup"><span data-stu-id="9a290-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="9a290-151">Puteți elimina dimensiunea implicită dacă doriți să creați *măsuri la nivel de afaceri*.</span><span class="sxs-lookup"><span data-stu-id="9a290-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="9a290-152">Selectați **Gata** pentru a adăuga dimensiunile la măsură.</span><span class="sxs-lookup"><span data-stu-id="9a290-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="9a290-153">Dacă există mai multe căi între entitatea de date pe care ați mapat-o și entitatea *Client* trebuie să alegeți una dintre [căile relației entității](relationships.md) identificate.</span><span class="sxs-lookup"><span data-stu-id="9a290-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="9a290-154">Rezultatele măsurătorilor pot varia în funcție de calea selectată.</span><span class="sxs-lookup"><span data-stu-id="9a290-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="9a290-155">Selectați **Preferințe de date** și alegeți calea entității care ar trebui utilizată pentru a vă identifica măsura.</span><span class="sxs-lookup"><span data-stu-id="9a290-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="9a290-156">Dacă există doar o singură cale către entitatea *Client*, acest control nu se va afișa.</span><span class="sxs-lookup"><span data-stu-id="9a290-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="9a290-157">Selectați **Terminat** pentru a aplica selecția dvs.</span><span class="sxs-lookup"><span data-stu-id="9a290-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Selectați entitatea cale pentru măsură.":::

1. <span data-ttu-id="9a290-159">Pentru a adăuga mai multe calcule pentru măsură, selectați **Calcul nou**.</span><span class="sxs-lookup"><span data-stu-id="9a290-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="9a290-160">Puteți utiliza entități pe aceeași cale de entitate numai pentru noi calcule.</span><span class="sxs-lookup"><span data-stu-id="9a290-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="9a290-161">Mai multe calcule vor fi afișate drept coloane dnoi în entitatea de ieșire de măsurare.</span><span class="sxs-lookup"><span data-stu-id="9a290-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="9a290-162">Selectați **...** asupra calculului la **Duplicat**, **Redenumiți**, sau **Eliminați** un calcul dintr-o măsură.</span><span class="sxs-lookup"><span data-stu-id="9a290-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="9a290-163">În zona **Previzualizare**, veți vedea schema de date a entității de ieșire a măsurii, inclusiv filtre și dimensiuni.</span><span class="sxs-lookup"><span data-stu-id="9a290-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="9a290-164">Previzualizarea reacționează dinamic la schimbările din configurație.</span><span class="sxs-lookup"><span data-stu-id="9a290-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="9a290-165">Selectați **Rulare** pentru a calcula rezultatele pentru măsura configurată.</span><span class="sxs-lookup"><span data-stu-id="9a290-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="9a290-166">Selectați **Salvați și închideți** dacă doriți să păstrați configurația curentă și să executați măsura mai târziu.</span><span class="sxs-lookup"><span data-stu-id="9a290-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="9a290-167">Accesați **Măsuri** pentru a vedea măsurarea nou creată în listă.</span><span class="sxs-lookup"><span data-stu-id="9a290-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="9a290-168">Gestionați-vă măsurile</span><span class="sxs-lookup"><span data-stu-id="9a290-168">Manage your measures</span></span>

<span data-ttu-id="9a290-169">După ce [creați o măsură](#create-a-measure), veți vedea o listă de măsuri pe pagina **Măsuri**.</span><span class="sxs-lookup"><span data-stu-id="9a290-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="9a290-170">Veți găsi informații despre tipul de măsură, creatorul, data creării, starea și starea.</span><span class="sxs-lookup"><span data-stu-id="9a290-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="9a290-171">Când selectați o măsură din listă, puteți previzualiza rezultatul și descărca un fișier .CSV.</span><span class="sxs-lookup"><span data-stu-id="9a290-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="9a290-172">Pentru a vă reîmprospăta toate măsurile în același timp, selectați **Reîmprospătați tot** fără a selecta o anumită măsură.</span><span class="sxs-lookup"><span data-stu-id="9a290-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9a290-173">![Acțiuni de gestionare a măsurilor unice](media/measure-actions.png "Acțiuni de gestionare a măsurilor unice")</span><span class="sxs-lookup"><span data-stu-id="9a290-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="9a290-174">Selectați o măsură din listă pentru următoarele opțiuni:</span><span class="sxs-lookup"><span data-stu-id="9a290-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="9a290-175">Selectați numele măsurii pentru a vedea detaliile acesteia.</span><span class="sxs-lookup"><span data-stu-id="9a290-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="9a290-176">**Editați** configurația măsurii.</span><span class="sxs-lookup"><span data-stu-id="9a290-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="9a290-177">**Reîmprospătați** măsura pe baza celor mai recente date.</span><span class="sxs-lookup"><span data-stu-id="9a290-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="9a290-178">**Redenumiți** măsura.</span><span class="sxs-lookup"><span data-stu-id="9a290-178">**Rename** the measure.</span></span>
- <span data-ttu-id="9a290-179">**Ștergeți** măsura.</span><span class="sxs-lookup"><span data-stu-id="9a290-179">**Delete** the measure.</span></span>
- <span data-ttu-id="9a290-180">**Activați** sau **Dezactivați**.</span><span class="sxs-lookup"><span data-stu-id="9a290-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="9a290-181">Măsurile inactive nu vor fi reîmprospătate în timpul unei [reîmprospătări planificate](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9a290-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="9a290-182">Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese.</span><span class="sxs-lookup"><span data-stu-id="9a290-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="9a290-183">În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="9a290-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="9a290-184">Puteți selecta starea unui proces pentru a vedea detalii despre evoluția întregii lucrări.</span><span class="sxs-lookup"><span data-stu-id="9a290-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="9a290-185">După selectarea **Vizualizare detalii** pentru una dintre sarcinile jobului, găsiți informații suplimentare: timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate sarcinii.</span><span class="sxs-lookup"><span data-stu-id="9a290-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="9a290-186">Următorul pas</span><span class="sxs-lookup"><span data-stu-id="9a290-186">Next step</span></span>

<span data-ttu-id="9a290-187">Utilizați cam măsurile existente pentru a crea [un segment de clienți](segments.md).</span><span class="sxs-lookup"><span data-stu-id="9a290-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]