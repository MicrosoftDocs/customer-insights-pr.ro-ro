---
title: Exportați datele Customer Insights în Salesforce Marketing Cloud
description: Aflați cum să configurați conexiunea și să exportați către Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314660"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="85d6f-103">Exportați segmente și alte date în Salesforce Marketing Cloud (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="85d6f-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="85d6f-104">Folosiți datele clienților dvs. în Salesforce Marketing Cloud exportându-le printr-o locație Protocol de transfer de fișiere securizat (SFTP).</span><span class="sxs-lookup"><span data-stu-id="85d6f-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="85d6f-105">Cerințe preliminare pentru conexiune</span><span class="sxs-lookup"><span data-stu-id="85d6f-105">Prerequisites for connection</span></span>

- <span data-ttu-id="85d6f-106">Disponibilitatea unei gazde SFTP și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="85d6f-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="85d6f-107">Cum se configurează locațiile SFTP pentru Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="85d6f-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="85d6f-108">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="85d6f-108">Known limitations</span></span>

- <span data-ttu-id="85d6f-109">Runtime-ul unui export depinde de performanța sistemului dvs.</span><span class="sxs-lookup"><span data-stu-id="85d6f-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="85d6f-110">Vă recomandăm două nuclee CPU și 1 Gb de memorie ca configurație minimă a serverului dvs.</span><span class="sxs-lookup"><span data-stu-id="85d6f-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="85d6f-111">Entitățile exportatoare cu până la 100 de milioane de profiluri de clienți pot dura 90 de minute când se utilizează configurația minimă recomandată.</span><span class="sxs-lookup"><span data-stu-id="85d6f-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="85d6f-112">Configurați conexiunea la Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="85d6f-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="85d6f-113">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="85d6f-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="85d6f-114">Selectați **Adăugați conexiune** și alegeți **Salesforce Marketing Cloud** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="85d6f-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="85d6f-115">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="85d6f-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="85d6f-116">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="85d6f-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="85d6f-117">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="85d6f-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="85d6f-118">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="85d6f-118">Choose who can use this connection.</span></span> <span data-ttu-id="85d6f-119">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="85d6f-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="85d6f-120">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="85d6f-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="85d6f-121">Furnizați un **Nume de utilizator**, **Parolă**, **Nume de gazdă** și **Folder de export** pentru contul dvs. de SFTP.</span><span class="sxs-lookup"><span data-stu-id="85d6f-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="85d6f-122">Selectați **Verificare** pentru a testa conexiunea.</span><span class="sxs-lookup"><span data-stu-id="85d6f-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="85d6f-123">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="85d6f-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="85d6f-124">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="85d6f-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="85d6f-125">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="85d6f-125">Configure an export</span></span>

<span data-ttu-id="85d6f-126">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="85d6f-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="85d6f-127">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="85d6f-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="85d6f-128">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="85d6f-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="85d6f-129">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="85d6f-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="85d6f-130">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea SFTP.</span><span class="sxs-lookup"><span data-stu-id="85d6f-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="85d6f-131">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="85d6f-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="85d6f-132">Alegeți dacă doriți să vă exportați datele dvs. în mod **Comprimat cu gzip** sau **Dezarhivat** și **delimitatorul de câmp** pentru fișierele exportate.</span><span class="sxs-lookup"><span data-stu-id="85d6f-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="85d6f-133">Selectați entitățile, de exemplu segmente pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="85d6f-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="85d6f-134">Fiecare entitate selectată va fi împărțită în maximum cinci fișiere de ieșire la export.</span><span class="sxs-lookup"><span data-stu-id="85d6f-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="85d6f-135">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="85d6f-135">Select **Save**.</span></span>

<span data-ttu-id="85d6f-136">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="85d6f-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="85d6f-137">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="85d6f-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="85d6f-138">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="85d6f-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="85d6f-139">Importați datele Customer Insights din locația SFTP în Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="85d6f-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="85d6f-140">Creați [extensii de date în Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) pentru a importa fișierul de date Customer Insights din locația SFTP.</span><span class="sxs-lookup"><span data-stu-id="85d6f-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="85d6f-141">[Importați datele din locația SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) în extensia de date Salesforce Marketing Cloud.</span><span class="sxs-lookup"><span data-stu-id="85d6f-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="85d6f-142">Configurați automatizarea pentru a importa datele în extensiile de date.</span><span class="sxs-lookup"><span data-stu-id="85d6f-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="85d6f-143">Aflați mai multe despre [automatizări de eliminare a fișierelor și automatizări planificate](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="85d6f-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="85d6f-144">Definiți o [automatizare de eliminare a fișierelor](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) sau o  [automatizare planificată](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="85d6f-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="85d6f-145">Iată un exemplu de [o automatizare cu SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="85d6f-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="85d6f-146">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="85d6f-146">Data privacy and compliance</span></span>

<span data-ttu-id="85d6f-147">Când activați Dynamics 365 Customer Insights pentru a transmite date prin SFTP, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="85d6f-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="85d6f-148">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că destinația de export îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="85d6f-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="85d6f-149">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="85d6f-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="85d6f-150">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="85d6f-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
