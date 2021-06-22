---
title: Exportați datele Customer Insights către Omnisend
description: Aflați cum să configurați conexiunea și să exportați la Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124538"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="caf17-103">Exportați segmente către Omnisend (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="caf17-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="caf17-104">Exportați segmente de profiluri de clienți unificate în Omnisend și folosiți-le pentru activități de marketing.</span><span class="sxs-lookup"><span data-stu-id="caf17-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="caf17-105">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="caf17-105">Prerequisites</span></span>

-   <span data-ttu-id="caf17-106">Aveți un [Cont Omnisend](https://www.omnisend.com/) și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="caf17-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="caf17-107">Aveți [segmente configurate](segments.md) în Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="caf17-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="caf17-108">Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.</span><span class="sxs-lookup"><span data-stu-id="caf17-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="caf17-109">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="caf17-109">Known limitations</span></span>

- <span data-ttu-id="caf17-110">Puteți exporta până la 1 milion de profiluri pe export către Omnisend și poate dura până la 4 ore până la finalizare.</span><span class="sxs-lookup"><span data-stu-id="caf17-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="caf17-111">Exportul către Omnisend este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="caf17-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="caf17-112">Numărul de profiluri pe care le puteți exporta în Omnisend depinde de contractul dvs. cu Omnisend.</span><span class="sxs-lookup"><span data-stu-id="caf17-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="caf17-113">Configurarea conexiunii la Omnisend</span><span class="sxs-lookup"><span data-stu-id="caf17-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="caf17-114">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="caf17-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="caf17-115">Selectați **Adăugați conexiune** și alegeți **Omnisend** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="caf17-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="caf17-116">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="caf17-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="caf17-117">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="caf17-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="caf17-118">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="caf17-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="caf17-119">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="caf17-119">Choose who can use this connection.</span></span> <span data-ttu-id="caf17-120">În mod implicit, este vorba doar de administratori.</span><span class="sxs-lookup"><span data-stu-id="caf17-120">By default it's only administrators.</span></span> <span data-ttu-id="caf17-121">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="caf17-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="caf17-122">Introduceți [Cheie API Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="caf17-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="caf17-123">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="caf17-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="caf17-124">Selectați **Conectați** pentru a inițializa conexiunea la Omnisend.</span><span class="sxs-lookup"><span data-stu-id="caf17-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="caf17-125">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="caf17-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="caf17-126">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="caf17-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="caf17-127">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="caf17-127">Configure an export</span></span>

<span data-ttu-id="caf17-128">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="caf17-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="caf17-129">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="caf17-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="caf17-130">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="caf17-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="caf17-131">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="caf17-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="caf17-132">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Omnisend.</span><span class="sxs-lookup"><span data-stu-id="caf17-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="caf17-133">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="caf17-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="caf17-134">În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="caf17-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="caf17-135">Este necesar să exportați segmente către Omnisend.</span><span class="sxs-lookup"><span data-stu-id="caf17-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="caf17-136">Opțional, puteți exporta Prenume, Nume de familie, Adresă, Țară/Regiune, Stat, Oraș și Cod poștal pentru a crea e-mailuri mai personalizate.</span><span class="sxs-lookup"><span data-stu-id="caf17-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="caf17-137">Selectați **Adăugare atribut** pentru a mapa aceste câmpuri.</span><span class="sxs-lookup"><span data-stu-id="caf17-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="caf17-138">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="caf17-138">Select **Save**.</span></span>

<span data-ttu-id="caf17-139">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="caf17-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="caf17-140">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="caf17-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="caf17-141">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="caf17-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="caf17-142">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="caf17-142">Data privacy and compliance</span></span>

<span data-ttu-id="caf17-143">Când activați Dynamics 365 Customer Insights pentru a transmite date către Ommisend, permiteți transferul de date în afara limitelor de conformitate cu Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi date cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="caf17-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="caf17-144">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Ommisend respectă orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="caf17-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="caf17-145">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="caf17-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="caf17-146">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="caf17-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
