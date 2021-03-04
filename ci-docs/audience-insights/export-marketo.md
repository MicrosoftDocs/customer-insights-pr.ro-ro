---
title: Exportați datele Customer Insights către Marketo
description: Aflați cum să configurați conexiunea la Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267096"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="35c69-103">Conector pentru Marketo (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="35c69-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="35c69-104">Exportați segmentele profilurilor client unificate pentru a genera campanii, a oferi marketing prin e-mail și a folosi anumite grupuri de clienți cu Marketo.</span><span class="sxs-lookup"><span data-stu-id="35c69-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="35c69-105">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="35c69-105">Prerequisites</span></span>

-   <span data-ttu-id="35c69-106">Aveți un [cont Marketo](https://login.marketo.com/) și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="35c69-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="35c69-107">Există liste în Marketo și ID-urile corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="35c69-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="35c69-108">Pentru informații suplimentare, consultați [Liste Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="35c69-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="35c69-109">Aveți [segmente configurate](segments.md).</span><span class="sxs-lookup"><span data-stu-id="35c69-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="35c69-110">Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.</span><span class="sxs-lookup"><span data-stu-id="35c69-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="35c69-111">Conectare la Marketo</span><span class="sxs-lookup"><span data-stu-id="35c69-111">Connect to Marketo</span></span>

1. <span data-ttu-id="35c69-112">Accesați **Administrator** > **Destinații de export**.</span><span class="sxs-lookup"><span data-stu-id="35c69-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="35c69-113">Sub **Marketo**, selectați **Configurare**.</span><span class="sxs-lookup"><span data-stu-id="35c69-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="35c69-114">Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="35c69-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="35c69-115">Introduceți **[ID-ul de client Marketo, secretul clientului și Numele de gazdă punct final REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="35c69-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="35c69-116">Introduceți **[ID-ul listă Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="35c69-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="35c69-117">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor** și selectați **Conectare** pentru a inițializa conexiunea la Marketo.</span><span class="sxs-lookup"><span data-stu-id="35c69-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="35c69-118">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="35c69-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Exportați captura de ecran pentru conexiunea Marketo":::

1. <span data-ttu-id="35c69-120">Selectați **Continuare** pentru a configura exportul.</span><span class="sxs-lookup"><span data-stu-id="35c69-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="35c69-121">Configurați conectorul</span><span class="sxs-lookup"><span data-stu-id="35c69-121">Configure the connector</span></span>

1. <span data-ttu-id="35c69-122">În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="35c69-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="35c69-123">Opțional, puteți exporta **Prenume**, **Nume de familie**, **Oraș**, **Stat**, și **Țară/Regiune** ca câmpuri suplimentare pentru a crea e-mailuri mai personalizate.</span><span class="sxs-lookup"><span data-stu-id="35c69-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="35c69-124">Selectați **Adăugare atribut** pentru a mapa aceste câmpuri.</span><span class="sxs-lookup"><span data-stu-id="35c69-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="35c69-125">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="35c69-125">Select the segments you want to export.</span></span> <span data-ttu-id="35c69-126">Puteți exporta până la 1 milion de profiluri de client în total către Marketo.</span><span class="sxs-lookup"><span data-stu-id="35c69-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Selectați câmpuri și segmente de exportat către Marketo":::

1. <span data-ttu-id="35c69-128">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="35c69-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="35c69-129">Exportați datele</span><span class="sxs-lookup"><span data-stu-id="35c69-129">Export the data</span></span>

<span data-ttu-id="35c69-130">Puteți [exporta date la cerere](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="35c69-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="35c69-131">Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="35c69-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="35c69-132">În Marketo, puteți găsi acum segmentele dvs. sub [Listele Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="35c69-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="35c69-133">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="35c69-133">Known limitations</span></span>

- <span data-ttu-id="35c69-134">Până la 1 milion de profiluri per export către Marketo.</span><span class="sxs-lookup"><span data-stu-id="35c69-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="35c69-135">Exportul către Marketo este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="35c69-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="35c69-136">Exportul de segmente cu un total de 1 milion de profiluri poate dura până la 3 ore.</span><span class="sxs-lookup"><span data-stu-id="35c69-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="35c69-137">Numărul de profiluri pe care le puteți exporta către Marketo este dependent și limitat de contractul dvs. cu Marketo.</span><span class="sxs-lookup"><span data-stu-id="35c69-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="35c69-138">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="35c69-138">Data privacy and compliance</span></span>

<span data-ttu-id="35c69-139">Când activați Dynamics 365 Customer Insights pentru a transmite date către Marketo, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="35c69-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="35c69-140">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Marketo îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="35c69-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="35c69-141">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="35c69-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="35c69-142">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="35c69-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]