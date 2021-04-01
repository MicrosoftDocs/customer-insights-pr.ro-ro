---
title: Exportați datele Customer Insights către AdRoll
description: Aflați cum să configurați conexiunea la AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697089"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="a2095-103">Conector pentru AdRoll (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="a2095-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="a2095-104">Exportați segmente de profiluri unificate ale clienților în AdRoll și folosiți-le pentru publicitate.</span><span class="sxs-lookup"><span data-stu-id="a2095-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="a2095-105">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="a2095-105">Prerequisites</span></span>

-   <span data-ttu-id="a2095-106">Aveți un [cont AdRoll](https://www.adroll.com/) și acredităările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="a2095-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a2095-107">Aveți [segmente configurate](segments.md) în Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="a2095-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a2095-108">Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.</span><span class="sxs-lookup"><span data-stu-id="a2095-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="a2095-109">Conectare la AdRoll</span><span class="sxs-lookup"><span data-stu-id="a2095-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="a2095-110">Accesați **Administrator** > **Destinații de export**.</span><span class="sxs-lookup"><span data-stu-id="a2095-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a2095-111">Sub **AdRoll**, selectați **Configurare**.</span><span class="sxs-lookup"><span data-stu-id="a2095-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="a2095-112">Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="a2095-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Panoul de configurare pentru conexiunea AdRoll.":::

1. <span data-ttu-id="a2095-114">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="a2095-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a2095-115">Selectați **Conectare** pentru a inițializa conexiunea la AdRoll.</span><span class="sxs-lookup"><span data-stu-id="a2095-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="a2095-116">Selectați **Autentificare cu AdRoll** și furnizați acreditările dvs. de administrator pentru AdRoll.</span><span class="sxs-lookup"><span data-stu-id="a2095-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="a2095-117">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a2095-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a2095-118">Introduceți **Codul de publicitate AdRoll** [AdRoll publicitar](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="a2095-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="a2095-119">Selectați **Continuare** pentru a configura exportul.</span><span class="sxs-lookup"><span data-stu-id="a2095-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="a2095-120">Configurați conectorul</span><span class="sxs-lookup"><span data-stu-id="a2095-120">Configure the connector</span></span>

1. <span data-ttu-id="a2095-121">În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="a2095-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a2095-122">Este necesar să exportați segmente în AdRoll.</span><span class="sxs-lookup"><span data-stu-id="a2095-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="a2095-123">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="a2095-123">Select the segments you want to export.</span></span> <span data-ttu-id="a2095-124">Selectați un segment cu cel puțin 100 de membri.</span><span class="sxs-lookup"><span data-stu-id="a2095-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="a2095-125">Nu puteți exporta segmente mai mici.</span><span class="sxs-lookup"><span data-stu-id="a2095-125">You can't export smaller segments.</span></span> <span data-ttu-id="a2095-126">În plus, dimensiunea maximă a unui segment de export este de 250.000 de membri pe export.</span><span class="sxs-lookup"><span data-stu-id="a2095-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="a2095-127">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="a2095-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a2095-128">Exportați datele</span><span class="sxs-lookup"><span data-stu-id="a2095-128">Export the data</span></span>

<span data-ttu-id="a2095-129">Puteți [exporta date la cerere](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a2095-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a2095-130">Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a2095-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a2095-131">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="a2095-131">Known limitations</span></span>

- <span data-ttu-id="a2095-132">Puteți exporta până la 250.000 de profiluri per export în AdRoll.</span><span class="sxs-lookup"><span data-stu-id="a2095-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="a2095-133">Nu puteți exporta segmente cu mai puțin de 100 de profiluri în AdRoll.</span><span class="sxs-lookup"><span data-stu-id="a2095-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="a2095-134">Exportul către AdRoll este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="a2095-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="a2095-135">Exportul până la 250.000 de profiluri în AdRoll poate dura până la 10 minute.</span><span class="sxs-lookup"><span data-stu-id="a2095-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="a2095-136">Numărul de profiluri pe care le puteți exporta către AdRoll este dependent și limitat de contractul dvs. cu AdRoll.</span><span class="sxs-lookup"><span data-stu-id="a2095-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a2095-137">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="a2095-137">Data privacy and compliance</span></span>

<span data-ttu-id="a2095-138">Când activați Dynamics 365 Customer Insights pentru a transmite date către AdRoll, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="a2095-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a2095-139">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că AdRoll îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="a2095-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a2095-140">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a2095-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="a2095-141">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="a2095-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
