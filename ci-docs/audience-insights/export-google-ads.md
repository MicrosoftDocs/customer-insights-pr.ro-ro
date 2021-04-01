---
title: Exportați datele Customer Insights către Google Ads
description: Aflați cum să configurați conexiunea la Google Ads.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598262"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="c4dcf-103">Conector pentru Google Ads (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="c4dcf-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="c4dcf-104">Exportați segmente de profiluri de clienți unificate în lista de audiență Google Ads și folosiți-le pentru publicitate în Căutarea Google, Gmail, YouTube și Rețeaua de vizualizare Google.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c4dcf-105">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="c4dcf-105">Prerequisites</span></span>

-   <span data-ttu-id="c4dcf-106">Aveți un [cont Google Ads](https://ads.google.com/) și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c4dcf-107">Există audiențe în Google Ads și ID-urile corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="c4dcf-108">Pentru informații suplimentare, consultați [Audiențe Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="c4dcf-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="c4dcf-109">Aveți [segmente configurate](segments.md)</span><span class="sxs-lookup"><span data-stu-id="c4dcf-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="c4dcf-110">Profilurile de clienți unificate din segmentele exportate conțin câmpuri care reprezintă o adresă de e-mail, prenumele și numele de familie</span><span class="sxs-lookup"><span data-stu-id="c4dcf-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="c4dcf-111">Conectare la Google Ads</span><span class="sxs-lookup"><span data-stu-id="c4dcf-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="c4dcf-112">Accesați **Administrator** > **Destinații de export**.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c4dcf-113">Sub **Google Ads**, selectați **Configurare**.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="c4dcf-114">Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c4dcf-115">Introduceți **[ID-ul de client Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="c4dcf-116">Introduceți **[Tokenul de dezvoltator aprobat de Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="c4dcf-117">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c4dcf-118">Introduceți **[ID-ul de audiență Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** și selectați **Conectare** pentru a inițializa conexiunea la Google Ads.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="c4dcf-119">Selectați **Autentificare cu Google Ads** și furnizați acreditările dvs. Google Ads.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="c4dcf-120">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Exportați captura de ecran pentru conexiunea Google Ads":::

1. <span data-ttu-id="c4dcf-122">Selectați **Continuare** pentru a configura exportul.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="c4dcf-123">Configurați conectorul</span><span class="sxs-lookup"><span data-stu-id="c4dcf-123">Configure the connector</span></span>

1. <span data-ttu-id="c4dcf-124">În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="c4dcf-125">Repetați aceiași pași pentru câmpurile **Prenume** și **Nume de familie**.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="c4dcf-126">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-126">Select the segments you want to export.</span></span> <span data-ttu-id="c4dcf-127">Puteți exporta până la 1 milion de profiluri de client în total către Google Ads.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="c4dcf-128">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c4dcf-129">Exportați datele</span><span class="sxs-lookup"><span data-stu-id="c4dcf-129">Export the data</span></span>

<span data-ttu-id="c4dcf-130">Puteți [exporta date la cerere](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c4dcf-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c4dcf-131">Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c4dcf-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c4dcf-132">În Google Ads, puteți găsi acum segmentele dvs. sub [Segmente de audiență Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="c4dcf-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c4dcf-133">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="c4dcf-133">Known limitations</span></span>

- <span data-ttu-id="c4dcf-134">Până la 1 milion de profiluri per export către Google Ads.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="c4dcf-135">Exportul către Google Ads este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="c4dcf-136">Exportul de segmente cu un total de 1 milion de profiluri poate dura până la 5 minute din cauza limitărilor din partea furnizorului.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="c4dcf-137">Potrivirea în Google Ads poate dura până la 48 de ore.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c4dcf-138">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="c4dcf-138">Data privacy and compliance</span></span>

<span data-ttu-id="c4dcf-139">Când activați Dynamics 365 Customer Insights pentru a transmite date către Google Ads, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c4dcf-140">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Google Ads îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="c4dcf-141">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c4dcf-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c4dcf-142">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="c4dcf-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]