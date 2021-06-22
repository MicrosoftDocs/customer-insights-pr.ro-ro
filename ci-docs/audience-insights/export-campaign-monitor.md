---
title: Exportați datele Customer Insights către Monitor de campanie
description: Aflați cum să configurați conexiunea și exportul la Monitor de campanie.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124196"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="21465-103">Exportați segmente în Monitor de campanie (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="21465-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="21465-104">Exportați segmente de profiluri de clienți unificate în Monitor de campanie și folosiți-le pentru activități de marketing.</span><span class="sxs-lookup"><span data-stu-id="21465-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="21465-105">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="21465-105">Prerequisites</span></span>

-   <span data-ttu-id="21465-106">Aveți un [Cont Monitor de campanie](https://www.campaignmonitor.com/) și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="21465-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="21465-107">Aveți [segmente configurate](segments.md) în Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="21465-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="21465-108">Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.</span><span class="sxs-lookup"><span data-stu-id="21465-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="21465-109">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="21465-109">Known limitations</span></span>

- <span data-ttu-id="21465-110">Puteți exporta până la 1 milion de profiluri per export către Monitor de campanie.</span><span class="sxs-lookup"><span data-stu-id="21465-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="21465-111">Exportul către Monitor de campanie este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="21465-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="21465-112">Exportul de până la 1 milion de profiluri pe Monitor de campanie poate dura până la 20 minute.</span><span class="sxs-lookup"><span data-stu-id="21465-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="21465-113">Numărul de profiluri pe care le puteți exporta în Monitor de campanie depinde și este limitat de contractul dvs. cu Monitor de campanie.</span><span class="sxs-lookup"><span data-stu-id="21465-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="21465-114">Configurați conexiunea la Monitor de campanie</span><span class="sxs-lookup"><span data-stu-id="21465-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="21465-115">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="21465-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="21465-116">Selectați **Adăugați conexiune** și alegeți **Monitor de campanie** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="21465-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="21465-117">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="21465-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="21465-118">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="21465-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="21465-119">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="21465-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="21465-120">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="21465-120">Choose who can use this connection.</span></span> <span data-ttu-id="21465-121">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="21465-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="21465-122">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="21465-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="21465-123">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="21465-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="21465-124">Selectați **Conectați** pentru a inițializa conexiunea la Monitor de campanie.</span><span class="sxs-lookup"><span data-stu-id="21465-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="21465-125">Selectați **Autentificare cu Monitor de campanie** și furnizați acreditările de administrator pentru Monitor de campanie.</span><span class="sxs-lookup"><span data-stu-id="21465-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="21465-126">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="21465-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="21465-127">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="21465-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="21465-128">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="21465-128">Configure an export</span></span>

<span data-ttu-id="21465-129">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="21465-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="21465-130">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="21465-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="21465-131">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="21465-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="21465-132">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="21465-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="21465-133">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Monitor de campanie.</span><span class="sxs-lookup"><span data-stu-id="21465-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="21465-134">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="21465-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="21465-135">Introduceți [**ID-ul listei de Monitor de campanie**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="21465-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="21465-136">Mai întâi, [Generați cheia API](https://www.campaignmonitor.com/api/getting-started/) din **Setările contului** în Monitor de campanie pentru a vedea ID-ul listei API.</span><span class="sxs-lookup"><span data-stu-id="21465-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="21465-137">În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="21465-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="21465-138">Este necesar să exportați segmente către Monitor de campanie.</span><span class="sxs-lookup"><span data-stu-id="21465-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="21465-139">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="21465-139">Select **Save**.</span></span>

<span data-ttu-id="21465-140">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="21465-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="21465-141">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="21465-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="21465-142">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="21465-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="21465-143">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="21465-143">Data privacy and compliance</span></span>

<span data-ttu-id="21465-144">Când activați Dynamics 365 Customer Insights pentru a transmite date către Monitor de campanie, permiteți transferul de date în afara limitelor de conformitate cu Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi date cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="21465-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="21465-145">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Monitor de campanie respectă orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="21465-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="21465-146">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="21465-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="21465-147">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="21465-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
