---
title: Exportați datele Customer Insights către Sendinblue
description: Aflați cum să configurați conexiunea și să exportați către Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314661"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="ce154-103">Exportați segmente în Sendinblue (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="ce154-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="ce154-104">Exportațio segmentele profilelor unificate de client pentru a genera campanii, a furniza marketing de e-mail și utiliza grupuri specifice de clienți cu Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="ce154-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="ce154-105">Cerințe preliminare pentru conexiune</span><span class="sxs-lookup"><span data-stu-id="ce154-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="ce154-106">Aveți un [Cont Sendinblue](https://www.sendinblue.com/) și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="ce154-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ce154-107">Există liste existente în Sendinblue și ID-urile corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="ce154-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="ce154-108">Aveți [segmente configurate](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ce154-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="ce154-109">Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.</span><span class="sxs-lookup"><span data-stu-id="ce154-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ce154-110">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="ce154-110">Known limitations</span></span>

- <span data-ttu-id="ce154-111">Până la 1 milion de profiluri pe export către Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="ce154-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="ce154-112">Exportul către Sendinblue este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="ce154-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="ce154-113">Exportarea segmentelor cu un total de 1 milion de profiluri poate dura până la 90 de minute.</span><span class="sxs-lookup"><span data-stu-id="ce154-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="ce154-114">Numărul de profiluri pe care le puteți exporta în Sendinblue depinde și este limitat de contractul dvs. cu Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="ce154-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="ce154-115">Configurați conexiunea la Sendinblue</span><span class="sxs-lookup"><span data-stu-id="ce154-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="ce154-116">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="ce154-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ce154-117">Selectați **Adăugați conexiune** și alegeți **Sendinblue** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="ce154-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="ce154-118">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="ce154-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ce154-119">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="ce154-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ce154-120">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="ce154-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ce154-121">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="ce154-121">Choose who can use this connection.</span></span> <span data-ttu-id="ce154-122">În mod implicit, este vorba doar de administratori.</span><span class="sxs-lookup"><span data-stu-id="ce154-122">By default it's only administrators.</span></span> <span data-ttu-id="ce154-123">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ce154-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ce154-124">Introduceți **[Cheia API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="ce154-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="ce154-125">Selectați **Sunt de acord** să confirm **Confidențialitatea și respectarea datelor** și selectați **Conectați** pentru a inițializa conexiunea la Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="ce154-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="ce154-126">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ce154-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ce154-127">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="ce154-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ce154-128">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="ce154-128">Configure an export</span></span>

<span data-ttu-id="ce154-129">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="ce154-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ce154-130">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ce154-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ce154-131">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="ce154-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ce154-132">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="ce154-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ce154-133">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="ce154-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="ce154-134">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="ce154-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ce154-135">Introduceți **ID-ul listei Sendinblue**</span><span class="sxs-lookup"><span data-stu-id="ce154-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="ce154-136">În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="ce154-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="ce154-137">Opțional, puteți exporta **Prenume**, **Nume de familie**, și **Telefon**  pentru a crea e-mailuri mai particularizate.</span><span class="sxs-lookup"><span data-stu-id="ce154-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="ce154-138">Selectați **Adăugare atribut** pentru a mapa aceste câmpuri.</span><span class="sxs-lookup"><span data-stu-id="ce154-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="ce154-139">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="ce154-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="ce154-140">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="ce154-140">Select **Save**.</span></span>

<span data-ttu-id="ce154-141">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="ce154-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ce154-142">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ce154-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ce154-143">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ce154-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ce154-144">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="ce154-144">Data privacy and compliance</span></span>

<span data-ttu-id="ce154-145">Când activați Dynamics 365 Customer Insights pentru a transmite date către Sendinblue, permiteți transfer de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi date cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="ce154-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ce154-146">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru a vă asigura că Sendinblue îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="ce154-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ce154-147">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ce154-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ce154-148">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="ce154-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
