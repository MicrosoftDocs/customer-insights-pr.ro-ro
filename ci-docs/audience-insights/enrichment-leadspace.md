---
title: Îmbogățirea profilurilor companiei cu îmbogățirea terță parte Leadspace
description: Informații generale despre îmbogățirea terță parte Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305217"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="39f7e-103">Îmbogățirea profilurilor companiei cu Leadspace (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="39f7e-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="39f7e-104">Leadspace este o companie de știință a datelor care oferă o platformă de date pentru clienți B2B.</span><span class="sxs-lookup"><span data-stu-id="39f7e-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="39f7e-105">Aceasta permite clienților cu profiluri de clienți unificate pentru companii să-și îmbogățească datele.</span><span class="sxs-lookup"><span data-stu-id="39f7e-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="39f7e-106">Îmbogățirile includ mai multe atribute, cum ar fi dimensiunea companiei, locația, industria și multe altele.</span><span class="sxs-lookup"><span data-stu-id="39f7e-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="39f7e-107">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="39f7e-107">Prerequisites</span></span>

<span data-ttu-id="39f7e-108">Pentru a configura Leadspace, trebuie îndeplinite următoarele cerințe preliminare:</span><span class="sxs-lookup"><span data-stu-id="39f7e-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="39f7e-109">Aveți o licență Leadspace activă.</span><span class="sxs-lookup"><span data-stu-id="39f7e-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="39f7e-110">Aveți [profiluri de clienți unificate](customer-profiles.md) pentru companii.</span><span class="sxs-lookup"><span data-stu-id="39f7e-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="39f7e-111">O conexiune Leadspace a fost deja configurată de un administrator sau aveți permisiuni de [administrator](permissions.md#administrator) și „cheia perpetuă" (denumită **Tokenul Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="39f7e-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="39f7e-112">Luați legătura în mod direct cu [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) pentru detalii despre produsul lor.</span><span class="sxs-lookup"><span data-stu-id="39f7e-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="39f7e-113">Configurați îmbogățirea</span><span class="sxs-lookup"><span data-stu-id="39f7e-113">Configure the enrichment</span></span>

1. <span data-ttu-id="39f7e-114">În Detalii despre audiență, accesați **Date** > **Îmbogățire**.</span><span class="sxs-lookup"><span data-stu-id="39f7e-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="39f7e-115">Selectați **Doresc îmbogățirea datelor** pe dala Leadspace și selectați **Începeți**.</span><span class="sxs-lookup"><span data-stu-id="39f7e-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captură de ecran a dalei Leadspace.":::

1. <span data-ttu-id="39f7e-117">Selectați o [conexiune](connections.md) din lista derulantă.</span><span class="sxs-lookup"><span data-stu-id="39f7e-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="39f7e-118">Contactați un administrator dacă nu este disponibilă nicio conexiune.</span><span class="sxs-lookup"><span data-stu-id="39f7e-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="39f7e-119">Dacă sunteți administrator, puteți crea o conexiune selectând **Adăugați conexiune** și alegând **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="39f7e-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="39f7e-120">Selectați **Conectați-vă la Leadspace** pentru a confirma conexiunea.</span><span class="sxs-lookup"><span data-stu-id="39f7e-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="39f7e-121">Selectați **Următorul** și alegeți **Set de date client** pe care doriți să le îmbogățiți cu date despre companie de la Leadspace.</span><span class="sxs-lookup"><span data-stu-id="39f7e-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="39f7e-122">Puteți selecta entitatea **Client** pentru a vă îmbogăți toate profilurile de clienți sau selectați o entitate de segment pentru a îmbogăți numai profilurile de clienți din acel segment.</span><span class="sxs-lookup"><span data-stu-id="39f7e-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Captură de ecran atunci când alegeți setul de date pentru clienți.":::

1. <span data-ttu-id="39f7e-124">Selectați **Următorul** și definiți ce câmpuri din profilurile dvs. unificate sunt utilizate pentru a căuta datele companiei potrivite de la Leadspace.</span><span class="sxs-lookup"><span data-stu-id="39f7e-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="39f7e-125">Câmpul **Numele companiei** este obligatoriu.</span><span class="sxs-lookup"><span data-stu-id="39f7e-125">The **Name of company** field is required.</span></span> <span data-ttu-id="39f7e-126">Pentru o precizie mai mare a potrivirii, până la două alte câmpuri, **Site-ul companiei** și **Locația companiei**, pot fi adăugate.</span><span class="sxs-lookup"><span data-stu-id="39f7e-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panoul de mapare a câmpului Leadspace.":::

1. <span data-ttu-id="39f7e-128">Selectați **Următorul** pentru a completa maparea câmpului.</span><span class="sxs-lookup"><span data-stu-id="39f7e-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="39f7e-129">Furnizați un nume pentru îmbogățire și selectați **Salvați îmbogățirea** după ce v-ați analizat alegerile.</span><span class="sxs-lookup"><span data-stu-id="39f7e-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="39f7e-130">Configurați conexiunea pentru Leadspace</span><span class="sxs-lookup"><span data-stu-id="39f7e-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="39f7e-131">Trebuie să fiți administrator pentru a configura conexiunile.</span><span class="sxs-lookup"><span data-stu-id="39f7e-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="39f7e-132">Selectați **Adăugați conexiune** la configurarea unei îmbogățiri *sau* mergeți la **Administrator** > **Conexiuni** și selectați **Configurare** pe dala Leadspace.</span><span class="sxs-lookup"><span data-stu-id="39f7e-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="39f7e-133">Selectați **Începeți lucrul**.</span><span class="sxs-lookup"><span data-stu-id="39f7e-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="39f7e-134">Introduceți un nume pentru conexiune în caseta **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="39f7e-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="39f7e-135">Furnizați un token Leadspace valid.</span><span class="sxs-lookup"><span data-stu-id="39f7e-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="39f7e-136">Examinați și furnizați consimțământul pentru **Confidențialitatea și respectarea datelor** prin selectarea **Sunt de acord**.</span><span class="sxs-lookup"><span data-stu-id="39f7e-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="39f7e-137">Selectați **Verificare** pentru a valida configurația.</span><span class="sxs-lookup"><span data-stu-id="39f7e-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="39f7e-138">După finalizarea verificării, selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="39f7e-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Pagina de configurare a conexiunii Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="39f7e-140">Rezultate de îmbogățire</span><span class="sxs-lookup"><span data-stu-id="39f7e-140">Enrichment results</span></span>

<span data-ttu-id="39f7e-141">După reîmprospătarea îmbogățirii, puteți examina datele companiei nou îmbogățite sub [Îmbogățirile mele](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="39f7e-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="39f7e-142">Puteți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.</span><span class="sxs-lookup"><span data-stu-id="39f7e-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="39f7e-143">Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.</span><span class="sxs-lookup"><span data-stu-id="39f7e-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="39f7e-144">Pentru informații suplimentare, consultați [API-uri Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="39f7e-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="39f7e-145">Pașii următori</span><span class="sxs-lookup"><span data-stu-id="39f7e-145">Next steps</span></span>

<span data-ttu-id="39f7e-146">Creați în plus față de datele îmbogățite ale clienților.</span><span class="sxs-lookup"><span data-stu-id="39f7e-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="39f7e-147">Creați [segmente](segments.md) și [măsuri](measures.md), și chiar [exportați datele](export-destinations.md) pentru a oferi clienților dvs. experiențe particularizate.</span><span class="sxs-lookup"><span data-stu-id="39f7e-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="39f7e-148">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="39f7e-148">Data privacy and compliance</span></span>

<span data-ttu-id="39f7e-149">Când activați Dynamics 365 Customer Insights pentru a transmite date către Leadspace, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="39f7e-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="39f7e-150">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Leadspace îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="39f7e-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="39f7e-151">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="39f7e-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="39f7e-152">Administratorul dvs. Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="39f7e-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
