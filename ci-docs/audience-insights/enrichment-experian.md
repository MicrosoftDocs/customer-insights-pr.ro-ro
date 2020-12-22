---
title: Îmbogățire cu îmbogățiri terță parte Experian
description: Informații generale despre îmbogățirea terță parte Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668827"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="896cc-103">Îmbogățirea profilurilor clienților cu date demografice de la Experian (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="896cc-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="896cc-104">Experian este lider global în raportarea creditelor pentru consumatori și afaceri și servicii de marketing.</span><span class="sxs-lookup"><span data-stu-id="896cc-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="896cc-105">Cu Serviciile de îmbogățire a datelor Experian, puteți construi o înțelegere mai profundă a clienților dvs. îmbogățind profilurile clienților cu date demografice, cum ar fi dimensiunea gospodăriei, veniturile și multe altele.</span><span class="sxs-lookup"><span data-stu-id="896cc-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="896cc-106">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="896cc-106">Prerequisites</span></span>

<span data-ttu-id="896cc-107">Pentru a configura Experian, trebuie îndeplinite următoarele condiții prealabile:</span><span class="sxs-lookup"><span data-stu-id="896cc-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="896cc-108">Aveți un abonament Experian activ.</span><span class="sxs-lookup"><span data-stu-id="896cc-108">You have an active Experian subscription.</span></span> <span data-ttu-id="896cc-109">Pentru a obține un abonament, [contactați Experian](https://www.experian.com/marketing-services/contact) direct.</span><span class="sxs-lookup"><span data-stu-id="896cc-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="896cc-110">[Aflați mai multe despre îmbogățirea datelor Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="896cc-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="896cc-111">Aveți ID-ul de utilizator, ID-ul de parte și numărul de model pentru contul dvs. cu SSH activat Secure Transport (ST) creat de Experian pentru dvs.</span><span class="sxs-lookup"><span data-stu-id="896cc-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="896cc-112">Aveți permisiuni de [Administrator](permissions.md#administrator) în Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="896cc-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="896cc-113">Configurație</span><span class="sxs-lookup"><span data-stu-id="896cc-113">Configuration</span></span>

1. <span data-ttu-id="896cc-114">Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**.</span><span class="sxs-lookup"><span data-stu-id="896cc-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="896cc-115">Selectați **Doresc îmbogățirea datelor** din dala Experian.</span><span class="sxs-lookup"><span data-stu-id="896cc-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="896cc-116">![Dală Experian](media/experian-tile.png "Dală Experian")</span><span class="sxs-lookup"><span data-stu-id="896cc-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="896cc-117">Selectați **Începere** și introduceți ID-ul de utilizator, ID-ul de parte și numărul de model pentru contul dvs. Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="896cc-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="896cc-118">Analizați și acordați-vă consimțământul pentru **Confidențialitatea și conformitatea datelor** prin selectarea casetei de selectare **Sunt de acord**.</span><span class="sxs-lookup"><span data-stu-id="896cc-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="896cc-119">Confirmați toate intrările selectând **Aplicare**.</span><span class="sxs-lookup"><span data-stu-id="896cc-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="896cc-120">Mapați câmpurile</span><span class="sxs-lookup"><span data-stu-id="896cc-120">Map your fields</span></span>

1. <span data-ttu-id="896cc-121">Selectați **Adăugare date** și alegeți identificatorii cheie din **Numele și adresa**, **E-mail**, sau **Telefon** pentru trimitere la Experian pentru rezolvarea identității.</span><span class="sxs-lookup"><span data-stu-id="896cc-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="896cc-122">Mai multe atribute de identificare cheie trimise către Experian generează probabil o rată de potrivire mai mare.</span><span class="sxs-lookup"><span data-stu-id="896cc-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="896cc-123">Selectați **Următorul** și mapați atributele corespunzătoare de la entitatea dvs. client unificată pentru câmpurile de identificare cheie selectate.</span><span class="sxs-lookup"><span data-stu-id="896cc-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="896cc-124">Selectați **Adăugare atribut** pentru a mapa orice atribute suplimentare pe care doriți să le trimiteți către Experian.</span><span class="sxs-lookup"><span data-stu-id="896cc-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="896cc-125">Selectați **Salvați** pentru a finaliza maparea câmpului.</span><span class="sxs-lookup"><span data-stu-id="896cc-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="896cc-126">![Mapare câmp Experian](media/experian-field-mapping.png "Mapare câmp Experian")</span><span class="sxs-lookup"><span data-stu-id="896cc-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="896cc-127">Rezultate de îmbogățire</span><span class="sxs-lookup"><span data-stu-id="896cc-127">Enrichment results</span></span>

<span data-ttu-id="896cc-128">Pentru a începe procesul de îmbogățire, selectați **Rulare** din bara de comenzi.</span><span class="sxs-lookup"><span data-stu-id="896cc-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="896cc-129">De asemenea, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei [reîmprospătări programate](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="896cc-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="896cc-130">Timpul de procesare va depinde de mărimea datelor clienților dvs. și de procesele de îmbogățire stabilite pentru contul dvs. de Experian.</span><span class="sxs-lookup"><span data-stu-id="896cc-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="896cc-131">După finalizarea procesului de îmbogățire, puteți consulta datele din profilurile clienților nou îmbogățite din **Îmbogățirile mele**.</span><span class="sxs-lookup"><span data-stu-id="896cc-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="896cc-132">În plus, veți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.</span><span class="sxs-lookup"><span data-stu-id="896cc-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="896cc-133">Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.</span><span class="sxs-lookup"><span data-stu-id="896cc-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="896cc-134">Pașii următori</span><span class="sxs-lookup"><span data-stu-id="896cc-134">Next steps</span></span>

<span data-ttu-id="896cc-135">Creați în plus față de datele îmbogățite ale clienților.</span><span class="sxs-lookup"><span data-stu-id="896cc-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="896cc-136">Creați [segmente](segments.md), [măsuri](measures.md) și chiar [exportați datele](export-destinations.md) pentru a oferi experiențe personalizate clienților.</span><span class="sxs-lookup"><span data-stu-id="896cc-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="896cc-137">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="896cc-137">Data privacy and compliance</span></span>

<span data-ttu-id="896cc-138">Când activați Dynamics 365 Customer Insights pentru a transmite date către Experian, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="896cc-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="896cc-139">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Experian îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="896cc-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="896cc-140">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="896cc-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="896cc-141">Administratorul Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="896cc-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
