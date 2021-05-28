---
title: Îmbogățirea îmbunătățirii adreselor
description: Îmbogățiți și normalizați informațiile de adresă ale profilurilor clienților cu modelele Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965593"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="e5e49-103">Îmbogățirea profilurilor clienților cu adrese îmbunătățite</span><span class="sxs-lookup"><span data-stu-id="e5e49-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="e5e49-104">Adresele din datele dvs. pot fi nestructurate, incomplete sau incorecte.</span><span class="sxs-lookup"><span data-stu-id="e5e49-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="e5e49-105">Utilizați modelele Microsoft pentru a vă normaliza și îmbogăți adresele în [Formatul Common Data Model](/common-data-model/schema/core/applicationcommon/address) pentru o mai bună acuratețe și informații.</span><span class="sxs-lookup"><span data-stu-id="e5e49-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="e5e49-106">Cum îmbunătățim adresele</span><span class="sxs-lookup"><span data-stu-id="e5e49-106">How we enhance addresses</span></span>

<span data-ttu-id="e5e49-107">Modelul nostru trece printr-un proces în doi pași pentru a îmbunătăți o adresă.</span><span class="sxs-lookup"><span data-stu-id="e5e49-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="e5e49-108">În primul rând, analizează adresa pentru a identifica componentele sale și le plasează într-un format structurat.</span><span class="sxs-lookup"><span data-stu-id="e5e49-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="e5e49-109">Apoi, folosim inteligența artificială pentru a corecta, completa și standardiza valorile din adresă.</span><span class="sxs-lookup"><span data-stu-id="e5e49-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="e5e49-110">Exemplu</span><span class="sxs-lookup"><span data-stu-id="e5e49-110">Example</span></span>

<span data-ttu-id="e5e49-111">Informațiile despre adresă pot fi într-un format non-standard și să conțină erori de ortografie.</span><span class="sxs-lookup"><span data-stu-id="e5e49-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="e5e49-112">Modelul poate rezolva aceste probleme și poate crea adrese consistente în profilurile unificate ale clienților.</span><span class="sxs-lookup"><span data-stu-id="e5e49-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="e5e49-113">Limitări</span><span class="sxs-lookup"><span data-stu-id="e5e49-113">Limitations</span></span>

<span data-ttu-id="e5e49-114">Adresele îmbunătățite funcționează numai cu valorile care există deja în datele de adresă ingerate.</span><span class="sxs-lookup"><span data-stu-id="e5e49-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="e5e49-115">Modelul nu:</span><span class="sxs-lookup"><span data-stu-id="e5e49-115">The model doesn't:</span></span> 

1. <span data-ttu-id="e5e49-116">Verificî dacă adresa este o adresă validă.</span><span class="sxs-lookup"><span data-stu-id="e5e49-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="e5e49-117">Verifică dacă oricare dintre valori, cum ar fi codurile poștale sau numele străzilor, sunt valide.</span><span class="sxs-lookup"><span data-stu-id="e5e49-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="e5e49-118">Schimbă valorile pe care nu le recunoaște.</span><span class="sxs-lookup"><span data-stu-id="e5e49-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="e5e49-119">Modelul utilizează tehnici bazate pe învățarea automată pentru a îmbunătăți adresele.</span><span class="sxs-lookup"><span data-stu-id="e5e49-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="e5e49-120">În timp ce aplicăm un prag de încredere ridicat pentru când modelul modifică o valoare de intrare, la fel ca în cazul oricărui model bazat pe ML, precizia 100% nu este garantată.</span><span class="sxs-lookup"><span data-stu-id="e5e49-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="e5e49-121">Țări sau regiuni sprijinite</span><span class="sxs-lookup"><span data-stu-id="e5e49-121">Supported countries or regions</span></span>

<span data-ttu-id="e5e49-122">În prezent, sprijinim adresele îmbogățitoare din aceste țări sau regiuni:</span><span class="sxs-lookup"><span data-stu-id="e5e49-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="e5e49-123">Australia</span><span class="sxs-lookup"><span data-stu-id="e5e49-123">Australia</span></span>
- <span data-ttu-id="e5e49-124">Canada</span><span class="sxs-lookup"><span data-stu-id="e5e49-124">Canada</span></span>
- <span data-ttu-id="e5e49-125">Regatul Unit</span><span class="sxs-lookup"><span data-stu-id="e5e49-125">United Kingdom</span></span>
- <span data-ttu-id="e5e49-126">Statele Unite ale Americii</span><span class="sxs-lookup"><span data-stu-id="e5e49-126">United States</span></span>

<span data-ttu-id="e5e49-127">Adresele trebuie să conțină o valoare a țării/regiunii.</span><span class="sxs-lookup"><span data-stu-id="e5e49-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="e5e49-128">Nu procesăm adrese pentru țări sau regiuni care nu sunt acceptate și adrese care nu au furnizat nicio țară sau regiune.</span><span class="sxs-lookup"><span data-stu-id="e5e49-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="e5e49-129">Configurați îmbogățirea</span><span class="sxs-lookup"><span data-stu-id="e5e49-129">Configure the enrichment</span></span>

1. <span data-ttu-id="e5e49-130">Accesați **Date** > **Îmbogățire**.</span><span class="sxs-lookup"><span data-stu-id="e5e49-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="e5e49-131">Selectați **Îmbogățire date** pe dala **Adrese îmbunătățite**.</span><span class="sxs-lookup"><span data-stu-id="e5e49-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Captură de ecran a plăcii Adrese îmbunătățite.":::

1. <span data-ttu-id="e5e49-133">Selectați **Set de date client** și alegeți entitatea care conține adresele pe care doriți să le îmbogățiți.</span><span class="sxs-lookup"><span data-stu-id="e5e49-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="e5e49-134">Puteți selecta entitatea *Client* pentru a îmbogăți adrese în toate profilurile dvs. de clienți sau selectați o entitate de segment pentru a îmbogăți adresele numai în profilurile de clienți din acel segment.</span><span class="sxs-lookup"><span data-stu-id="e5e49-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="e5e49-135">Selectați formatatul adreselor în setul de date al dvs.</span><span class="sxs-lookup"><span data-stu-id="e5e49-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="e5e49-136">Alegeți **Adresă cu un singur atribut** dacă adresele din datele dvs. utilizează un singur câmp.</span><span class="sxs-lookup"><span data-stu-id="e5e49-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="e5e49-137">Alegeți **Adresă cu atribute multiple** dacă adresele din datele dvs. utilizează mai mult de un singur câmp de date.</span><span class="sxs-lookup"><span data-stu-id="e5e49-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e5e49-138">Țara/regiunea este obligatorie atât în adresa cu atribut unic, cât și în adresa cu atribut multiplu.</span><span class="sxs-lookup"><span data-stu-id="e5e49-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="e5e49-139">Adresele care nu conțin valori valabile sau acceptate de țară/regiune nu vor fi îmbogățite</span><span class="sxs-lookup"><span data-stu-id="e5e49-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="e5e49-140">Mapați câmpurile de adresă de la entitatea client unificată.</span><span class="sxs-lookup"><span data-stu-id="e5e49-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Pagina îmbunătățită de mapare a câmpului de adrese.":::

1. <span data-ttu-id="e5e49-142">Selectați **Următorul** pentru a completa maparea câmpului.</span><span class="sxs-lookup"><span data-stu-id="e5e49-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="e5e49-143">Furnizați un nume pentru îmbogățire și entitatea de ieșire.</span><span class="sxs-lookup"><span data-stu-id="e5e49-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="e5e49-144">Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.</span><span class="sxs-lookup"><span data-stu-id="e5e49-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="e5e49-145">Rezultate de îmbogățire</span><span class="sxs-lookup"><span data-stu-id="e5e49-145">Enrichment results</span></span>

<span data-ttu-id="e5e49-146">Pentru a începe procesul de îmbogățire, selectați **Rulare** din bara de comenzi.</span><span class="sxs-lookup"><span data-stu-id="e5e49-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="e5e49-147">De asemenea, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei [reîmprospătări programate](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e5e49-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e5e49-148">Timpul de procesare depinde de dimensiunea datelor clienților dvs.</span><span class="sxs-lookup"><span data-stu-id="e5e49-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="e5e49-149">După finalizarea procesului de îmbogățire, puteți consulta datele din profilurile clienților nou îmbogățite din **Îmbogățirile mele**.</span><span class="sxs-lookup"><span data-stu-id="e5e49-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="e5e49-150">În plus, veți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.</span><span class="sxs-lookup"><span data-stu-id="e5e49-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="e5e49-151">Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.</span><span class="sxs-lookup"><span data-stu-id="e5e49-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e5e49-152">Pașii următori</span><span class="sxs-lookup"><span data-stu-id="e5e49-152">Next steps</span></span>

<span data-ttu-id="e5e49-153">Creați în plus față de datele îmbogățite ale clienților.</span><span class="sxs-lookup"><span data-stu-id="e5e49-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e5e49-154">Creați [segmente](segments.md), [măsuri](measures.md) și chiar [exportați datele](export-destinations.md) pentru a oferi experiențe personalizate clienților.</span><span class="sxs-lookup"><span data-stu-id="e5e49-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
