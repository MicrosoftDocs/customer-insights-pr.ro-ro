---
title: Exportați datele Customer Insights către Facebook Ads Manager
description: Aflați cum puteți configura conexiunea la Managerul de reclame Facebook.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269989"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="6f900-103">Conector pentru Managerul de reclame Facebook (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="6f900-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="6f900-104">Exportați segmente de profiluri de client unificate către Managerul de reclame Facebook pentru a crea campanii pe Facebook și Instagram.</span><span class="sxs-lookup"><span data-stu-id="6f900-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6f900-105">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="6f900-105">Prerequisites</span></span>

- <span data-ttu-id="6f900-106">Trebuie să aveți un [**Facebook Cont publicitar**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) care include un [**Facebook Cont de afaceri**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="6f900-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="6f900-107">Trebuie să fiți administrator pe [**Facebook Contul publicitar**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="6f900-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="6f900-108">Conectați-vă la Managerul de reclame Facebook</span><span class="sxs-lookup"><span data-stu-id="6f900-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="6f900-109">Accesați **Administrator** > **Destinații de export**.</span><span class="sxs-lookup"><span data-stu-id="6f900-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6f900-110">Sub Managerul de reclame **Facebook**, selectați **Configurat**.</span><span class="sxs-lookup"><span data-stu-id="6f900-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="6f900-111">Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="6f900-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="6f900-112">Selectați **Continuă cu Facebook** pentru a vă conecta la Contul dvs. publicitar Facebook.</span><span class="sxs-lookup"><span data-stu-id="6f900-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="6f900-113">Acceptați permisiunea **ads_management** după autentificare cu Facebook.</span><span class="sxs-lookup"><span data-stu-id="6f900-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="6f900-114">Selectați **Contul publicitar Facebook** cu care doriți să lucrați.</span><span class="sxs-lookup"><span data-stu-id="6f900-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="6f900-115">Selectați un **Public personalizat existent** din lista derulantă sau creați un **Public personalizat nou**.</span><span class="sxs-lookup"><span data-stu-id="6f900-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="6f900-116">Pentru mai multe informații, consultați [**Publicuri în Managerul de reclame Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="6f900-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="6f900-117">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="6f900-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6f900-118">Selectați **Continuare** pentru a configura exportul.</span><span class="sxs-lookup"><span data-stu-id="6f900-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="6f900-119">Configurați conectorul</span><span class="sxs-lookup"><span data-stu-id="6f900-119">Configure the connector</span></span>

1. <span data-ttu-id="6f900-120">În **Alegeți câmpul dvs. de identificare cheie**, selectați **E-mail**, **Nume și adresă** sau **Telefon** pentru a trimite la Managerul de reclame Facebook.</span><span class="sxs-lookup"><span data-stu-id="6f900-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="6f900-121">Mapați atributele corespunzătoare de la entitatea clientului dvs. unificat pentru identificatorul de cheie selectat.</span><span class="sxs-lookup"><span data-stu-id="6f900-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="6f900-122">[TIP] Cele mai bune șanse pentru o corespondență apar dacă selectați **E-mail** ca identificator cheie.</span><span class="sxs-lookup"><span data-stu-id="6f900-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="6f900-123">Adăugarea identificatorilor suplimentari poate îmbunătăți corespondența.</span><span class="sxs-lookup"><span data-stu-id="6f900-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="6f900-124">Selectați **Adăugați atributul** pentru a mapa atribute suplimentare pentru a trimite la Managerul de reclame Facebook.</span><span class="sxs-lookup"><span data-stu-id="6f900-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="6f900-125">Atributele din Manager de reclame Facebook mapează la următoarele nume ușor de utilizat: **FN** = **Prenume**, **LN** = **Nume de familie**, **FI** = **Prima inițială**, **TELEFON** = **Telefon**, **GEN** = **Gen**, **DOB** = **Data nașterii**, **ST** = **Statul**, **CT** = **Oraș**, **ZIP** = **Cod poștal / Zip code**, **ȚARA** = **Tara / Regiunea**</span><span class="sxs-lookup"><span data-stu-id="6f900-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="6f900-126">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="6f900-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="6f900-127">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="6f900-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="6f900-128">Exportați datele</span><span class="sxs-lookup"><span data-stu-id="6f900-128">Export the data</span></span>

<span data-ttu-id="6f900-129">Puteți [exporta date la cerere](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="6f900-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="6f900-130">Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6f900-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6f900-131">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="6f900-131">Known limitations</span></span>

- <span data-ttu-id="6f900-132">Profil de client de până la 10 milioane pe export către Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="6f900-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="6f900-133">Exportul către Facebook Ads Manager este limitat la segmente</span><span class="sxs-lookup"><span data-stu-id="6f900-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="6f900-134">Exportul de segmente cu un total de 10 milion de profiluri poate dura până la 90 de minute până la finalizare.</span><span class="sxs-lookup"><span data-stu-id="6f900-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6f900-135">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="6f900-135">Data privacy and compliance</span></span>

<span data-ttu-id="6f900-136">Când activați Dynamics 365 Customer Insights pentru a transmite date către Facebook Ads Manager, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="6f900-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6f900-137">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Facebook Ads îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="6f900-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="6f900-138">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6f900-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6f900-139">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="6f900-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]