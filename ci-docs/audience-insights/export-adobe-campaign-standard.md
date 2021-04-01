---
title: Exportați datele Customer Insights în Adobe Campaign Standard
description: Aflați cum utilizați segmentele de statistici privind publicul în Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596330"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="cd216-103">Utilizați segmentele de Customer Insights în Adobe Campaign Standard (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="cd216-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="cd216-104">Ca utilizator al statisticilor publicului pentru Dynamics 365 Customer Insights, este posibil să fi creat segmente pentru a vă face campaniile de marketing mai eficiente, vizând publicuri relevante.</span><span class="sxs-lookup"><span data-stu-id="cd216-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="cd216-105">Pentru a utiliza un segment din statisticile publicului în Adobe Experience Platform și aplicații precum Adobe Campaign Standard, trebuie să urmați câțiva pași descriși în acest articol.</span><span class="sxs-lookup"><span data-stu-id="cd216-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de proces a pașilor descriși în acest articol.":::

## <a name="prerequisites"></a><span data-ttu-id="cd216-107">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="cd216-107">Prerequisites</span></span>

-   <span data-ttu-id="cd216-108">Licență Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="cd216-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="cd216-109">Licență Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="cd216-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="cd216-110">Cont Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="cd216-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="cd216-111">Prezentare generală campanie</span><span class="sxs-lookup"><span data-stu-id="cd216-111">Campaign Overview</span></span>

<span data-ttu-id="cd216-112">Pentru a înțelege mai bine modul în care puteți utiliza segmente din statisticile publicului în platforma Adobe Experience, haideți să analizăm un exemplu de campanie fictivă.</span><span class="sxs-lookup"><span data-stu-id="cd216-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="cd216-113">Să presupunem că compania dvs. oferă clienților dvs. din Statele Unite un serviciu lunar, bazat pe abonament.</span><span class="sxs-lookup"><span data-stu-id="cd216-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="cd216-114">Doriți să identificați clienții ale căror abonamente trebuie reînnoite în următoarele opt zile, dar nu și-au reînnoit abonamentul.</span><span class="sxs-lookup"><span data-stu-id="cd216-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="cd216-115">Pentru a păstra acești clienți, doriți să le trimiteți o ofertă promoțională prin e-mail, utilizând Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="cd216-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="cd216-116">În acest exemplu, dorim să derulăm o dată campania de e-mail promoțională.</span><span class="sxs-lookup"><span data-stu-id="cd216-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="cd216-117">Acest articol nu acoperă cazul de utilizare al desfășurării campaniei de mai multe ori.</span><span class="sxs-lookup"><span data-stu-id="cd216-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="cd216-118">Cu toate acestea, statisticile publicului și Adobe Campaign Standard pot fi configurate pentru a funcționa și pentru un scenariu de campanie recurentă.</span><span class="sxs-lookup"><span data-stu-id="cd216-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="cd216-119">Identificați-vă publicul țintă</span><span class="sxs-lookup"><span data-stu-id="cd216-119">Identify your target audience</span></span>

<span data-ttu-id="cd216-120">În scenariul nostru, presupunem că adresele de e-mail ale clienților sunt disponibile în statisticile publicului, iar preferințele lor promoționale au fost analizate pentru a identifica membrii segmentului.</span><span class="sxs-lookup"><span data-stu-id="cd216-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="cd216-121">[Segmentul pe care l-ați definit în statistici privind publicul](segments.md) se numește **ChurnProneCustomers** și intenționați să trimiteți acestor clienți promoția prin e-mail.</span><span class="sxs-lookup"><span data-stu-id="cd216-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captură de ecran a paginii segmente cu segmentul ChurnProneCustomers creat.":::

<span data-ttu-id="cd216-123">E-mailul de ofertă pe care doriți să îl trimiteți va conține prenume, nume de familie, și data de încheiere a abonamentului clientului.</span><span class="sxs-lookup"><span data-stu-id="cd216-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="cd216-124">Acesta informează clienții despre reducerea pe care o vor primi dacă își reînnoiesc abonamentul înainte de a se încheia.</span><span class="sxs-lookup"><span data-stu-id="cd216-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="cd216-125">Expportați-vă publicul țintă</span><span class="sxs-lookup"><span data-stu-id="cd216-125">Export your target audience</span></span>

<span data-ttu-id="cd216-126">Odată cu publicul țintă identificat, putem configura exportul din statistici privind publicul către un cont de stocare Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="cd216-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="cd216-127">În Detalii despre audiență, accesați **Administrator** > **Destinații export**.</span><span class="sxs-lookup"><span data-stu-id="cd216-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="cd216-128">În dala **Campanie Adobe**, selectați **Configurare**.</span><span class="sxs-lookup"><span data-stu-id="cd216-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Placă de configurare pentru Adobe Campaign Standard.":::

1. <span data-ttu-id="cd216-130">Furnizează un **Nume afișat** pentru această nouă destinație de export și apoi introduceți **Nume de cont**, **Cheia contului** și **Recipient** din contul Azure Blob Storage în care doriți să exportați segmentul.</span><span class="sxs-lookup"><span data-stu-id="cd216-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captură de ecran a configurării contului de stocare. "::: 

   - <span data-ttu-id="cd216-132">Pentru a afla mai multe despre cum puteți găsi numele contului Stocarea de bloburi Azure și cheia contului, consultați [Gestionați setările contului de stocare în portalul Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="cd216-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="cd216-133">Pentru a afla cum să creați un container, consultați [Creați un container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="cd216-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="cd216-134">Selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="cd216-134">Select **Next**.</span></span>

1. <span data-ttu-id="cd216-135">Alegeți segmentul pe care doriți să îl exportați.</span><span class="sxs-lookup"><span data-stu-id="cd216-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="cd216-136">În acest exemplu, este **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="cd216-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captură de ecran a interfeței de selectare a segmentului cu segmentul ChurnProneCustomers selectat.":::

1. <span data-ttu-id="cd216-138">Selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="cd216-138">Select **Next**.</span></span>

1. <span data-ttu-id="cd216-139">Acum mapăm câmpurile **Sursă** de la segmentul de statistici al publicului la numele câmpurilor **Ţintă** din schema de profil Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="cd216-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Cartarea câmpului pentru conectorul Adobe Campaign Standard.":::

   <span data-ttu-id="cd216-141">Dacă doriți să adăugați mai multe atribute, selectați **Adăugați un atribut**.</span><span class="sxs-lookup"><span data-stu-id="cd216-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="cd216-142">Numele țintă poate fi diferit de numele câmpului sursă, astfel încât să puteți mapa în continuare rezultatele segmentelor din statistici privind publicul către Adobe Campaign Standard dacă câmpurile nu au același nume în cele două sisteme.</span><span class="sxs-lookup"><span data-stu-id="cd216-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cd216-143">Adresa de e-mail este utilizată ca un câmp de identitate, dar puteți utiliza orice alt identificator din profilul de client al informațiilor despre public pentru a mapa datele la Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="cd216-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="cd216-144">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="cd216-144">Select **Save**.</span></span>

<span data-ttu-id="cd216-145">După salvarea destinației de export, o găsiți pe **Administrator** > **Exporturi** > **Destinațiile mele de export**.</span><span class="sxs-lookup"><span data-stu-id="cd216-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Captură de ecran cu lista exporturilor și segmentul eșantion evidențiat.":::

<span data-ttu-id="cd216-147">Acum puteți [exporta segmentul la cerere](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="cd216-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="cd216-148">Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md).</span><span class="sxs-lookup"><span data-stu-id="cd216-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="cd216-149">Asigurați-vă că numărul de înregistrări din segmentul exportat se încadrează în limita permisă a licenței dvs. Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="cd216-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="cd216-150">Datele exportate sunt stocate în containerul de stocare Azure Blob pe care l-ați configurat mai sus.</span><span class="sxs-lookup"><span data-stu-id="cd216-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="cd216-151">Următoarea cale a folderului este creată automat în container:</span><span class="sxs-lookup"><span data-stu-id="cd216-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="cd216-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="cd216-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="cd216-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="cd216-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="cd216-154">Configurați Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="cd216-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="cd216-155">Atunci când un segment din statistici privind publicul este exportat, acesta conține coloanele pe care le-ați selectat în timp ce definiți destinația de export în pasul anterior.</span><span class="sxs-lookup"><span data-stu-id="cd216-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="cd216-156">Aceste date pot fi utilizate pentru [crearea profilurilor în Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="cd216-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="cd216-157">Pentru a utiliza segmentul în Adobe Campaign Standard, trebuie să extindem schema de profil în Adobe Campaign Standard pentru a include două câmpuri suplimentare.</span><span class="sxs-lookup"><span data-stu-id="cd216-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="cd216-158">Aflați cum să [extindeți resursa profilului](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) cu câmpuri noi în Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="cd216-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="cd216-159">În exemplul nostru, aceste câmpuri sunt *Numele segmentului și data segmentului (opțional).*</span><span class="sxs-lookup"><span data-stu-id="cd216-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="cd216-160">Vom folosi aceste câmpuri pentru a identifica profilurile din Adobe Campaign Standard pe care dorim să le vizăm pentru această campanie.</span><span class="sxs-lookup"><span data-stu-id="cd216-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="cd216-161">Dacă nu există alte înregistrări în Adobe Campaign Standard, în afară de ceea ce urmează să importați, puteți sări peste acest pas.</span><span class="sxs-lookup"><span data-stu-id="cd216-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="cd216-162">Importați date în Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="cd216-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="cd216-163">Acum că totul este la locul său, trebuie să importăm datele pregătite despre audiență din statistici despre audiență în Adobe Campaign Standard pentru a crea profiluri.</span><span class="sxs-lookup"><span data-stu-id="cd216-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="cd216-164">Învățați [cum să importați profiluri în Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) folosind un flux de lucru.</span><span class="sxs-lookup"><span data-stu-id="cd216-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="cd216-165">Fluxul de lucru de import din imaginea de mai jos a fost configurat să ruleze la fiecare 8 ore și caută segmente de informații despre publicul exportat (fișier .csv în Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="cd216-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="cd216-166">Fluxul de lucru extrage conținutul fișierului .csv într-o ordine de coloane specificată.</span><span class="sxs-lookup"><span data-stu-id="cd216-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="cd216-167">Acest flux de lucru a fost creat pentru a efectua tratarea erorilor de bază și pentru a se asigura că fiecare înregistrare are o adresă de e-mail înainte de a hidrata datele în Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="cd216-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="cd216-168">Fluxul de lucru extrage, de asemenea, numele segmentului din numele fișierului înainte de a fi introdus în datele profilului ACS.</span><span class="sxs-lookup"><span data-stu-id="cd216-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captură de ecran a unui flux de lucru de import în interfața cu utilizatorul Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="cd216-170">Regăsiți publicul în Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="cd216-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="cd216-171">Odată ce datele sunt importate în Adobe Campaign Standard, dvs. [poate crea un flux de lucru](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) și [interogare](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) clienții pe baza *Nume segment* și *Data segmentului* pentru a selecta profilurile care au fost identificate pentru campania noastră eșantion.</span><span class="sxs-lookup"><span data-stu-id="cd216-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="cd216-172">Creați și trimiteți e-mailul utilizând Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="cd216-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="cd216-173">Creați conținutul e-mailului și apoi [testați și trimiteți](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email-ul dvs.</span><span class="sxs-lookup"><span data-stu-id="cd216-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Eșantion de e-mail cu ofertă de reînnoire de la Adobe Campaign Standard.":::