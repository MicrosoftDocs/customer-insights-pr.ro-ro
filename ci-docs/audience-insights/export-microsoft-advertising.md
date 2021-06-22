---
title: Exportați datele Customer Insights în Microsoft Advertising
description: Aflați cum să configurați conexiunea și exportul la Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124537"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="1e0f1-103">Exportați segmente în Microsoft Advertising (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="1e0f1-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="1e0f1-104">Exportați segmentele Customer Insights în Microsoft Advertising pentru a crea segmente de public Matched Audiences.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="1e0f1-105">Utilizați aceste segmente de public pentru campaniile dvs. publicitare.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1e0f1-106">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="1e0f1-106">Prerequisites</span></span>

-   <span data-ttu-id="1e0f1-107">Un [Cont Microsoft Advertising](https://ads.microsoft.com/) și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1e0f1-108">Ați acceptat condițiile de utilizare pentru Customer Match.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="1e0f1-109">[Segmente configurate](segments.md) în detalii despre public.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="1e0f1-110">Profilurile de clienți unificate din segmentele exportate conțin un câmp cu o adresă de e-mail.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1e0f1-111">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="1e0f1-111">Known limitations</span></span>

- <span data-ttu-id="1e0f1-112">Puteți exporta până la 500 milioane de profiluri per export către Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="1e0f1-113">Exportul către Microsoft Advertising constantă este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="1e0f1-114">Exportul de până la 500 milioane de profiluri pe Microsoft Advertising poate dura până la 10 minute.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="1e0f1-115">Configurați conexiunea la Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="1e0f1-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="1e0f1-116">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1e0f1-117">Selectați **Adăugați conexiune** și alegeți **Microsoft Advertising** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="1e0f1-118">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1e0f1-119">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1e0f1-120">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1e0f1-121">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-121">Choose who can use this connection.</span></span> <span data-ttu-id="1e0f1-122">În mod implicit sunt administratorii.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-122">The default is administrators.</span></span> <span data-ttu-id="1e0f1-123">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1e0f1-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1e0f1-124">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1e0f1-125">Selectați **Conectați** pentru a inițializa conexiunea la Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="1e0f1-126">Selectați **Autentificare cu Microsoft Advertising** și furnizați acreditările de administrator pentru Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="1e0f1-127">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1e0f1-128">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1e0f1-129">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="1e0f1-129">Configure an export</span></span>

<span data-ttu-id="1e0f1-130">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1e0f1-131">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1e0f1-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1e0f1-132">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1e0f1-133">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1e0f1-134">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="1e0f1-135">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1e0f1-136">Selectați segmentele pentru export.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-136">Select the segments to export.</span></span> <span data-ttu-id="1e0f1-137">Audiențele de potrivire după clienți din Microsoft Advertising sunt create automat cu numele segmentelor selectate pentru export.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="1e0f1-138">Fiecare segment va avea ca rezultat un public separat Matched audience.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="1e0f1-139">Introduceți **ID client Microsoft Advertising și ID cont**.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="1e0f1-140">Puteți găsi ID-ul de client (`cid`) și ID-ul contului (`aid`) în parametrii adresei URL când sunteți conectat la Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="1e0f1-141">În secțiunea **Potrivirea datelor**, în **E-mail**, selectați câmpul din profilul dvs. de client unificat cu adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="1e0f1-142">Este necesar să exportați segmente către Match Advertising.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="1e0f1-143">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-143">Select **Save**.</span></span>

<span data-ttu-id="1e0f1-144">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1e0f1-145">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1e0f1-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1e0f1-146">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1e0f1-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1e0f1-147">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="1e0f1-147">Data privacy and compliance</span></span>

<span data-ttu-id="1e0f1-148">Când activați Dynamics 365 Customer Insights pentru a transmite date către Microsoft Advertising, permiteți transferul de date în afara limitelor de conformitate cu Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi date cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1e0f1-149">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Microsoft Advertising respectă orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1e0f1-150">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1e0f1-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="1e0f1-151">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="1e0f1-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
