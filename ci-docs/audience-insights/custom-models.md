---
title: Modele învățare programată particularizate | Documente Microsoft
description: Lucrați cu modele particularizate de la Învățare programată Azure în Dynamics 365 Customer Insights.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 187995cdf4d92a0609f8abb4c792e698ad4342cdb1f578744136add1bfcf3a53
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032957"
---
# <a name="custom-machine-learning-models"></a>Modele învățare programată particularizate

**Informații** > **Modele particularizate** vă permite să gestionați fluxurile de lucru pe baza modelelor Azure Machine Learning. Fluxurile de lucru vă ajută să alegeți datele din care doriți să generați detalii și să mapați rezultatele la datele unificate ale clienților. Pentru mai multe informații despre construirea de modele ML particularizate, consultați [Utilizare modele bazate pe Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>AI responsabil

Predicțiile oferă capacități pentru crearea de experiențe client mai bune, îmbunătățirea capacităților de afaceri și fluxurilor de venituri. Vă recomandăm cu tărie să compensați valoarea predicției dvs. cu impactul pe care îl are și cu interferențele care pot fi introduse într-o manieră etică. Aflați mai multe despre cum Microsoft [tratează AI responsabil](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Puteți afla și despre [tehnici și procese pentru învățare programată responsabilă](/azure/machine-learning/concept-responsible-ml) specifice Azure Machine Learning.

## <a name="prerequisites"></a>Cerințe preliminare

- În prezent, această caracteristică acceptă serviciile web publicate prin intermediul [Machine Learning Studio (clasic)](https://studio.azureml.net) și [canalele lot Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines).

- Aveți nevoie de un cont Azure Data Lake Storage Gen2 asociat instanței dvs. Azure Studio pentru a utiliza această caracteristică. Pentru mai multe informații, consultați [Creați un Cont de stocare Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- Pentru spațiile de lucru Azure Machine Learning cu canale, aveți nevoie de permisiunile proprietarului sau ale administratorului accesului la spațiul de lucru Azure Machine Learning.

   > [!NOTE]
   > Datele sunt transferate între instanțele dvs. Customer Insights și serviciile web sau canalele Azure selectate din fluxul de lucru. Când transferați date către un serviciu Azure, asigurați-vă că serviciul este configurat să proceseze date în modul și locația necesare pentru a se conforma oricărei cerințe legale sau de reglementare pentru respectivele date din organizația dvs.

## <a name="add-a-new-workflow"></a>Adăugați un nou flux de lucru

1. Accesați **Informații** > **Modele particularizate** și selectați **Flux de lucru nou**.

1. Dați modelului dvs. particularizat un nume ușor de recunoscut în câmpul **Nume**.

   > [!div class="mx-imgBorder"]
   > ![Captură de ecran a panoului noului flux de lucru.](media/new-workflowv2.png "Captură de ecran a panoului noului flux de lucru")

1. Selectați organizația care conține serviciul web din **Entitate găzduită care conține serviciul dvs. web**.

1. Dacă abonamentul dvs. Azure Machine Learning se află într-o entitate găzduită diferită de Customer Insights, selectați **Autentificare** cu datele dvs. de acreditare pentru organizația selectată.

1. Selectați **Spații de lucru** asociate cu serviciul dvs. web. Există două secțiuni listate, una pentru Azure Machine Learning v1 (Machine Learning Studio (clasic)) și Azure Machine Learning v2 (Azure Machine Learning). Dacă nu sunteți sigur care spațiu de lucru este cel potrivit pentru serviciul dvs. web Machine Learning Studio (clasic), selectați **Oricare**.

1. Alegeți serviciul web Machine Learning Studio (clasic) sau canalul Azure Machine Learning în lista verticală **Serviciu web care conține modelul dvs.**. Apoi, selectați **Următorul**.
   - Aflați mai multe despre [publicarea unui serviciu web în Machine Learning Studio (clasic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Aflați mai multe despre [publicarea unui canal în Azure Machine Learning folosind designerul](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) sau [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Canalul dvs. trebuie publicat sub un [punctul final al canalului](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Pentru fiecare **Intrare serviciu web**, selectați **Entitatea** adecvată pentru Detalii despre audiență și selectați **Următorul**.
   > [!NOTE]
   > Fluxul de lucru al modelului personalizat va aplica euristică pentru a mapa câmpurile de intrare ale serviciului web la atributele entității pe baza numelui și tipului de date al câmpului. Veți vedea o eroare dacă un câmp de servicii web nu poate fi mapat la o entitate.

   > [!div class="mx-imgBorder"]
   > ![Configurați un flux de lucru.](media/intelligence-screen2-updated.png "Configurați un flux de lucru")

1. În pasul **Parametri de ieșire model**, setați următoarele proprietăți:
   - Machine Learning Studio (clasic)
      1. Introduceți ieșirea **Numele entității** în care doriți ca rezultatele de ieșire ale serviciului web să treacă.
   - Învățare programată Azure
      1. Introduceți ieșirea **Numele entității** în care doriți ca rezultatele de ieșire ale canalului să treacă.
      1. Selectați **Nume parametru ieșire depozit de date** din canalul lotului din meniul vertical.
      1. Selectați **Nume parametru cale de ieșire** din canalul lotului din meniul vertical.

      > [!div class="mx-imgBorder"]
      > ![Panou parametru de ieșire model.](media/intelligence-screen3-outputparameters.png "Panou parametru de ieșire model")

1. Selectați atributul de potrivire din lista verticală **ID Client în rezultate** care identifică clienții și selectați **Salvare**.

   > [!div class="mx-imgBorder"]
   > ![Corelare rezultate cu panoul datele clienților.](media/intelligence-screen4-relatetocustomer.png "Corelare rezultate cu panoul datele clienților")

1. Vei vedea ecranul **Flux de lucru salvat** cu detalii despre fluxul de lucru.    
   Dacă ați configurat un flux de lucru pentru un canal Azure Machine Learning, Detaliile despre audiență se vor atașa la spațiul de lucru care conține canalul. Detaliile despre audiență vor avea un rol de **Colaborator** în spațiul de lucru Azure.

1. Selectați **Terminat**.

1. Acum puteți rula fluxul de lucru din pagina **Modele particularizate**.

## <a name="edit-a-workflow"></a>Editați un flux de lucru

1. Pe pagina **Modele particularizate**, selectați elipsele verticale din coloana **Acțiuni** de lângă un flux de lucru pe care l-ați creat anterior și selectați **Editare**.

1. Puteți actualiza numele recunoscut al fluxului de lucru în câmpul **Nume afișat**, dar nu puteți schimba serviciul web configurat sau canalul. Selectați **Următorul**.

1. Pentru fiecare **Intrare serviciu web**, puteți actualiza **Entitatea** potrivită din Detalii despre audiență. Apoi, selectați **Următorul**.

1. În pasul **Parametri de ieșire model**, setați următoarele proprietăți:
   - Machine Learning Studio (clasic)
      1. Introduceți ieșirea **Numele entității** în care doriți ca rezultatele de ieșire ale serviciului web să treacă.
   - Învățare programată Azure
      1. Introduceți ieșirea **Numele entității** în care doriți ca rezultatele de ieșire ale canalului să treacă.
      1. Selectați **Nume parametru ieșire depozit de date** pentru canalul de testare.
      1. Selectați **Nume parametru ieșire cale** pentru canalul de testare.

1. Selectați atributul de potrivire din lista verticală **ID Client în rezultate** care identifică clienții și selectați **Salvare**.
   Alegeți un atribut din rezultatul inferenței cu valori similare coloanei ID client a entității client. Dacă nu aveți o astfel de coloană în setul de date, alegeți un atribut care identifică în mod unic rândul.

## <a name="run-a-workflow"></a>Executarea unui flux de lucru

1. Pe pagina **Modele particularizate**, selectați elipsele verticale din coloana **Acțiuni** de lângă un flux de lucru pe care l-ați creat anterior.

1. Selectare rând **Rulare**.

Fluxul dvs. de lucru rulează automat cu fiecare reîmprospătare planificată. Aflați mai multe despre [configurarea reîmprospătărilor planificate](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Ștergeți un flux de lucru

1. Pe pagina **Modele particularizate**, selectați elipsele verticale din coloana **Acțiuni** de lângă un flux de lucru pe care l-ați creat anterior.

1. Selectați **Ștergere** și confirmați ștergerea.

Fluxul de lucru va fi șters. [Entitatea](entities.md) care a fost creată atunci când ați creat fluxul de lucru persistă și poate fi vizualizată din pagina **Entități**.

## <a name="results"></a>Rezultate

Rezultatele dintr-un flux de lucru sunt stocate în entitatea configurată în timpul fazei Parametru de ieșire model. Puteți accesa aceste date din [pagina entităților](entities.md) sau cu [Acces API](apis.md).

### <a name="api-access"></a>Acces API

Pentru interogarea specifică OData pentru a obține date de la o entitate model personalizată, utilizați următorul format:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Înlocuiți `<your instance id>` cu ID-ul mediului dvs. Customer Insights, pe care îl găsiți în bara de adrese a browserului dvs. când accesați Customer Insights.

1. Înlocuiți `<custom model output entity>` cu numele entității pe care l-ați furnizat în timpul pasului Model Output Parameters din configurația modelului personalizat.

1. Înlocuiți `<guid value>` cu codul de client al clientului pentru care doriți să accesați înregistrarea. De obicei, puteți găsi acest ID pe [pagina profilurilor clienților](customer-profiles.md) în câmpul CustomerID.

## <a name="frequently-asked-questions"></a>Întrebări frecvente

- De ce nu-mi pot vedea conducta la configurarea unui flux de lucru model personalizat?    
  Această problemă este cauzată frecvent de o problemă de configurare în canal. Asigurați-vă că [parametrul de intrare este configurat](azure-machine-learning-experiments.md#dataset-configuration) și [date de ieșire și parametri de cale](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) sunt, de asemenea, configurate.

- Ce înseamnă eroarea „Nu s-a putut salva fluxul de lucru al informațiilor”?    
  Utilizatorii văd de obicei acest mesaj de eroare dacă nu au privilegii proprietar sau administrator de acces utilizator în spațiul de lucru. Utilizatorul are nevoie de un nivel mai înalt de permisiuni pentru a permite Customer Insights să proceseze fluxul de lucru ca un serviciu, mai degrabă decât să utilizeze acreditările utilizatorului pentru rulările ulterioare ale fluxului de lucru.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
