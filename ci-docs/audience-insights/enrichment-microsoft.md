---
title: Îmbogățiți profilurile clienților cu date de la Microsoft
description: Folosiți date cu caracter proprietar de la Microsoft pentru a vă îmbogăți datele clienților cu afinități de marcă și de interes.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f19033236190547f68d2b91ec6b32074bf7912a
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896617"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="c9b11-103">Îmbogățiți profilurile clienților cu afinități de brand și interes (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="c9b11-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="c9b11-104">Folosiți datele cu caracter proprietar ale Microsoft pentru a vă îmbogăți datele clienților cu afinități de marcă și de interes.</span><span class="sxs-lookup"><span data-stu-id="c9b11-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="c9b11-105">Aceste afinități sunt determinate pe baza datelor de la persoane cu o demografie similară pentru clienții dvs.</span><span class="sxs-lookup"><span data-stu-id="c9b11-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="c9b11-106">Aceste informații vă ajută să vă înțelegeți și să vă segmentați mai bine clienții în funcție de afinitățile lor către anumite mărci și interese.</span><span class="sxs-lookup"><span data-stu-id="c9b11-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="c9b11-107">În detalii despre audiență, accesați **Date** > **Îmbogățire** pentru a [configura și vizualiza îmbogățiri](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="c9b11-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="c9b11-108">Pentru a configura îmbogățirea afinităților de marcă, accesați fila **Descoperire** și selectați **Îmbogățiți-mi datele** pe dala **Mărci**.</span><span class="sxs-lookup"><span data-stu-id="c9b11-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="c9b11-109">Pentru a configura îmbogățirea afinităților de interes, accesați fila **Descoperire** și selectați **Îmbogățiți-mi datele** pe dala **Interese**.</span><span class="sxs-lookup"><span data-stu-id="c9b11-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c9b11-110">![Dale Branduri și interese](media/BrandsInterest-tile-Hub.png "Dale Branduri și interese")</span><span class="sxs-lookup"><span data-stu-id="c9b11-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="c9b11-111">Cum determinăm afinitățile</span><span class="sxs-lookup"><span data-stu-id="c9b11-111">How we determine affinities</span></span>

<span data-ttu-id="c9b11-112">Folosim datele de căutare online ale Microsoft pentru a găsi afinități pentru mărci și interese în diferite segmente demografice (definite în funcție de vârstă, sex sau locație).</span><span class="sxs-lookup"><span data-stu-id="c9b11-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="c9b11-113">Volumul de căutare online pentru o marcă sau interes determină cât de multă afinitate are un segment demografic, comparativ cu alte segmente, față de acea marcă sau interes.</span><span class="sxs-lookup"><span data-stu-id="c9b11-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span> <span data-ttu-id="c9b11-114">marca sau interesul.</span><span class="sxs-lookup"><span data-stu-id="c9b11-114">brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="c9b11-115">Nivelul și scorul de afinitate</span><span class="sxs-lookup"><span data-stu-id="c9b11-115">Affinity level and score</span></span>

<span data-ttu-id="c9b11-116">Pe fiecare profil de client îmbogățit, oferim două valori conexe - nivelul de afinitate și scorul de afinitate.</span><span class="sxs-lookup"><span data-stu-id="c9b11-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="c9b11-117">Aceste valori vă ajută să determinați cât de puternică este afinitatea pentru segmentul demografic al profilului respectiv, pentru un brand sau interes, în comparație cu alte segmente demografice.</span><span class="sxs-lookup"><span data-stu-id="c9b11-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="c9b11-118">*Nivelul de afinitate* este format din patru niveluri și *scor de afinitate* este calculat pe o scară de 100 de puncte care se mapează la nivelurile de afinitate.</span><span class="sxs-lookup"><span data-stu-id="c9b11-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="c9b11-119">Nivelul de afinitate</span><span class="sxs-lookup"><span data-stu-id="c9b11-119">Affinity level</span></span> |<span data-ttu-id="c9b11-120">Scor de afinitate</span><span class="sxs-lookup"><span data-stu-id="c9b11-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="c9b11-121">Foarte mare</span><span class="sxs-lookup"><span data-stu-id="c9b11-121">Very high</span></span>     | <span data-ttu-id="c9b11-122">85-100</span><span class="sxs-lookup"><span data-stu-id="c9b11-122">85-100</span></span>       |
|<span data-ttu-id="c9b11-123">Înalt</span><span class="sxs-lookup"><span data-stu-id="c9b11-123">High</span></span>     | <span data-ttu-id="c9b11-124">70-84</span><span class="sxs-lookup"><span data-stu-id="c9b11-124">70-84</span></span>        |
|<span data-ttu-id="c9b11-125">Mediu</span><span class="sxs-lookup"><span data-stu-id="c9b11-125">Medium</span></span>     | <span data-ttu-id="c9b11-126">35-69</span><span class="sxs-lookup"><span data-stu-id="c9b11-126">35-69</span></span>        |
|<span data-ttu-id="c9b11-127">Redusă</span><span class="sxs-lookup"><span data-stu-id="c9b11-127">Low</span></span>     | <span data-ttu-id="c9b11-128">1-34</span><span class="sxs-lookup"><span data-stu-id="c9b11-128">1-34</span></span>        |

<span data-ttu-id="c9b11-129">În funcție de granularitatea pe care doriți să o măsurați afinitatea, puteți utiliza fie nivelul de afinitate, fie punctajul.</span><span class="sxs-lookup"><span data-stu-id="c9b11-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="c9b11-130">Scorul de afinitate vă oferă un control mai precis.</span><span class="sxs-lookup"><span data-stu-id="c9b11-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="c9b11-131">Țări / regiuni acceptate</span><span class="sxs-lookup"><span data-stu-id="c9b11-131">Supported countries/regions</span></span>

<span data-ttu-id="c9b11-132">În prezent, acceptăm următoarele opțiuni de țară/regiune: Australia, Canada (engleză), Franța, Germania, Regatul Unit sau Statele Unite (engleză).</span><span class="sxs-lookup"><span data-stu-id="c9b11-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="c9b11-133">Pentru a selecta o țară, deschideți **Îmbogățirea mărcilor** sau **Îmbogățirea intereselor** și selectați **Schimbare** lângă **Țară/Regiune**.</span><span class="sxs-lookup"><span data-stu-id="c9b11-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="c9b11-134">În panoul **Setări de țară/regiune**, alegeți o opțiune și selectați **Aplicare**.</span><span class="sxs-lookup"><span data-stu-id="c9b11-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="c9b11-135">Implicații legate de selecția țării</span><span class="sxs-lookup"><span data-stu-id="c9b11-135">Implications related to country selection</span></span>

- <span data-ttu-id="c9b11-136">Când [alegeți propriile mărci](#define-your-brands-or-interests), sistemul oferă sugestii pe baza țării sau regiunii selectate.</span><span class="sxs-lookup"><span data-stu-id="c9b11-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="c9b11-137">Când [alegeți o industrie](#define-your-brands-or-interests), veți obține cele mai relevante mărci sau interese în funcție de țara sau regiunea selectată.</span><span class="sxs-lookup"><span data-stu-id="c9b11-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="c9b11-138">Când [îmbogățim profiluri](#refresh-enrichment), vom îmbogăți toate profilurile clienților pentru care obținem date pentru mărcile și interesele selectate.</span><span class="sxs-lookup"><span data-stu-id="c9b11-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="c9b11-139">Inclusiv profiluri care nu se află în țara sau regiunea selectată.</span><span class="sxs-lookup"><span data-stu-id="c9b11-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="c9b11-140">De exemplu, dacă ați selectat Germania, vom îmbogăți profilurile situate în Statele Unite dacă avem date disponibile pentru mărcile și interesele selectate din SUA.</span><span class="sxs-lookup"><span data-stu-id="c9b11-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="c9b11-141">Configurați îmbogățirea</span><span class="sxs-lookup"><span data-stu-id="c9b11-141">Configure Enrichment</span></span>

<span data-ttu-id="c9b11-142">O experiență ghidată vă ajută prin configurarea îmbogățirilor.</span><span class="sxs-lookup"><span data-stu-id="c9b11-142">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="c9b11-143">Definiți-vă brandurile sau interesele</span><span class="sxs-lookup"><span data-stu-id="c9b11-143">Define your brands or interests</span></span>

<span data-ttu-id="c9b11-144">Selectați una dintre următoarele opțiuni:</span><span class="sxs-lookup"><span data-stu-id="c9b11-144">Select one of the following options:</span></span>

- <span data-ttu-id="c9b11-145">**Industrie**: Sistemul identifică cele mai importante mărci sau interese relevante pentru industria dvs. și îmbogățește datele clientului cu acestea.</span><span class="sxs-lookup"><span data-stu-id="c9b11-145">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="c9b11-146">**Alegeți-vă una proprie**: Selectați până la cinci articole din lista mărcilor sau a intereselor care sunt cele mai relevante pentru organizația dvs.</span><span class="sxs-lookup"><span data-stu-id="c9b11-146">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="c9b11-147">Pentru a adăuga o marcă sau interes, introduceți-o în zona de intrare pentru a primi sugestii bazate pe termeni potriviți.</span><span class="sxs-lookup"><span data-stu-id="c9b11-147">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="c9b11-148">Dacă nu enumerăm o marcă sau un interes pe care îl căutați, trimiteți-ne feedback folosind legătura **Sugerați**.</span><span class="sxs-lookup"><span data-stu-id="c9b11-148">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="c9b11-149">Recenzie preferințe de îmbogățire</span><span class="sxs-lookup"><span data-stu-id="c9b11-149">Review enrichment preferences</span></span>

<span data-ttu-id="c9b11-150">Examinați preferințele implicite de îmbogățire și actualizați-le după cum este necesar.</span><span class="sxs-lookup"><span data-stu-id="c9b11-150">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captură de ecran a ferestrei preferințelor de îmbogățire.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="c9b11-152">Selectați entitatea de îmbogățit</span><span class="sxs-lookup"><span data-stu-id="c9b11-152">Select entity to enrich</span></span>

<span data-ttu-id="c9b11-153">Selectați **Entitate îmbogățită** și alegeți setul de date pe care doriți să îl îmbogățiți cu datele companiei de la Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9b11-153">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="c9b11-154">Puteți selecta entitatea Client pentru a vă îmbogăți toate profilurile de clienți sau selectați o entitate de segment pentru a îmbogăți numai profilurile de clienți din acel segment.</span><span class="sxs-lookup"><span data-stu-id="c9b11-154">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="c9b11-155">Mapați câmpurile</span><span class="sxs-lookup"><span data-stu-id="c9b11-155">Map your fields</span></span>

<span data-ttu-id="c9b11-156">Hartați câmpurile de la entitatea dvs. client unificată pentru a defini segmentul demografic pe care doriți să îl utilizeze sistemul pentru îmbogățirea datelor despre clienți.</span><span class="sxs-lookup"><span data-stu-id="c9b11-156">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="c9b11-157">Mapați Țară/Regiune și cel puțin Data nașterii sau atributele de gen.</span><span class="sxs-lookup"><span data-stu-id="c9b11-157">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="c9b11-158">În plus, trebuie să mapați cel puțin unul dintre oraș (și stat/provincie) sau cod poștal.</span><span class="sxs-lookup"><span data-stu-id="c9b11-158">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="c9b11-159">Selectați **Editați** pentru a defini maparea câmpurilor și selectați **Aplicare** când ați terminat.</span><span class="sxs-lookup"><span data-stu-id="c9b11-159">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="c9b11-160">Selectați **Salvați** pentru a finaliza maparea câmpului.</span><span class="sxs-lookup"><span data-stu-id="c9b11-160">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="c9b11-161">Următoarele formate și valori sunt acceptate, valorile nu sunt sensibile la litere mari și mici:</span><span class="sxs-lookup"><span data-stu-id="c9b11-161">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="c9b11-162">**Data de naștere**: Recomandăm ca data nașterii să fie transformată în tip DateTime în timpul ingestiei de date.</span><span class="sxs-lookup"><span data-stu-id="c9b11-162">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="c9b11-163">Alternativ, poate fi un șir în format [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format „aaaa-LL-zz” sau „aaaa-LL-zzTOO:mm:ssZ”.</span><span class="sxs-lookup"><span data-stu-id="c9b11-163">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="c9b11-164">**Sex**: Bărbat, Femeie, Necunoscut</span><span class="sxs-lookup"><span data-stu-id="c9b11-164">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="c9b11-165">**Cod poștal**: Coduri poștale de cinci cifre pentru SUA, cod poștal standard în restul locațiilor</span><span class="sxs-lookup"><span data-stu-id="c9b11-165">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="c9b11-166">**Oraș**: Numele orașului în engleză</span><span class="sxs-lookup"><span data-stu-id="c9b11-166">**City**: City name in English</span></span>
- <span data-ttu-id="c9b11-167">**Stat/Provincie**: Abreviere cu două litere pentru SUA și Canada.</span><span class="sxs-lookup"><span data-stu-id="c9b11-167">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="c9b11-168">Abreviere cu două sau trei litere pentru Australia.</span><span class="sxs-lookup"><span data-stu-id="c9b11-168">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="c9b11-169">Nu se aplică Franței, Germaniei sau Regatului Unit.</span><span class="sxs-lookup"><span data-stu-id="c9b11-169">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="c9b11-170">**Țară/regiune**:</span><span class="sxs-lookup"><span data-stu-id="c9b11-170">**Country/Region**:</span></span>

  - <span data-ttu-id="c9b11-171">SUA: Statele Unite ale Americii, Statele Unite, SUA, SUA, America</span><span class="sxs-lookup"><span data-stu-id="c9b11-171">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="c9b11-172">CA: Canada, CA</span><span class="sxs-lookup"><span data-stu-id="c9b11-172">CA: Canada, CA</span></span>
  - <span data-ttu-id="c9b11-173">GB: Regatul Unit, UK, Marea Britanie, GB, Regatul Unit al Marii Britanii și Irlandei de Nord, Regatul Unit al Marii Britanii</span><span class="sxs-lookup"><span data-stu-id="c9b11-173">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="c9b11-174">AU: Australia, AU, Commonwealth-ul Australiei</span><span class="sxs-lookup"><span data-stu-id="c9b11-174">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="c9b11-175">FR: Franța, FR, Republica Franceză</span><span class="sxs-lookup"><span data-stu-id="c9b11-175">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="c9b11-176">DE: Germania, German, Deutschland, Allemagne, DE, Republica Federală Germania, Republica Germania</span><span class="sxs-lookup"><span data-stu-id="c9b11-176">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="c9b11-177">Examinați și denumiți îmbogățirea</span><span class="sxs-lookup"><span data-stu-id="c9b11-177">Review and name the enrichment</span></span>

<span data-ttu-id="c9b11-178">În cele din urmă, trebuie să examinați informațiile și să furnizați un nume pentru îmbogățire.</span><span class="sxs-lookup"><span data-stu-id="c9b11-178">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Revizuirea intereselor și denumirea paginii.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="c9b11-180">Reîmprospătare îmbogățire</span><span class="sxs-lookup"><span data-stu-id="c9b11-180">Refresh enrichment</span></span>

<span data-ttu-id="c9b11-181">Rulați îmbogățirea după configurarea mărcilor, a intereselor și a mapării câmpului pentru demografie.</span><span class="sxs-lookup"><span data-stu-id="c9b11-181">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="c9b11-182">Pentru a începe procesul, selectați **Rulare** pe pagina de configurare a mărcii sau a intereselor.</span><span class="sxs-lookup"><span data-stu-id="c9b11-182">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="c9b11-183">În plus, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei actualizări programate.</span><span class="sxs-lookup"><span data-stu-id="c9b11-183">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="c9b11-184">În funcție de dimensiunea datelor clientului dvs., este posibil să dureze câteva minute pentru a finaliza o îmbogățire.</span><span class="sxs-lookup"><span data-stu-id="c9b11-184">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="c9b11-185">Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese.</span><span class="sxs-lookup"><span data-stu-id="c9b11-185">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="c9b11-186">În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="c9b11-186">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="c9b11-187">Puteți selecta starea unui proces pentru a vedea detalii despre evoluția întregii lucrări.</span><span class="sxs-lookup"><span data-stu-id="c9b11-187">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="c9b11-188">După selectarea **Vizualizare detalii** pentru una dintre sarcinile jobului, găsiți informații suplimentare: timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate sarcinii.</span><span class="sxs-lookup"><span data-stu-id="c9b11-188">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="c9b11-189">Rezultate de îmbogățire</span><span class="sxs-lookup"><span data-stu-id="c9b11-189">Enrichment results</span></span>

<span data-ttu-id="c9b11-190">După executarea procesului de îmbogățire, accesați **Îmbogățirile mele** pentru a analiza numărul total de clienți îmbogățiți și o defalcare a mărcilor sau a intereselor în profilurile de clienți îmbogățite.</span><span class="sxs-lookup"><span data-stu-id="c9b11-190">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Previzualizarea rezultatelor după executarea procesului de îmbogățire":::

<span data-ttu-id="c9b11-192">Verificați datele îmbogățite selectând **Vizualizați date îmbogățite** în grafic.</span><span class="sxs-lookup"><span data-stu-id="c9b11-192">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="c9b11-193">Datele îmbogățite pentru mărci se includ în entitatea **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="c9b11-193">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="c9b11-194">Datele pentru interese sunt în entitatea **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="c9b11-194">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="c9b11-195">De asemenea, veți găsi aceste entități listate în grupul **Îmbogățire** în **Date** > **Entități**.</span><span class="sxs-lookup"><span data-stu-id="c9b11-195">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="c9b11-196">Consultați datele de îmbogățire de pe cardul clientului</span><span class="sxs-lookup"><span data-stu-id="c9b11-196">See enrichment data on the customer card</span></span>

<span data-ttu-id="c9b11-197">Afinitățile de marcă și interes pot fi, de asemenea, vizualizate pe carduri individuale ale clienților.</span><span class="sxs-lookup"><span data-stu-id="c9b11-197">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="c9b11-198">Accesați **Clienți** și selectați un profil de client.</span><span class="sxs-lookup"><span data-stu-id="c9b11-198">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="c9b11-199">În cardul de client, veți găsi diagrame pentru mărcile sau interesele pentru care persoanele din profilul demografic al clientului au afinitate.</span><span class="sxs-lookup"><span data-stu-id="c9b11-199">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Card de client cu date îmbogățite":::

## <a name="next-steps"></a><span data-ttu-id="c9b11-201">Următorii pași</span><span class="sxs-lookup"><span data-stu-id="c9b11-201">Next steps</span></span>

<span data-ttu-id="c9b11-202">Creați în plus față de datele îmbogățite ale clienților.</span><span class="sxs-lookup"><span data-stu-id="c9b11-202">Build on top of your enriched customer data.</span></span> <span data-ttu-id="c9b11-203">Creați [Segmente](segments.md), [Măsuri](measures.md) și chiar [exportați datele](export-destinations.md) pentru a oferi experiențe personalizate clienților.</span><span class="sxs-lookup"><span data-stu-id="c9b11-203">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
