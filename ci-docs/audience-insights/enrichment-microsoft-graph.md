---
title: Îmbogățiți profilurile clienților cu Microsoft Graph
description: Utilizați datele de proprietate din Microsoft Graph pentru a îmbogăți datele clienților dvs. cu afinități de marcă și interes.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406674"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="db315-103">Îmbogățiți profilurile clienților cu afinități de brand și interes (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="db315-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="db315-104">Utilizați datele de proprietate din Microsoft Graph pentru a îmbogăți datele clienților dvs. cu afinități de marcă și interes.</span><span class="sxs-lookup"><span data-stu-id="db315-104">Use proprietary data from the Microsoft Graph to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="db315-105">Aceste afinități sunt determinate pe baza datelor de la persoane cu o demografie similară pentru clienții dvs.</span><span class="sxs-lookup"><span data-stu-id="db315-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="db315-106">Aceste informații vă ajută să vă înțelegeți și să vă segmentați mai bine clienții în funcție de afinitățile lor către anumite mărci și interese.</span><span class="sxs-lookup"><span data-stu-id="db315-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="db315-107">În Detalii despre audiență, accesați **Date** > **Îmbogățire** pentru a [configura și vizualiza îmbogățiri](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="db315-107">In ausience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="db315-108">Pentru a configura îmbogățirea afinităților de marcă, accesați fila **Descoperire** și selectați **Îmbogățiți-mi datele** pe dala **Mărci**.</span><span class="sxs-lookup"><span data-stu-id="db315-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="db315-109">Pentru a configura îmbogățirea afinităților de interes, accesați fila **Descoperire** și selectați **Îmbogățiți-mi datele** pe dala **Interese**.</span><span class="sxs-lookup"><span data-stu-id="db315-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="db315-110">![Dale Branduri și interese](media/BrandsInterest-tile-Hub.png "Dale Branduri și interese")</span><span class="sxs-lookup"><span data-stu-id="db315-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="about-microsoft-graph"></a><span data-ttu-id="db315-111">Despre Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="db315-111">About Microsoft Graph</span></span>

<span data-ttu-id="db315-112">Folosim datele de căutare online din Microsoft Graph pentru a găsi afinități pentru mărci și interese pe diverse segmente demografice (definite în funcție de vârstă, sex sau locație).</span><span class="sxs-lookup"><span data-stu-id="db315-112">We use online search data from the Microsoft Graph to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="db315-113">Volumul de căutare online pentru o marcă sau interes determină cât de multă afinitate are un segment demografic, comparativ cu alte segmente, față de acea marcă sau interes.</span><span class="sxs-lookup"><span data-stu-id="db315-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

<span data-ttu-id="db315-114">[Aflați mai multe despre Microsoft Graph](https://docs.microsoft.com/graph/overview).</span><span class="sxs-lookup"><span data-stu-id="db315-114">[Learn more about Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>

## <a name="affinity-score-and-confidence"></a><span data-ttu-id="db315-115">Scorul de afinitate și încrederea</span><span class="sxs-lookup"><span data-stu-id="db315-115">Affinity score and confidence</span></span>

<span data-ttu-id="db315-116">**Scorul de afinitate** este calculat pe o scară de 100 de puncte, 100 reprezentând segmentul care are cea mai mare afinitate pentru o marcă sau interes.</span><span class="sxs-lookup"><span data-stu-id="db315-116">The **affinity score** is calculated on a 100-point scale, with 100 representing the segment that has the highest affinity for a brand or interest.</span></span>

<span data-ttu-id="db315-117">**Încredere în afinitate** se calculează, de asemenea, pe o scară de 100 de puncte.</span><span class="sxs-lookup"><span data-stu-id="db315-117">The **affinity confidence** is also calculated on a 100-point scale.</span></span> <span data-ttu-id="db315-118">Indică nivelul de încredere al sistemului că un segment are afinitate pentru brand sau interes.</span><span class="sxs-lookup"><span data-stu-id="db315-118">It indicates the system's confidence level that a segment has an affinity for the brand or interest.</span></span> <span data-ttu-id="db315-119">Nivelul de încredere se bazează pe mărimea segmentului și pe granularitatea segmentului.</span><span class="sxs-lookup"><span data-stu-id="db315-119">Confidence level is based on the segment size and the segment granularity.</span></span> <span data-ttu-id="db315-120">Mărimea segmentului este determinată de cantitatea de date pe care o avem pentru un segment dat.</span><span class="sxs-lookup"><span data-stu-id="db315-120">Segment size is determined by the amount of data we have for a given segment.</span></span> <span data-ttu-id="db315-121">Granularitatea segmentului este determinată de câte atribute (vârstă, sex, locație) sunt disponibile într-un profil.</span><span class="sxs-lookup"><span data-stu-id="db315-121">Segment granularity is determined by how many attributes (age, gender, location) are available in a profile.</span></span>

<span data-ttu-id="db315-122">Nu normalizăm scorurile pentru setul dvs. de date.</span><span class="sxs-lookup"><span data-stu-id="db315-122">We don't normalize the scores for your dataset.</span></span> <span data-ttu-id="db315-123">În consecință, este posibil să nu vedeți toate valorile posibile ale scorului de afinitate pentru setul dvs. de date.</span><span class="sxs-lookup"><span data-stu-id="db315-123">Consequently, you may not see all possible affinity score values for your dataset.</span></span> <span data-ttu-id="db315-124">De exemplu, este posibil să nu existe un profil de clienți îmbogățit cu scorul de afinitate 100 în datele dvs.</span><span class="sxs-lookup"><span data-stu-id="db315-124">For example, there may be no enriched customer profile with affinity score 100 in your data.</span></span> <span data-ttu-id="db315-125">Acest lucru este posibil dacă nu există clienți în segmentul demografic care a înregistrat un scor de 100 pentru o anumită marcă sau interes.</span><span class="sxs-lookup"><span data-stu-id="db315-125">That's possible if no customers exist in the demographic segment that scored 100 for a given brand or interest.</span></span>

> [!TIP]
> <span data-ttu-id="db315-126">Când [creați segmente](segments.md) utilizând scoruri de afinitate, consultați distribuția scorurilor de afinitate pentru setul de date înainte de a decide cu privire la pragurile de scor corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="db315-126">When [creating segments](segments.md) using affinity scores, review the distribution of affinity scores for your dataset before deciding on the appropriate score thresholds.</span></span> <span data-ttu-id="db315-127">De exemplu, un scor de afinitate de 10 poate fi considerat semnificativ într-un set de date care are un scor de afinitate cel mai mare de doar 25 pentru o anumită marcă sau interes.</span><span class="sxs-lookup"><span data-stu-id="db315-127">For example, an affinity score of 10 can be considered significant in a dataset that has a highest affinity score of only 25 for a given brand or interest.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="db315-128">Țări / regiuni acceptate</span><span class="sxs-lookup"><span data-stu-id="db315-128">Supported countries/regions</span></span>

<span data-ttu-id="db315-129">În prezent, acceptăm următoarele opțiuni de țară/regiune: Australia, Canada (engleză), Franța, Germania, Regatul Unit sau Statele Unite (engleză).</span><span class="sxs-lookup"><span data-stu-id="db315-129">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="db315-130">Pentru a selecta o țară, deschideți **Îmbogățirea mărcilor** sau **Îmbogățirea intereselor** și selectați **Schimbare** lângă **Țară/Regiune**.</span><span class="sxs-lookup"><span data-stu-id="db315-130">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="db315-131">În panoul **Setări de țară/regiune**, alegeți o opțiune și selectați **Aplicare**.</span><span class="sxs-lookup"><span data-stu-id="db315-131">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="db315-132">Implicații legate de selecția țării</span><span class="sxs-lookup"><span data-stu-id="db315-132">Implications related to country selection</span></span>

- <span data-ttu-id="db315-133">La [alegerea propriilor mărci](#define-your-brands-or-interests), vom oferi sugestii în funcție de țara/regiunea selectată.</span><span class="sxs-lookup"><span data-stu-id="db315-133">When [choosing your own brands](#define-your-brands-or-interests), we will provide suggestions based on the selected country/region.</span></span>

- <span data-ttu-id="db315-134">Când [alegeți o industrie](#define-your-brands-or-interests), vom identifica cele mai relevante mărci sau interese pe baza țării/regiunii selectate.</span><span class="sxs-lookup"><span data-stu-id="db315-134">When [choosing an industry](#define-your-brands-or-interests), we will identify the most relevant brands or interests based on the selected country/region.</span></span>

- <span data-ttu-id="db315-135">La [maparea câmpurilor dvs.](#map-your-fields), când câmpul Țară/Regiune nu este mapat, vom folosi datele Microsoft Graph din țara/regiunea selectată pentru a vă îmbogăți profilurile de clienți.</span><span class="sxs-lookup"><span data-stu-id="db315-135">When [mapping your fields](#map-your-fields), if the Country/Region field isn't mapped, we'll use Microsoft Graph data from the selected country/region to enrich your customer profiles.</span></span> <span data-ttu-id="db315-136">De asemenea, vom folosi respectiva selecție pentru a vă îmbogăți profilurile de clienți care nu au date de țară/regiune disponibile.</span><span class="sxs-lookup"><span data-stu-id="db315-136">We'll also use that selection to enrich your customer profiles that don't have country/region data available.</span></span>

- <span data-ttu-id="db315-137">La [îmbogățirea profilurilor](#refresh-enrichment), vom îmbogăți toate profilurile clienților pentru care avem date Microsoft Graph disponibile pentru mărcile și interesele selectate, inclusiv profilurile care nu sunt în țara/regiunea selectată.</span><span class="sxs-lookup"><span data-stu-id="db315-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we have Microsoft Graph data available for the selected brands and interests, including profiles that are not in the selected country/region.</span></span> <span data-ttu-id="db315-138">De exemplu, dacă ați selectat Germania, vom îmbogăți profilurile situate în Statele Unite dacă avem date Microsoft Graph disponibile pentru mărcile și interesele selectate din SUA.</span><span class="sxs-lookup"><span data-stu-id="db315-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have Microsoft Graph data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="db315-139">Configurați îmbogățirea</span><span class="sxs-lookup"><span data-stu-id="db315-139">Configure Enrichment</span></span>

<span data-ttu-id="db315-140">Configurarea îmbogățirii mărcilor sau intereselor constă în doi pași:</span><span class="sxs-lookup"><span data-stu-id="db315-140">Configuring brands or interests enrichment consists of two steps:</span></span>

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="db315-141">Definiți-vă brandurile sau interesele</span><span class="sxs-lookup"><span data-stu-id="db315-141">Define your brands or interests</span></span>

<span data-ttu-id="db315-142">Selectaţi una dintre următoarele opţiuni:</span><span class="sxs-lookup"><span data-stu-id="db315-142">Select one of the following options:</span></span>

- <span data-ttu-id="db315-143">**Industrie**: Sistemul identifică cele mai importante mărci sau interese relevante pentru industria dvs. și îmbogățește datele clientului cu acestea.</span><span class="sxs-lookup"><span data-stu-id="db315-143">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="db315-144">**Alegeți-vă una proprie**: Selectați până la cinci articole din lista mărcilor sau a intereselor care sunt cele mai relevante pentru organizația dvs.</span><span class="sxs-lookup"><span data-stu-id="db315-144">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="db315-145">Pentru a adăuga o marcă sau interes, introduceți-o în zona de intrare pentru a primi sugestii bazate pe termeni potriviți.</span><span class="sxs-lookup"><span data-stu-id="db315-145">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="db315-146">Dacă nu enumerăm o marcă sau un interes pe care îl căutați, trimiteți-ne feedback folosind legătura **Sugerați**.</span><span class="sxs-lookup"><span data-stu-id="db315-146">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="db315-147">Mapați câmpurile</span><span class="sxs-lookup"><span data-stu-id="db315-147">Map your fields</span></span>

<span data-ttu-id="db315-148">Mapați câmpurile de la entitatea dvs. de client unificată la cel puțin două atribute pentru a defini segmentul demografic pe care doriți să îl utilizați pentru îmbogățirea datelor clientului dvs.</span><span class="sxs-lookup"><span data-stu-id="db315-148">Map fields from your unified customer entity to at least two attributes to define the demographic segment you want us to use for enriching your customer data.</span></span> <span data-ttu-id="db315-149">Selectați **Editați** pentru a defini maparea câmpurilor și selectați **Aplicare** când ați terminat.</span><span class="sxs-lookup"><span data-stu-id="db315-149">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="db315-150">Selectați **Salvați** pentru a finaliza maparea câmpului.</span><span class="sxs-lookup"><span data-stu-id="db315-150">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="db315-151">Următoarele formate și valori sunt acceptate, valorile nu sunt sensibile la litere mari și mici:</span><span class="sxs-lookup"><span data-stu-id="db315-151">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="db315-152">**Data de naștere**: Recomandăm ca data nașterii să fie transformată în tip DateTime în timpul ingestiei de date.</span><span class="sxs-lookup"><span data-stu-id="db315-152">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="db315-153">Alternativ, poate fi un șir în format [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format „aaaa-LL-zz” sau „aaaa-LL-zzTOO:mm:ssZ”.</span><span class="sxs-lookup"><span data-stu-id="db315-153">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="db315-154">**Sex**: Bărbat, Femeie, Necunoscut</span><span class="sxs-lookup"><span data-stu-id="db315-154">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="db315-155">**Cod poștal**: Coduri poștale de cinci cifre pentru SUA, cod poștal standard în restul locațiilor</span><span class="sxs-lookup"><span data-stu-id="db315-155">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="db315-156">**Oraș**: Numele orașului în engleză</span><span class="sxs-lookup"><span data-stu-id="db315-156">**City**: City name in English</span></span>
- <span data-ttu-id="db315-157">**Stat/Provincie**: Abreviere cu două litere pentru SUA și Canada.</span><span class="sxs-lookup"><span data-stu-id="db315-157">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="db315-158">Abreviere cu două sau trei litere pentru Australia.</span><span class="sxs-lookup"><span data-stu-id="db315-158">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="db315-159">Nu se aplică Franței, Germaniei sau Regatului Unit.</span><span class="sxs-lookup"><span data-stu-id="db315-159">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="db315-160">**Țară/regiune**:</span><span class="sxs-lookup"><span data-stu-id="db315-160">**Country/Region**:</span></span>

  - <span data-ttu-id="db315-161">SUA: Statele Unite ale Americii, Statele Unite, SUA, SUA, America</span><span class="sxs-lookup"><span data-stu-id="db315-161">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="db315-162">CA: Canada, CA</span><span class="sxs-lookup"><span data-stu-id="db315-162">CA: Canada, CA</span></span>
  - <span data-ttu-id="db315-163">GB: Regatul Unit, UK, Marea Britanie, GB, Regatul Unit al Marii Britanii și Irlandei de Nord, Regatul Unit al Marii Britanii</span><span class="sxs-lookup"><span data-stu-id="db315-163">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="db315-164">AU: Australia, AU, Commonwealth-ul Australiei</span><span class="sxs-lookup"><span data-stu-id="db315-164">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="db315-165">FR: Franța, FR, Republica Franceză</span><span class="sxs-lookup"><span data-stu-id="db315-165">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="db315-166">DE: Germania, German, Deutschland, Allemagne, DE, Republica Federală Germania, Republica Germania</span><span class="sxs-lookup"><span data-stu-id="db315-166">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="refresh-enrichment"></a><span data-ttu-id="db315-167">Reîmprospătare îmbogățire</span><span class="sxs-lookup"><span data-stu-id="db315-167">Refresh enrichment</span></span>

<span data-ttu-id="db315-168">Rulați îmbogățirea după configurarea mărcilor, a intereselor și a mapării câmpului pentru demografie.</span><span class="sxs-lookup"><span data-stu-id="db315-168">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="db315-169">Pentru a începe procesul, selectați **Rulare** pe pagina de configurare a mărcii sau a intereselor.</span><span class="sxs-lookup"><span data-stu-id="db315-169">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="db315-170">În plus, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei actualizări programate.</span><span class="sxs-lookup"><span data-stu-id="db315-170">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="db315-171">În funcție de dimensiunea datelor clientului dvs., este posibil să dureze câteva minute pentru a finaliza o îmbogățire.</span><span class="sxs-lookup"><span data-stu-id="db315-171">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="db315-172">Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese.</span><span class="sxs-lookup"><span data-stu-id="db315-172">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="db315-173">În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="db315-173">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="db315-174">Puteți selecta starea unui proces pentru a vedea detalii despre evoluția întregii lucrări.</span><span class="sxs-lookup"><span data-stu-id="db315-174">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="db315-175">După selectarea **Vizualizare detalii** pentru una dintre sarcinile jobului, găsiți informații suplimentare: timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate sarcinii.</span><span class="sxs-lookup"><span data-stu-id="db315-175">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="db315-176">Rezultate de îmbogățire</span><span class="sxs-lookup"><span data-stu-id="db315-176">Enrichment results</span></span>

<span data-ttu-id="db315-177">După executarea procesului de îmbogățire, accesați **Îmbogățirile mele** pentru a analiza numărul total de clienți îmbogățiți și o defalcare a mărcilor sau a intereselor în profilurile de clienți îmbogățite.</span><span class="sxs-lookup"><span data-stu-id="db315-177">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Previzualizarea rezultatelor după executarea procesului de îmbogățire":::

<span data-ttu-id="db315-179">Verificați datele îmbogățite selectând **Vizualizați date îmbogățite** în grafic.</span><span class="sxs-lookup"><span data-stu-id="db315-179">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="db315-180">Datele îmbogățite pentru mărci se includ în entitatea **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="db315-180">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="db315-181">Datele pentru interese sunt în entitatea **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="db315-181">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="db315-182">De asemenea, veți găsi aceste entități listate în grupul **Îmbogățire** în **Date** > **Entități**.</span><span class="sxs-lookup"><span data-stu-id="db315-182">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="db315-183">Consultați datele de îmbogățire de pe cardul clientului</span><span class="sxs-lookup"><span data-stu-id="db315-183">See enrichment data on the customer card</span></span>

<span data-ttu-id="db315-184">Afinitățile de marcă și interes pot fi, de asemenea, vizualizate pe carduri individuale ale clienților.</span><span class="sxs-lookup"><span data-stu-id="db315-184">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="db315-185">Accesați **Clienți** și selectați un profil de client.</span><span class="sxs-lookup"><span data-stu-id="db315-185">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="db315-186">În cardul de client, veți găsi diagrame pentru mărcile sau interesele pentru care persoanele din profilul demografic al clientului au afinitate.</span><span class="sxs-lookup"><span data-stu-id="db315-186">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Card de client cu date îmbogățite":::

## <a name="next-steps"></a><span data-ttu-id="db315-188">Următorii pași</span><span class="sxs-lookup"><span data-stu-id="db315-188">Next steps</span></span>

<span data-ttu-id="db315-189">Creați în plus față de datele îmbogățite ale clienților.</span><span class="sxs-lookup"><span data-stu-id="db315-189">Build on top of your enriched customer data.</span></span> <span data-ttu-id="db315-190">Creați [Segmente](segments.md), [Măsuri](measures.md) și chiar [exportați datele](export-destinations.md) pentru a oferi experiențe personalizate clienților.</span><span class="sxs-lookup"><span data-stu-id="db315-190">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>