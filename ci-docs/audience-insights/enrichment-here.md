---
title: Îmbogățire cu îmbogățiri terță parte HERE Technologies
description: Informații generale despre îmbogățirea terță parte HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 258e37de9d9685d9ebc30b3c6b8d238d583431b4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269529"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="ed1ff-103">Îmbogățirea profilurilor clienților cu HERE Technologies (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="ed1ff-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="ed1ff-104">HERE Technologies este o companie de platformă de localizare care oferă date și servicii centrate pe locație.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="ed1ff-105">Cu serviciile de îmbogățire a datelor de la HERE Technologies, puteți construi o înțelegere mai precisă a locației clienților dvs. cu normalizarea adreselor, extragerea latitudinii și longitudinii și multe altele.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ed1ff-106">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="ed1ff-106">Prerequisites</span></span>

<span data-ttu-id="ed1ff-107">Pentru a configura îmbogățirile HERE Technologies, trebuie îndeplinite următoarele condiții prealabile:</span><span class="sxs-lookup"><span data-stu-id="ed1ff-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="ed1ff-108">Aveți un abonament activ HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="ed1ff-109">Pentru a obține un abonament, puteți să vă [înscrieți aici](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) sau [contactați HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direct.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="ed1ff-110">Aflați mai multe despre îmbogățirea locației HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="ed1ff-111">Aveți cheia API HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="ed1ff-112">Aveți permisiuni de [Administrator](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="ed1ff-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="ed1ff-113">Configurație</span><span class="sxs-lookup"><span data-stu-id="ed1ff-113">Configuration</span></span>

1. <span data-ttu-id="ed1ff-114">Accesați **Date** > **Îmbogățire**.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="ed1ff-115">Pe dala HERE Technologies, selectați **Doresc îmbogățirea datelor**.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ed1ff-116">![Dală HERE Technologies](media/HERE-tile.png "Dală HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="ed1ff-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="ed1ff-117">Introduceți o **cheie API HERE Technologies** activă.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="ed1ff-118">Analizați și acordați-vă consimțământul pentru **Confidențialitatea și conformitatea datelor** prin selectarea casetei de selectare **Sunt de acord**.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="ed1ff-119">Confirmați ambele intrări selectând **Conectați-vă la HERE**.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="ed1ff-120">Selectați **Adăugați date** și alegeți **Set de date client** doriți să îmbogățiți cu date de localizare de la HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="ed1ff-121">Puteți selecta entitatea **Client** pentru a vă îmbogăți toate profilurile de clienți sau selectați o entitate de segment pentru a îmbogăți numai profilurile de clienți din acel segment.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Captură de ecran atunci când alegeți setul de date pentru clienți.":::

1. <span data-ttu-id="ed1ff-123">Alegeți dacă doriți să mapați câmpurile la adresa primară și/sau secundară.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="ed1ff-124">Puteți specifica o mapare a câmpului pentru ambele adrese (de exemplu, o adresă de domiciliu și una pentru companie) și puteți îmbogăți profilurile pentru ambele adrese separat.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="ed1ff-125">Selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-125">Select **Next**.</span></span>

1. <span data-ttu-id="ed1ff-126">Definiți ce câmpuri din profilurile dvs. unificate ar trebui utilizate pentru a căuta date de locație potrivite de la HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="ed1ff-127">Câmpurile **Stradă 1** și **Cod poștal** sunt obligatorii pentru adresa primară și/sau secundară selectată.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="ed1ff-128">Pentru o precizie mai mare a potrivirii, pot fi adăugate mai multe câmpuri.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ed1ff-129">![Pagina de configurare pentru îmbogățirii HERE Technologies](media/enrichment-HERE-configuration.png "Pagina de configurare pentru îmbogățirii HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="ed1ff-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="ed1ff-130">Selectați **Aplicare** pentru a finaliza maparea câmpului.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="ed1ff-131">Rezultate de îmbogățire</span><span class="sxs-lookup"><span data-stu-id="ed1ff-131">Enrichment results</span></span>

<span data-ttu-id="ed1ff-132">Pentru a începe procesul de îmbogățire, selectați **Rulare** din bara de comenzi.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="ed1ff-133">De asemenea, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei [reîmprospătări programate](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ed1ff-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ed1ff-134">Timpul de procesare va depinde de mărimea datelor clienților dvs. și de timpii de răspuns API de la HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="ed1ff-135">După finalizarea procesului de îmbogățire, puteți consulta datele din profilurile clienților nou îmbogățite din **Îmbogățirile mele**.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="ed1ff-136">În plus, veți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="ed1ff-137">Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ed1ff-138">Pașii următori</span><span class="sxs-lookup"><span data-stu-id="ed1ff-138">Next steps</span></span>

<span data-ttu-id="ed1ff-139">Creați în plus față de datele îmbogățite ale clienților.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="ed1ff-140">Creați [segmente](segments.md), [măsuri](measures.md) și chiar [exportați datele](export-destinations.md) pentru a oferi experiențe personalizate clienților.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ed1ff-141">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="ed1ff-141">Data privacy and compliance</span></span>

<span data-ttu-id="ed1ff-142">Când activați Dynamics 365 Customer Insights pentru a transmite date către HERE Technologies, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ed1ff-143">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că HERE Technologies îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ed1ff-144">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ed1ff-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ed1ff-145">Administratorul Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="ed1ff-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]