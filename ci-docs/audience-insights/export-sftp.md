---
title: Exportați datele Customer Insights către gazde SFTP
description: Aflați cum să configurați conexiunea la o gazdă SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643518"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="70032-103">Conector pentru SFTP (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="70032-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="70032-104">Utilizați datele despre clienți în aplicații terțe, exportându-le către o gazdă Secure File Transfer Protocol(SFTP).</span><span class="sxs-lookup"><span data-stu-id="70032-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="70032-105">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="70032-105">Prerequisites</span></span>

- <span data-ttu-id="70032-106">Disponibilitatea unei gazde SFTP și acreditările corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="70032-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="70032-107">Conectare la SFTP</span><span class="sxs-lookup"><span data-stu-id="70032-107">Connect to SFTP</span></span>

1. <span data-ttu-id="70032-108">Accesați **Administrator** > **Destinații de export**.</span><span class="sxs-lookup"><span data-stu-id="70032-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="70032-109">Sub **SFTP**, selectați **Configurare**.</span><span class="sxs-lookup"><span data-stu-id="70032-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="70032-110">Dați destinației dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="70032-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="70032-111">Furnizați un **Nume de utilizator**, **Parolă** și **Nume gazdă** pentru contul dvs. SFTP.</span><span class="sxs-lookup"><span data-stu-id="70032-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="70032-112">Exemplu: Dacă folderul rădăcină al serverului dvs. SFTP este /root/folder, și doriți ca datele să fie exportate în /root/folder/ci_export_destination_folder, gazda ar trebui să fie sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="70032-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="70032-113">Selectați **Verificare** pentru a testa conexiunea.</span><span class="sxs-lookup"><span data-stu-id="70032-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="70032-114">După verificarea reușită, alegeți dacă doriți să exportați datele **Arhivate** sau **Dezarhivate** și selectați **Delimitatorul de câmp** pentru fișierele exportate.</span><span class="sxs-lookup"><span data-stu-id="70032-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="70032-115">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="70032-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="70032-116">Selectați **Următorul** pentru a începe configurarea exportului.</span><span class="sxs-lookup"><span data-stu-id="70032-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="70032-117">Configurați conexiunea</span><span class="sxs-lookup"><span data-stu-id="70032-117">Configure the connection</span></span>

1. <span data-ttu-id="70032-118">Selectați **atributele clientului** pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="70032-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="70032-119">Aveți posibilitatea să exportați unul sau mai multe atribute.</span><span class="sxs-lookup"><span data-stu-id="70032-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="70032-120">Selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="70032-120">Select **Next**.</span></span>

1. <span data-ttu-id="70032-121">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="70032-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="70032-122">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="70032-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="70032-123">Exportați datele</span><span class="sxs-lookup"><span data-stu-id="70032-123">Export the data</span></span>

<span data-ttu-id="70032-124">Puteți [exporta date la cerere](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="70032-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="70032-125">Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="70032-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="70032-126">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="70032-126">Data privacy and compliance</span></span>

<span data-ttu-id="70032-127">Când activați Dynamics 365 Customer Insights pentru a transmite date prin SFTP, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="70032-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="70032-128">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că destinația de export îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="70032-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="70032-129">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="70032-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="70032-130">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="70032-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
