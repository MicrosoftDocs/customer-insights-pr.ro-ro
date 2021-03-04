---
title: Crearea și gestionarea mediilor
description: Aflați cum să vă înscrieți pentru serviciu și cum să gestionați mediile.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 744f0bcbf5d2700363180f44e38d6dee9bf5df63
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270127"
---
# <a name="manage-environments"></a><span data-ttu-id="2bc65-103">Gestionați mediile</span><span class="sxs-lookup"><span data-stu-id="2bc65-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="2bc65-104">Acest articol explică cum să creați o nouă organizație și cum să asigurați accesul la un mediu.</span><span class="sxs-lookup"><span data-stu-id="2bc65-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="2bc65-105">Înscrieți-vă și creați o organizație</span><span class="sxs-lookup"><span data-stu-id="2bc65-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="2bc65-106">Accesați site-ul web [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="2bc65-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="2bc65-107">Selectați **Începeți lucrul**.</span><span class="sxs-lookup"><span data-stu-id="2bc65-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="2bc65-108">Alegeți scenariul de înregistrare preferat și selectați linkul corespunzător.</span><span class="sxs-lookup"><span data-stu-id="2bc65-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="2bc65-109">Acceptați termenii și condițiile și selectați **Continuare** pentru a începe crearea organizației.</span><span class="sxs-lookup"><span data-stu-id="2bc65-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="2bc65-110">După crearea mediului, veți fi redirecționat către [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="2bc65-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="2bc65-111">Utilizați mediul de demonstrație pentru a explora aplicația sau creați un mediu nou urmând pașii din secțiunea următoare.</span><span class="sxs-lookup"><span data-stu-id="2bc65-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="2bc65-112">După specificarea setărilor de mediu, selectați **Creați**.</span><span class="sxs-lookup"><span data-stu-id="2bc65-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="2bc65-113">Veți fi conectat după ce mediul a fost creat cu succes.</span><span class="sxs-lookup"><span data-stu-id="2bc65-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="2bc65-114">Creați un mediu într-o organizație existentă</span><span class="sxs-lookup"><span data-stu-id="2bc65-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="2bc65-115">Există două moduri de a crea un mediu nou.</span><span class="sxs-lookup"><span data-stu-id="2bc65-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="2bc65-116">Puteți fie specifica o configurație complet nouă, sau puteți copia unele setări de configurare dintr-un mediu existent.</span><span class="sxs-lookup"><span data-stu-id="2bc65-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="2bc65-117">Pentru crearea unui mediu:</span><span class="sxs-lookup"><span data-stu-id="2bc65-117">To create an environment:</span></span>

1. <span data-ttu-id="2bc65-118">Selectați selectorul **Mediu** în antetul aplicației.</span><span class="sxs-lookup"><span data-stu-id="2bc65-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="2bc65-119">Selectați **Nou**.</span><span class="sxs-lookup"><span data-stu-id="2bc65-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2bc65-120">![Setări ale mediului](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="2bc65-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="2bc65-121">În caseta de dialog **Creare mediu nou**, selectați **Mediu nou**.</span><span class="sxs-lookup"><span data-stu-id="2bc65-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="2bc65-122">Dacă doriți să [copiați date din mediul actual](#additional-considerations-for-copy-configuration-preview), selectați **Copiere din mediul existent**.</span><span class="sxs-lookup"><span data-stu-id="2bc65-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="2bc65-123">Veți vedea o listă cu toate mediile disponibile în organizația dvs. de unde puteți copia datele.</span><span class="sxs-lookup"><span data-stu-id="2bc65-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="2bc65-124">Furnizați următoarele detalii:</span><span class="sxs-lookup"><span data-stu-id="2bc65-124">Provide the following details:</span></span>
   - <span data-ttu-id="2bc65-125">**Nume**: Numele pentru acest mediu.</span><span class="sxs-lookup"><span data-stu-id="2bc65-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="2bc65-126">Acest câmp este deja completat dacă ați copiat dintr-un mediu existent, dar îl puteți modifica.</span><span class="sxs-lookup"><span data-stu-id="2bc65-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="2bc65-127">**Regiune**: Regiunea în care este implementat și găzduit serviciul.</span><span class="sxs-lookup"><span data-stu-id="2bc65-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="2bc65-128">**Tip**: Selectați dacă doriți să creați un mediu de producție sau sandbox.</span><span class="sxs-lookup"><span data-stu-id="2bc65-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="2bc65-129">Opțional, puteți selecta **Setări complexe**:</span><span class="sxs-lookup"><span data-stu-id="2bc65-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="2bc65-130">**Se salvează toate datele în**: Specifică unde doriți să stocați datele de ieșire generate de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2bc65-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="2bc65-131">Veți avea două opțiuni: **spațiu de stocare Customer Insights** (un Azure Data Lake gestionat de echipa Customer Insights) și **Azure Data Lake Storage Gen2** (Azure Data Lake Storage ale dvs.).</span><span class="sxs-lookup"><span data-stu-id="2bc65-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="2bc65-132">Opțiunea de stocare a Customer Insights este selectată în mod implicit.</span><span class="sxs-lookup"><span data-stu-id="2bc65-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2bc65-133">Prin salvarea datelor în Azure Data Lake Storage, sunteți de acord că datele vor fi transferate și stocate în locația geografică corespunzătoare pentru respectivul cont de stocare Azure, care poate diferi de locul în care sunt stocate datele în Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2bc65-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="2bc65-134">Aflați mai multe de la Centrul de autorizare Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2bc65-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="2bc65-135">În prezent, entitățile ingerate sunt întotdeauna stocate în data lake gestionat de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2bc65-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="2bc65-136">Acceptăm numai conturi Azure Data Lake Storage Gen2 din aceeași regiune Azure pe care ați selectat-o la crearea mediului.</span><span class="sxs-lookup"><span data-stu-id="2bc65-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="2bc65-137">Acceptăm numai conturile de stocare activate pentru Nume Spațiu Ierarhic Azure Data Lake Gen2 (HNS).</span><span class="sxs-lookup"><span data-stu-id="2bc65-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="2bc65-138">Pentru opțiunea Azure Data Lake Storage Gen2, puteți alege între utilizarea unei opțiuni bazate pe resurse și o opțiune bazată pe abonament pentru autentificare.</span><span class="sxs-lookup"><span data-stu-id="2bc65-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="2bc65-139">pentru mai multe informații, consultați [Conectați detaliile privind publicul la un cont Azure Data Lake Storage Gen2 cu o entitate principală de serviciu Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="2bc65-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="2bc65-140">Numele **Recipient** nu poate fi schimbat și va fi „customerinsights”.</span><span class="sxs-lookup"><span data-stu-id="2bc65-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="2bc65-141">Dacă doriți să utilizați [predicții](predictions.md) sau configurați partajarea datelor cu aplicații și soluții bazate pe Microsoft Dataverse, furnizați adresa URL de mediu Microsoft Dataverse sub **Configurați partajarea datelor cu Microsoft Dataverse și să activeze capabilități suplimentare**.</span><span class="sxs-lookup"><span data-stu-id="2bc65-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="2bc65-142">Selectați **Activați partajarea datelor** pentru a partaja datele de ieșire Customer Insights cu un Microsoft Dataverse Data Lake gestionat.</span><span class="sxs-lookup"><span data-stu-id="2bc65-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="2bc65-143">Partajarea datelor cu Microsoft Dataverse Data Lage gestionat nu este acceptat atunci când salvați toate datele pe propriul Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="2bc65-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="2bc65-144">[Predicția valorilor lipsă într-o entitate](predictions.md) momentan nu este acceptată atunci când activați partajarea datelor cu Microsoft Dataverse Data Lake gestionat.</span><span class="sxs-lookup"><span data-stu-id="2bc65-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="2bc65-145">![Opțiuni de configurare pentru a permite partajarea datelor cu Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="2bc65-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="2bc65-146">Când rulați procese, cum ar fi ingestia de date sau crearea de segmente, folderele corespunzătoare vor fi create în contul de stocare pe care l-ați specificat mai sus.</span><span class="sxs-lookup"><span data-stu-id="2bc65-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="2bc65-147">Fișierele de date și fișierele model.json vor fi create și adăugate la subfolderele respective pe baza procesului pe care îl derulați.</span><span class="sxs-lookup"><span data-stu-id="2bc65-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="2bc65-148">Dacă creați mai multe medii de Customer Insights și alegeți să salvați entitățile de ieșire din acele medii în contul dvs. de stocare, vor fi create dosare separate pentru fiecare mediu cu ci_<environmentid> în recipient.</span><span class="sxs-lookup"><span data-stu-id="2bc65-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="2bc65-149">Considerente suplimentare pentru configurarea copiei (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="2bc65-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="2bc65-150">Sunt copiate următoarele setări de configurare:</span><span class="sxs-lookup"><span data-stu-id="2bc65-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="2bc65-151">Configurații caracteristică</span><span class="sxs-lookup"><span data-stu-id="2bc65-151">Feature configurations</span></span>
- <span data-ttu-id="2bc65-152">Surse de date ingerate/importate</span><span class="sxs-lookup"><span data-stu-id="2bc65-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="2bc65-153">Configurarea unificării datelor (mapare, potrivire, îmbinare)</span><span class="sxs-lookup"><span data-stu-id="2bc65-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="2bc65-154">Segmente</span><span class="sxs-lookup"><span data-stu-id="2bc65-154">Segments</span></span>
- <span data-ttu-id="2bc65-155">Măsuri</span><span class="sxs-lookup"><span data-stu-id="2bc65-155">Measures</span></span>
- <span data-ttu-id="2bc65-156">Relaţii</span><span class="sxs-lookup"><span data-stu-id="2bc65-156">Relationships</span></span>
- <span data-ttu-id="2bc65-157">Activități</span><span class="sxs-lookup"><span data-stu-id="2bc65-157">Activities</span></span>
- <span data-ttu-id="2bc65-158">Index de căutare și filtrare</span><span class="sxs-lookup"><span data-stu-id="2bc65-158">Search & filter Index</span></span>
- <span data-ttu-id="2bc65-159">Destinații export</span><span class="sxs-lookup"><span data-stu-id="2bc65-159">Export destinations</span></span>
- <span data-ttu-id="2bc65-160">Reîmprospătare planificată</span><span class="sxs-lookup"><span data-stu-id="2bc65-160">Scheduled refresh</span></span>
- <span data-ttu-id="2bc65-161">Îmbogățiri</span><span class="sxs-lookup"><span data-stu-id="2bc65-161">Enrichments</span></span>
- <span data-ttu-id="2bc65-162">Management model</span><span class="sxs-lookup"><span data-stu-id="2bc65-162">Model management</span></span>
- <span data-ttu-id="2bc65-163">Atribuiri rol</span><span class="sxs-lookup"><span data-stu-id="2bc65-163">Role assignments</span></span>

<span data-ttu-id="2bc65-164">Următoarele setări *nu* sunt copiate:</span><span class="sxs-lookup"><span data-stu-id="2bc65-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="2bc65-165">Profiluri de client.</span><span class="sxs-lookup"><span data-stu-id="2bc65-165">Customer profiles.</span></span>
- <span data-ttu-id="2bc65-166">Acreditările sursă de date.</span><span class="sxs-lookup"><span data-stu-id="2bc65-166">Data source credentials.</span></span> <span data-ttu-id="2bc65-167">Va trebui să furnizați acreditările pentru fiecare sursă de date și să reîmprospătați sursele de date manual.</span><span class="sxs-lookup"><span data-stu-id="2bc65-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="2bc65-168">Surse de date din folderul Common Data Model și lake-ul gestionat Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2bc65-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="2bc65-169">Va trebui să creați acele surse de date manual cu același nume ca în mediul sursă.</span><span class="sxs-lookup"><span data-stu-id="2bc65-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="2bc65-170">Când copiați un mediu, veți vedea un mesaj de confirmare a faptului că noul mediu a fost creat.</span><span class="sxs-lookup"><span data-stu-id="2bc65-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="2bc65-171">Selectați **Accesați sursele de date** pentru a vedea lista surselor de date.</span><span class="sxs-lookup"><span data-stu-id="2bc65-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="2bc65-172">Toate sursele de date vor arăta o stare **Acreditări necesare**.</span><span class="sxs-lookup"><span data-stu-id="2bc65-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="2bc65-173">Editați sursele de date și introduceți acreditările pentru a le reîmprospăta.</span><span class="sxs-lookup"><span data-stu-id="2bc65-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2bc65-174">![Surse de date copiate](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="2bc65-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="2bc65-175">După reîmprospătarea surselor de date, accesați **Date** > **Unificare**.</span><span class="sxs-lookup"><span data-stu-id="2bc65-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="2bc65-176">Aici veți găsi setările din mediul sursă.</span><span class="sxs-lookup"><span data-stu-id="2bc65-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="2bc65-177">Editați-le după cum este necesar sau selectați **Rulează** pentru a începe procesul de unificare a datelor și a crea entitatea clientului unificat.</span><span class="sxs-lookup"><span data-stu-id="2bc65-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="2bc65-178">Când unificarea datelor este completă, accesați **Măsuri** și **Segmente** pentru a le reîmprospăta și pe acestea.</span><span class="sxs-lookup"><span data-stu-id="2bc65-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="2bc65-179">Editați un mediu existent</span><span class="sxs-lookup"><span data-stu-id="2bc65-179">Edit an existing environment</span></span>

<span data-ttu-id="2bc65-180">Puteți edita câteva dintre detaliile mediilor existente.</span><span class="sxs-lookup"><span data-stu-id="2bc65-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="2bc65-181">Selectați selectorul **Mediu** în antetul aplicației.</span><span class="sxs-lookup"><span data-stu-id="2bc65-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="2bc65-182">Selectați pictograma **Editare**.</span><span class="sxs-lookup"><span data-stu-id="2bc65-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="2bc65-183">În caseta **Editați mediul**, puteți actualiza **Numele afișat** al mediului, dar nu puteți schimba **Regiune** sau **Tip**.</span><span class="sxs-lookup"><span data-stu-id="2bc65-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="2bc65-184">Dacă un mediu este configurat pentru a stoca date în Azure Data Lake Storage Gen2, puteți actualiza **Cheia contului**.</span><span class="sxs-lookup"><span data-stu-id="2bc65-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="2bc65-185">Cu toate acestea, nu puteți schimba **Numele de cont** sau numele **Containerului**.</span><span class="sxs-lookup"><span data-stu-id="2bc65-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="2bc65-186">Opțional, puteți actualiza de la o conexiune bazată pe cheie de cont la o conexiune bazată pe resurse sau bazată pe abonament.</span><span class="sxs-lookup"><span data-stu-id="2bc65-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="2bc65-187">După actualizare, nu puteți reveni la cheia de cont după actualizare.</span><span class="sxs-lookup"><span data-stu-id="2bc65-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="2bc65-188">pentru mai multe informații, consultați [Conectați detaliile privind publicul la un cont Azure Data Lake Storage Gen2 cu o entitate principală de serviciu Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="2bc65-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="2bc65-189">Nu puteți schimba informațiile legate de **Recipient** la actualizarea conexiunii.</span><span class="sxs-lookup"><span data-stu-id="2bc65-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="2bc65-190">Resetați un mediu existent</span><span class="sxs-lookup"><span data-stu-id="2bc65-190">Reset an existing environment</span></span>

<span data-ttu-id="2bc65-191">Ca administrator, puteți reseta un mediu la o stare goală dacă doriți să ștergeți toate configurațiile și să eliminați datele ingerate.</span><span class="sxs-lookup"><span data-stu-id="2bc65-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="2bc65-192">Selectați selectorul **Mediu** în antetul aplicației.</span><span class="sxs-lookup"><span data-stu-id="2bc65-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="2bc65-193">Selectați mediul pe care doriți să îl resetați și selectați punctele de suspensie **...**.</span><span class="sxs-lookup"><span data-stu-id="2bc65-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="2bc65-194">Alegeți opțiunea **Resetați**.</span><span class="sxs-lookup"><span data-stu-id="2bc65-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="2bc65-195">Pentru a confirma ștergerea, introduceți numele mediului și selectați **Resetare**.</span><span class="sxs-lookup"><span data-stu-id="2bc65-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="2bc65-196">Ștergeți un mediu existent (disponibil numai pentru administratori)</span><span class="sxs-lookup"><span data-stu-id="2bc65-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="2bc65-197">În calitate de administrator, puteți șterge un mediu pe care îl administrați.</span><span class="sxs-lookup"><span data-stu-id="2bc65-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="2bc65-198">Selectați selectorul **Mediu** în antetul aplicației.</span><span class="sxs-lookup"><span data-stu-id="2bc65-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="2bc65-199">Selectați mediul pe care doriți să îl resetați și selectați punctele de suspensie **...**.</span><span class="sxs-lookup"><span data-stu-id="2bc65-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="2bc65-200">Alegeți opțiunea **Ștergere**.</span><span class="sxs-lookup"><span data-stu-id="2bc65-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="2bc65-201">Pentru a confirma ștergerea, introduceți numele mediului și selectați **Ștergere**.</span><span class="sxs-lookup"><span data-stu-id="2bc65-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]