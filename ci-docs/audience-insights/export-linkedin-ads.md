---
title: Exportați datele Customer Insights către Anunțuri LinkedIn
description: Aflați cum să configurați conexiunea și să exportați la Anunțuri LinkedIn.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124539"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="eb66d-103">Exportați segmente în Anunțuri LinkedIn (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="eb66d-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="eb66d-104">Exportați segmente de profiluri de clienți unificate în Anunțuri LinkedIn pentru a crea segmente Matched Audiences.</span><span class="sxs-lookup"><span data-stu-id="eb66d-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="eb66d-105">Utilizați segmentele de Matched Audiences pentru direcționarea către companii și direcționarea prin contact.</span><span class="sxs-lookup"><span data-stu-id="eb66d-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eb66d-106">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="eb66d-106">Prerequisites</span></span>

-   <span data-ttu-id="eb66d-107">Aveți un [Cont LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="eb66d-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="eb66d-108">Aveți [segmente configurate](segments.md) în Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="eb66d-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="eb66d-109">Profilurile de clienți din segmentele exportate conțin un câmp cu o adresă de e-mail.</span><span class="sxs-lookup"><span data-stu-id="eb66d-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="eb66d-110">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="eb66d-110">Known limitations</span></span>

- <span data-ttu-id="eb66d-111">Puteți exporta până la 100.000 de profiluri per export către Anunțuri LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="eb66d-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="eb66d-112">Exportul către Anunțuri LinkedIn este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="eb66d-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="eb66d-113">Se exportă până la 100.000 de profiluri pe Anunțuri LinkedIn poate dura până la 10 minute.</span><span class="sxs-lookup"><span data-stu-id="eb66d-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="eb66d-114">Configurați conexiunea la spațiul de Anunțuri LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="eb66d-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="eb66d-115">În statisticile publicului, accesați **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="eb66d-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="eb66d-116">Selectați **Adăugați conexiune** și alegeți **Anunțuri LinkedIn** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="eb66d-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="eb66d-117">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="eb66d-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="eb66d-118">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="eb66d-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="eb66d-119">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="eb66d-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="eb66d-120">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="eb66d-120">Choose who can use this connection.</span></span> <span data-ttu-id="eb66d-121">Dacă nu luați nicio măsură, valoarea implicită este Administratori.</span><span class="sxs-lookup"><span data-stu-id="eb66d-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="eb66d-122">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="eb66d-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="eb66d-123">Furnizați-vă [ID-ul de cont LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="eb66d-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="eb66d-124">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="eb66d-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="eb66d-125">Selectați **Conectați** pentru a inițializa conexiunea la Monitor de campanie.</span><span class="sxs-lookup"><span data-stu-id="eb66d-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="eb66d-126">Selectați **Autentificare cu LinkedIn** și furnizați acreditările de administrator pentru LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="eb66d-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="eb66d-127">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="eb66d-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="eb66d-128">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="eb66d-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="eb66d-129">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="eb66d-129">Configure an export</span></span>

<span data-ttu-id="eb66d-130">Puteți configura un export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="eb66d-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="eb66d-131">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="eb66d-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="eb66d-132">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="eb66d-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="eb66d-133">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="eb66d-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="eb66d-134">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="eb66d-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="eb66d-135">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="eb66d-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="eb66d-136">Alegeți dacă doriți să exportați date pentru a face [direcționarea prin contact](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) sau [direcționarea către companii](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) pe LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="eb66d-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="eb66d-137">În secțiunea **Potrivirea datelor** selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="eb66d-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="eb66d-138">Este necesar să exportați segmente către Anunțuri LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="eb66d-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="eb66d-139">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="eb66d-139">Select the segments you want to export.</span></span> <span data-ttu-id="eb66d-140">Publicul potrivit Matched audiences din LinkedIn Campaign Manager va fi creat automat cu numele segmentelor pe care le-ați selectat pentru export.</span><span class="sxs-lookup"><span data-stu-id="eb66d-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="eb66d-141">Fiecare segment va avea ca rezultat un public separat Matched audience.</span><span class="sxs-lookup"><span data-stu-id="eb66d-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="eb66d-142">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="eb66d-142">Select **Save**.</span></span>

<span data-ttu-id="eb66d-143">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="eb66d-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="eb66d-144">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="eb66d-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="eb66d-145">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="eb66d-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="eb66d-146">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="eb66d-146">Data privacy and compliance</span></span>

<span data-ttu-id="eb66d-147">Când activați Dynamics 365 Customer Insights pentru a transmite date către Anunțuri LinkedIn, permiteți transferul de date în afara limitelor de conformitate cu Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi date cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="eb66d-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="eb66d-148">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Anunțuri LinkedIn respectă orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="eb66d-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="eb66d-149">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="eb66d-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="eb66d-150">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="eb66d-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
