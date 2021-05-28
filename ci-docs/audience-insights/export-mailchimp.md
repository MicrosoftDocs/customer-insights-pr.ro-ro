---
title: Exportați datele Customer Insights către Mailchimp
description: Aflați cum să configurați conexiunea și să exportați la Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 35848998e738c7ecc1642f2b75912ff78d85f79e
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976170"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="c4826-103">Exportați listele de segmente în Mailchimp (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="c4826-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="c4826-104">Exportați segmente de profiluri unificate ale clienților către Mailchimp pentru a crea buletine informative și campanii de e-mail.</span><span class="sxs-lookup"><span data-stu-id="c4826-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="c4826-105">Cerințe preliminare pentru conexiune</span><span class="sxs-lookup"><span data-stu-id="c4826-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="c4826-106">Aveți un [cont Mailchimp](https://mailchimp.com/) și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="c4826-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c4826-107">Există audiențe în Mailchimp și ID-urile corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="c4826-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="c4826-108">Pentru informații suplimentare, consultați [Audiențe Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="c4826-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="c4826-109">Aveți [segmente configurate](segments.md)</span><span class="sxs-lookup"><span data-stu-id="c4826-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="c4826-110">Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.</span><span class="sxs-lookup"><span data-stu-id="c4826-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c4826-111">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="c4826-111">Known limitations</span></span>

- <span data-ttu-id="c4826-112">Până la 1 milion de profiluri per export către Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="c4826-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="c4826-113">Exportul către Mailchimp este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="c4826-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="c4826-114">Exportarea segmentelor cu 1 milion de profiluri poate dura până la trei ore.</span><span class="sxs-lookup"><span data-stu-id="c4826-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="c4826-115">Numărul de profiluri pe care le puteți exporta către Mailchimp este dependent și limitat de contractul dvs. cu Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="c4826-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="c4826-116">Configurarea conexiunii la Mailchimp</span><span class="sxs-lookup"><span data-stu-id="c4826-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="c4826-117">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="c4826-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c4826-118">Selectați **Adăugați conexiune** și alegeți **Autopilot** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="c4826-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="c4826-119">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="c4826-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c4826-120">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="c4826-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c4826-121">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="c4826-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c4826-122">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="c4826-122">Choose who can use this connection.</span></span> <span data-ttu-id="c4826-123">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="c4826-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c4826-124">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c4826-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c4826-125">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="c4826-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c4826-126">Selectați **Conectați** pentru a inițializa conexiunea la Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="c4826-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="c4826-127">Selectați **Autentificare cu Mailchimp** și furnizați acreditările dvs. Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="c4826-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="c4826-128">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c4826-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c4826-129">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="c4826-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="c4826-130">Configurați conectorul</span><span class="sxs-lookup"><span data-stu-id="c4826-130">Configure the connector</span></span>

<span data-ttu-id="c4826-131">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="c4826-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c4826-132">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c4826-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c4826-133">Faceți salt la **Date**> **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="c4826-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="c4826-134">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="c4826-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c4826-135">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="c4826-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="c4826-136">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="c4826-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c4826-137">Introduceți **[ID public Mailchimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="c4826-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="c4826-138">În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="c4826-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="c4826-139">Opțional, puteți exporta **Prenume** și **Nume de familie** pentru a crea e-mailuri mai personalizate.</span><span class="sxs-lookup"><span data-stu-id="c4826-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="c4826-140">Selectați **Adăugare atribut** pentru a mapa aceste câmpuri.</span><span class="sxs-lookup"><span data-stu-id="c4826-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="c4826-141">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="c4826-141">Select the segments you want to export.</span></span> <span data-ttu-id="c4826-142">Puteți exporta până la 1 milion de profiluri de client în total către Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="c4826-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="c4826-143">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="c4826-143">Select **Save**.</span></span>

<span data-ttu-id="c4826-144">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="c4826-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c4826-145">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c4826-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c4826-146">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c4826-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c4826-147">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="c4826-147">Data privacy and compliance</span></span>

<span data-ttu-id="c4826-148">Când activați Dynamics 365 Customer Insights pentru a transmite date către Mailchimp, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="c4826-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c4826-149">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Mailchimp îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="c4826-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c4826-150">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c4826-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c4826-151">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="c4826-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
