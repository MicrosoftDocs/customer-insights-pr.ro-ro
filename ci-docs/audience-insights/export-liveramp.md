---
title: 'conector LiveRamp '
description: Aflați cum să exportați datele la LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270173"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="b1378-103">Conector LiveRamp &reg; (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="b1378-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="b1378-104">Activați-vă datele în LiveRamp pentru a vă conecta cu peste 500 de platforme pe ecosistemele digitale, sociale și TV.</span><span class="sxs-lookup"><span data-stu-id="b1378-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="b1378-105">Lucrați cu datele dvs. în LiveRamp pentru a viza, suprima și personaliza campaniile publicitare.</span><span class="sxs-lookup"><span data-stu-id="b1378-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b1378-106">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="b1378-106">Prerequisites</span></span>

- <span data-ttu-id="b1378-107">Pentru a utiliza acest conector aveți nevoie de un abonament LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b1378-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="b1378-108">Pentru a obține un abonament, [contactați LiveRamp](https://liveramp.com/contact/) direct.</span><span class="sxs-lookup"><span data-stu-id="b1378-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="b1378-109">[Aflați mai multe despre Îndrumări LiveRamp](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="b1378-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="b1378-110">Conectare la LiveRamp</span><span class="sxs-lookup"><span data-stu-id="b1378-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="b1378-111">În Detalii despre audiență, accesați **Administrator** > **Destinații export**.</span><span class="sxs-lookup"><span data-stu-id="b1378-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b1378-112">În dala **LiveRamp**, selectați **Configurare**.</span><span class="sxs-lookup"><span data-stu-id="b1378-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="b1378-113">Dați destinației dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="b1378-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b1378-114">Furnizează un **Nume de utilizator** și **Parola** pentru contul dvs. LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="b1378-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="b1378-115">Aceste acreditări pot fi diferite de datele de acreditare Îndrumări LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b1378-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="b1378-116">Selectați **Verificare** pentru a testa conexiunea la LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b1378-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="b1378-117">După verificarea cu succes, acordați-vă consimțământul pentru **Confidențialitatea și conformitatea datelor** prin selectarea casetei de selectare **Sunt de acord**.</span><span class="sxs-lookup"><span data-stu-id="b1378-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="b1378-118">Selectați **Următorul** pentru a configura conectorul LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b1378-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="b1378-119">Configurați conectorul</span><span class="sxs-lookup"><span data-stu-id="b1378-119">Configure the connector</span></span>

1. <span data-ttu-id="b1378-120">În câmpul **Alegeți identificatorul de cheie**, selectați **E-mail**,  **Numele și adresa**, sau **Telefon** pentru a trimite la LiveRamp pentru rezolvarea identității.</span><span class="sxs-lookup"><span data-stu-id="b1378-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="b1378-121">Mapați atributele corespunzătoare de la entitatea clientului dvs. unificat pentru identificatorul de cheie selectat.</span><span class="sxs-lookup"><span data-stu-id="b1378-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="b1378-122">Selectați **Adăugați atributul** pentru a face o mapare a atributelor suplimentare pe care să le trimiteți la LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b1378-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="b1378-123">Trimiterea mai multor atribute de identificare cheie către LiveRamp este probabil să vă obțină o rată de potrivire mai mare.</span><span class="sxs-lookup"><span data-stu-id="b1378-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="b1378-124">Selectați segmentele pe care doriți să le exportați în LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b1378-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="b1378-125">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="b1378-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b1378-126">![Conector LiveRamp cu mapare de atribute](media/export-liveramp-segments.png "Conector LiveRamp cu mapare de atribute")</span><span class="sxs-lookup"><span data-stu-id="b1378-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b1378-127">Exportați datele</span><span class="sxs-lookup"><span data-stu-id="b1378-127">Export the data</span></span>

<span data-ttu-id="b1378-128">Exportul va începe curând dacă toate condițiile preliminare pentru export au fost finalizate.</span><span class="sxs-lookup"><span data-stu-id="b1378-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="b1378-129">Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b1378-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="b1378-130">După ce exportul este încheiat cu succes, vă puteți conecta la Îndrumare LiveRamp pentru a activa și distribui datele.</span><span class="sxs-lookup"><span data-stu-id="b1378-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b1378-131">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="b1378-131">Data privacy and compliance</span></span>

<span data-ttu-id="b1378-132">Când activați Dynamics 365 Customer Insights pentru a transmite date către Liveramp, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="b1378-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b1378-133">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Liveramp îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="b1378-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b1378-134">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b1378-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b1378-135">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="b1378-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]