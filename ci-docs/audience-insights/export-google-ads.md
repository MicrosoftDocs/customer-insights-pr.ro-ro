---
title: Exportați datele Customer Insights către Google Ads
description: Aflați cum să configurați conexiunea și să exportați la Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976333"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="99134-103">Exportați segmente în Google Ads (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="99134-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="99134-104">Exportați segmente de profiluri de clienți unificate în lista de audiență Google Ads și folosiți-le pentru publicitate în Căutarea Google, Gmail, YouTube și Rețeaua de vizualizare Google.</span><span class="sxs-lookup"><span data-stu-id="99134-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="99134-105">Cerințe preliminare pentru conexiune</span><span class="sxs-lookup"><span data-stu-id="99134-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="99134-106">Aveți un [cont Google Ads](https://ads.google.com/) și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="99134-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="99134-107">Aveți [aprobat un token pentru dezvoltatori Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="99134-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="99134-108">Îndepliniți cerințele pentru [Politica Customer Match](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="99134-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="99134-109">Îndepliniți cerințele pentru [remarketing al dimensiunilor listei](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="99134-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="99134-110">Există audiențe în Google Ads și ID-urile corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="99134-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="99134-111">Pentru informații suplimentare, consultați [Audiențe Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="99134-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="99134-112">Aveți [segmente configurate](segments.md)</span><span class="sxs-lookup"><span data-stu-id="99134-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="99134-113">Profilurile de clienți unificate din segmentele exportate conțin câmpuri care reprezintă o adresă de e-mail, prenumele și numele de familie</span><span class="sxs-lookup"><span data-stu-id="99134-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="99134-114">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="99134-114">Known limitations</span></span>

- <span data-ttu-id="99134-115">Până la 1 milion de profiluri per export către Google Ads.</span><span class="sxs-lookup"><span data-stu-id="99134-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="99134-116">Exportul către Google Ads este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="99134-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="99134-117">Exportul de segmente cu un total de 1 milion de profiluri poate dura până la 5 minute din cauza limitărilor din partea furnizorului.</span><span class="sxs-lookup"><span data-stu-id="99134-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="99134-118">Potrivirea în Google Ads poate dura până la 48 de ore.</span><span class="sxs-lookup"><span data-stu-id="99134-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="99134-119">Configurarea conexiunii la Google Ads</span><span class="sxs-lookup"><span data-stu-id="99134-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="99134-120">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="99134-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="99134-121">Selectați **Adăugați conexiune** și alegeți **Google Ads** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="99134-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="99134-122">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="99134-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="99134-123">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="99134-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="99134-124">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="99134-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="99134-125">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="99134-125">Choose who can use this connection.</span></span> <span data-ttu-id="99134-126">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="99134-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="99134-127">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="99134-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="99134-128">Introduceți **[ID-ul de client Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="99134-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="99134-129">Introduceți **[Tokenul de dezvoltator aprobat de Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="99134-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="99134-130">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="99134-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="99134-131">Selectați **Autentificare cu Google Ads** și furnizați acreditările dvs. Google Ads.</span><span class="sxs-lookup"><span data-stu-id="99134-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="99134-132">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="99134-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="99134-133">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="99134-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="99134-134">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="99134-134">Configure an export</span></span>

<span data-ttu-id="99134-135">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="99134-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="99134-136">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="99134-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="99134-137">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="99134-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="99134-138">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="99134-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="99134-139">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Google Ads.</span><span class="sxs-lookup"><span data-stu-id="99134-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="99134-140">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="99134-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="99134-141">Introduceți **[ID-ul de audiență Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** și selectați **Conectare** pentru a inițializa conexiunea la Google Ads.</span><span class="sxs-lookup"><span data-stu-id="99134-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="99134-142">În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="99134-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="99134-143">Repetați aceiași pași pentru câmpurile **Prenume** și **Nume de familie**.</span><span class="sxs-lookup"><span data-stu-id="99134-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="99134-144">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="99134-144">Select the segments you want to export.</span></span> <span data-ttu-id="99134-145">Puteți exporta până la 1 milion de profiluri de client în total către Google Ads.</span><span class="sxs-lookup"><span data-stu-id="99134-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="99134-146">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="99134-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="99134-147">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="99134-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="99134-148">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="99134-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="99134-149">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="99134-149">Data privacy and compliance</span></span>

<span data-ttu-id="99134-150">Când activați Dynamics 365 Customer Insights pentru a transmite date către Google Ads, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="99134-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="99134-151">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Google Ads îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="99134-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="99134-152">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="99134-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="99134-153">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="99134-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
