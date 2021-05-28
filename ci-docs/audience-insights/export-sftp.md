---
title: Exportați datele Customer Insights către gazde SFTP
description: Aflați cum să configurați conexiunea și să exportați către o locație SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3663a48955f0b1db8a96e25403e5f8947bc6a220
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976954"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="292c1-103">Exportați listele de segmente și alte date către SFTP (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="292c1-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="292c1-104">Utilizați datele clienților dvs. în aplicații terțe, exportându-le într-o locație Protocol de transfer securizat al fișierelor (SFTP).</span><span class="sxs-lookup"><span data-stu-id="292c1-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="292c1-105">Cerințe preliminare pentru conexiune</span><span class="sxs-lookup"><span data-stu-id="292c1-105">Prerequisites for connection</span></span>

- <span data-ttu-id="292c1-106">Disponibilitatea unei gazde SFTP și acreditările corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="292c1-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="292c1-107">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="292c1-107">Known limitations</span></span>

- <span data-ttu-id="292c1-108">Runtime-ul unui export depinde de performanța sistemului dvs.</span><span class="sxs-lookup"><span data-stu-id="292c1-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="292c1-109">Vă recomandăm două nuclee CPU și 1 Gb de memorie ca configurație minimă a serverului dvs.</span><span class="sxs-lookup"><span data-stu-id="292c1-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="292c1-110">Entitățile exportatoare cu până la 100 de milioane de profiluri de clienți pot dura 90 de minute când se utilizează configurația minimă recomandată a două nuclee CPU și 1 Gb de memorie.</span><span class="sxs-lookup"><span data-stu-id="292c1-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="292c1-111">Configurarea conexiuni la SFTP</span><span class="sxs-lookup"><span data-stu-id="292c1-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="292c1-112">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="292c1-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="292c1-113">Selectați **Adăugați conexiune** și alegeți **SFTP** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="292c1-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="292c1-114">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="292c1-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="292c1-115">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="292c1-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="292c1-116">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="292c1-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="292c1-117">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="292c1-117">Choose who can use this connection.</span></span> <span data-ttu-id="292c1-118">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="292c1-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="292c1-119">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="292c1-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="292c1-120">Furnizați un **Nume de utilizator**, **Parolă**, **Nume de gazdă** și **Folder de export** pentru contul dvs. de SFTP.</span><span class="sxs-lookup"><span data-stu-id="292c1-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="292c1-121">Selectați **Verificare** pentru a testa conexiunea.</span><span class="sxs-lookup"><span data-stu-id="292c1-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="292c1-122">Alegeți dacă doriți să vă exportați datele dvs. în mod **Comprimat cu gzip** sau **Dezarhivat** și **delimitatorul de câmp** pentru fișierele exportate.</span><span class="sxs-lookup"><span data-stu-id="292c1-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="292c1-123">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="292c1-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="292c1-124">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="292c1-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="292c1-125">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="292c1-125">Configure an export</span></span>

<span data-ttu-id="292c1-126">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="292c1-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="292c1-127">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="292c1-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="292c1-128">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="292c1-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="292c1-129">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="292c1-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="292c1-130">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea SFTP.</span><span class="sxs-lookup"><span data-stu-id="292c1-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="292c1-131">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="292c1-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="292c1-132">Selectați entitățile, de exemplu segmente pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="292c1-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="292c1-133">Fiecare entitate selectată va fi împărțită în maximum cinci fișiere de ieșire la export.</span><span class="sxs-lookup"><span data-stu-id="292c1-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="292c1-134">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="292c1-134">Select **Save**.</span></span>

<span data-ttu-id="292c1-135">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="292c1-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="292c1-136">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="292c1-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="292c1-137">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="292c1-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="292c1-138">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="292c1-138">Data privacy and compliance</span></span>

<span data-ttu-id="292c1-139">Când activați Dynamics 365 Customer Insights pentru a transmite date prin SFTP, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="292c1-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="292c1-140">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că destinația de export îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="292c1-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="292c1-141">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="292c1-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="292c1-142">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="292c1-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
