---
title: Exportați datele Customer Insights către SendGrid
description: Aflați cum să configurați conexiunea și să exportați la SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759780"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="a47f6-103">Exportați segmente către SendGrid (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="a47f6-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="a47f6-104">Exportați segmente de profiluri unificate ale clienților în SendGrid și utilizați-le pentru campanii și marketing prin e-mail în SendGrid.</span><span class="sxs-lookup"><span data-stu-id="a47f6-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="a47f6-105">Cerințe preliminare pentru o conexiune</span><span class="sxs-lookup"><span data-stu-id="a47f6-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="a47f6-106">Aveți un [cont SendGrid](https://sendgrid.com/) și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="a47f6-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a47f6-107">Există liste de persoane de contact în SendGrid și ID-urile corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="a47f6-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="a47f6-108">Pentru mai multe informații, consultați [SendGrid - Gestionați persoanele de contact](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="a47f6-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="a47f6-109">Aveți [segmente configurate](segments.md) în Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="a47f6-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a47f6-110">Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.</span><span class="sxs-lookup"><span data-stu-id="a47f6-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a47f6-111">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="a47f6-111">Known limitations</span></span>

- <span data-ttu-id="a47f6-112">Până la 100.000 de profiluri în total la SendGrid.</span><span class="sxs-lookup"><span data-stu-id="a47f6-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="a47f6-113">Exportul către SendGrid este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="a47f6-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="a47f6-114">Exportul până la 100'000 de profiluri către SendGrid poate dura până la câteva ore.</span><span class="sxs-lookup"><span data-stu-id="a47f6-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="a47f6-115">Numărul de profiluri pe care le puteți exporta către SendGrid este dependent și limitat de contractul dvs. cu SendGrid.</span><span class="sxs-lookup"><span data-stu-id="a47f6-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="a47f6-116">Configurarea conexiunii la SendGrid</span><span class="sxs-lookup"><span data-stu-id="a47f6-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="a47f6-117">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="a47f6-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a47f6-118">Selectați **Adăugați conexiune** și alegeți **SendGrid** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="a47f6-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="a47f6-119">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="a47f6-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a47f6-120">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="a47f6-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a47f6-121">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="a47f6-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a47f6-122">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="a47f6-122">Choose who can use this connection.</span></span> <span data-ttu-id="a47f6-123">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="a47f6-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a47f6-124">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a47f6-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a47f6-125">Introduceți **Cheia API SendGrid** [Cheia API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="a47f6-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="a47f6-126">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="a47f6-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a47f6-127">Selectați **Conectare** pentru a inițializa conexiunea la SendGrid.</span><span class="sxs-lookup"><span data-stu-id="a47f6-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="a47f6-128">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a47f6-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a47f6-129">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="a47f6-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a47f6-130">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="a47f6-130">Configure an export</span></span>

<span data-ttu-id="a47f6-131">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="a47f6-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a47f6-132">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a47f6-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a47f6-133">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="a47f6-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a47f6-134">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="a47f6-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a47f6-135">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea SendGrid.</span><span class="sxs-lookup"><span data-stu-id="a47f6-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="a47f6-136">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="a47f6-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a47f6-137">Introduceți **[ID-ul listă SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="a47f6-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="a47f6-138">În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="a47f6-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a47f6-139">Repetați aceiași pași pentru alte câmpuri opționale precum **Prenume**, **Nume**, **Țară/Regiune**, **Stare**, **Oraș** și **Cod poștal**.</span><span class="sxs-lookup"><span data-stu-id="a47f6-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="a47f6-140">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="a47f6-140">Select the segments you want to export.</span></span> <span data-ttu-id="a47f6-141">Ferm **recomandăm să nu exportați mai mult de 100.000 de profiluri de clienți în total** la SendGrid.</span><span class="sxs-lookup"><span data-stu-id="a47f6-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="a47f6-142">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="a47f6-142">Select **Save**.</span></span>

<span data-ttu-id="a47f6-143">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="a47f6-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a47f6-144">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a47f6-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a47f6-145">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a47f6-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a47f6-146">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="a47f6-146">Data privacy and compliance</span></span>

<span data-ttu-id="a47f6-147">Când activați Dynamics 365 Customer Insights pentru a transmite date către SendGrid, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="a47f6-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a47f6-148">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că SendGrid îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="a47f6-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="a47f6-149">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a47f6-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a47f6-150">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="a47f6-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]