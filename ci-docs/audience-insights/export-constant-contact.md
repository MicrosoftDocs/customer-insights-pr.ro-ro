---
title: Exportați datele Customer Insights către Constant Contact
description: Aflați cum să configurați conexiunea și exportul la Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760611"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a><span data-ttu-id="88f48-103">Exportați listele de segmente în Constant Contact (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="88f48-103">Export segment lists to Constant Contact (preview)</span></span>

<span data-ttu-id="88f48-104">Exportați segmente de profiluri de clienți unificate în Constant Contact și folosiți-le pentru activități de marketing.</span><span class="sxs-lookup"><span data-stu-id="88f48-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="88f48-105">Cerințe preliminare pentru o conexiune</span><span class="sxs-lookup"><span data-stu-id="88f48-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="88f48-106">Aveți un [Cont Constant Contact](https://www.constantcontact.com/account-home) și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="88f48-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="88f48-107">Aveți [segmente configurate](segments.md) în Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="88f48-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="88f48-108">Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.</span><span class="sxs-lookup"><span data-stu-id="88f48-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="88f48-109">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="88f48-109">Known limitations</span></span>

- <span data-ttu-id="88f48-110">Puteți exporta până la 1 milion de profiluri per export către Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="88f48-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="88f48-111">Exportul către Constant Contact este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="88f48-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="88f48-112">Exportul de până la 1 milion de profiluri pe Constant Contact poate dura până la 1 oră.</span><span class="sxs-lookup"><span data-stu-id="88f48-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="88f48-113">Numărul de profiluri pe care le puteți exporta în Constant Contact depinde și este limitat de contractul dvs. cu Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="88f48-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="88f48-114">Configurați conexiunea la Constant Contact</span><span class="sxs-lookup"><span data-stu-id="88f48-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="88f48-115">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="88f48-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="88f48-116">Selectați **Adăugați conexiune** și alegeți **Constant Contact** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="88f48-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="88f48-117">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="88f48-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="88f48-118">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="88f48-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="88f48-119">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="88f48-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="88f48-120">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="88f48-120">Choose who can use this connection.</span></span> <span data-ttu-id="88f48-121">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="88f48-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="88f48-122">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="88f48-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="88f48-123">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="88f48-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="88f48-124">Selectați **Conectați** pentru a inițializa conexiunea la Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="88f48-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="88f48-125">Selectați **Autentificare cu AdRoll** și furnizați acreditările de administrator pentru Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="88f48-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="88f48-126">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="88f48-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="88f48-127">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="88f48-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="88f48-128">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="88f48-128">Configure an export</span></span>

<span data-ttu-id="88f48-129">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="88f48-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="88f48-130">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="88f48-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="88f48-131">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="88f48-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="88f48-132">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="88f48-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="88f48-133">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="88f48-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="88f48-134">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="88f48-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="88f48-135">Introduceți [**ID-ul listei de Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="88f48-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="88f48-136">Deschideți o listă în Constant Contact pentru a găsi ID-ul listei în URL.</span><span class="sxs-lookup"><span data-stu-id="88f48-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="88f48-137">În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="88f48-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="88f48-138">Este necesar să exportați segmente către Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="88f48-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="88f48-139">Opțional, puteți exporta Prenume și Nume de familie ca câmpuri suplimentare pentru a crea e-mailuri mai personalizate.</span><span class="sxs-lookup"><span data-stu-id="88f48-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="88f48-140">Selectați **Adăugare atribut** pentru a mapa aceste câmpuri.</span><span class="sxs-lookup"><span data-stu-id="88f48-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="88f48-141">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="88f48-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="88f48-142">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="88f48-142">Select **Save**.</span></span>

<span data-ttu-id="88f48-143">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="88f48-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="88f48-144">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="88f48-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="88f48-145">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="88f48-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="88f48-146">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="88f48-146">Data privacy and compliance</span></span>

<span data-ttu-id="88f48-147">Când activați Dynamics 365 Customer Insights pentru a transmite date către Constant Contact, permiteți transferul de date în afara limitelor de conformitate cu Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi date cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="88f48-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="88f48-148">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Constant Contact respectă orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="88f48-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="88f48-149">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="88f48-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="88f48-150">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="88f48-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
