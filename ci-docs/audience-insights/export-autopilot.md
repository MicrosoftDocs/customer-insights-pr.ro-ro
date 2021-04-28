---
title: Exportați datele Customer Insights către Autopilot
description: Aflați cum să configurați conexiunea și să exportați la Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760158"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="505c1-103">Exportați segmente către Autopilot (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="505c1-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="505c1-104">Exportați segmente de profiluri unificate ale clienților în Autopilot și utilizați-le pentru marketing prin e-mail în Autopilot.</span><span class="sxs-lookup"><span data-stu-id="505c1-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="505c1-105">Cerințe preliminare pentru o conexiune</span><span class="sxs-lookup"><span data-stu-id="505c1-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="505c1-106">Aveți un [cont Autopilotl](https://www.autopilothq.com/) și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="505c1-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="505c1-107">Aveți [segmente configurate](segments.md) în Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="505c1-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="505c1-108">Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.</span><span class="sxs-lookup"><span data-stu-id="505c1-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="505c1-109">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="505c1-109">Known limitations</span></span>

- <span data-ttu-id="505c1-110">Puteți exporta până la 100.000 de profiluri de client în total către Autopilot.</span><span class="sxs-lookup"><span data-stu-id="505c1-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="505c1-111">Exportul către Autopilot este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="505c1-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="505c1-112">Exportul până la 100'000 de profiluri către Autopilot poate dura până la câteva ore.</span><span class="sxs-lookup"><span data-stu-id="505c1-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="505c1-113">Numărul de profiluri pe care le puteți exporta către Autopilot este dependent și limitat de contractul dvs. cu Autopilot.</span><span class="sxs-lookup"><span data-stu-id="505c1-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="505c1-114">Configurarea conexiunii la Autopilot</span><span class="sxs-lookup"><span data-stu-id="505c1-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="505c1-115">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="505c1-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="505c1-116">Selectați **Adăugați conexiune** și alegeți **Autopilot** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="505c1-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="505c1-117">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="505c1-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="505c1-118">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="505c1-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="505c1-119">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="505c1-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="505c1-120">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="505c1-120">Choose who can use this connection.</span></span> <span data-ttu-id="505c1-121">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="505c1-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="505c1-122">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="505c1-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="505c1-123">Introduceți [Cheie API Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="505c1-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="505c1-124">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="505c1-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="505c1-125">Selectați **Conectare** pentru a inițializa conexiunea la Autopilot.</span><span class="sxs-lookup"><span data-stu-id="505c1-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="505c1-126">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="505c1-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="505c1-127">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="505c1-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="505c1-128">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="505c1-128">Configure an export</span></span>

<span data-ttu-id="505c1-129">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="505c1-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="505c1-130">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="505c1-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="505c1-131">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="505c1-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="505c1-132">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="505c1-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="505c1-133">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Autopilot.</span><span class="sxs-lookup"><span data-stu-id="505c1-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="505c1-134">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="505c1-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="505c1-135">În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="505c1-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="505c1-136">Repetați aceiași pași pentru alte câmpuri opționale, cum ar fi **Prenume**, **Nume**.</span><span class="sxs-lookup"><span data-stu-id="505c1-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="505c1-137">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="505c1-137">Select the segments you want to export.</span></span> <span data-ttu-id="505c1-138">Ferm **recomandăm să nu exportați mai mult de 100.000 de profiluri de clienți în total** la Autopilot.</span><span class="sxs-lookup"><span data-stu-id="505c1-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="505c1-139">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="505c1-139">Select **Save**.</span></span>

<span data-ttu-id="505c1-140">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="505c1-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="505c1-141">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="505c1-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="505c1-142">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="505c1-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="505c1-143">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="505c1-143">Data privacy and compliance</span></span>

<span data-ttu-id="505c1-144">Când activați Dynamics 365 Customer Insights pentru a transmite date către Autopilot, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="505c1-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="505c1-145">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Autopilot îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="505c1-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="505c1-146">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="505c1-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="505c1-147">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="505c1-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
