---
title: Exportați datele Customer Insights către Snapchat
description: Aflați cum să configurați conexiunea și să exportați la Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6565ab81599abcc0f94465e1153f08e0bc119839
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124058"
---
# <a name="export-segments-to-snapchat-preview"></a><span data-ttu-id="048eb-103">Exportați segmente în Snapchat (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="048eb-103">Export segments to Snapchat (preview)</span></span>

<span data-ttu-id="048eb-104">Exportați segmente de profiluri de clienți unificate în Snapchat și folosiți-le pentru publicitate.</span><span class="sxs-lookup"><span data-stu-id="048eb-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="048eb-105">Cerințe preliminare pentru o conexiune</span><span class="sxs-lookup"><span data-stu-id="048eb-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="048eb-106">Aveți un [Cont Snapchat Business](https://business.snapchat.com/), un [Cont Snapchat Ads](https://ads.snapchat.com/) și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="048eb-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="048eb-107">Aveți [segmente configurate](segments.md) în Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="048eb-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="048eb-108">Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.</span><span class="sxs-lookup"><span data-stu-id="048eb-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="048eb-109">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="048eb-109">Known limitations</span></span>

- <span data-ttu-id="048eb-110">Exportul către Snapchat este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="048eb-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="048eb-111">Exportul de până la 1 milion de profiluri pe Snapchat poate dura până la 15 minute.</span><span class="sxs-lookup"><span data-stu-id="048eb-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="048eb-112">Configurarea conexiunii la Snapchat</span><span class="sxs-lookup"><span data-stu-id="048eb-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="048eb-113">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="048eb-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="048eb-114">Selectați **Adăugați conexiune** și alegeți **Snapchat** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="048eb-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="048eb-115">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="048eb-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="048eb-116">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="048eb-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="048eb-117">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="048eb-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="048eb-118">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="048eb-118">Choose who can use this connection.</span></span> <span data-ttu-id="048eb-119">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="048eb-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="048eb-120">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="048eb-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="048eb-121">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="048eb-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="048eb-122">Selectați **Conectați** pentru a inițializa conexiunea la Snapchat.</span><span class="sxs-lookup"><span data-stu-id="048eb-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="048eb-123">Selectați **Autentificare cu Snapchat** și furnizați acreditările de administrator pentru Snapchat.</span><span class="sxs-lookup"><span data-stu-id="048eb-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="048eb-124">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="048eb-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="048eb-125">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="048eb-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="048eb-126">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="048eb-126">Configure an export</span></span>

<span data-ttu-id="048eb-127">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="048eb-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="048eb-128">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="048eb-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="048eb-129">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="048eb-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="048eb-130">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="048eb-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="048eb-131">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Snapchat.</span><span class="sxs-lookup"><span data-stu-id="048eb-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="048eb-132">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="048eb-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="048eb-133">Introduceți [**ID-ul de audiență Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="048eb-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="048eb-134">În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="048eb-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="048eb-135">Este necesar să exportați segmente către Snapchat.</span><span class="sxs-lookup"><span data-stu-id="048eb-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="048eb-136">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="048eb-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="048eb-137">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="048eb-137">Select **Save**.</span></span>

<span data-ttu-id="048eb-138">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="048eb-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="048eb-139">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="048eb-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="048eb-140">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="048eb-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="048eb-141">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="048eb-141">Data privacy and compliance</span></span>

<span data-ttu-id="048eb-142">Când activați Dynamics 365 Customer Insights pentru a transmite date către Snapchat, permiteți transferul de date în afara limitelor de conformitate cu Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi date cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="048eb-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="048eb-143">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Snapchat respectă orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="048eb-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="048eb-144">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="048eb-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="048eb-145">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="048eb-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
