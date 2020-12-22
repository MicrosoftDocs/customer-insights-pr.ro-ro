---
title: Exportați datele Customer Insights către DotDigital
description: Aflați cum să configurați conexiunea la DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644463"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="858bf-103">Conector pentru DotDigital (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="858bf-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="858bf-104">Exportați segmente de profiluri de clienți unificate în agende DotDigital și folosiți-le pentru campanii, marketing prin e-mail și pentru a crea segmente de clienți cu DotDigital.</span><span class="sxs-lookup"><span data-stu-id="858bf-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="858bf-105">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="858bf-105">Prerequisites</span></span>

-   <span data-ttu-id="858bf-106">Aveți un [cont DotDigital](https://dotdigital.com/) și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="858bf-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="858bf-107">Există agende în DotDigital și ID-urile corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="858bf-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="858bf-108">ID-ul poate fi găsit în adresa URL atunci când selectați și deschideți o agendă.</span><span class="sxs-lookup"><span data-stu-id="858bf-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="858bf-109">Pentru mai multe informații, consultați [Agende DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="858bf-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="858bf-110">Aveți [segmente configurate](segments.md) în Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="858bf-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="858bf-111">Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.</span><span class="sxs-lookup"><span data-stu-id="858bf-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="858bf-112">Conectarea la DotDigital</span><span class="sxs-lookup"><span data-stu-id="858bf-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="858bf-113">Accesați **Administrator** > **Destinații de export**.</span><span class="sxs-lookup"><span data-stu-id="858bf-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="858bf-114">Sub **DotDigital**, selectați **Configurare**.</span><span class="sxs-lookup"><span data-stu-id="858bf-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="858bf-115">Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="858bf-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Panoul de configurare pentru exportul DotDigital.":::

1. <span data-ttu-id="858bf-117">Introduceți **numele de utilizator și parola DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="858bf-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="858bf-118">Introduceți **[ID-ul agendei DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="858bf-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="858bf-119">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="858bf-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="858bf-120">Selectați **Conectare** pentru a inițializa conexiunea la DotDigital.</span><span class="sxs-lookup"><span data-stu-id="858bf-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="858bf-121">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="858bf-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="858bf-122">Selectați **Continuare** pentru a configura exportul.</span><span class="sxs-lookup"><span data-stu-id="858bf-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="858bf-123">Configurați conectorul</span><span class="sxs-lookup"><span data-stu-id="858bf-123">Configure the connector</span></span>

1. <span data-ttu-id="858bf-124">În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="858bf-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="858bf-125">Repetați aceiași pași pentru alte câmpuri opționale, cum ar fi **Prenume**, **Nume de familie**, **Nume complet**, **Gen**, și **Cod poștal**.</span><span class="sxs-lookup"><span data-stu-id="858bf-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="858bf-126">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="858bf-126">Select the segments you want to export.</span></span> <span data-ttu-id="858bf-127">Puteți exporta până la 1 milion de profiluri de client în total către DotDigital.</span><span class="sxs-lookup"><span data-stu-id="858bf-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="858bf-128">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="858bf-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="858bf-129">Exportați datele</span><span class="sxs-lookup"><span data-stu-id="858bf-129">Export the data</span></span>

<span data-ttu-id="858bf-130">Puteți [exporta date la cerere](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="858bf-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="858bf-131">Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="858bf-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="858bf-132">În DotDigital, puteți găsi acum segmentele dvs. în [Agendele DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="858bf-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="858bf-133">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="858bf-133">Known limitations</span></span>

- <span data-ttu-id="858bf-134">Până la 1 milion de profiluri per export către DotDigital.</span><span class="sxs-lookup"><span data-stu-id="858bf-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="858bf-135">Exportul către DotDigital este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="858bf-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="858bf-136">Exportul de segmente cu un total de 1 milion de profiluri poate dura până la 3 ore din cauza limitărilor din partea furnizorului.</span><span class="sxs-lookup"><span data-stu-id="858bf-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="858bf-137">Numărul de profiluri pe care le puteți exporta către DotDigital este dependent și limitat de contractul dvs. cu DotDigital.</span><span class="sxs-lookup"><span data-stu-id="858bf-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="858bf-138">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="858bf-138">Data privacy and compliance</span></span>

<span data-ttu-id="858bf-139">Când activați Dynamics 365 Customer Insights pentru a transmite date către DotDigital, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="858bf-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="858bf-140">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că DotDigital îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="858bf-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="858bf-141">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="858bf-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="858bf-142">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="858bf-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
