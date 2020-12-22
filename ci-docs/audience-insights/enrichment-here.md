---
title: Îmbogățire cu îmbogățiri terță parte HERE Technologies
description: Informații generale despre îmbogățirea terță parte HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668693"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="2e6f7-103">Îmbogățirea profilurilor clienților cu HERE Technologies (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="2e6f7-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="2e6f7-104">HERE Technologies este o companie de platformă de localizare care oferă date și servicii centrate pe locație.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="2e6f7-105">Cu serviciile de îmbogățire a datelor de la HERE Technologies, puteți construi o înțelegere mai precisă a locației clienților dvs. cu normalizarea adreselor, extragerea latitudinii și longitudinii și multe altele.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2e6f7-106">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="2e6f7-106">Prerequisites</span></span>

<span data-ttu-id="2e6f7-107">Pentru a configura îmbogățirile HERE Technologies, trebuie îndeplinite următoarele condiții prealabile:</span><span class="sxs-lookup"><span data-stu-id="2e6f7-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="2e6f7-108">Aveți un abonament activ HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="2e6f7-109">Pentru a obține un abonament, puteți să vă [înscrieți aici](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) sau [contactați HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direct.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="2e6f7-110">Aflați mai multe despre îmbogățirea locației HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="2e6f7-111">Aveți cheia API HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="2e6f7-112">Aveți permisiuni de [Administrator](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="2e6f7-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="2e6f7-113">Configurație</span><span class="sxs-lookup"><span data-stu-id="2e6f7-113">Configuration</span></span>

1. <span data-ttu-id="2e6f7-114">Accesați **Date** > **Îmbogățire**.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="2e6f7-115">Pe dala HERE Technologies, selectați **Doresc îmbogățirea datelor**.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2e6f7-116">![Dală HERE Technologies](media/HERE-tile.png "Dală HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="2e6f7-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="2e6f7-117">Introduceți o **cheie API HERE Technologies** activă.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="2e6f7-118">Analizați și acordați-vă consimțământul pentru **Confidențialitatea și conformitatea datelor** prin selectarea casetei de selectare **Sunt de acord**.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="2e6f7-119">Confirmați ambele intrări selectând **Conectați-vă la HERE**.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1. <span data-ttu-id="2e6f7-120">Selectați **Adăugare date** și alegeți dacă doriți să mapați câmpurile la adresa primară și/sau secundară.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-120">Select **Add data** and choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="2e6f7-121">Puteți specifica o mapare a câmpului pentru ambele adrese (de exemplu, o adresă de domiciliu și una pentru companie) și puteți îmbogăți profilurile pentru ambele adrese separat.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-121">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="2e6f7-122">Selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-122">Select **Next**.</span></span>

1. <span data-ttu-id="2e6f7-123">Definiți ce câmpuri din profilurile dvs. unificate ar trebui utilizate pentru a căuta date de locație potrivite de la HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-123">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="2e6f7-124">Câmpurile **Stradă 1** și **Cod poștal** sunt obligatorii pentru adresa primară și/sau secundară selectată.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-124">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="2e6f7-125">Pentru o precizie mai mare a potrivirii, pot fi adăugate mai multe câmpuri.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-125">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2e6f7-126">![Pagina de configurare pentru îmbogățirii HERE Technologies](media/enrichment-HERE-configuration.png "Pagina de configurare pentru îmbogățirii HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="2e6f7-126">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="2e6f7-127">Selectați **Aplicare** pentru a finaliza maparea câmpului.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-127">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="2e6f7-128">Rezultate de îmbogățire</span><span class="sxs-lookup"><span data-stu-id="2e6f7-128">Enrichment results</span></span>

<span data-ttu-id="2e6f7-129">Pentru a începe procesul de îmbogățire, selectați **Rulare** din bara de comenzi.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-129">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="2e6f7-130">De asemenea, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei [reîmprospătări programate](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2e6f7-130">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2e6f7-131">Timpul de procesare va depinde de mărimea datelor clienților dvs. și de timpii de răspuns API de la HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-131">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="2e6f7-132">După finalizarea procesului de îmbogățire, puteți consulta datele din profilurile clienților nou îmbogățite din **Îmbogățirile mele**.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-132">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="2e6f7-133">În plus, veți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-133">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="2e6f7-134">Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-134">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2e6f7-135">Pașii următori</span><span class="sxs-lookup"><span data-stu-id="2e6f7-135">Next steps</span></span>

<span data-ttu-id="2e6f7-136">Creați în plus față de datele îmbogățite ale clienților.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="2e6f7-137">Creați [segmente](segments.md), [măsuri](measures.md) și chiar [exportați datele](export-destinations.md) pentru a oferi experiențe personalizate clienților.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2e6f7-138">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="2e6f7-138">Data privacy and compliance</span></span>

<span data-ttu-id="2e6f7-139">Când activați Dynamics 365 Customer Insights pentru a transmite date către HERE Technologies, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-139">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2e6f7-140">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că HERE Technologies îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2e6f7-141">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2e6f7-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2e6f7-142">Administratorul Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="2e6f7-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
