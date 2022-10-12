---
title: Modele învățare programată particularizate | Documente Microsoft
description: Lucrați cu modele particularizate de la Învățare programată Azure în Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609761"
---
# <a name="custom-machine-learning-models"></a>Modele învățare programată particularizate

> [!NOTE]
> Asistența pentru învățare programată Studio (clasic) se va încheia pe 31 august 2024. Vă recomandăm să treceți la [Azure învățare programată](/azure/machine-learning/overview-what-is-azure-machine-learning) până la acea dată.
>
> Începând cu 1 decembrie 2021, nu veți putea crea resurse noi învățare programată Studio (clasic). Până la 31 august 2024, puteți continua să utilizați resursele existente învățare programată Studio (clasic). Pentru mai multe informații, vezi [Migrați la Azure învățare programată](/azure/machine-learning/migrate-overview).

Modelele personalizate vă permit să gestionați fluxurile de lucru pe baza modelelor Azure învățare programată. Fluxurile de lucru vă ajută să alegeți datele din care doriți să generați detalii și să mapați rezultatele la datele unificate ale clienților. Pentru mai multe informații despre construirea de modele ML particularizate, consultați [Utilizare modele bazate pe Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Cerințe preliminare

- Servicii web publicate prin [Conducte batch învățare programată Azure](/azure/machine-learning/concept-ml-pipelines).
- Conducta trebuie publicată sub a [punctul final al conductei](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- Un [Cont de stocare Azure Data Lake Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account) asociat cu instanța dvs. Azure Studio.
- Pentru spațiile de lucru Azure învățare programată cu conducte, permisiuni de administrator sau acces proprietar la spațiul de lucru Azure învățare programată.

  > [!NOTE]
  > Datele sunt transferate între instanțele dvs. Customer Insights și serviciile web sau canalele Azure selectate din fluxul de lucru. Când transferați date către un serviciu Azure, asigurați-vă că serviciul este configurat să proceseze date în modul și locația necesare pentru a se conforma oricărei cerințe legale sau de reglementare pentru respectivele date din organizația dvs.

## <a name="add-a-new-workflow"></a>Adăugați un nou flux de lucru

1. Accesați **Informații** > **Modele particularizate** și selectați **Flux de lucru nou**.

1. Oferiți o recunoaștere **Nume**.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Captură de ecran a panoului noului flux de lucru.":::

1. Selectați organizația care conține serviciul web din **Entitate găzduită care conține serviciul dvs. web**.

1. Dacă abonamentul dvs. Azure Machine Learning se află într-o entitate găzduită diferită de Customer Insights, selectați **Autentificare** cu datele dvs. de acreditare pentru organizația selectată.

1. Selectați **Spații de lucru** asociate cu serviciul dvs. web.

1. Alegeți conducta Azure învățare programată în **Serviciu web care conține modelul dvs** scapă jos. Apoi, selectați **Următorul**.
   Aflați mai multe despre [publicarea unui canal în Azure Machine Learning folosind designerul](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) sau [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. Pentru fiecare **Intrare serviciu web**, selectați potrivirea **Entitate** din Customer Insights. Apoi, selectați **Următorul**.
   > [!NOTE]
   > Fluxul de lucru al modelului personalizat va aplica euristică pentru a mapa câmpurile de intrare ale serviciului web la atributele entității pe baza numelui și tipului de date al câmpului. Veți vedea o eroare dacă un câmp de servicii web nu poate fi mapat la o entitate.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Configurați un flux de lucru.":::

1. Pentru **Parametrii de ieșire a modelului**, setați următoarele proprietăți:
   - **Numele entitatii** pentru rezultatele ieșirii conductei
   - **Ieșire depozit de date numele parametrului** a conductei dvs. de lot
   - **Numele parametrului Calea de ieșire** a conductei dvs. de lot

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Panou parametru de ieșire model.":::

1. Selectați atributul potrivit din **ID client în rezultate** care identifică clienții și selectează **Salvați**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Corelare rezultate cu panoul datele clienților.":::

   The **Flux de lucru salvat** ecranul afișează detalii despre fluxul de lucru. Dacă ați configurat un flux de lucru pentru o conductă Azure învățare programată, Customer Insights se atașează la spațiul de lucru care conține conducta. Customer Insights va primi a **Colaborator** rol în spațiul de lucru Azure.

1. Selectați **Terminat**. The **Modele personalizate** afișează pagina.

1. Selectați elipsa verticală (&vellip;) pentru fluxul de lucru și selectați **Alerga**. Fluxul de lucru rulează automat cu fiecare [reîmprospătare programată](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Gestionați un flux de lucru existent

Mergi la **Inteligența** > **Modele personalizate** pentru a vizualiza fluxurile de lucru pe care le-ați creat.

Selectați un flux de lucru pentru a vedea acțiunile disponibile.

- **Editați | ×** un flux de lucru
- **Alerga** un flux de lucru
- [**Șterge**](#delete-a-workflow) un flux de lucru

### <a name="edit-a-workflow"></a>Editați un flux de lucru

1. Mergi la **Inteligența** > **Modele personalizate**.

1. Lângă fluxul de lucru pe care doriți să îl actualizați, selectați punctele de suspensie verticale (&vellip;) și selectați **Editați | ×**.

1. Schimbare **Numele de afișare** dacă este necesar și selectați **Următorul**.

1. Pentru fiecare **Intrare serviciu web**, actualizați potrivirea **Entitate** din Customer Insights, dacă este necesar. Apoi, selectați **Următorul**.

1. Pentru **Parametrii de ieșire a modelului**, modificați oricare dintre următoarele:
   - **Numele entitatii** pentru rezultatele ieșirii conductei
   - **Ieșire depozit de date numele parametrului** a conductei dvs. de lot
   - **Numele parametrului Calea de ieșire** a conductei dvs. de lot

1. Schimbați atributul de potrivire din **ID client în rezultate** pentru a identifica clienții. Alegeți un atribut din rezultatul inferenței cu valori similare coloanei ID client a entității client. Dacă nu aveți o astfel de coloană în setul dvs. de date, alegeți un atribut care identifică în mod unic rândul.

1. Selectați **Salvare**

### <a name="delete-a-workflow"></a>Ștergeți un flux de lucru

1. Mergi la **Inteligența** > **Modele personalizate**.

1. Lângă fluxul de lucru pe care doriți să-l ștergeți, selectați punctele de suspensie verticale (&vellip;) și selectați **Șterge**.

1. Confirmați ștergerea.

Fluxul de lucru va fi șters. The [entitate](entities.md) care a fost creat când ați creat fluxul de lucru persistă și poate fi vizualizat din **Date** > **Entități** pagină.

## <a name="view-the-results"></a>Vedeți rezultatele

Rezultatele unui flux de lucru sunt stocate în numele entității definit pentru **Parametrii de ieșire a modelului**. Accesați aceste date din [**Date** > **Entități** pagină](entities.md) sau cu [Acces API](apis.md).

### <a name="api-access"></a>Acces API

Pentru interogarea specifică OData pentru a obține date de la o entitate model personalizată, utilizați următorul format:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. A inlocui`<your instance id>` cu ID-ul mediului dvs. Customer Insights, care se afișează în bara de adrese a browserului dvs. atunci când accesați Customer Insights.

1. A inlocui`<custom model output entity>` cu numele entității pe care l-ați furnizat pentru **Parametrii de ieșire a modelului**.

1. A inlocui`<guid value>` cu ID-ul de client al clientului pe care doriți să-l accesați. Acest ID se afișează pe [pagina de profiluri ale clienților](customer-profiles.md) în câmpul CustomerID.

## <a name="frequently-asked-questions"></a>Întrebări frecvente

- De ce nu-mi pot vedea conducta la configurarea unui flux de lucru model personalizat?
  Această problemă este cauzată frecvent de o problemă de configurare în canal. Asigurați-vă că [parametrul de intrare este configurat](azure-machine-learning-experiments.md#dataset-configuration) și [date de ieșire și parametri de cale](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) sunt, de asemenea, configurate.

- Ce înseamnă eroarea „Nu s-a putut salva fluxul de lucru al informațiilor”? 
  Utilizatorii văd de obicei acest mesaj de eroare dacă nu au privilegii proprietar sau administrator de acces utilizator în spațiul de lucru. Utilizatorul are nevoie de un nivel mai înalt de permisiuni pentru a permite Customer Insights să proceseze fluxul de lucru ca un serviciu, mai degrabă decât să utilizeze acreditările utilizatorului pentru rulările ulterioare ale fluxului de lucru.

- Este acceptat un punct final privat/un link privat pentru fluxul de lucru al modelului meu personalizat?
  Customer Insights nu acceptă în prezent un punct final privat pentru modele personalizate, dar este disponibilă o soluție manuală. Vă rugăm să contactați asistența pentru detalii.

## <a name="responsible-ai"></a>AI responsabil

Predicțiile oferă capacități pentru crearea de experiențe client mai bune, îmbunătățirea capacităților de afaceri și fluxurilor de venituri. Vă recomandăm cu tărie să compensați valoarea predicției dvs. cu impactul pe care îl are și cu interferențele care pot fi introduse într-o manieră etică. Aflați mai multe despre cum Microsoft [tratează AI responsabil](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Puteți afla și despre [tehnici și procese pentru învățare programată responsabilă](/azure/machine-learning/concept-responsible-ml) specifice Azure Machine Learning.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
