---
title: Exportați datele Customer Insights în Adobe Experience Platform
description: Aflați cum utilizați segmentele de statistici privind publicul în Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760116"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="5f2c5-103">Utilizați segmentele de Customer Insights în Adobe Experience Platform (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="5f2c5-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="5f2c5-104">Ca utilizator al statisticilor publicului pentru Dynamics 365 Customer Insights, este posibil să fi creat segmente pentru a vă face campaniile de marketing mai eficiente, vizând publicuri relevante.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="5f2c5-105">Pentru a utiliza un segment din statisticile publicului în Adobe Experience Platform și aplicații precum Adobe Campaign Standard, trebuie să urmați câțiva pași descriși în acest articol.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama de proces a pașilor descriși în acest articol.":::

## <a name="prerequisites"></a><span data-ttu-id="5f2c5-107">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="5f2c5-107">Prerequisites</span></span>

-   <span data-ttu-id="5f2c5-108">Licență Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="5f2c5-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="5f2c5-109">Licență Platformă Adobe Experience</span><span class="sxs-lookup"><span data-stu-id="5f2c5-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="5f2c5-110">Licență Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="5f2c5-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="5f2c5-111">Cont Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="5f2c5-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="5f2c5-112">Prezentare generală campanie</span><span class="sxs-lookup"><span data-stu-id="5f2c5-112">Campaign Overview</span></span>

<span data-ttu-id="5f2c5-113">Pentru a înțelege mai bine modul în care puteți utiliza segmente din statisticile publicului în platforma Adobe Experience, haideți să analizăm un exemplu de campanie fictivă.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="5f2c5-114">Să presupunem că compania dvs. oferă clienților dvs. din Statele Unite un serviciu lunar, bazat pe abonament.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="5f2c5-115">Doriți să identificați clienții ale căror abonamente trebuie reînnoite în următoarele opt zile, dar nu și-au reînnoit abonamentul.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="5f2c5-116">Pentru a păstra acești clienți, doriți să le trimiteți o ofertă promoțională prin e-mail, utilizând Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="5f2c5-117">În acest exemplu, dorim să derulăm o dată campania de e-mail promoțională.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="5f2c5-118">Acest articol nu acoperă cazul de utilizare al desfășurării campaniei de mai multe ori.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="5f2c5-119">Identificați-vă publicul țintă</span><span class="sxs-lookup"><span data-stu-id="5f2c5-119">Identify your target audience</span></span>

<span data-ttu-id="5f2c5-120">În scenariul nostru, presupunem că adresele de e-mail ale clienților sunt disponibile în statisticile publicului, iar preferințele lor promoționale au fost analizate pentru a identifica membrii segmentului.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="5f2c5-121">[Segmentul pe care l-ați definit în statistici privind publicul](segments.md) se numește **ChurnProneCustomers** și intenționați să trimiteți acestor clienți promoția prin e-mail.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captură de ecran a paginii segmente cu segmentul ChurnProneCustomers creat.":::

<span data-ttu-id="5f2c5-123">E-mailul de ofertă pe care doriți să îl trimiteți va conține prenume, nume de familie, și data de încheiere a abonamentului clientului.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="5f2c5-124">Acesta informează clienții despre reducerea pe care o vor primi dacă își reînnoiesc abonamentul înainte de a se încheia.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="5f2c5-125">Expportați-vă publicul țintă</span><span class="sxs-lookup"><span data-stu-id="5f2c5-125">Export your target audience</span></span>

<span data-ttu-id="5f2c5-126">Odată cu publicul țintă identificat, putem configura exportul din statistici privind publicul către un cont de stocare Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="5f2c5-127">Configurați o conexiune</span><span class="sxs-lookup"><span data-stu-id="5f2c5-127">Configure a connection</span></span>

1. <span data-ttu-id="5f2c5-128">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5f2c5-129">Selectați **Adăugați conexiune** și alegeți **Stocare bloburi Azure** sau selectați **Configurat** în dala **Stocare bloburi Azure**:</span><span class="sxs-lookup"><span data-stu-id="5f2c5-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile:</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Dală de configurare pentru stocare Blob Azure."::: <span data-ttu-id="5f2c5-131">pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-131">to configure the connection.</span></span>

1. <span data-ttu-id="5f2c5-132">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-132">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5f2c5-133">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-133">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5f2c5-134">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-134">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5f2c5-135">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-135">Choose who can use this connection.</span></span> <span data-ttu-id="5f2c5-136">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-136">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="5f2c5-137">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="5f2c5-137">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="5f2c5-138">Introduceți **Nume de cont**, **Cheia de cont** și **Recipient** pentru contul dvs. de stocare de bloburi în care doriți să exportați segmentul.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-138">Enter **Account name**, **Account key**, and **Container** for your Blob storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captură de ecran a configurării contului de stocare. "::: 
   
    - <span data-ttu-id="5f2c5-140">Pentru a afla mai multe despre cum să aflați numele contului de stocare de bloburi și cheia de cont, consultați [Gestionați setările contului de stocare în portalul Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="5f2c5-140">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="5f2c5-141">Pentru a afla cum să creați un container, consultați [Creați un container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="5f2c5-141">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="5f2c5-142">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-142">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="5f2c5-143">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="5f2c5-143">Configure an export</span></span>

<span data-ttu-id="5f2c5-144">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-144">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5f2c5-145">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="5f2c5-145">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5f2c5-146">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5f2c5-147">Pentru a crea un nou export, selectați **Adăugare export**.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-147">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="5f2c5-148">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Stocare bloburi Azure.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-148">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="5f2c5-149">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-149">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="5f2c5-150">Alegeți segmentul pe care doriți să îl exportați.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-150">Choose the segment that you want to export.</span></span> <span data-ttu-id="5f2c5-151">În acest exemplu, este **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-151">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captură de ecran a interfeței de selectare a segmentului cu segmentul ChurnProneCustomers selectat.":::

1. <span data-ttu-id="5f2c5-153">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-153">Select **Save**.</span></span>

<span data-ttu-id="5f2c5-154">După salvarea destinației de export, o veți găsi pe **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-154">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="5f2c5-155">Acum puteți [exporta segmentul la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="5f2c5-155">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="5f2c5-156">Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md).</span><span class="sxs-lookup"><span data-stu-id="5f2c5-156">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5f2c5-157">Asigurați-vă că numărul de înregistrări din segmentul exportat se încadrează în limita permisă a licenței dvs. Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-157">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="5f2c5-158">Datele exportate sunt stocate în containerul de stocare Azure Blob pe care l-ați configurat mai sus.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-158">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="5f2c5-159">Următoarea cale a folderului este creată automat în container:</span><span class="sxs-lookup"><span data-stu-id="5f2c5-159">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="5f2c5-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="5f2c5-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="5f2c5-161">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="5f2c5-161">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="5f2c5-162">*model.json* pentru entitățile exportate se află la nivelul *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-162">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="5f2c5-163">Exemplu: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="5f2c5-163">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="5f2c5-164">Definiți modelul de date pentru experiență (XDM) în platforma Adobe Experience</span><span class="sxs-lookup"><span data-stu-id="5f2c5-164">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="5f2c5-165">Înainte ca datele exportate din statistici privind publicul să poată fi utilizate în platforma Adobe Experience, trebuie să definim schema modelului de date experiență și [configurați datele pentru Profilul clientului în timp real](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="5f2c5-165">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="5f2c5-166">Învățați [ce este XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) și înțelegeți [elementele de bază ale compoziției schemei](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="5f2c5-166">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="5f2c5-167">Importați date în Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="5f2c5-167">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="5f2c5-168">Acum că totul este la locul său, trebuie să importăm datele pregătite despre audiență din statistici despre audiență în Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-168">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="5f2c5-169">În primul rând, [creați o conexiune sursă Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="5f2c5-169">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="5f2c5-170">După definirea conexiunii sursă, [configurați un flux de date](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pentru o conexiune batch de stocare în cloud pentru a importa ieșirea segmentului din statisticile publicului în Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-170">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="5f2c5-171">Creați un public în Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="5f2c5-171">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="5f2c5-172">Pentru a trimite e-mailul pentru această campanie, vom folosi Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-172">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="5f2c5-173">După importul datelor în Adobe Experience Platform, trebuie să [creați un public](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) în Adobe Campaign Standard folosind datele din Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-173">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="5f2c5-174">Aflați cum să [utilizați generatorul de segmente](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) în Adobe Campaign Standard pentru a defini un public pe baza datelor din Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-174">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="5f2c5-175">Creați și trimiteți e-mailul utilizând Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="5f2c5-175">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="5f2c5-176">Creați conținutul e-mailului și apoi [testați și trimiteți](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email-ul dvs.</span><span class="sxs-lookup"><span data-stu-id="5f2c5-176">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Eșantion de e-mail cu ofertă de reînnoire de la Adobe Campaign Standard.":::
