---
title: Experimente Azure Machine Learning
description: Utilizați modele bazate pe Azure Machine Learning în Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4c04a1d08aba152ce91d452ae2300c1ce0fc79e5d6980ac506dc40d9914c9fca
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033187"
---
# <a name="use-azure-machine-learning-based-models"></a>Utilizați modele bazate pe Azure Machine Learning

Datele unificate din Dynamics 365 Customer Insights sunt o sursă pentru construirea de modele de învățare programată care pot genera informații suplimentare despre afaceri. Customer Insights se integrează cu Machine Learning Studio (clasic) și Azure Machine Learning pentru a utiliza propriile modele particularizate. Consultați [Experimente Machine Learning Studio (clasic)](machine-learning-studio-experiments.md) pentru exemple de experimente construite pe Machine Learning Studio (clasic). 

## <a name="prerequisites"></a>Cerințe preliminare

- Accesați la Customer Insights
- Abonament activ Azure Enterprise
- [Profiluri de client unificate](data-unification.md)
- [Export entitate către stocarea Blob Azure](export-azure-blob-storage.md) configurat

## <a name="set-up-azure-machine-learning-workspace"></a>Configurați spațiul de lucru Azure Machine Learning

1. Consultați [creați un spațiu de lucru Azure Machine Learning](/azure/machine-learning/concept-workspace#-create-a-workspace) pentru diferitele opțiuni de creare a spațiului de lucru. Pentru cele mai bune performanțe, creați spațiul de lucru într-o regiune Azure care este cea mai apropiată geografic de mediul dvs. Customer Insights.

1. Accesați spațiul dvs. de lucru prin [Azure Machine Learning Studio](https://ml.azure.com/). Sunt câteva [modalități de interacțiune](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) cu spațiul dvs. de lucru.

## <a name="work-with-azure-machine-learning-designer"></a>Lucrați cu designerul Azure Machine Learning

Designerul Azure Machine Learning oferă o pânză vizuală în care puteți glisa și fixa seturi de date și module, similar cu Machine Learning Studio (clasic). Un canal de lot creat din designer poate fi integrată în Customer Insights dacă acestea sunt configurate corespunzător. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Lucrul cu SDK Azure Machine Learning

Specialiștii în date și dezvoltatorii de AI folosesc [SDK Azure Machine Learning](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) pentru a construi fluxuri de lucru de învățare programată. În prezent, modelele instruite folosind SDK nu pot fi integrate direct cu Customer Insights. Pentru integrarea cu Customer Insights este necesar un canal de inferență de lot care consumă acel model.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Cerințe de canal de lot pentru integrare cu Customer Insights

### <a name="dataset-configuration"></a>Configurare set de date

Trebuie să creați seturi de date pentru a utiliza datele entității din Customer Insights în canalul de inferență a lotului. Aceste seturi de date trebuie înregistrate în spațiul de lucru. În prezent, acceptăm doar [seturi de date tabelare](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) în format .csv. Seturile de date care corespund datelor entității trebuie parametrizate ca parametru de canal.
   
* Parametrii setului de date în Designer
   
     În designer, deschideți **Selectare Coloane în setul de date** și selectați **Setare ca parametru al canalului** unde furnizați un nume pentru parametru.

     > [!div class="mx-imgBorder"]
     > ![Parametrizare set de date în proiectant.](media/intelligence-designer-dataset-parameters.png "Parametrizare set de date în designer")
   
* Parametru set de date în SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Canal de inferență a lotului
  
* În designer, un canal de instruire poate fi utilizat pentru a crea sau actualiza un canal de inferență. În prezent, sunt acceptate doar canalele de inferență în lot.

* Folosind SDK, puteți publica canalul într-un punct final. În prezent, Customer Insights se integrează cu canalul implicit într-un punct final al canalului de lot din spațiul de lucru Machine Learning.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Importați datele canalelor în Customer Insights

* Designerul oferă [modulul Export date](/azure/machine-learning/algorithm-module-reference/export-data) care permite exportarea ieșirii unui canal în stocarea Azure. În prezent, modulul trebuie să utilizeze tipul de depozit de date **Stocare Blob Azure** și parametrizează **Depozitul de date** și **Calea** relativă. Customer Insights anulează ambii acești parametri în timpul executării canalului cu un depozit de date și o cale accesibilă produsului.
   > [!div class="mx-imgBorder"]
   > ![Exportul configurării modulului de date.](media/intelligence-designer-importdata.png "Exportul configurării modulului de date")
   
* Când scrieți ieșirea de inferență folosind cod, puteți încărca ieșirea către cale dintr-un *depozit de date înregistrat* în spațiul de lucru. Când calea și depozitul de date sunt parametrizate în canal, Customer Insights va putea citi și importa ieșirea de inferență. În prezent, este acceptată o singură ieșire tabulară în format csv. Calea trebuie să includă directorul și numele fișierului.

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