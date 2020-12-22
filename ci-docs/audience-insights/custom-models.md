---
title: Modele învățare programată particularizate | Documente Microsoft
description: Lucrați cu modele particularizate de la Învățare programată Azure în Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668918"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="9452d-103">Modele învățare programată particularizate</span><span class="sxs-lookup"><span data-stu-id="9452d-103">Custom machine learning models</span></span>

<span data-ttu-id="9452d-104">**Informații** > **Modele particularizate** vă permite să gestionați fluxurile de lucru pe baza modelelor Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="9452d-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="9452d-105">Fluxurile de lucru vă ajută să alegeți datele din care doriți să generați detalii și să mapați rezultatele la datele unificate ale clienților.</span><span class="sxs-lookup"><span data-stu-id="9452d-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="9452d-106">Pentru mai multe informații despre construirea de modele ML particularizate, consultați [Utilizare modele bazate pe Azure Machine Learning](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="9452d-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="9452d-107">AI responsabil</span><span class="sxs-lookup"><span data-stu-id="9452d-107">Responsible AI</span></span>

<span data-ttu-id="9452d-108">Predicțiile oferă capacități pentru crearea de experiențe client mai bune, îmbunătățirea capacităților de afaceri și fluxurilor de venituri.</span><span class="sxs-lookup"><span data-stu-id="9452d-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="9452d-109">Vă recomandăm cu tărie să compensați valoarea predicției dvs. cu impactul pe care îl are și cu interferențele care pot fi introduse într-o manieră etică.</span><span class="sxs-lookup"><span data-stu-id="9452d-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="9452d-110">Aflați mai multe despre cum Microsoft [tratează AI responsabil](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="9452d-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="9452d-111">Puteți afla și despre [tehnici și procese pentru învățare programată responsabilă](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specifice Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="9452d-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9452d-112">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="9452d-112">Prerequisites</span></span>

- <span data-ttu-id="9452d-113">În prezent, această caracteristică acceptă serviciile web publicate prin intermediul [Machine Learning Studio (clasic)](https://studio.azureml.net) și [canalele lot Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="9452d-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="9452d-114">Aveți nevoie de un cont Azure Data Lake Storage Gen2 asociat instanței dvs. Azure Studio pentru a utiliza această caracteristică.</span><span class="sxs-lookup"><span data-stu-id="9452d-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="9452d-115">Pentru mai multe informații, consultați [Creați un Cont de stocare Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="9452d-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="9452d-116">Adăugați un nou flux de lucru</span><span class="sxs-lookup"><span data-stu-id="9452d-116">Add a new workflow</span></span>

1. <span data-ttu-id="9452d-117">Accesați **Informații** > **Modele particularizate** și selectați **Flux de lucru nou**.</span><span class="sxs-lookup"><span data-stu-id="9452d-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="9452d-118">Dați modelului dvs. particularizat un nume ușor de recunoscut în câmpul **Nume**.</span><span class="sxs-lookup"><span data-stu-id="9452d-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9452d-119">![Captură de ecran a panoului noului flux de lucru](media/new-workflowv2.png "Captură de ecran a panoului noului flux de lucru")</span><span class="sxs-lookup"><span data-stu-id="9452d-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="9452d-120">Selectați organizația care conține serviciul web din **Entitate găzduită care conține serviciul dvs. web**.</span><span class="sxs-lookup"><span data-stu-id="9452d-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="9452d-121">Dacă abonamentul dvs. Azure Machine Learning se află într-o entitate găzduită diferită de Customer Insights, selectați **Autentificare** cu datele dvs. de acreditare pentru organizația selectată.</span><span class="sxs-lookup"><span data-stu-id="9452d-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="9452d-122">Selectați **Spații de lucru** asociate cu serviciul dvs. web.</span><span class="sxs-lookup"><span data-stu-id="9452d-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="9452d-123">Există două secțiuni listate, una pentru Azure Machine Learning v1 (Machine Learning Studio (clasic)) și Azure Machine Learning v2 (Azure Machine Learning).</span><span class="sxs-lookup"><span data-stu-id="9452d-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="9452d-124">Dacă nu sunteți sigur care spațiu de lucru este cel potrivit pentru serviciul dvs. web Machine Learning Studio (clasic), selectați **Oricare**.</span><span class="sxs-lookup"><span data-stu-id="9452d-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="9452d-125">Alegeți serviciul web Machine Learning Studio (clasic) sau canalul Azure Machine Learning în lista verticală **Serviciu web care conține modelul dvs.**.</span><span class="sxs-lookup"><span data-stu-id="9452d-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="9452d-126">Apoi, selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="9452d-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="9452d-127">Aflați mai multe despre [publicarea unui serviciu web în Machine Learning Studio (clasic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="9452d-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="9452d-128">Aflați mai multe despre [publicarea unui canal în Azure Machine Learning folosind designerul](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) sau [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="9452d-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="9452d-129">Canalul dvs. trebuie publicat sub un [punctul final al canalului](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="9452d-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="9452d-130">Pentru fiecare **Intrare serviciu web**, selectați **Entitatea** adecvată pentru Detalii despre audiență și selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="9452d-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9452d-131">![Configurați un flux de lucru](media/intelligence-screen2-updated.png "Configurați un flux de lucru")</span><span class="sxs-lookup"><span data-stu-id="9452d-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="9452d-132">În pasul **Parametri de ieșire model**, setați următoarele proprietăți:</span><span class="sxs-lookup"><span data-stu-id="9452d-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="9452d-133">Machine Learning Studio (clasic)</span><span class="sxs-lookup"><span data-stu-id="9452d-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="9452d-134">Introduceți ieșirea **Numele entității** în care doriți ca rezultatele de ieșire ale serviciului web să treacă.</span><span class="sxs-lookup"><span data-stu-id="9452d-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="9452d-135">Învățare programată Azure</span><span class="sxs-lookup"><span data-stu-id="9452d-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="9452d-136">Introduceți ieșirea **Numele entității** în care doriți ca rezultatele de ieșire ale canalului să treacă.</span><span class="sxs-lookup"><span data-stu-id="9452d-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="9452d-137">Selectați **Nume parametru ieșire depozit de date** din canalul lotului din meniul vertical.</span><span class="sxs-lookup"><span data-stu-id="9452d-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="9452d-138">Selectați **Nume parametru cale de ieșire** din canalul lotului din meniul vertical.</span><span class="sxs-lookup"><span data-stu-id="9452d-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="9452d-139">![Panou parametru de ieșire model](media/intelligence-screen3-outputparameters.png "Panou parametru de ieșire model")</span><span class="sxs-lookup"><span data-stu-id="9452d-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="9452d-140">Selectați atributul de potrivire din lista verticală **ID client în rezultate** care identifică clienții și selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="9452d-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9452d-141">![Corelare rezultate cu panoul datele clienților](media/intelligence-screen4-relatetocustomer.png "Corelare rezultate cu panoul datele clienților")</span><span class="sxs-lookup"><span data-stu-id="9452d-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="9452d-142">Vei vedea ecranul **Flux de lucru salvat** cu detalii despre fluxul de lucru.</span><span class="sxs-lookup"><span data-stu-id="9452d-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="9452d-143">Dacă ați configurat un flux de lucru pentru un canal Azure Machine Learning, Detaliile despre audiență se vor atașa la spațiul de lucru care conține canalul.</span><span class="sxs-lookup"><span data-stu-id="9452d-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="9452d-144">Detaliile despre audiență vor avea un rol de **Colaborator** în spațiul de lucru Azure.</span><span class="sxs-lookup"><span data-stu-id="9452d-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="9452d-145">Selectați **Terminat**.</span><span class="sxs-lookup"><span data-stu-id="9452d-145">Select **Done**.</span></span>

1. <span data-ttu-id="9452d-146">Acum puteți rula fluxul de lucru din pagina **Modele particularizate**.</span><span class="sxs-lookup"><span data-stu-id="9452d-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="9452d-147">Editați un flux de lucru</span><span class="sxs-lookup"><span data-stu-id="9452d-147">Edit a workflow</span></span>

1. <span data-ttu-id="9452d-148">Pe pagina **Modele particularizate**, selectați elipsele verticale din coloana **Acțiuni** de lângă un flux de lucru pe care l-ați creat anterior și selectați **Editare**.</span><span class="sxs-lookup"><span data-stu-id="9452d-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="9452d-149">Puteți actualiza numele recunoscut al fluxului de lucru în câmpul **Nume afișat**, dar nu puteți schimba serviciul web configurat sau canalul.</span><span class="sxs-lookup"><span data-stu-id="9452d-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="9452d-150">Selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="9452d-150">Select **Next**.</span></span>

1. <span data-ttu-id="9452d-151">Pentru fiecare **Intrare serviciu web**, puteți actualiza **Entitatea** potrivită din Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="9452d-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="9452d-152">Apoi, selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="9452d-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="9452d-153">În pasul **Parametri de ieșire model**, setați următoarele proprietăți:</span><span class="sxs-lookup"><span data-stu-id="9452d-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="9452d-154">Machine Learning Studio (clasic)</span><span class="sxs-lookup"><span data-stu-id="9452d-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="9452d-155">Introduceți ieșirea **Numele entității** în care doriți ca rezultatele de ieșire ale serviciului web să treacă.</span><span class="sxs-lookup"><span data-stu-id="9452d-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="9452d-156">Învățare programată Azure</span><span class="sxs-lookup"><span data-stu-id="9452d-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="9452d-157">Introduceți ieșirea **Numele entității** în care doriți ca rezultatele de ieșire ale canalului să treacă.</span><span class="sxs-lookup"><span data-stu-id="9452d-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="9452d-158">Selectați **Nume parametru ieșire depozit de date** pentru canalul de testare.</span><span class="sxs-lookup"><span data-stu-id="9452d-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="9452d-159">Selectați **Nume parametru ieșire cale** pentru canalul de testare.</span><span class="sxs-lookup"><span data-stu-id="9452d-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="9452d-160">Selectați atributul de potrivire din lista verticală **ID client în rezultate** care identifică clienții și selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="9452d-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="9452d-161">Trebuie să alegeți un atribut din rezultatul inferenței cu valori similare coloanei ID client a entității client.</span><span class="sxs-lookup"><span data-stu-id="9452d-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="9452d-162">Dacă nu aveți o astfel de coloană în setul de date, alegeți un atribut care identifică în mod unic rândul.</span><span class="sxs-lookup"><span data-stu-id="9452d-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="9452d-163">Executarea unui flux de lucru</span><span class="sxs-lookup"><span data-stu-id="9452d-163">Run a workflow</span></span>

1. <span data-ttu-id="9452d-164">Pe pagina **Modele particularizate**, selectați elipsele verticale din coloana **Acțiuni** de lângă un flux de lucru pe care l-ați creat anterior.</span><span class="sxs-lookup"><span data-stu-id="9452d-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="9452d-165">Selectare rând **Rulare**.</span><span class="sxs-lookup"><span data-stu-id="9452d-165">Select **Run**.</span></span>

<span data-ttu-id="9452d-166">Fluxul dvs. de lucru rulează automat cu fiecare reîmprospătare planificată.</span><span class="sxs-lookup"><span data-stu-id="9452d-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="9452d-167">Aflați mai multe despre [configurarea reîmprospătărilor planificate](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9452d-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="9452d-168">Ștergeți un flux de lucru</span><span class="sxs-lookup"><span data-stu-id="9452d-168">Delete a workflow</span></span>

1. <span data-ttu-id="9452d-169">Pe pagina **Modele particularizate**, selectați elipsele verticale din coloana **Acțiuni** de lângă un flux de lucru pe care l-ați creat anterior.</span><span class="sxs-lookup"><span data-stu-id="9452d-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="9452d-170">Selectați **Ștergere** și confirmați ștergerea.</span><span class="sxs-lookup"><span data-stu-id="9452d-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="9452d-171">Fluxul de lucru va fi șters.</span><span class="sxs-lookup"><span data-stu-id="9452d-171">Your workflow will be deleted.</span></span> <span data-ttu-id="9452d-172">[Entitatea](entities.md) care a fost creată atunci când ați creat fluxul de lucru persistă și poate fi vizualizată din pagina **Entități**.</span><span class="sxs-lookup"><span data-stu-id="9452d-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
