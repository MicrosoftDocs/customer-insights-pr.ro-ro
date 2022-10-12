---
title: Utilizați modele bazate pe Azure Machine Learning
description: Utilizați modele bazate pe Azure Machine Learning în Dynamics 365 Customer Insights.
ms.date: 09/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8d9c9324ea4840b585b9af1a58d505ccaea6f18e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609840"
---
# <a name="use-azure-machine-learning-based-models"></a>Utilizați modele bazate pe Azure Machine Learning

Datele unificate din Dynamics 365 Customer Insights sunt o sursă pentru construirea de modele de învățare programată care pot genera informații suplimentare despre afaceri. Customer Insights se integrează cu învățare programată Azure pentru a utiliza propriile modele personalizate.

## <a name="prerequisites"></a>Cerințe preliminare

- Accesați la Customer Insights
- Abonament activ Azure Enterprise
- [Profiluri de client unificate](data-unification.md)
- [Export entitate către stocarea Blob Azure](export-azure-blob-storage.md) configurat

## <a name="set-up-azure-machine-learning-workspace"></a>Configurați spațiul de lucru Azure Machine Learning

1. Consultați [creați un spațiu de lucru Azure Machine Learning](/azure/machine-learning/concept-workspace#-create-a-workspace) pentru diferitele opțiuni de creare a spațiului de lucru. Pentru cele mai bune performanțe, creați spațiul de lucru într-o regiune Azure care este cea mai apropiată geografic de mediul dvs. Customer Insights.

1. Accesați spațiul dvs. de lucru prin [Azure Machine Learning Studio](https://ml.azure.com/). Sunt câteva [modalități de interacțiune](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) cu spațiul dvs. de lucru.

## <a name="work-with-azure-machine-learning-designer"></a>Lucrați cu designerul Azure Machine Learning

Designerul Azure învățare programată oferă o pânză vizuală în care puteți glisa și plasa seturi de date și module. Un canal de lot creat din designer poate fi integrată în Customer Insights dacă acestea sunt configurate corespunzător. 

## <a name="working-with-azure-machine-learning-sdk"></a>Lucrul cu SDK Azure Machine Learning

Specialiștii în date și dezvoltatorii de AI folosesc [SDK Azure Machine Learning](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) pentru a construi fluxuri de lucru de învățare programată. În prezent, modelele instruite folosind SDK nu pot fi integrate direct cu Customer Insights. Pentru integrarea cu Customer Insights este necesar un canal de inferență de lot care consumă acel model.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Cerințe de canal de lot pentru integrare cu Customer Insights

### <a name="dataset-configuration"></a>Configurația setului de date

Creați seturi de date pentru a utiliza datele de entitate din Customer Insights pentru conducta dvs. de inferență pe lot. Înregistrați aceste seturi de date în spațiul de lucru. În prezent, acceptăm doar [seturi de date tabelare](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) în format .csv. Parametrizați seturile de date care corespund datelor de entitate ca parametru de conductă.

- Parametrii setului de date în Designer

  În designer, deschideți **Selectare Coloane în setul de date** și selectați **Setare ca parametru al canalului** unde furnizați un nume pentru parametru.

  :::image type="content" source="media/intelligence-designer-dataset-parameters.png" alt-text="Parametrizare set de date în proiectant.":::

- Parametru set de date în SDK (Python)

   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Canal de inferență a lotului
  
- În designer, utilizați o conductă de antrenament pentru a crea sau actualiza o conductă de inferență. În prezent, sunt acceptate doar canalele de inferență în lot.

- Folosind SDK-ul, publicați pipeline la un punct final. În prezent, Customer Insights se integrează cu canalul implicit într-un punct final al canalului de lot din spațiul de lucru Machine Learning.

   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Importați datele canalelor în Customer Insights

- Designerul oferă [modulul Export date](/azure/machine-learning/algorithm-module-reference/export-data) care permite exportarea ieșirii unui canal în stocarea Azure. În prezent, modulul trebuie să utilizeze tipul de depozit de date **Stocare Blob Azure** și parametrizează **Depozitul de date** și **Calea** relativă. Customer Insights anulează ambii acești parametri în timpul executării canalului cu un depozit de date și o cale accesibilă produsului.

  :::image type="content" source="media/intelligence-designer-importdata.png" alt-text="Exportul configurării modulului de date.":::

- Când scrieți rezultatul de inferență folosind cod, încărcați rezultatul pe o cale din a *depozit de date înregistrat* în spațiul de lucru. Când calea și depozitul de date sunt parametrizate în canal, Customer Insights va putea citi și importa ieșirea de inferență. În prezent, este acceptată o singură ieșire tabulară în format csv. Calea trebuie să includă directorul și numele fișierului.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]