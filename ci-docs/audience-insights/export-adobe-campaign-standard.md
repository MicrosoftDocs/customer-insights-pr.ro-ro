---
title: Exportați datele Customer Insights în Adobe Campaign Standard
description: Aflați cum utilizați segmentele de statistici privind publicul în Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760296"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="21685-103">Utilizați segmentele de Customer Insights în Adobe Campaign Standard (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="21685-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="21685-104">Ca utilizator al statisticilor publicului pentru Dynamics 365 Customer Insights, este posibil să fi creat segmente pentru a vă face campaniile de marketing mai eficiente, vizând publicuri relevante.</span><span class="sxs-lookup"><span data-stu-id="21685-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="21685-105">Pentru a utiliza un segment din statisticile publicului în Adobe Experience Platform și aplicații precum Adobe Campaign Standard, trebuie să urmați câțiva pași descriși în acest articol.</span><span class="sxs-lookup"><span data-stu-id="21685-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de proces a pașilor descriși în acest articol.":::

## <a name="prerequisites"></a><span data-ttu-id="21685-107">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="21685-107">Prerequisites</span></span>

-   <span data-ttu-id="21685-108">Licență Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="21685-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="21685-109">Licență Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="21685-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="21685-110">Cont Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="21685-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="21685-111">Prezentare generală campanie</span><span class="sxs-lookup"><span data-stu-id="21685-111">Campaign Overview</span></span>

<span data-ttu-id="21685-112">Pentru a înțelege mai bine modul în care puteți utiliza segmente din statisticile publicului în platforma Adobe Experience, haideți să analizăm un exemplu de campanie fictivă.</span><span class="sxs-lookup"><span data-stu-id="21685-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="21685-113">Să presupunem că compania dvs. oferă clienților dvs. din Statele Unite un serviciu lunar, bazat pe abonament.</span><span class="sxs-lookup"><span data-stu-id="21685-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="21685-114">Doriți să identificați clienții ale căror abonamente trebuie reînnoite în următoarele opt zile, dar nu și-au reînnoit abonamentul.</span><span class="sxs-lookup"><span data-stu-id="21685-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="21685-115">Pentru a păstra acești clienți, doriți să le trimiteți o ofertă promoțională prin e-mail, utilizând Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="21685-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="21685-116">În acest exemplu, dorim să derulăm o dată campania de e-mail promoțională.</span><span class="sxs-lookup"><span data-stu-id="21685-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="21685-117">Acest articol nu acoperă cazul de utilizare al desfășurării campaniei de mai multe ori.</span><span class="sxs-lookup"><span data-stu-id="21685-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="21685-118">Cu toate acestea, statisticile publicului și Adobe Campaign Standard pot fi configurate pentru a funcționa și pentru un scenariu de campanie recurentă.</span><span class="sxs-lookup"><span data-stu-id="21685-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="21685-119">Identificați-vă publicul țintă</span><span class="sxs-lookup"><span data-stu-id="21685-119">Identify your target audience</span></span>

<span data-ttu-id="21685-120">În scenariul nostru, presupunem că adresele de e-mail ale clienților sunt disponibile în statisticile publicului, iar preferințele lor promoționale au fost analizate pentru a identifica membrii segmentului.</span><span class="sxs-lookup"><span data-stu-id="21685-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="21685-121">[Segmentul pe care l-ați definit în statistici privind publicul](segments.md) se numește **ChurnProneCustomers** și intenționați să trimiteți acestor clienți promoția prin e-mail.</span><span class="sxs-lookup"><span data-stu-id="21685-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captură de ecran a paginii segmente cu segmentul ChurnProneCustomers creat.":::

<span data-ttu-id="21685-123">E-mailul de ofertă pe care doriți să îl trimiteți va conține prenume, nume de familie, și data de încheiere a abonamentului clientului.</span><span class="sxs-lookup"><span data-stu-id="21685-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="21685-124">Acesta informează clienții despre reducerea pe care o vor primi dacă își reînnoiesc abonamentul înainte de a se încheia.</span><span class="sxs-lookup"><span data-stu-id="21685-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="21685-125">Expportați-vă publicul țintă</span><span class="sxs-lookup"><span data-stu-id="21685-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="21685-126">Configurați o conexiune</span><span class="sxs-lookup"><span data-stu-id="21685-126">Configure a connection</span></span>

<span data-ttu-id="21685-127">Odată cu publicul țintă identificat, putem configura exportul din statistici privind publicul către un cont de stocare Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="21685-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="21685-128">În statisticile publicului, accesați **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="21685-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="21685-129">Selectați **Adăugare conexiune** și alegeți **Adobe Campaign** pentru a configura conexiunea sau a selecta **Configurat** în dala **Adobe Campaign**</span><span class="sxs-lookup"><span data-stu-id="21685-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Placă de configurare pentru Adobe Campaign Standard.":::

1. <span data-ttu-id="21685-131">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="21685-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="21685-132">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="21685-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="21685-133">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="21685-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="21685-134">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="21685-134">Choose who can use this connection.</span></span> <span data-ttu-id="21685-135">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="21685-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="21685-136">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="21685-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="21685-137">Introduceți **Nume de cont**, **Cheia de cont** și **Recipient** pentru contul Azure Blob Storage în care doriți să exportați segmentul.</span><span class="sxs-lookup"><span data-stu-id="21685-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captură de ecran a configurării contului de stocare. "::: 

   - <span data-ttu-id="21685-139">Pentru a afla mai multe despre cum puteți găsi numele contului Stocarea de bloburi Azure și cheia contului, consultați [Gestionați setările contului de stocare în portalul Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="21685-139">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="21685-140">Pentru a afla cum să creați un container, consultați [Creați un container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="21685-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="21685-141">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="21685-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="21685-142">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="21685-142">Configure an export</span></span>

<span data-ttu-id="21685-143">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="21685-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="21685-144">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="21685-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="21685-145">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="21685-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="21685-146">Pentru a crea un nou export, selectați **Adăugare export**.</span><span class="sxs-lookup"><span data-stu-id="21685-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="21685-147">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Adobe Campaign.</span><span class="sxs-lookup"><span data-stu-id="21685-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="21685-148">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="21685-148">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="21685-149">Alegeți segmentul pe care doriți să îl exportați.</span><span class="sxs-lookup"><span data-stu-id="21685-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="21685-150">În acest exemplu, este **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="21685-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captură de ecran a interfeței de selectare a segmentului cu segmentul ChurnProneCustomers selectat.":::

1. <span data-ttu-id="21685-152">Selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="21685-152">Select **Next**.</span></span>

1. <span data-ttu-id="21685-153">Acum mapăm câmpurile **Sursă** de la segmentul de statistici al publicului la numele câmpurilor **Ţintă** din schema de profil Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="21685-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Cartarea câmpului pentru conectorul Adobe Campaign Standard.":::

   <span data-ttu-id="21685-155">Dacă doriți să adăugați mai multe atribute, selectați **Adăugați un atribut**.</span><span class="sxs-lookup"><span data-stu-id="21685-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="21685-156">Numele țintă poate fi diferit de numele câmpului sursă, astfel încât să puteți mapa în continuare rezultatele segmentelor din statistici privind publicul către Adobe Campaign Standard dacă câmpurile nu au același nume în cele două sisteme.</span><span class="sxs-lookup"><span data-stu-id="21685-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="21685-157">Adresa de e-mail este utilizată ca un câmp de identitate, dar puteți utiliza orice alt identificator din profilul de client al informațiilor despre public pentru a mapa datele la Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="21685-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="21685-158">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="21685-158">Select **Save**.</span></span>

<span data-ttu-id="21685-159">După salvarea destinației de export, o veți găsi pe **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="21685-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="21685-160">Acum puteți [exporta segmentul la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="21685-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="21685-161">Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md).</span><span class="sxs-lookup"><span data-stu-id="21685-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="21685-162">Asigurați-vă că numărul de înregistrări din segmentul exportat se încadrează în limita permisă a licenței dvs. Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="21685-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="21685-163">Datele exportate sunt stocate în containerul de stocare Azure Blob pe care l-ați configurat mai sus.</span><span class="sxs-lookup"><span data-stu-id="21685-163">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="21685-164">Următoarea cale a folderului este creată automat în container:</span><span class="sxs-lookup"><span data-stu-id="21685-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="21685-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="21685-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="21685-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="21685-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="21685-167">Configurați Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="21685-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="21685-168">Atunci când un segment din statistici privind publicul este exportat, acesta conține coloanele pe care le-ați selectat în timp ce definiți destinația de export în pasul anterior.</span><span class="sxs-lookup"><span data-stu-id="21685-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="21685-169">Aceste date pot fi utilizate pentru [crearea profilurilor în Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="21685-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="21685-170">Pentru a utiliza segmentul în Adobe Campaign Standard, trebuie să extindem schema de profil în Adobe Campaign Standard pentru a include două câmpuri suplimentare.</span><span class="sxs-lookup"><span data-stu-id="21685-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="21685-171">Aflați cum să [extindeți resursa profilului](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) cu câmpuri noi în Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="21685-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="21685-172">În exemplul nostru, aceste câmpuri sunt *Numele segmentului și data segmentului (opțional).*</span><span class="sxs-lookup"><span data-stu-id="21685-172">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="21685-173">Vom folosi aceste câmpuri pentru a identifica profilurile din Adobe Campaign Standard pe care dorim să le vizăm pentru această campanie.</span><span class="sxs-lookup"><span data-stu-id="21685-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="21685-174">Dacă nu există alte înregistrări în Adobe Campaign Standard, în afară de ceea ce urmează să importați, puteți sări peste acest pas.</span><span class="sxs-lookup"><span data-stu-id="21685-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="21685-175">Importați date în Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="21685-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="21685-176">Acum că totul este la locul său, trebuie să importăm datele pregătite despre audiență din statistici despre audiență în Adobe Campaign Standard pentru a crea profiluri.</span><span class="sxs-lookup"><span data-stu-id="21685-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="21685-177">Învățați [cum să importați profiluri în Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) folosind un flux de lucru.</span><span class="sxs-lookup"><span data-stu-id="21685-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="21685-178">Fluxul de lucru de import din imaginea de mai jos a fost configurat să ruleze la fiecare 8 ore și caută segmente de informații despre publicul exportat (fișier .csv în Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="21685-178">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="21685-179">Fluxul de lucru extrage conținutul fișierului .csv într-o ordine de coloane specificată.</span><span class="sxs-lookup"><span data-stu-id="21685-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="21685-180">Acest flux de lucru a fost creat pentru a efectua tratarea erorilor de bază și pentru a se asigura că fiecare înregistrare are o adresă de e-mail înainte de a hidrata datele în Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="21685-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="21685-181">Fluxul de lucru extrage, de asemenea, numele segmentului din numele fișierului înainte de a fi introdus în datele profilului ACS.</span><span class="sxs-lookup"><span data-stu-id="21685-181">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captură de ecran a unui flux de lucru de import în interfața cu utilizatorul Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="21685-183">Regăsiți publicul în Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="21685-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="21685-184">Odată ce datele sunt importate în Adobe Campaign Standard, dvs. [poate crea un flux de lucru](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) și [interogare](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) clienții pe baza *Nume segment* și *Data segmentului* pentru a selecta profilurile care au fost identificate pentru campania noastră eșantion.</span><span class="sxs-lookup"><span data-stu-id="21685-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="21685-185">Creați și trimiteți e-mailul utilizând Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="21685-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="21685-186">Creați conținutul e-mailului și apoi [testați și trimiteți](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email-ul dvs.</span><span class="sxs-lookup"><span data-stu-id="21685-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Eșantion de e-mail cu ofertă de reînnoire de la Adobe Campaign Standard.":::
