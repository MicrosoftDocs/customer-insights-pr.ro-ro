---
title: Îmbogățirea HERE Technologies de terță parte
description: Informații generale despre îmbogățirea terță parte HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305309"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="57ae9-103">Îmbogățirea profilurilor clienților cu HERE Technologies (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="57ae9-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="57ae9-104">HERE Technologies este o companie de platformă de localizare care oferă date și servicii centrate pe locație.</span><span class="sxs-lookup"><span data-stu-id="57ae9-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="57ae9-105">Cu serviciile de îmbogățire a datelor de la HERE Technologies, puteți construi o înțelegere mai precisă a locației clienților dvs. cu normalizarea adreselor, extragerea latitudinii și longitudinii și multe altele.</span><span class="sxs-lookup"><span data-stu-id="57ae9-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="57ae9-106">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="57ae9-106">Prerequisites</span></span>

<span data-ttu-id="57ae9-107">Pentru a configura îmbogățirile HERE Technologies, trebuie îndeplinite următoarele condiții prealabile:</span><span class="sxs-lookup"><span data-stu-id="57ae9-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="57ae9-108">Aveți un abonament activ HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="57ae9-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="57ae9-109">Pentru a obține un abonament, puteți să vă [înscrieți aici](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) sau [contactați HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direct.</span><span class="sxs-lookup"><span data-stu-id="57ae9-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="57ae9-110">Aflați mai multe despre îmbogățirea locației HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="57ae9-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="57ae9-111">O [conexiune](connections.md) HERE este disponibilă *sau* aveți permisiuni de [administrator](permissions.md#administrator) și cheia API HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="57ae9-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="57ae9-112">Configurați îmbogățirea</span><span class="sxs-lookup"><span data-stu-id="57ae9-112">Configure the enrichment</span></span>

1. <span data-ttu-id="57ae9-113">Accesați **Date** > **Îmbogățire**.</span><span class="sxs-lookup"><span data-stu-id="57ae9-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="57ae9-114">Selectați **Doresc îmbogățirea datelor** pe dala HERE Technologies și selectați **Începeți**.</span><span class="sxs-lookup"><span data-stu-id="57ae9-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="57ae9-115">![Dală HERE Technologies](media/HERE-tile.png "Dală HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="57ae9-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="57ae9-116">Selectați o [conexiune](connections.md) din lista derulantă.</span><span class="sxs-lookup"><span data-stu-id="57ae9-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="57ae9-117">Contactați un administrator dacă nu este disponibilă nicio conexiune.</span><span class="sxs-lookup"><span data-stu-id="57ae9-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="57ae9-118">Dacă sunteți administrator, puteți crea o conexiune selectând **Adăugați conexiune**.</span><span class="sxs-lookup"><span data-stu-id="57ae9-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="57ae9-119">Alegeți **HERE Technologies** din lista derulantă.</span><span class="sxs-lookup"><span data-stu-id="57ae9-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="57ae9-120">Selectați **Conectați-vă la HERE Technologies** pentru a confirma selecția.</span><span class="sxs-lookup"><span data-stu-id="57ae9-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="57ae9-121">Selectați **Următorul** și alegeți **Set de date client** pe care doriți să le îmbogățiți cu date de localizare de la HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="57ae9-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="57ae9-122">Puteți selecta entitatea **Client** pentru a vă îmbogăți toate profilurile de clienți sau selectați o entitate de segment pentru a îmbogăți numai profilurile de clienți din acel segment.</span><span class="sxs-lookup"><span data-stu-id="57ae9-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Captură de ecran atunci când alegeți setul de date pentru clienți.":::

1. <span data-ttu-id="57ae9-124">Alegeți dacă doriți să mapați câmpurile la adresa primară și/sau secundară.</span><span class="sxs-lookup"><span data-stu-id="57ae9-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="57ae9-125">Puteți specifica o mapare a câmpului pentru ambele adrese și puteți îmbogăți profilurile pentru ambele adrese separat.</span><span class="sxs-lookup"><span data-stu-id="57ae9-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="57ae9-126">De exemplu, dacă există o adresă de domiciliu și a companiei.</span><span class="sxs-lookup"><span data-stu-id="57ae9-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="57ae9-127">Selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="57ae9-127">Select **Next**.</span></span>

1. <span data-ttu-id="57ae9-128">Definiți ce câmpuri din profilurile dvs. unificate ar trebui utilizate pentru a căuta date de locație potrivite de la HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="57ae9-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="57ae9-129">Câmpurile **Stradă 1** și **Cod poștal** sunt obligatorii pentru adresa primară și/sau secundară selectată.</span><span class="sxs-lookup"><span data-stu-id="57ae9-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="57ae9-130">Pentru o precizie mai mare a potrivirii, pot fi adăugate mai multe câmpuri.</span><span class="sxs-lookup"><span data-stu-id="57ae9-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="57ae9-131">![Pagina de configurare pentru îmbogățirii HERE Technologies](media/enrichment-HERE-configuration.png "Pagina de configurare pentru îmbogățirii HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="57ae9-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="57ae9-132">Selectați **Următorul** pentru a completa maparea câmpului.</span><span class="sxs-lookup"><span data-stu-id="57ae9-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="57ae9-133">Oferiți un nume pentru îmbogățire.</span><span class="sxs-lookup"><span data-stu-id="57ae9-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="57ae9-134">Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.</span><span class="sxs-lookup"><span data-stu-id="57ae9-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="57ae9-135">Configurați conexiunea pentru HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="57ae9-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="57ae9-136">Trebuie să fiți administrator pentru a configura conexiunile.</span><span class="sxs-lookup"><span data-stu-id="57ae9-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="57ae9-137">Selectați **Adăugați conexiune** la configurarea unei îmbogățiri *sau* mergeți la **Administrator** > **Conexiuni** și selectați **Configurare** pe dala HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="57ae9-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="57ae9-138">Introduceți un nume pentru conexiune în caseta **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="57ae9-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="57ae9-139">Furnizați o cheie API HERE Technologies validă.</span><span class="sxs-lookup"><span data-stu-id="57ae9-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="57ae9-140">Examinați și furnizați consimțământul pentru **Confidențialitatea și respectarea datelor** prin selectarea **Sunt de acord**.</span><span class="sxs-lookup"><span data-stu-id="57ae9-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="57ae9-141">Selectați **Verificare** pentru a valida configurația.</span><span class="sxs-lookup"><span data-stu-id="57ae9-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="57ae9-142">După finalizarea verificării, selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="57ae9-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="57ae9-143">![Pagina de configurare a conexiunii HERE Technologies](media/enrichment-HERE-connection.png "Pagina de configurare a conexiunii HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="57ae9-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="57ae9-144">Rezultate de îmbogățire</span><span class="sxs-lookup"><span data-stu-id="57ae9-144">Enrichment results</span></span>

<span data-ttu-id="57ae9-145">Pentru a începe procesul de îmbogățire, selectați **Rulare** din bara de comenzi.</span><span class="sxs-lookup"><span data-stu-id="57ae9-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="57ae9-146">De asemenea, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei [reîmprospătări programate](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="57ae9-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="57ae9-147">Timpul de procesare va depinde de mărimea datelor clienților dvs. și de timpii de răspuns API de la HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="57ae9-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="57ae9-148">După finalizarea procesului de îmbogățire, puteți consulta datele din profilurile clienților nou îmbogățite din **Îmbogățirile mele**.</span><span class="sxs-lookup"><span data-stu-id="57ae9-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="57ae9-149">În plus, veți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.</span><span class="sxs-lookup"><span data-stu-id="57ae9-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="57ae9-150">Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.</span><span class="sxs-lookup"><span data-stu-id="57ae9-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="57ae9-151">Pașii următori</span><span class="sxs-lookup"><span data-stu-id="57ae9-151">Next steps</span></span>

<span data-ttu-id="57ae9-152">Creați în plus față de datele îmbogățite ale clienților.</span><span class="sxs-lookup"><span data-stu-id="57ae9-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="57ae9-153">Creați [segmente](segments.md) și [măsuri](measures.md), și chiar [exportați datele](export-destinations.md) pentru a oferi clienților dvs. experiențe particularizate.</span><span class="sxs-lookup"><span data-stu-id="57ae9-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="57ae9-154">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="57ae9-154">Data privacy and compliance</span></span>

<span data-ttu-id="57ae9-155">Când activați Dynamics 365 Customer Insights pentru a transmite date către HERE Technologies, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="57ae9-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="57ae9-156">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că HERE Technologies îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="57ae9-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="57ae9-157">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="57ae9-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="57ae9-158">Administratorul dvs. Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="57ae9-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
