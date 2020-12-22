---
title: Îmbogățirea profilurilor companiei cu îmbogățirea terță parte Leadspace
description: Informații generale despre îmbogățirea terță parte Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668738"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="38945-103">Îmbogățirea profilurilor companiei cu Leadspace (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="38945-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="38945-104">Leadspace este o companie de știință a datelor care oferă o platformă de date pentru clienți B2B.</span><span class="sxs-lookup"><span data-stu-id="38945-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="38945-105">Aceasta permite clienților cu profiluri de clienți unificate pentru companii să-și îmbogățească datele.</span><span class="sxs-lookup"><span data-stu-id="38945-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="38945-106">Îmbogățirile includ atribute suplimentare cum ar fi dimensiunea firmei, locația, domeniul de activitate și multe altele.</span><span class="sxs-lookup"><span data-stu-id="38945-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="38945-107">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="38945-107">Prerequisites</span></span>

<span data-ttu-id="38945-108">Pentru a configura Leadspace, trebuie îndeplinite următoarele cerințe preliminare:</span><span class="sxs-lookup"><span data-stu-id="38945-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="38945-109">Aveți o licență Leadspace activă și „cheia perpetuă” (denumită **Token Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="38945-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="38945-110">Contactați direct [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) pentru detalii despre produsul lor.</span><span class="sxs-lookup"><span data-stu-id="38945-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="38945-111">Aveți permisiuni de [Administrator](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="38945-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="38945-112">Aveți [profiluri de clienți unificate](customer-profiles.md) pentru companii.</span><span class="sxs-lookup"><span data-stu-id="38945-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="38945-113">Configurație</span><span class="sxs-lookup"><span data-stu-id="38945-113">Configuration</span></span>

1. <span data-ttu-id="38945-114">În Detalii despre audiență, accesați **Date** > **Îmbogățire**.</span><span class="sxs-lookup"><span data-stu-id="38945-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="38945-115">Selectați **Doresc îmbogățirea datelor** pe dala Leadspace.</span><span class="sxs-lookup"><span data-stu-id="38945-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captură de ecran a dalei Leadspace.":::

1. <span data-ttu-id="38945-117">Selectați **Începeți** și apoi introduceți un **token Leadspace** activ (cheie perpetuă).</span><span class="sxs-lookup"><span data-stu-id="38945-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="38945-118">Analizați și acordați-vă consimțământul pentru **Confidențialitatea și conformitatea datelor** prin selectarea casetei de selectare **Sunt de acord**.</span><span class="sxs-lookup"><span data-stu-id="38945-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="38945-119">Confirmați ambele intrări selectând **Conectați-vă la Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="38945-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="38945-120">Selectați **Date cartografice** și definiți ce câmpuri din profilurile dvs. unificate ar trebui utilizate pentru a căuta datele companiei potrivite din Leadspace.</span><span class="sxs-lookup"><span data-stu-id="38945-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="38945-121">Câmpul **Numele companiei** este obligatoriu.</span><span class="sxs-lookup"><span data-stu-id="38945-121">The **Name of company** field is required.</span></span> <span data-ttu-id="38945-122">Pentru o precizie mai mare a potrivirii, până la două alte câmpuri, **Site-ul companiei** și **Locația companiei**, pot fi adăugate.</span><span class="sxs-lookup"><span data-stu-id="38945-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panoul de mapare a câmpului Leadspace.":::
   
1. <span data-ttu-id="38945-124">Selectați **Aplicare** pentru a finaliza maparea câmpului.</span><span class="sxs-lookup"><span data-stu-id="38945-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="38945-125">Selectați **Rulare** pentru a îmbogăți profilurile companiei.</span><span class="sxs-lookup"><span data-stu-id="38945-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="38945-126">Cât durează o îmbogățire depinde de numărul de profiluri unificate ale clienților.</span><span class="sxs-lookup"><span data-stu-id="38945-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="38945-127">Rezultate de îmbogățire</span><span class="sxs-lookup"><span data-stu-id="38945-127">Enrichment results</span></span>

<span data-ttu-id="38945-128">După reîmprospătarea îmbogățirii, puteți examina datele companiei nou îmbogățite sub [Îmbogățirile mele](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="38945-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="38945-129">Puteți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.</span><span class="sxs-lookup"><span data-stu-id="38945-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="38945-130">Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.</span><span class="sxs-lookup"><span data-stu-id="38945-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="38945-131">Pentru informații suplimentare, consultați [API-uri Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="38945-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="38945-132">Pașii următori</span><span class="sxs-lookup"><span data-stu-id="38945-132">Next steps</span></span>

<span data-ttu-id="38945-133">Creați în plus față de datele îmbogățite ale clienților.</span><span class="sxs-lookup"><span data-stu-id="38945-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="38945-134">Creați [segmente](segments.md), [măsuri](measures.md) și chiar [exportați datele](export-destinations.md) pentru a oferi experiențe personalizate clienților.</span><span class="sxs-lookup"><span data-stu-id="38945-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="38945-135">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="38945-135">Data privacy and compliance</span></span>

<span data-ttu-id="38945-136">Când activați Dynamics 365 Customer Insights pentru a transmite date către Leadspace, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="38945-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="38945-137">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Leadspace îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="38945-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="38945-138">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="38945-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="38945-139">Administratorul Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="38945-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>