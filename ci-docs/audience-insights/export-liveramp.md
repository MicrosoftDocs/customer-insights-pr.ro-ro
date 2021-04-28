---
title: 'conector LiveRamp '
description: Aflați cum să configurați conexiunea și exportul la LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760342"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="4caca-103">Exportați segmente către LiveRamp&reg; (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="4caca-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="4caca-104">Activați-vă datele din LiveRamp pentru a vă conecta cu peste 500 de platforme din ecosisteme digitale, sociale și de televiziune.</span><span class="sxs-lookup"><span data-stu-id="4caca-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="4caca-105">Lucrați cu datele dvs. în LiveRamp pentru a viza, suprima și personaliza campaniile publicitare.</span><span class="sxs-lookup"><span data-stu-id="4caca-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="4caca-106">Cerințe preliminare pentru o conexiune</span><span class="sxs-lookup"><span data-stu-id="4caca-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="4caca-107">Pentru a utiliza acest conector aveți nevoie de un abonament LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="4caca-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="4caca-108">Pentru a obține un abonament, [contactați LiveRamp](https://liveramp.com/contact/) direct.</span><span class="sxs-lookup"><span data-stu-id="4caca-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="4caca-109">[Aflați mai multe despre Îndrumări LiveRamp](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="4caca-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="4caca-110">Configurarea conexiunii la LiveRamp</span><span class="sxs-lookup"><span data-stu-id="4caca-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="4caca-111">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="4caca-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4caca-112">Selectați **Adăugați conexiune** și alegeți **LiveRamp** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="4caca-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="4caca-113">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="4caca-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4caca-114">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="4caca-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4caca-115">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="4caca-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4caca-116">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="4caca-116">Choose who can use this connection.</span></span> <span data-ttu-id="4caca-117">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="4caca-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="4caca-118">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="4caca-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="4caca-119">Furnizează un **Nume de utilizator** și **Parola** pentru contul dvs. LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="4caca-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="4caca-120">Aceste acreditări pot fi diferite de datele de acreditare Îndrumări LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="4caca-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="4caca-121">Selectați **Verificare** pentru a testa conexiunea la LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="4caca-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="4caca-122">După verificarea cu succes, acordați-vă consimțământul pentru **Confidențialitatea și conformitatea datelor** prin selectarea casetei de selectare **Sunt de acord**.</span><span class="sxs-lookup"><span data-stu-id="4caca-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="4caca-123">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="4caca-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="4caca-124">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="4caca-124">Configure an export</span></span>

<span data-ttu-id="4caca-125">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="4caca-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4caca-126">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="4caca-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4caca-127">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="4caca-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4caca-128">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="4caca-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="4caca-129">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="4caca-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="4caca-130">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="4caca-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="4caca-131">În câmpul **Alegeți identificatorul de cheie**, selectați **E-mail**,  **Numele și adresa**, sau **Telefon** pentru a trimite la LiveRamp pentru rezolvarea identității.</span><span class="sxs-lookup"><span data-stu-id="4caca-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4caca-132">![Conector LiveRamp cu mapare de atribute](media/export-liveramp-segments.png "Conector LiveRamp cu mapare de atribute")</span><span class="sxs-lookup"><span data-stu-id="4caca-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="4caca-133">Mapați atributele corespunzătoare de la entitatea clientului dvs. unificat pentru identificatorul de cheie selectat.</span><span class="sxs-lookup"><span data-stu-id="4caca-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="4caca-134">Selectați **Adăugați un atribut** pentru a mapa mai multe atribute de trimis către LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="4caca-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="4caca-135">Trimiterea mai multor atribute de identificare cheie către LiveRamp este probabil să vă obțină o rată de potrivire mai mare.</span><span class="sxs-lookup"><span data-stu-id="4caca-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="4caca-136">Selectați segmentele pe care doriți să le exportați în LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="4caca-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="4caca-137">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="4caca-137">Select **Save**.</span></span>

<span data-ttu-id="4caca-138">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="4caca-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="4caca-139">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4caca-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4caca-140">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="4caca-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4caca-141">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="4caca-141">Data privacy and compliance</span></span>

<span data-ttu-id="4caca-142">Când activați Dynamics 365 Customer Insights pentru a transmite date către Liveramp, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="4caca-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4caca-143">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Liveramp îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="4caca-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4caca-144">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4caca-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4caca-145">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="4caca-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
