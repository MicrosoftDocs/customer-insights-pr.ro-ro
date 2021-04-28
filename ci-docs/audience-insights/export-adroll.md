---
title: Exportați datele Customer Insights către AdRoll
description: Aflați cum să configurați conexiunea și să exportați la AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e8f4d4ee6b2c6cdec513b700641db568fa16076d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895974"
---
# <a name="export-segment-lists-to-adroll-preview"></a><span data-ttu-id="4e710-103">Exportați listele de segmente în AdRoll (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="4e710-103">Export segment lists to AdRoll (preview)</span></span>

<span data-ttu-id="4e710-104">Exportați segmente de profiluri unificate ale clienților în AdRoll și folosiți-le pentru publicitate.</span><span class="sxs-lookup"><span data-stu-id="4e710-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="4e710-105">Cerințe preliminare pentru o conexiune</span><span class="sxs-lookup"><span data-stu-id="4e710-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="4e710-106">Aveți un [cont AdRoll](https://www.adroll.com/) și acredităările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="4e710-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="4e710-107">Aveți [segmente configurate](segments.md) în Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="4e710-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="4e710-108">Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.</span><span class="sxs-lookup"><span data-stu-id="4e710-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="4e710-109">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="4e710-109">Known limitations</span></span>

- <span data-ttu-id="4e710-110">Puteți exporta până la 250.000 de profiluri per export în AdRoll.</span><span class="sxs-lookup"><span data-stu-id="4e710-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="4e710-111">Nu puteți exporta segmente cu mai puțin de 100 de profiluri în AdRoll.</span><span class="sxs-lookup"><span data-stu-id="4e710-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="4e710-112">Exportul către AdRoll este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="4e710-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="4e710-113">Exportul până la 250.000 de profiluri în AdRoll poate dura până la 10 minute.</span><span class="sxs-lookup"><span data-stu-id="4e710-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="4e710-114">Numărul de profiluri pe care le puteți exporta către AdRoll este dependent și limitat de contractul dvs. cu AdRoll.</span><span class="sxs-lookup"><span data-stu-id="4e710-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="4e710-115">Configurarea conexiunii la AdRoll</span><span class="sxs-lookup"><span data-stu-id="4e710-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="4e710-116">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="4e710-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4e710-117">Selectați **Adăugați conexiune** și alegeți **AdRoll** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="4e710-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="4e710-118">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="4e710-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4e710-119">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="4e710-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4e710-120">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="4e710-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4e710-121">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="4e710-121">Choose who can use this connection.</span></span> <span data-ttu-id="4e710-122">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="4e710-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="4e710-123">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="4e710-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="4e710-124">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="4e710-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="4e710-125">Selectați **Conectare** pentru a inițializa conexiunea la AdRoll.</span><span class="sxs-lookup"><span data-stu-id="4e710-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="4e710-126">Selectați **Autentificare cu AdRoll** și furnizați acreditările dvs. de administrator pentru AdRoll.</span><span class="sxs-lookup"><span data-stu-id="4e710-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="4e710-127">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4e710-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="4e710-128">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="4e710-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="4e710-129">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="4e710-129">Configure an export</span></span>

<span data-ttu-id="4e710-130">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="4e710-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4e710-131">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="4e710-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4e710-132">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="4e710-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4e710-133">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="4e710-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="4e710-134">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea AdRoll.</span><span class="sxs-lookup"><span data-stu-id="4e710-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="4e710-135">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="4e710-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="4e710-136">Introduceți **ID-ul de agent de publicitate AdRoll** Pentru mai multe informații, consultați [Profiluri de agent de publicitate AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="4e710-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="4e710-137">În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="4e710-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="4e710-138">Este necesar să exportați segmente în AdRoll.</span><span class="sxs-lookup"><span data-stu-id="4e710-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="4e710-139">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="4e710-139">Select the segments you want to export.</span></span> <span data-ttu-id="4e710-140">Selectați un segment cu cel puțin 100 de membri.</span><span class="sxs-lookup"><span data-stu-id="4e710-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="4e710-141">Nu puteți exporta segmente mai mici.</span><span class="sxs-lookup"><span data-stu-id="4e710-141">You can't export smaller segments.</span></span> <span data-ttu-id="4e710-142">În plus, dimensiunea maximă a unui segment de export este de 250.000 de membri pe export.</span><span class="sxs-lookup"><span data-stu-id="4e710-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="4e710-143">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="4e710-143">Select **Save**.</span></span>

<span data-ttu-id="4e710-144">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="4e710-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="4e710-145">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4e710-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4e710-146">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="4e710-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4e710-147">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="4e710-147">Data privacy and compliance</span></span>

<span data-ttu-id="4e710-148">Când activați Dynamics 365 Customer Insights pentru a transmite date către AdRoll, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="4e710-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4e710-149">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că AdRoll îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="4e710-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4e710-150">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4e710-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="4e710-151">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="4e710-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
