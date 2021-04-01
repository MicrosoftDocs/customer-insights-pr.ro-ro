---
title: Îmbogățirea profilurilor companiei cu îmbogățirea terță parte Leadspace
description: Informații generale despre îmbogățirea terță parte Leadspace.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597664"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="a5088-103">Îmbogățirea profilurilor companiei cu Leadspace (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="a5088-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="a5088-104">Leadspace este o companie de știință a datelor care oferă o platformă de date pentru clienți B2B.</span><span class="sxs-lookup"><span data-stu-id="a5088-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="a5088-105">Aceasta permite clienților cu profiluri de clienți unificate pentru companii să-și îmbogățească datele.</span><span class="sxs-lookup"><span data-stu-id="a5088-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="a5088-106">Îmbogățirile includ atribute suplimentare cum ar fi dimensiunea firmei, locația, domeniul de activitate și multe altele.</span><span class="sxs-lookup"><span data-stu-id="a5088-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a5088-107">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="a5088-107">Prerequisites</span></span>

<span data-ttu-id="a5088-108">Pentru a configura Leadspace, trebuie îndeplinite următoarele cerințe preliminare:</span><span class="sxs-lookup"><span data-stu-id="a5088-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="a5088-109">Aveți o licență Leadspace activă și „cheia perpetuă” (denumită **Token Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="a5088-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="a5088-110">Contactați direct [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) pentru detalii despre produsul lor.</span><span class="sxs-lookup"><span data-stu-id="a5088-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="a5088-111">Aveți permisiuni de [Administrator](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="a5088-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="a5088-112">Aveți [profiluri de clienți unificate](customer-profiles.md) pentru companii.</span><span class="sxs-lookup"><span data-stu-id="a5088-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="a5088-113">Configurație</span><span class="sxs-lookup"><span data-stu-id="a5088-113">Configuration</span></span>

1. <span data-ttu-id="a5088-114">În Detalii despre audiență, accesați **Date** > **Îmbogățire**.</span><span class="sxs-lookup"><span data-stu-id="a5088-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="a5088-115">Selectați **Doresc îmbogățirea datelor** pe dala Leadspace.</span><span class="sxs-lookup"><span data-stu-id="a5088-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captură de ecran a dalei Leadspace.":::

1. <span data-ttu-id="a5088-117">Selectați **Începeți** și apoi introduceți un **token Leadspace** activ (cheie perpetuă).</span><span class="sxs-lookup"><span data-stu-id="a5088-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="a5088-118">Analizați și acordați-vă consimțământul pentru **Confidențialitatea și conformitatea datelor** prin selectarea casetei de selectare **Sunt de acord**.</span><span class="sxs-lookup"><span data-stu-id="a5088-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="a5088-119">Confirmați ambele intrări selectând **Conectați-vă la Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="a5088-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="a5088-120">Selectați **Mapare date** și alegeți setul de date pe care doriți să îl îmbogățiți cu date de companie din Leadspace.</span><span class="sxs-lookup"><span data-stu-id="a5088-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="a5088-121">Puteți selecta entitatea *Client* pentru a vă îmbogăți toate profilurile de clienți sau selectați o entitate de segment pentru a îmbogăți numai profilurile de clienți din acel segment.</span><span class="sxs-lookup"><span data-stu-id="a5088-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Alegeți între profilul clientului și îmbogățirea segmentului":::

1. <span data-ttu-id="a5088-123">Faceți clic pe **Următorul** și definiți ce câmpuri din profilurile dvs. unificate ar trebui utilizate pentru a căuta datele companiei potrivite din Leadspace.</span><span class="sxs-lookup"><span data-stu-id="a5088-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="a5088-124">Câmpul **Numele companiei** este obligatoriu.</span><span class="sxs-lookup"><span data-stu-id="a5088-124">The **Name of company** field is required.</span></span> <span data-ttu-id="a5088-125">Pentru o precizie mai mare a potrivirii, până la două alte câmpuri, **Site-ul companiei** și **Locația companiei**, pot fi adăugate.</span><span class="sxs-lookup"><span data-stu-id="a5088-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panoul de mapare a câmpului Leadspace.":::
   
1. <span data-ttu-id="a5088-127">Selectați **Aplicare** pentru a finaliza maparea câmpului.</span><span class="sxs-lookup"><span data-stu-id="a5088-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="a5088-128">Selectați **Rulare** pentru a îmbogăți profilurile companiei.</span><span class="sxs-lookup"><span data-stu-id="a5088-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="a5088-129">Cât durează o îmbogățire depinde de numărul de profiluri unificate ale clienților.</span><span class="sxs-lookup"><span data-stu-id="a5088-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="a5088-130">Rezultate de îmbogățire</span><span class="sxs-lookup"><span data-stu-id="a5088-130">Enrichment results</span></span>

<span data-ttu-id="a5088-131">După reîmprospătarea îmbogățirii, puteți examina datele companiei nou îmbogățite sub [Îmbogățirile mele](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="a5088-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="a5088-132">Puteți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.</span><span class="sxs-lookup"><span data-stu-id="a5088-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="a5088-133">Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.</span><span class="sxs-lookup"><span data-stu-id="a5088-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="a5088-134">Pentru informații suplimentare, consultați [API-uri Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="a5088-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a5088-135">Pașii următori</span><span class="sxs-lookup"><span data-stu-id="a5088-135">Next steps</span></span>

<span data-ttu-id="a5088-136">Creați în plus față de datele îmbogățite ale clienților.</span><span class="sxs-lookup"><span data-stu-id="a5088-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a5088-137">Creați [segmente](segments.md), [măsuri](measures.md) și chiar [exportați datele](export-destinations.md) pentru a oferi experiențe personalizate clienților.</span><span class="sxs-lookup"><span data-stu-id="a5088-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a5088-138">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="a5088-138">Data privacy and compliance</span></span>

<span data-ttu-id="a5088-139">Când activați Dynamics 365 Customer Insights pentru a transmite date către Leadspace, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="a5088-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a5088-140">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Leadspace îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="a5088-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a5088-141">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a5088-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a5088-142">Administratorul Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="a5088-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]