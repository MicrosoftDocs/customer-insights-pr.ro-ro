---
title: Experimente Azure Machine Learning
description: Utilizați modele bazate pe Azure Machine Learning în Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: c166015b92596da0c6097e3d25e89579a5186ce0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267921"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="d0cc1-103">Utilizați modele bazate pe Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="d0cc1-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="d0cc1-104">Datele unificate din Dynamics 365 Customer Insights sunt o sursă pentru construirea de modele de învățare programată care pot genera informații suplimentare despre afaceri.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="d0cc1-105">Customer Insights se integrează cu Machine Learning Studio (clasic) și Azure Machine Learning pentru a utiliza propriile modele particularizate.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="d0cc1-106">Consultați [Experimente Machine Learning Studio (clasic)](machine-learning-studio-experiments.md) pentru exemple de experimente construite pe Machine Learning Studio (clasic).</span><span class="sxs-lookup"><span data-stu-id="d0cc1-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="d0cc1-107">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="d0cc1-107">Prerequisites</span></span>

- <span data-ttu-id="d0cc1-108">Accesați la Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d0cc1-108">Access to Customer Insights</span></span>
- <span data-ttu-id="d0cc1-109">Abonament activ Azure Enterprise</span><span class="sxs-lookup"><span data-stu-id="d0cc1-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="d0cc1-110">Profiluri de client unificate</span><span class="sxs-lookup"><span data-stu-id="d0cc1-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="d0cc1-111">[Export entitate către stocarea Blob Azure](export-azure-blob-storage.md) configurat</span><span class="sxs-lookup"><span data-stu-id="d0cc1-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="d0cc1-112">Configurați spațiul de lucru Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="d0cc1-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="d0cc1-113">Consultați [creați un spațiu de lucru Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) pentru diferitele opțiuni de creare a spațiului de lucru.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="d0cc1-114">Pentru cele mai bune performanțe, creați spațiul de lucru într-o regiune Azure care este cea mai apropiată geografic de mediul dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="d0cc1-115">Accesați spațiul dvs. de lucru prin [Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="d0cc1-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="d0cc1-116">Sunt câteva [modalități de interacțiune](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) cu spațiul dvs. de lucru.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="d0cc1-117">Lucrați cu designerul Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="d0cc1-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="d0cc1-118">Designerul Azure Machine Learning oferă o pânză vizuală în care puteți glisa și fixa seturi de date și module, similar cu Machine Learning Studio (clasic).</span><span class="sxs-lookup"><span data-stu-id="d0cc1-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="d0cc1-119">Un canal de lot creat din designer poate fi integrată în Customer Insights dacă acestea sunt configurate corespunzător.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="d0cc1-120">Lucrul cu SDK Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="d0cc1-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="d0cc1-121">Specialiștii în date și dezvoltatorii de AI folosesc [SDK Azure Machine Learning](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) pentru a construi fluxuri de lucru de învățare programată.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="d0cc1-122">În prezent, modelele instruite folosind SDK nu pot fi integrate direct cu Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="d0cc1-123">Pentru integrarea cu Customer Insights este necesar un canal de inferență de lot care consumă acel model.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="d0cc1-124">Cerințe de canal de lot pentru integrare cu Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d0cc1-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="d0cc1-125">Configurare set de date</span><span class="sxs-lookup"><span data-stu-id="d0cc1-125">Dataset Configuration</span></span>

<span data-ttu-id="d0cc1-126">Trebuie să creați seturi de date pentru a utiliza datele entității din Customer Insights în canalul de inferență a lotului.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="d0cc1-127">Aceste seturi de date trebuie înregistrate în spațiul de lucru.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="d0cc1-128">În prezent, acceptăm doar [seturi de date tabelare](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) în format .csv.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="d0cc1-129">Seturile de date care corespund datelor entității trebuie parametrizate ca parametru de canal.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="d0cc1-130">Parametrii setului de date în Designer</span><span class="sxs-lookup"><span data-stu-id="d0cc1-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="d0cc1-131">În designer, deschideți **Selectare Coloane în setul de date** și selectați **Setare ca parametru al canalului** unde furnizați un nume pentru parametru.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="d0cc1-132">![Parametrizare set de date în designer](media/intelligence-designer-dataset-parameters.png "Parametrizare set de date în designer")</span><span class="sxs-lookup"><span data-stu-id="d0cc1-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="d0cc1-133">Parametru set de date în SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="d0cc1-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="d0cc1-134">Canal de inferență a lotului</span><span class="sxs-lookup"><span data-stu-id="d0cc1-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="d0cc1-135">În designer, un canal de instruire poate fi utilizat pentru a crea sau actualiza un canal de inferență.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="d0cc1-136">În prezent, sunt acceptate doar canalele de inferență în lot.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="d0cc1-137">Folosind SDK, puteți publica canalul într-un punct final.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="d0cc1-138">În prezent, Customer Insights se integrează cu canalul implicit într-un punct final al canalului de lot din spațiul de lucru Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="d0cc1-139">Importați datele canalelor în Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d0cc1-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="d0cc1-140">Designerul oferă [modulul Export date](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) care permite exportarea ieșirii unui canal în stocarea Azure.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="d0cc1-141">În prezent, modulul trebuie să utilizeze tipul de depozit de date **Stocare Blob Azure** și parametrizează **Depozitul de date** și **Calea** relativă.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="d0cc1-142">Customer Insights anulează ambii acești parametri în timpul executării canalului cu un depozit de date și o cale accesibilă produsului.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d0cc1-143">![Exportul configurării modulului de date](media/intelligence-designer-importdata.png "Exportul configurării modulului de date")</span><span class="sxs-lookup"><span data-stu-id="d0cc1-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="d0cc1-144">Când scrieți ieșirea de inferență folosind cod, puteți încărca ieșirea către cale dintr-un *depozit de date înregistrat* în spațiul de lucru.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="d0cc1-145">Când calea și depozitul de date sunt parametrizate în canal, Customer Insights va putea citi și importa ieșirea de inferență.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="d0cc1-146">În prezent, este acceptată o singură ieșire tabulară în format csv.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="d0cc1-147">Calea trebuie să includă directorul și numele fișierului.</span><span class="sxs-lookup"><span data-stu-id="d0cc1-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]