---
title: Exportați datele Customer Insights către ActiveCampaign
description: Aflați cum să configurați conexiunea și să exportați către ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314662"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="bb2b8-103">Exportați segmente în ActiveCampaign (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="bb2b8-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="bb2b8-104">Exportați segmente de profiluri unificate ale clienților în ActiveCampaign și folosiți-le pentru activități de marketing.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bb2b8-105">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="bb2b8-105">Prerequisites</span></span>

-   <span data-ttu-id="bb2b8-106">Aveți un [Cont ActiveCampaign](https://www.activecampaign.com/) și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="bb2b8-107">Aveți [segmente configurate](segments.md) în Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="bb2b8-108">Profilurile de clienți unificate din segmentele exportate conțin un câmp cu o adresă de e-mail.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bb2b8-109">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="bb2b8-109">Known limitations</span></span>

- <span data-ttu-id="bb2b8-110">Puteți exporta până la 1 milion de profiluri pe export către ActiveCampaign și poate dura până la 90 de minute pentru a finaliza.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="bb2b8-111">Exportul către ActiveCampaign este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="bb2b8-112">Numărul de profiluri pe care le puteți exporta în ActiveCampaign depinde de contractul dvs. cu ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="bb2b8-113">Configurați conexiunea la ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="bb2b8-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="bb2b8-114">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bb2b8-115">Selectați **Adăugați conexiune** și alegeți **ActiveCampaign** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="bb2b8-116">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bb2b8-117">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bb2b8-118">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bb2b8-119">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-119">Choose who can use this connection.</span></span> <span data-ttu-id="bb2b8-120">În mod implicit, sunt doar de administratori.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-120">By default, it's only administrators.</span></span> <span data-ttu-id="bb2b8-121">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bb2b8-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bb2b8-122">Introduceți [Cheia API ActiveCampaign și REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="bb2b8-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="bb2b8-123">Numele de gazdă REST Endpoint este doar numele gazdei, fără https://.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="bb2b8-124">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bb2b8-125">Selectați **Conectare** pentru a inițializa conexiunea la ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="bb2b8-126">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="bb2b8-127">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="bb2b8-128">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="bb2b8-128">Configure an export</span></span>

<span data-ttu-id="bb2b8-129">Puteți configura un export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="bb2b8-130">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bb2b8-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bb2b8-131">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bb2b8-132">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="bb2b8-133">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="bb2b8-134">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bb2b8-135">Introduceți [**ID listă ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="bb2b8-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="bb2b8-136">În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="bb2b8-137">Este nevoie să exportați segmente la ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="bb2b8-138">Opțional, puteți exporta Prenume, Nume de familie, și Telefon pentru a crea e-mailuri mai particularizate.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="bb2b8-139">Selectați Adăugare atribut pentru a mapa aceste câmpuri.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="bb2b8-140">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-140">Select **Save**.</span></span>

<span data-ttu-id="bb2b8-141">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bb2b8-142">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bb2b8-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bb2b8-143">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bb2b8-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bb2b8-144">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="bb2b8-144">Data privacy and compliance</span></span>

<span data-ttu-id="bb2b8-145">Când activați Dynamics 365 Customer Insights pentru a transmite date către ActiveCampaign, permiteți transfer de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi date cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bb2b8-146">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru a vă asigura că ActiveCampaign îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bb2b8-147">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bb2b8-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="bb2b8-148">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="bb2b8-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
