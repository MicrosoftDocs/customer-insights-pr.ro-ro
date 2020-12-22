---
title: Exportați datele Customer Insights către Mailchimp
description: Aflați cum să configurați conexiunea la Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: edff494f6edf26a8b641cb1d788a715389ddb346
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406668"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="36484-103">Conector pentru Mailchimp (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="36484-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="36484-104">Exportați segmente de profiluri unificate ale clienților către Mailchimp pentru a crea buletine informative și campanii de e-mail.</span><span class="sxs-lookup"><span data-stu-id="36484-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="36484-105">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="36484-105">Prerequisites</span></span>

-   <span data-ttu-id="36484-106">Aveți un [cont Mailchimp](https://mailchimp.com/) și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="36484-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="36484-107">Există audiențe în Mailchimp și ID-urile corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="36484-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="36484-108">Pentru informații suplimentare, consultați [Audiențe Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="36484-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="36484-109">Aveți [segmente configurate](segments.md)</span><span class="sxs-lookup"><span data-stu-id="36484-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="36484-110">Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.</span><span class="sxs-lookup"><span data-stu-id="36484-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="36484-111">Conectare la Mailchimp</span><span class="sxs-lookup"><span data-stu-id="36484-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="36484-112">Accesați **Administrator** > **Destinații de export**.</span><span class="sxs-lookup"><span data-stu-id="36484-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="36484-113">Sub **Mailchimp**, selectați **Configurare**.</span><span class="sxs-lookup"><span data-stu-id="36484-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="36484-114">Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="36484-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="36484-115">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="36484-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="36484-116">Introduceți **[ID-ul de audiență Mailchimp](https://mailchimp.com/help/find-audience-id/)** și selectați **Conectare** pentru a inițializa conexiunea la Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="36484-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="36484-117">Selectați **Autentificare cu Mailchimp** și furnizați acreditările dvs. Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="36484-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="36484-118">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="36484-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Exportați captura de ecran pentru conexiunea Mailchimp":::

1. <span data-ttu-id="36484-120">Selectați **Continuare** pentru a configura exportul.</span><span class="sxs-lookup"><span data-stu-id="36484-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="36484-121">Configurați conectorul</span><span class="sxs-lookup"><span data-stu-id="36484-121">Configure the connector</span></span>

1. <span data-ttu-id="36484-122">În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="36484-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="36484-123">Opțional, puteți exporta **Prenume** și **Nume de familie** ca câmpuri suplimentare pentru a crea e-mailuri mai personalizate.</span><span class="sxs-lookup"><span data-stu-id="36484-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="36484-124">Selectați **Adăugare atribut** pentru a mapa aceste câmpuri.</span><span class="sxs-lookup"><span data-stu-id="36484-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="36484-125">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="36484-125">Select the segments you want to export.</span></span> <span data-ttu-id="36484-126">Puteți exporta până la 1 milion de profiluri de client în total către Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="36484-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Selectați câmpuri și segmente de exportat către Mailchimp":::

1. <span data-ttu-id="36484-128">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="36484-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="36484-129">Exportați datele</span><span class="sxs-lookup"><span data-stu-id="36484-129">Export the data</span></span>

<span data-ttu-id="36484-130">Puteți [exporta date la cerere](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="36484-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="36484-131">Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="36484-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="36484-132">În Mailchimp, puteți găsi acum segmentele dvs. sub [Audiențele Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="36484-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="36484-133">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="36484-133">Known limitations</span></span>

- <span data-ttu-id="36484-134">Până la 1 milion de profiluri per export către Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="36484-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="36484-135">Exportul către Mailchimp este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="36484-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="36484-136">Exportul de segmente cu un total de 1 milion de profiluri poate dura până la trei ore datorită limitărilor din partea furnizorului.</span><span class="sxs-lookup"><span data-stu-id="36484-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="36484-137">Numărul de profiluri pe care le puteți exporta către Mailchimp este dependent și limitat de contractul dvs. cu Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="36484-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="36484-138">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="36484-138">Data privacy and compliance</span></span>

<span data-ttu-id="36484-139">Când activați Dynamics 365 Customer Insights pentru a transmite date către Mailchimp, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="36484-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="36484-140">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Mailchimp îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="36484-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="36484-141">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="36484-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="36484-142">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="36484-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
