---
title: Exportați datele Customer Insights către SendGrid
description: Aflați cum să configurați conexiunea la SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597296"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="431a0-103">Conector pentru SendGrid (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="431a0-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="431a0-104">Exportați segmente de profiluri unificate ale clienților în SendGrid și utilizați-le pentru campanii și marketing prin e-mail în SendGrid.</span><span class="sxs-lookup"><span data-stu-id="431a0-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="431a0-105">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="431a0-105">Prerequisites</span></span>

-   <span data-ttu-id="431a0-106">Aveți un [cont SendGrid](https://sendgrid.com/) și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="431a0-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="431a0-107">Există liste de persoane de contact în SendGrid și ID-urile corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="431a0-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="431a0-108">Pentru mai multe informații, consultați [SendGrid - Gestionați persoanele de contact](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="431a0-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="431a0-109">Aveți [segmente configurate](segments.md) în Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="431a0-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="431a0-110">Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.</span><span class="sxs-lookup"><span data-stu-id="431a0-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="431a0-111">Conectare la SendGrid</span><span class="sxs-lookup"><span data-stu-id="431a0-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="431a0-112">Accesați **Administrator** > **Destinații de export**.</span><span class="sxs-lookup"><span data-stu-id="431a0-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="431a0-113">Sub **SendGrid**, selectați **Configurare**.</span><span class="sxs-lookup"><span data-stu-id="431a0-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="431a0-114">Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="431a0-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Panoul de configurare pentru exportul SendGrid.":::

1. <span data-ttu-id="431a0-116">Introduceți **Cheia API SendGrid** [Cheia API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="431a0-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="431a0-117">Introduceți **[ID-ul listă SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="431a0-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="431a0-118">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="431a0-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="431a0-119">Selectați **Conectare** pentru a inițializa conexiunea la SendGrid.</span><span class="sxs-lookup"><span data-stu-id="431a0-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="431a0-120">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="431a0-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="431a0-121">Selectați **Continuare** pentru a configura exportul.</span><span class="sxs-lookup"><span data-stu-id="431a0-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="431a0-122">Configurați conectorul</span><span class="sxs-lookup"><span data-stu-id="431a0-122">Configure the connector</span></span>

1. <span data-ttu-id="431a0-123">În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="431a0-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="431a0-124">Repetați aceiași pași pentru alte câmpuri opționale precum **Prenume**, **Nume**, **Țară/Regiune**, **Stare**, **Oraș** și **Cod poștal**.</span><span class="sxs-lookup"><span data-stu-id="431a0-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="431a0-125">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="431a0-125">Select the segments you want to export.</span></span> <span data-ttu-id="431a0-126">Ferm **recomandăm să nu exportați mai mult de 100.000 de profiluri de clienți în total** la SendGrid.</span><span class="sxs-lookup"><span data-stu-id="431a0-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="431a0-127">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="431a0-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="431a0-128">Exportați datele</span><span class="sxs-lookup"><span data-stu-id="431a0-128">Export the data</span></span>

<span data-ttu-id="431a0-129">Puteți [exporta date la cerere](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="431a0-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="431a0-130">Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="431a0-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="431a0-131">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="431a0-131">Known limitations</span></span>

- <span data-ttu-id="431a0-132">Până la 100.000 de profiluri în total la SendGrid.</span><span class="sxs-lookup"><span data-stu-id="431a0-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="431a0-133">Exportul către SendGrid este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="431a0-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="431a0-134">Exportul până la 100'000 de profiluri către SendGrid poate dura până la câteva ore.</span><span class="sxs-lookup"><span data-stu-id="431a0-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="431a0-135">Numărul de profiluri pe care le puteți exporta către SendGrid este dependent și limitat de contractul dvs. cu SendGrid.</span><span class="sxs-lookup"><span data-stu-id="431a0-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="431a0-136">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="431a0-136">Data privacy and compliance</span></span>

<span data-ttu-id="431a0-137">Când activați Dynamics 365 Customer Insights pentru a transmite date către SendGrid, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="431a0-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="431a0-138">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că SendGrid îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="431a0-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="431a0-139">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="431a0-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="431a0-140">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="431a0-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]