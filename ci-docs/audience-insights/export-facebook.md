---
title: Exportați datele Customer Insights către Facebook Ads Manager
description: Aflați cum să configurați conexiunea și să exportați la Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e20c7b7fd3989d7621cb7765f38b85c8ab4adfcb
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305125"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="01d35-103">Exportați lista de segmente în Facebook Ads Manager (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="01d35-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="01d35-104">Exportați segmente de profiluri de client unificate către Managerul de reclame Facebook pentru a crea campanii pe Facebook și Instagram.</span><span class="sxs-lookup"><span data-stu-id="01d35-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="01d35-105">Cerințe preliminare pentru conexiune</span><span class="sxs-lookup"><span data-stu-id="01d35-105">Prerequisites for connection</span></span>

- <span data-ttu-id="01d35-106">Trebuie să aveți un [**Cont Facebook Ads**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) care include un [**Cont Facebook Business**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="01d35-106">You need to have a [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="01d35-107">Trebuie să fiți administrator pe [**Contul Facebook Ads**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="01d35-107">You need to be an administrator on the [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="01d35-108">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="01d35-108">Known limitations</span></span>

- <span data-ttu-id="01d35-109">Până la 10 milioane de profiluri de clienți pe export către Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="01d35-109">Up to 10 million customer profiles per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="01d35-110">Exportul către Facebook Ads Manager este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="01d35-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="01d35-111">Creați sau actualizați segmente de public personalizate în Facebook de tip doar *lista de clienți*.</span><span class="sxs-lookup"><span data-stu-id="01d35-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="01d35-112">Exportul de segmente cu un total de 10 milion de profiluri poate dura până la 90 de minute până la finalizare.</span><span class="sxs-lookup"><span data-stu-id="01d35-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="01d35-113">Configurarea conexiunii la Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="01d35-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="01d35-114">Înainte ca utilizatorii să poată crea un export, un administrator trebuie să configureze conexiunea la serviciu și să permită contribuitorilor să utilizeze conexiunea.</span><span class="sxs-lookup"><span data-stu-id="01d35-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="01d35-115">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="01d35-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="01d35-116">Selectați **Adăugați conexiune** și alegeți **Facebook Ads Manager** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="01d35-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="01d35-117">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="01d35-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="01d35-118">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="01d35-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="01d35-119">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="01d35-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="01d35-120">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="01d35-120">Choose who can use this connection.</span></span> <span data-ttu-id="01d35-121">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="01d35-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="01d35-122">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="01d35-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="01d35-123">Autentificare cu Facebook Ads:</span><span class="sxs-lookup"><span data-stu-id="01d35-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="01d35-124">Selectați **Continuați cu Facebook** pentru a vă conecta la contul Facebook Ads.</span><span class="sxs-lookup"><span data-stu-id="01d35-124">Select **Continue with Facebook** to sign in to your Facebook Ads account.</span></span>

   1. <span data-ttu-id="01d35-125">Acceptați permisiunea **ads_management** după autentificare cu Facebook.</span><span class="sxs-lookup"><span data-stu-id="01d35-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="01d35-126">Selectați **Contul publicitar Facebook** cu care doriți să lucrați.</span><span class="sxs-lookup"><span data-stu-id="01d35-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="01d35-127">Selectați un **Public particularizat existent** din lista derulantă sau creați un **Public nou particularizat**.</span><span class="sxs-lookup"><span data-stu-id="01d35-127">Select an **Existing custom audience** from the dropdown list or create a **New custom audience**.</span></span> <span data-ttu-id="01d35-128">Pentru mai multe informații, consultați [**Publicuri în Managerul de reclame Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="01d35-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="01d35-129">Puteți crea sau actualiza numai segmente de public personalizate pe Facebook de tipul *lista de clienți* cu acest export.</span><span class="sxs-lookup"><span data-stu-id="01d35-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="01d35-130">În unele cazuri, vedeți segmente de public particularizate de diferite tipuri în lista derulantă.</span><span class="sxs-lookup"><span data-stu-id="01d35-130">In some cases, you see custom audiences of different types in the dropdown list.</span></span> <span data-ttu-id="01d35-131">Selectarea unui alt tip decât *lista de clienți* va duce la un eșec al exportului.</span><span class="sxs-lookup"><span data-stu-id="01d35-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="01d35-132">Examinați **Confidențialitatea și conformitatea datelor** și selectați **De acord**.</span><span class="sxs-lookup"><span data-stu-id="01d35-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="01d35-133">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="01d35-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="01d35-134">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="01d35-134">Configure an export</span></span>

<span data-ttu-id="01d35-135">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="01d35-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="01d35-136">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="01d35-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="01d35-137">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="01d35-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="01d35-138">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="01d35-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="01d35-139">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="01d35-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="01d35-140">Dacă nu vedeți numele acestei secțiuni, atunci nu aveți la dispoziție conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="01d35-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="01d35-141">În **Alegeți câmpul dvs. de identificare cheie**, selectați **E-mail**, **Nume și adresă** sau **Telefon** pentru a trimite la Managerul de reclame Facebook.</span><span class="sxs-lookup"><span data-stu-id="01d35-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="01d35-142">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="01d35-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="01d35-143">Mapați atributele corespunzătoare de la entitatea clientului dvs. unificat pentru identificatorul de cheie selectat.</span><span class="sxs-lookup"><span data-stu-id="01d35-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > [!TIP]
   > <span data-ttu-id="01d35-144">Cele mai bune șanse pentru o corespondență apar dacă selectați **E-mail** ca identificator cheie.</span><span class="sxs-lookup"><span data-stu-id="01d35-144">The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="01d35-145">Adăugarea identificatorilor suplimentari poate îmbunătăți corespondența.</span><span class="sxs-lookup"><span data-stu-id="01d35-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="01d35-146">Selectați **Adăugați un atribut** pentru a mapa mai multe atribute de trimis către Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="01d35-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="01d35-147">Atributele din Facebook Ads Manager mapează la următoarele nume ușor de utilizat: **FN** = **Prenume**, **LN** = **Nume de familie**, **FI** = **Prima inițială**, **TELEFON** = **Telefon**, **GEN** = **Gen**, **DOB** = **Data nașterii**, **ST** = **Statul**, **CT** = **Oraș**, **ZIP** = **Cod poștal**, **ȚARA** = **Țară/Regiune**</span><span class="sxs-lookup"><span data-stu-id="01d35-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / ZIP Code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="01d35-148">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="01d35-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="01d35-149">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="01d35-149">Select **Save**.</span></span>

<span data-ttu-id="01d35-150">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="01d35-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="01d35-151">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="01d35-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="01d35-152">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="01d35-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="01d35-153">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="01d35-153">Data privacy and compliance</span></span>

<span data-ttu-id="01d35-154">Când activați Dynamics 365 Customer Insights pentru a transmite date către Facebook Ads Manager, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="01d35-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="01d35-155">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Facebook Ads îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="01d35-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="01d35-156">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="01d35-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="01d35-157">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="01d35-157">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
