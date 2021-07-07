---
title: Crearea și gestionarea măsurilor
description: Definiți măsuri pentru a analiza și reflecta performanța afacerii dvs.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a83caf2428f3dbd9791b9f746d00d370362a508c
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304818"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="64c67-103">Definiți și gestionați măsurile</span><span class="sxs-lookup"><span data-stu-id="64c67-103">Define and manage measures</span></span>

<span data-ttu-id="64c67-104">Măsurile vă ajută să înțelegeți mai bine comportamentele clienților și performanța afacerii.</span><span class="sxs-lookup"><span data-stu-id="64c67-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="64c67-105">Se uită la valorile relevante din [profiluri unificate](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="64c67-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="64c67-106">De exemplu, o companie vrea să vadă *cheltuielile totale per client* pentru a înțelege istoricul sau măsura achizițiilor unui client individual *vânzările totale ale companiei* pentru a înțelege veniturile la nivel agregat din întreaga afacere.</span><span class="sxs-lookup"><span data-stu-id="64c67-106">For example, a business wants to see the *total spend per customer* to understand an individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="64c67-107">Măsurile sunt create folosind generatorul de măsuri, o platformă de interogare a datelor cu diverși operatori și opțiuni simple de mapare.</span><span class="sxs-lookup"><span data-stu-id="64c67-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="64c67-108">Vă permite să filtrați datele, să grupați rezultatele, să detectați [căile relației entității](relationships.md), și previzualizați ieșirea.</span><span class="sxs-lookup"><span data-stu-id="64c67-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="64c67-109">Utilizați instrumentul de măsurare pentru a planifica activități comerciale prin interogarea datelor despre clienți și extragerea de informații.</span><span class="sxs-lookup"><span data-stu-id="64c67-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="64c67-110">De exemplu, crearea unei măsuri de *cheltuieli totale per client* și *returnare totală per client* ajută la identificarea unui grup de clienți cu cheltuieli mari, dar cu randament ridicat.</span><span class="sxs-lookup"><span data-stu-id="64c67-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="64c67-111">Puteți [crea un segment](segments.md) pentru a conduce următoarele cele mai bune acțiuni.</span><span class="sxs-lookup"><span data-stu-id="64c67-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="64c67-112">Construiți propria măsură de la zero</span><span class="sxs-lookup"><span data-stu-id="64c67-112">Build your own measure from scratch</span></span>

<span data-ttu-id="64c67-113">Această secțiune vă ajută să creați o nouă măsură de la zero.</span><span class="sxs-lookup"><span data-stu-id="64c67-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="64c67-114">Puteți construi o măsură cu atribute de date de la entități de date care au o relație configurată pentru a se conecta cu entitatea Client.</span><span class="sxs-lookup"><span data-stu-id="64c67-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="64c67-115">În Detalii despre public, accesați **Măsuri**.</span><span class="sxs-lookup"><span data-stu-id="64c67-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="64c67-116">Selectați **Nou** și alegeți **Construiți una proprie**.</span><span class="sxs-lookup"><span data-stu-id="64c67-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="64c67-117">Selectați **Editează nume** și furnizați un **Nume** pentru măsură.</span><span class="sxs-lookup"><span data-stu-id="64c67-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="64c67-118">Dacă noua dvs. configurație de măsurare are doar două câmpuri—de exemplu, CustomerID și un singur calcul—rezultatul va fi adăugat ca o nouă coloană la entitatea generată de sistem numită Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="64c67-118">If your new measure configuration has only two fields—for example, CustomerID and one calculation—the output will be added as a new column to the system-generated entity called Customer_Measure.</span></span> <span data-ttu-id="64c67-119">Și veți putea vedea valoarea măsurii în profilul de client unificat.</span><span class="sxs-lookup"><span data-stu-id="64c67-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="64c67-120">Alte măsuri își vor genera propriile entități.</span><span class="sxs-lookup"><span data-stu-id="64c67-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="64c67-121">În zona de configurare, alegeți funcția de agregare din meniul derulant **Selectați Funcție**.</span><span class="sxs-lookup"><span data-stu-id="64c67-121">In the configuration area, choose the aggregation function from the **Select Function** dropdown menu.</span></span> <span data-ttu-id="64c67-122">Funcțiile de agregare includ:</span><span class="sxs-lookup"><span data-stu-id="64c67-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="64c67-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="64c67-123">**Sum**</span></span>
   - <span data-ttu-id="64c67-124">**Medie**</span><span class="sxs-lookup"><span data-stu-id="64c67-124">**Average**</span></span>
   - <span data-ttu-id="64c67-125">**Contor**</span><span class="sxs-lookup"><span data-stu-id="64c67-125">**Count**</span></span>
   - <span data-ttu-id="64c67-126">**Număr unic**</span><span class="sxs-lookup"><span data-stu-id="64c67-126">**Count Unique**</span></span>
   - <span data-ttu-id="64c67-127">**Max**</span><span class="sxs-lookup"><span data-stu-id="64c67-127">**Max**</span></span>
   - <span data-ttu-id="64c67-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="64c67-128">**Min**</span></span>
   - <span data-ttu-id="64c67-129">**Primul**: ia prima valoare a înregistrării de date</span><span class="sxs-lookup"><span data-stu-id="64c67-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="64c67-130">**Ultimul**: ia ultima valoare care a fost adăugată la înregistrarea de date</span><span class="sxs-lookup"><span data-stu-id="64c67-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatori pentru calcule de măsură.":::

1. <span data-ttu-id="64c67-132">Selectați **Adăugați un atribut** pentru a selecta datele de care aveți nevoie pentru a crea această măsură.</span><span class="sxs-lookup"><span data-stu-id="64c67-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="64c67-133">Selectați fila **Atribute**.</span><span class="sxs-lookup"><span data-stu-id="64c67-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="64c67-134">Entitate de date: alegeți entitatea care include atributul pe care doriți să îl măsurați.</span><span class="sxs-lookup"><span data-stu-id="64c67-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="64c67-135">Atribut de date: alegeți atributul pe care doriți să îl utilizați în funcția de agregare pentru a calcula măsura.</span><span class="sxs-lookup"><span data-stu-id="64c67-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="64c67-136">Puteți selecta doar un singur atribut o dată.</span><span class="sxs-lookup"><span data-stu-id="64c67-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="64c67-137">De asemenea, puteți selecta un atribut de date dintr-o măsură existentă selectând fila **Măsuri**. Sau puteți căuta o entitate sau un nume de măsură.</span><span class="sxs-lookup"><span data-stu-id="64c67-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="64c67-138">Selectați **Adăuga** pentru a adăuga atributul selectat la măsură.</span><span class="sxs-lookup"><span data-stu-id="64c67-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Selectați un atribut de utilizat în calcule.":::

1. <span data-ttu-id="64c67-140">Pentru a construi măsuri mai complexe, puteți adăuga mai multe atribute sau puteți utiliza operatori matematici în funcția de măsurare.</span><span class="sxs-lookup"><span data-stu-id="64c67-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Creați o măsură complexă cu operatori matematici.":::

1. <span data-ttu-id="64c67-142">Pentru a adăuga filtre, selectați **Filtru** în zona de configurare.</span><span class="sxs-lookup"><span data-stu-id="64c67-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="64c67-143">În secțiunea **Adăugați atribut** a panoului **Filtre**, selectați atributul pe care doriți să îl utilizați pentru a crea filtre.</span><span class="sxs-lookup"><span data-stu-id="64c67-143">In the **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="64c67-144">Setați operatorii de filtrare să definească filtrul pentru fiecare atribut selectat.</span><span class="sxs-lookup"><span data-stu-id="64c67-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="64c67-145">Selectați **Aplicare** pentru a adăuga filtrele la măsură.</span><span class="sxs-lookup"><span data-stu-id="64c67-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="64c67-146">Pentru a adăuga dimensiuni, selectați **Dimensiune** în zona de configurare.</span><span class="sxs-lookup"><span data-stu-id="64c67-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="64c67-147">Dimensiunile vor fi afișate ca coloane în entitatea de ieșire de măsurare.</span><span class="sxs-lookup"><span data-stu-id="64c67-147">Dimensions will show as columns in the measure output entity.</span></span>
 
   1. <span data-ttu-id="64c67-148">Selectați **Editați dimensiunile** pentru a adăuga atribute de date pe care doriți să le grupați valorile măsurate.</span><span class="sxs-lookup"><span data-stu-id="64c67-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="64c67-149">De exemplu, oraș sau sex.</span><span class="sxs-lookup"><span data-stu-id="64c67-149">For example, city or gender.</span></span> <span data-ttu-id="64c67-150">În mod implicit, dimensiunea *CustomerID* este selectată pentru a crea *măsuri la nivel de client*.</span><span class="sxs-lookup"><span data-stu-id="64c67-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="64c67-151">Puteți elimina dimensiunea implicită dacă doriți să creați *măsuri la nivel de afaceri*.</span><span class="sxs-lookup"><span data-stu-id="64c67-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="64c67-152">Selectați **Gata** pentru a adăuga dimensiunile la măsură.</span><span class="sxs-lookup"><span data-stu-id="64c67-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="64c67-153">Dacă există date în datele dvs. pe care trebuie să le înlocuiți cu un număr întreg—de exemplu, înlocuiți *nul* cu *0*—selectați **Reguli**.</span><span class="sxs-lookup"><span data-stu-id="64c67-153">If there are values in your data that you need to replace with an integer—for example, replace *null* with *0*—select **Rules**.</span></span> <span data-ttu-id="64c67-154">Configurați regula și asigurați-vă că alegeți numai numere întregi ca înlocuitoare.</span><span class="sxs-lookup"><span data-stu-id="64c67-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="64c67-155">Dacă există mai multe căi între entitatea de date pe care ați mapat-o și entitatea *Client* trebuie să alegeți una dintre [căile relației entității](relationships.md) identificate.</span><span class="sxs-lookup"><span data-stu-id="64c67-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="64c67-156">Rezultatele măsurătorilor pot varia în funcție de calea selectată.</span><span class="sxs-lookup"><span data-stu-id="64c67-156">Measure results can vary depending on the selected path.</span></span> 
   
   1. <span data-ttu-id="64c67-157">Selectați **Preferințe de date** și alegeți calea entității care ar trebui utilizată pentru a vă identifica măsura.</span><span class="sxs-lookup"><span data-stu-id="64c67-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="64c67-158">Dacă există doar o singură cale către entitatea *Client*, acest control nu se va afișa.</span><span class="sxs-lookup"><span data-stu-id="64c67-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="64c67-159">Selectați **Terminat** pentru a aplica selecția dvs.</span><span class="sxs-lookup"><span data-stu-id="64c67-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Selectați entitatea cale pentru măsură.":::

1. <span data-ttu-id="64c67-161">Pentru a adăuga mai multe calcule pentru măsură, selectați **Calcul nou**.</span><span class="sxs-lookup"><span data-stu-id="64c67-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="64c67-162">Puteți utiliza entități pe aceeași cale de entitate numai pentru noi calcule.</span><span class="sxs-lookup"><span data-stu-id="64c67-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="64c67-163">Mai multe calcule vor fi afișate drept coloane dnoi în entitatea de ieșire de măsurare.</span><span class="sxs-lookup"><span data-stu-id="64c67-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="64c67-164">Selectați **...** asupra calculului la **Duplicat**, **Redenumiți**, sau **Eliminați** un calcul dintr-o măsură.</span><span class="sxs-lookup"><span data-stu-id="64c67-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="64c67-165">În zona **Previzualizare**, veți vedea schema de date a entității de ieșire a măsurii, inclusiv filtre și dimensiuni.</span><span class="sxs-lookup"><span data-stu-id="64c67-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="64c67-166">Previzualizarea reacționează dinamic la schimbările din configurație.</span><span class="sxs-lookup"><span data-stu-id="64c67-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="64c67-167">Selectați **Rulare** pentru a calcula rezultatele pentru măsura configurată.</span><span class="sxs-lookup"><span data-stu-id="64c67-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="64c67-168">Selectați **Salvați și închideți** dacă doriți să păstrați configurația curentă și să executați măsura mai târziu.</span><span class="sxs-lookup"><span data-stu-id="64c67-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="64c67-169">Accesați **Măsuri** pentru a vedea măsurarea nou creată în listă.</span><span class="sxs-lookup"><span data-stu-id="64c67-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="64c67-170">Utilizați un șablon pentru a construi o măsură</span><span class="sxs-lookup"><span data-stu-id="64c67-170">Use a template to build a measure</span></span>

<span data-ttu-id="64c67-171">Puteți utiliza șabloane predefinite de măsuri utilizate în mod obișnuit pentru a le crea.</span><span class="sxs-lookup"><span data-stu-id="64c67-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="64c67-172">Descrieri detaliate ale șabloanelor și o experiență ghidată vă ajută la crearea eficientă a măsurilor.</span><span class="sxs-lookup"><span data-stu-id="64c67-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="64c67-173">Șabloanele se bazează pe date cartografiate din entitatea *Activitate unificată*.</span><span class="sxs-lookup"><span data-stu-id="64c67-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="64c67-174">Deci, asigurați-vă că ați configurat [activitățile clienților](activities.md) înainte de a crea o măsură dintr-un șablon.</span><span class="sxs-lookup"><span data-stu-id="64c67-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="64c67-175">Șabloane de măsură disponibile:</span><span class="sxs-lookup"><span data-stu-id="64c67-175">Available measure templates:</span></span> 
- <span data-ttu-id="64c67-176">Valoarea medie a tranzacției (ATV)</span><span class="sxs-lookup"><span data-stu-id="64c67-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="64c67-177">Valoarea totală a tranzacțiilor</span><span class="sxs-lookup"><span data-stu-id="64c67-177">Total transaction value</span></span>
- <span data-ttu-id="64c67-178">Venitul mediu zilnic</span><span class="sxs-lookup"><span data-stu-id="64c67-178">Average daily revenue</span></span>
- <span data-ttu-id="64c67-179">Venitul mediu anual</span><span class="sxs-lookup"><span data-stu-id="64c67-179">Average yearly revenue</span></span>
- <span data-ttu-id="64c67-180">Numărul de tranzacții</span><span class="sxs-lookup"><span data-stu-id="64c67-180">Transaction count</span></span>
- <span data-ttu-id="64c67-181">Puncte de fidelitate câștigate</span><span class="sxs-lookup"><span data-stu-id="64c67-181">Loyalty points earned</span></span>
- <span data-ttu-id="64c67-182">Puncte de fidelitate valorificate</span><span class="sxs-lookup"><span data-stu-id="64c67-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="64c67-183">Soldul punctelor de fidelitate</span><span class="sxs-lookup"><span data-stu-id="64c67-183">Loyalty points balance</span></span>
- <span data-ttu-id="64c67-184">Durată activă a ciclului de viață a clientului</span><span class="sxs-lookup"><span data-stu-id="64c67-184">Active customer lifespan</span></span>
- <span data-ttu-id="64c67-185">Durata apartenenței la programul de fidelitate</span><span class="sxs-lookup"><span data-stu-id="64c67-185">Loyalty membership duration</span></span>
- <span data-ttu-id="64c67-186">Timp de la ultima achiziție</span><span class="sxs-lookup"><span data-stu-id="64c67-186">Time since last purchase</span></span>

<span data-ttu-id="64c67-187">Următoarea procedură prezintă pașii pentru a construi o nouă măsură folosind un șablon.</span><span class="sxs-lookup"><span data-stu-id="64c67-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="64c67-188">În Detalii despre public, accesați **Măsuri**.</span><span class="sxs-lookup"><span data-stu-id="64c67-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="64c67-189">Selectați **Nou** și selectați **Alegeți un șablon**.</span><span class="sxs-lookup"><span data-stu-id="64c67-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Captură de ecran a meniului derulant atunci când creați o nouă măsură cu evidențiere pe șablon.":::

1. <span data-ttu-id="64c67-191">Găsiți șablonul care se potrivește nevoilor dvs. și selectați **Alegeți șablonul**.</span><span class="sxs-lookup"><span data-stu-id="64c67-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="64c67-192">Examinați datele necesare și selectați **Începeți** dacă aveți toate datele la locul lor.</span><span class="sxs-lookup"><span data-stu-id="64c67-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="64c67-193">În panoul **Editați nume**, setați numele măsurii dvs. și entitatea de ieșire.</span><span class="sxs-lookup"><span data-stu-id="64c67-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="64c67-194">Selectați **Terminat**.</span><span class="sxs-lookup"><span data-stu-id="64c67-194">Select **Done**.</span></span>

1. <span data-ttu-id="64c67-195">În secțiunea **Setați perioada de timp**, definiți intervalul de timp al datelor de utilizat.</span><span class="sxs-lookup"><span data-stu-id="64c67-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="64c67-196">Alegeți dacă doriți ca noua măsură să acopere întregul set de date selectând **Tot timpul**, sau dacă doriți ca măsura să se concentreze pe o **Anumită perioadă de timp**.</span><span class="sxs-lookup"><span data-stu-id="64c67-196">Choose if you want the new measure to cover the entire dataset by selecting **All time**, or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captură de ecran care arată secțiunea perioadei de timp la configurarea unei măsuri dintr-un șablon.":::

1. <span data-ttu-id="64c67-198">În secțiunea următoare, selectați **Adăugați date** pentru a alege activitățile și pentru a mapa datele corespunzătoare din entitatea *Activitate unificată*.</span><span class="sxs-lookup"><span data-stu-id="64c67-198">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="64c67-199">Pasul 1 din 2: Sub **Tipul activității**, alegeți tipul entității pe care doriți să o utilizați.</span><span class="sxs-lookup"><span data-stu-id="64c67-199">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="64c67-200">Pentru **Activități**, selectați entitățile pe care doriți să le mapați.</span><span class="sxs-lookup"><span data-stu-id="64c67-200">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="64c67-201">Pasul 2 din 2: Alegeți atributul din entitatea *Activitate unificată* pentru componenta cerută de formulă.</span><span class="sxs-lookup"><span data-stu-id="64c67-201">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="64c67-202">De exemplu, pentru Valoarea medie a tranzacției, este atributul care reprezintă valoarea tranzacției.</span><span class="sxs-lookup"><span data-stu-id="64c67-202">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="64c67-203">Pentru **Marcaj de timp al activității**, alegeți atributul din entitatea de activitate unificată care reprezintă data și ora activității.</span><span class="sxs-lookup"><span data-stu-id="64c67-203">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="64c67-204">Odată ce maparea datelor are succes, puteți vedea starea drept **Finalizată** și numele activităților și atributelor mapate.</span><span class="sxs-lookup"><span data-stu-id="64c67-204">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Captură de ecran a unei configurații completate a șablonului de măsură.":::

1. <span data-ttu-id="64c67-206">Acum puteți selecta **Rulare** pentru a calcula rezultatele măsurii.</span><span class="sxs-lookup"><span data-stu-id="64c67-206">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="64c67-207">Pentru a-l rafina mai târziu, selectați **Salvați schița**.</span><span class="sxs-lookup"><span data-stu-id="64c67-207">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="64c67-208">Gestionați-vă măsurile</span><span class="sxs-lookup"><span data-stu-id="64c67-208">Manage your measures</span></span>

<span data-ttu-id="64c67-209">Puteți găsi lista măsurilor pe pagina **Măsuri**.</span><span class="sxs-lookup"><span data-stu-id="64c67-209">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="64c67-210">Veți găsi informații despre tipul de măsură, creatorul, data creării, starea și starea.</span><span class="sxs-lookup"><span data-stu-id="64c67-210">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="64c67-211">Când selectați o măsură din listă, puteți previzualiza ieșirea și descărca un fișier CSV.</span><span class="sxs-lookup"><span data-stu-id="64c67-211">When you select a measure from the list, you can preview the output and download a CSV file.</span></span>

<span data-ttu-id="64c67-212">Pentru a vă reîmprospăta toate măsurile în același timp, selectați **Reîmprospătați tot** fără a selecta o anumită măsură.</span><span class="sxs-lookup"><span data-stu-id="64c67-212">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="64c67-213">![Acțiuni de gestionare a măsurilor unice.](media/measure-actions.png "Acțiuni de gestionare a măsurilor unice.")</span><span class="sxs-lookup"><span data-stu-id="64c67-213">![Actions to manage single measures.](media/measure-actions.png "Actions to manage single measures.")</span></span>

<span data-ttu-id="64c67-214">Selectați o măsură din listă pentru următoarele opțiuni:</span><span class="sxs-lookup"><span data-stu-id="64c67-214">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="64c67-215">Selectați numele măsurii pentru a vedea detaliile acesteia.</span><span class="sxs-lookup"><span data-stu-id="64c67-215">Select the measure name to see its details.</span></span>
- <span data-ttu-id="64c67-216">**Editați** configurația măsurii.</span><span class="sxs-lookup"><span data-stu-id="64c67-216">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="64c67-217">**Reîmprospătați** măsura pe baza celor mai recente date.</span><span class="sxs-lookup"><span data-stu-id="64c67-217">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="64c67-218">**Redenumiți** măsura.</span><span class="sxs-lookup"><span data-stu-id="64c67-218">**Rename** the measure.</span></span>
- <span data-ttu-id="64c67-219">**Ștergeți** măsura.</span><span class="sxs-lookup"><span data-stu-id="64c67-219">**Delete** the measure.</span></span>
- <span data-ttu-id="64c67-220">**Activați** sau **Dezactivați**.</span><span class="sxs-lookup"><span data-stu-id="64c67-220">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="64c67-221">Măsurile inactive nu vor fi reîmprospătate în timpul unei [reîmprospătări planificate](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="64c67-221">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="64c67-222">Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese.</span><span class="sxs-lookup"><span data-stu-id="64c67-222">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="64c67-223">În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="64c67-223">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="64c67-224">Puteți selecta starea unui proces pentru a vedea detalii despre evoluția întregii lucrări.</span><span class="sxs-lookup"><span data-stu-id="64c67-224">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="64c67-225">După selectare **Vezi detalii** pentru una dintre activitățile operațiunii, veți găsi informații suplimentare: timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate activității.</span><span class="sxs-lookup"><span data-stu-id="64c67-225">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="64c67-226">Următorul pas</span><span class="sxs-lookup"><span data-stu-id="64c67-226">Next step</span></span>

<span data-ttu-id="64c67-227">Puteți utiliza măsurile existente pentru a crea [un segment de clienți](segments.md).</span><span class="sxs-lookup"><span data-stu-id="64c67-227">You can use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
