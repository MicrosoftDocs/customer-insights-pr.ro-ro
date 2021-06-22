---
title: Îmbogățiți profilurile clienților cu date de la Microsoft
description: Folosiți date cu caracter proprietar de la Microsoft pentru a vă îmbogăți datele clienților cu afinități de marcă și de interes.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e92360bb886739cfe477ce1d2eb62219228a0292
ms.sourcegitcommit: d4b4053f6ee8f60f1a214982c4726c9de84615ef
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/14/2021
ms.locfileid: "6245722"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="1cfc0-103">Îmbogățiți profilurile clienților cu afinități de brand și interes (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="1cfc0-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="1cfc0-104">Folosiți datele cu caracter proprietar ale Microsoft pentru a vă îmbogăți datele clienților cu afinități de marcă și de interes.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="1cfc0-105">Aceste afinități sunt determinate pe baza datelor de la persoane cu o demografie similară pentru clienții dvs.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="1cfc0-106">Aceste informații vă ajută să vă înțelegeți și să vă segmentați mai bine clienții în funcție de afinitățile lor către anumite mărci și interese.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="1cfc0-107">În detalii despre audiență, accesați **Date** > **Îmbogățire** pentru a [configura și vizualiza îmbogățiri](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="1cfc0-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="1cfc0-108">Pentru a configura îmbogățirea afinităților de marcă, accesați fila **Descoperire** și selectați **Îmbogățiți-mi datele** pe dala **Mărci**.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="1cfc0-109">Pentru a configura îmbogățirea afinităților de interes, accesați fila **Descoperire** și selectați **Îmbogățiți-mi datele** pe dala **Interese**.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1cfc0-110">![Dale Branduri și interese](media/BrandsInterest-tile-Hub.png "Dale Branduri și interese")</span><span class="sxs-lookup"><span data-stu-id="1cfc0-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="1cfc0-111">Cum determinăm afinitățile</span><span class="sxs-lookup"><span data-stu-id="1cfc0-111">How we determine affinities</span></span>

<span data-ttu-id="1cfc0-112">Folosim datele de căutare online ale Microsoft pentru a găsi afinități pentru mărci și interese în diferite segmente demografice (definite în funcție de vârstă, sex sau locație).</span><span class="sxs-lookup"><span data-stu-id="1cfc0-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="1cfc0-113">Volumul de căutare online pentru o marcă sau interes determină cât de multă afinitate are un segment demografic, comparativ cu alte segmente, față de acea marcă sau interes.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="1cfc0-114">Nivelul și scorul de afinitate</span><span class="sxs-lookup"><span data-stu-id="1cfc0-114">Affinity level and score</span></span>

<span data-ttu-id="1cfc0-115">Pe fiecare profil de client îmbogățit, oferim două valori conexe - nivelul de afinitate și scorul de afinitate.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="1cfc0-116">Aceste valori vă ajută să determinați cât de puternică este afinitatea pentru segmentul demografic al profilului respectiv, pentru un brand sau interes, în comparație cu alte segmente demografice.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="1cfc0-117">*Nivelul de afinitate* este format din patru niveluri și *scor de afinitate* este calculat pe o scară de 100 de puncte care se mapează la nivelurile de afinitate.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="1cfc0-118">Nivelul de afinitate</span><span class="sxs-lookup"><span data-stu-id="1cfc0-118">Affinity level</span></span> |<span data-ttu-id="1cfc0-119">Scor de afinitate</span><span class="sxs-lookup"><span data-stu-id="1cfc0-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="1cfc0-120">Foarte mare</span><span class="sxs-lookup"><span data-stu-id="1cfc0-120">Very high</span></span>     | <span data-ttu-id="1cfc0-121">85-100</span><span class="sxs-lookup"><span data-stu-id="1cfc0-121">85-100</span></span>       |
|<span data-ttu-id="1cfc0-122">Înalt</span><span class="sxs-lookup"><span data-stu-id="1cfc0-122">High</span></span>     | <span data-ttu-id="1cfc0-123">70-84</span><span class="sxs-lookup"><span data-stu-id="1cfc0-123">70-84</span></span>        |
|<span data-ttu-id="1cfc0-124">Mediu</span><span class="sxs-lookup"><span data-stu-id="1cfc0-124">Medium</span></span>     | <span data-ttu-id="1cfc0-125">35-69</span><span class="sxs-lookup"><span data-stu-id="1cfc0-125">35-69</span></span>        |
|<span data-ttu-id="1cfc0-126">Redusă</span><span class="sxs-lookup"><span data-stu-id="1cfc0-126">Low</span></span>     | <span data-ttu-id="1cfc0-127">1-34</span><span class="sxs-lookup"><span data-stu-id="1cfc0-127">1-34</span></span>        |

<span data-ttu-id="1cfc0-128">În funcție de granularitatea pe care doriți să o măsurați afinitatea, puteți utiliza fie nivelul de afinitate, fie punctajul.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="1cfc0-129">Scorul de afinitate vă oferă un control mai precis.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="1cfc0-130">Țări / regiuni acceptate</span><span class="sxs-lookup"><span data-stu-id="1cfc0-130">Supported countries/regions</span></span>

<span data-ttu-id="1cfc0-131">În prezent, acceptăm următoarele opțiuni de țară/regiune: Australia, Canada (engleză), Franța, Germania, Regatul Unit sau Statele Unite (engleză).</span><span class="sxs-lookup"><span data-stu-id="1cfc0-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="1cfc0-132">Pentru a selecta o țară, deschideți **Îmbogățirea mărcilor** sau **Îmbogățirea intereselor** și selectați **Schimbare** lângă **Țară/Regiune**.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="1cfc0-133">În panoul **Setări de țară/regiune**, alegeți o opțiune și selectați **Aplicare**.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="1cfc0-134">Implicații legate de selecția țării</span><span class="sxs-lookup"><span data-stu-id="1cfc0-134">Implications related to country selection</span></span>

- <span data-ttu-id="1cfc0-135">Când [alegeți propriile mărci](#define-your-brands-or-interests), sistemul oferă sugestii pe baza țării sau regiunii selectate.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="1cfc0-136">Când [alegeți o industrie](#define-your-brands-or-interests), veți obține cele mai relevante mărci sau interese în funcție de țara sau regiunea selectată.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="1cfc0-137">Când [îmbogățim profiluri](#refresh-enrichment), vom îmbogăți toate profilurile clienților pentru care obținem date pentru mărcile și interesele selectate.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="1cfc0-138">Inclusiv profiluri care nu se află în țara sau regiunea selectată.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="1cfc0-139">De exemplu, dacă ați selectat Germania, vom îmbogăți profilurile situate în Statele Unite dacă avem date disponibile pentru mărcile și interesele selectate din SUA.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="1cfc0-140">Configurați îmbogățirea</span><span class="sxs-lookup"><span data-stu-id="1cfc0-140">Configure Enrichment</span></span>

<span data-ttu-id="1cfc0-141">O experiență ghidată vă ajută prin configurarea îmbogățirilor.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="1cfc0-142">Definiți-vă brandurile sau interesele</span><span class="sxs-lookup"><span data-stu-id="1cfc0-142">Define your brands or interests</span></span>

<span data-ttu-id="1cfc0-143">Alegeți până la cinci mărci sau interese folosind una sau ambele opțiuni:</span><span class="sxs-lookup"><span data-stu-id="1cfc0-143">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="1cfc0-144">**Industrie**: Selectați-vă industria din lista verticală și apoi alegeți dintre cele mai importante mărci sau interese pentru industria respectivă.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-144">**Industry**: Select your industry from the drop-down list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="1cfc0-145">**Alegeți-vă una proprie**: Introduceți o marcă sau un interes relevant pentru organizația dvs. și apoi alegeți dintre sugestiile potrivite.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-145">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="1cfc0-146">Dacă nu enumerăm o marcă sau un interes pe care îl căutați, trimiteți-ne feedback folosind legătura **Sugerați**.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-146">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="1cfc0-147">Recenzie preferințe de îmbogățire</span><span class="sxs-lookup"><span data-stu-id="1cfc0-147">Review enrichment preferences</span></span>

<span data-ttu-id="1cfc0-148">Examinați preferințele implicite de îmbogățire și actualizați-le după cum este necesar.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-148">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captură de ecran a ferestrei preferințelor de îmbogățire.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="1cfc0-150">Selectați entitatea de îmbogățit</span><span class="sxs-lookup"><span data-stu-id="1cfc0-150">Select entity to enrich</span></span>

<span data-ttu-id="1cfc0-151">Selectați **Entitate îmbogățită** și alegeți setul de date pe care doriți să îl îmbogățiți cu datele companiei de la Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-151">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="1cfc0-152">Puteți selecta entitatea Client pentru a vă îmbogăți toate profilurile de clienți sau selectați o entitate de segment pentru a îmbogăți numai profilurile de clienți din acel segment.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-152">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="1cfc0-153">Mapați câmpurile</span><span class="sxs-lookup"><span data-stu-id="1cfc0-153">Map your fields</span></span>

<span data-ttu-id="1cfc0-154">Hartați câmpurile de la entitatea dvs. client unificată pentru a defini segmentul demografic pe care doriți să îl utilizeze sistemul pentru îmbogățirea datelor despre clienți.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-154">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="1cfc0-155">Mapați Țară/Regiune și cel puțin Data nașterii sau atributele de gen.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-155">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="1cfc0-156">În plus, trebuie să mapați cel puțin unul dintre oraș (și stat/provincie) sau cod poștal.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-156">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="1cfc0-157">Selectați **Editați** pentru a defini maparea câmpurilor și selectați **Aplicare** când ați terminat.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-157">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="1cfc0-158">Selectați **Salvați** pentru a finaliza maparea câmpului.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-158">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="1cfc0-159">Următoarele formate și valori sunt acceptate, valorile nu sunt sensibile la litere mari și mici:</span><span class="sxs-lookup"><span data-stu-id="1cfc0-159">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="1cfc0-160">**Data de naștere**: Recomandăm ca data nașterii să fie transformată în tip DateTime în timpul ingestiei de date.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-160">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="1cfc0-161">Alternativ, poate fi un șir în format [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format „aaaa-LL-zz” sau „aaaa-LL-zzTOO:mm:ssZ”.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-161">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="1cfc0-162">**Sex**: Bărbat, Femeie, Necunoscut</span><span class="sxs-lookup"><span data-stu-id="1cfc0-162">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="1cfc0-163">**Cod poștal**: Coduri poștale de cinci cifre pentru SUA, cod poștal standard în restul locațiilor</span><span class="sxs-lookup"><span data-stu-id="1cfc0-163">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="1cfc0-164">**Oraș**: Numele orașului în engleză</span><span class="sxs-lookup"><span data-stu-id="1cfc0-164">**City**: City name in English</span></span>
- <span data-ttu-id="1cfc0-165">**Stat/Provincie**: Abreviere cu două litere pentru SUA și Canada.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-165">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="1cfc0-166">Abreviere cu două sau trei litere pentru Australia.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-166">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="1cfc0-167">Nu se aplică Franței, Germaniei sau Regatului Unit.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-167">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="1cfc0-168">**Țară/regiune**:</span><span class="sxs-lookup"><span data-stu-id="1cfc0-168">**Country/Region**:</span></span>

  - <span data-ttu-id="1cfc0-169">SUA: Statele Unite ale Americii, Statele Unite, SUA, SUA, America</span><span class="sxs-lookup"><span data-stu-id="1cfc0-169">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="1cfc0-170">CA: Canada, CA</span><span class="sxs-lookup"><span data-stu-id="1cfc0-170">CA: Canada, CA</span></span>
  - <span data-ttu-id="1cfc0-171">GB: Regatul Unit, UK, Marea Britanie, GB, Regatul Unit al Marii Britanii și Irlandei de Nord, Regatul Unit al Marii Britanii</span><span class="sxs-lookup"><span data-stu-id="1cfc0-171">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="1cfc0-172">AU: Australia, AU, Commonwealth-ul Australiei</span><span class="sxs-lookup"><span data-stu-id="1cfc0-172">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="1cfc0-173">FR: Franța, FR, Republica Franceză</span><span class="sxs-lookup"><span data-stu-id="1cfc0-173">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="1cfc0-174">DE: Germania, German, Deutschland, Allemagne, DE, Republica Federală Germania, Republica Germania</span><span class="sxs-lookup"><span data-stu-id="1cfc0-174">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="1cfc0-175">Examinați și denumiți îmbogățirea</span><span class="sxs-lookup"><span data-stu-id="1cfc0-175">Review and name the enrichment</span></span>

<span data-ttu-id="1cfc0-176">În cele din urmă, trebuie să examinați informațiile și să furnizați un nume pentru îmbogățire.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-176">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Revizuirea intereselor și denumirea paginii.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="1cfc0-178">Reîmprospătare îmbogățire</span><span class="sxs-lookup"><span data-stu-id="1cfc0-178">Refresh enrichment</span></span>

<span data-ttu-id="1cfc0-179">Rulați îmbogățirea după configurarea mărcilor, a intereselor și a mapării câmpului pentru demografie.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-179">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="1cfc0-180">Pentru a începe procesul, selectați **Rulare** pe pagina de configurare a mărcii sau a intereselor.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-180">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="1cfc0-181">În plus, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei actualizări programate.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-181">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="1cfc0-182">În funcție de dimensiunea datelor clientului dvs., este posibil să dureze câteva minute pentru a finaliza o îmbogățire.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-182">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="1cfc0-183">Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-183">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="1cfc0-184">În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="1cfc0-184">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="1cfc0-185">Puteți selecta starea unui proces pentru a vedea detalii despre evoluția întregii lucrări.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-185">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="1cfc0-186">După selectarea **Vizualizare detalii** pentru una dintre sarcinile jobului, găsiți informații suplimentare: timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate sarcinii.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-186">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="1cfc0-187">Rezultate de îmbogățire</span><span class="sxs-lookup"><span data-stu-id="1cfc0-187">Enrichment results</span></span>

<span data-ttu-id="1cfc0-188">După executarea procesului de îmbogățire, accesați **Îmbogățirile mele** pentru a analiza numărul total de clienți îmbogățiți și o defalcare a mărcilor sau a intereselor în profilurile de clienți îmbogățite.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-188">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Previzualizarea rezultatelor după executarea procesului de îmbogățire":::

<span data-ttu-id="1cfc0-190">Verificați datele îmbogățite selectând **Vizualizați date îmbogățite** în grafic.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-190">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="1cfc0-191">Datele îmbogățite pentru mărci se includ în entitatea **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-191">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="1cfc0-192">Datele pentru interese sunt în entitatea **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-192">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="1cfc0-193">De asemenea, veți găsi aceste entități listate în grupul **Îmbogățire** în **Date** > **Entități**.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-193">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="1cfc0-194">Consultați datele de îmbogățire de pe cardul clientului</span><span class="sxs-lookup"><span data-stu-id="1cfc0-194">See enrichment data on the customer card</span></span>

<span data-ttu-id="1cfc0-195">Afinitățile de marcă și interes pot fi, de asemenea, vizualizate pe carduri individuale ale clienților.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-195">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="1cfc0-196">Accesați **Clienți** și selectați un profil de client.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-196">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="1cfc0-197">În cardul de client, veți găsi diagrame pentru mărcile sau interesele pentru care persoanele din profilul demografic al clientului au afinitate.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-197">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Card de client cu date îmbogățite":::

## <a name="next-steps"></a><span data-ttu-id="1cfc0-199">Următorii pași</span><span class="sxs-lookup"><span data-stu-id="1cfc0-199">Next steps</span></span>

<span data-ttu-id="1cfc0-200">Creați în plus față de datele îmbogățite ale clienților.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-200">Build on top of your enriched customer data.</span></span> <span data-ttu-id="1cfc0-201">Creați [Segmente](segments.md), [Măsuri](measures.md) și chiar [exportați datele](export-destinations.md) pentru a oferi experiențe personalizate clienților.</span><span class="sxs-lookup"><span data-stu-id="1cfc0-201">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
