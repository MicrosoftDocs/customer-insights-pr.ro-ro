---
title: Exportați datele Customer Insights către Autopilot
description: Aflați cum să configurați conexiunea la Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269253"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="81d1c-103">Conector pentru Autopilot (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="81d1c-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="81d1c-104">Exportați segmente de profiluri unificate ale clienților în Autopilot și utilizați-le pentru marketing prin e-mail în Autopilot.</span><span class="sxs-lookup"><span data-stu-id="81d1c-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="81d1c-105">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="81d1c-105">Prerequisites</span></span>

-   <span data-ttu-id="81d1c-106">Aveți un [cont Autopilotl](https://www.autopilothq.com/) și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="81d1c-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="81d1c-107">Aveți [segmente configurate](segments.md) în Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="81d1c-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="81d1c-108">Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.</span><span class="sxs-lookup"><span data-stu-id="81d1c-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="81d1c-109">Conectare la Autopilot</span><span class="sxs-lookup"><span data-stu-id="81d1c-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="81d1c-110">Accesați **Administrator** > **Destinații de export**.</span><span class="sxs-lookup"><span data-stu-id="81d1c-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="81d1c-111">Sub **Autopilot**, selectați **Configurare**.</span><span class="sxs-lookup"><span data-stu-id="81d1c-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="81d1c-112">Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="81d1c-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Panoul de configurare pentru conexiunea Autopilot.":::

1. <span data-ttu-id="81d1c-114">Introduceți **Cheie API pentru Autopilot** [Cheie API pentru Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="81d1c-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="81d1c-115">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="81d1c-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="81d1c-116">Selectați **Conectare** pentru a inițializa conexiunea la Autopilot.</span><span class="sxs-lookup"><span data-stu-id="81d1c-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="81d1c-117">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="81d1c-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="81d1c-118">Selectați **Continuare** pentru a configura exportul.</span><span class="sxs-lookup"><span data-stu-id="81d1c-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="81d1c-119">Configurați conectorul</span><span class="sxs-lookup"><span data-stu-id="81d1c-119">Configure the connector</span></span>

1. <span data-ttu-id="81d1c-120">În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="81d1c-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="81d1c-121">Repetați aceiași pași pentru alte câmpuri opționale, cum ar fi **Prenume**, **Nume**.</span><span class="sxs-lookup"><span data-stu-id="81d1c-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="81d1c-122">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="81d1c-122">Select the segments you want to export.</span></span> <span data-ttu-id="81d1c-123">Ferm **recomandăm să nu exportați mai mult de 100.000 de profiluri de clienți în total** la Autopilot.</span><span class="sxs-lookup"><span data-stu-id="81d1c-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="81d1c-124">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="81d1c-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="81d1c-125">Exportați datele</span><span class="sxs-lookup"><span data-stu-id="81d1c-125">Export the data</span></span>

<span data-ttu-id="81d1c-126">Puteți [exporta date la cerere](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="81d1c-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="81d1c-127">Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="81d1c-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="81d1c-128">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="81d1c-128">Known limitations</span></span>

- <span data-ttu-id="81d1c-129">Puteți exporta până la 100.000 de profiluri de client în total către Autopilot.</span><span class="sxs-lookup"><span data-stu-id="81d1c-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="81d1c-130">Exportul către Autopilot este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="81d1c-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="81d1c-131">Exportul până la 100'000 de profiluri către Autopilot poate dura până la câteva ore.</span><span class="sxs-lookup"><span data-stu-id="81d1c-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="81d1c-132">Numărul de profiluri pe care le puteți exporta către Autopilot este dependent și limitat de contractul dvs. cu Autopilot.</span><span class="sxs-lookup"><span data-stu-id="81d1c-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="81d1c-133">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="81d1c-133">Data privacy and compliance</span></span>

<span data-ttu-id="81d1c-134">Când activați Dynamics 365 Customer Insights pentru a transmite date către Autopilot, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="81d1c-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="81d1c-135">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Autopilot îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="81d1c-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="81d1c-136">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="81d1c-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="81d1c-137">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="81d1c-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]