---
title: Experimente Machine Learning Studio (clasic)
description: Utilizați modele Machine Learning Studio (clasic) în Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2eb44604e72b32292f971754d4f8c4fd1988c697
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555184"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Utilizați modele bazate pe Azure Machine Learning Studio (clasic)

Datele unificate din Dynamics 365 Customer Insights sunt o sursă pentru construirea de modele de învățare programată care pot genera informații suplimentare despre afaceri. Customer Insights se integrează cu Machine Learning Studio (clasic) pentru a utiliza propriile dvs. modele particularizate. Pentru a vedea cum sunt integrate modelele dezvoltate în Azure Machine Learning cu Customer Insights, consultați [Experimente Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Cerințe preliminare

- Accesați la Customer Insights
- Abonament activ Azure Enterprise
- [Profiluri de client unificate](data-unification.md)
- Configurați [Export de entitate în stocarea Azure Blob](export-azure-blob-storage.md)

## <a name="set-up-machine-learning-studio-classic"></a>Configurați Machine Learning Studio Clasic

Într-un prim pas, trebuie să creăm un spațiu de lucru pentru și să deschidem Machine Learning Studio (clasic).

1. Accesați[https://www.portal.azure.com](https://www.portal.azure.com/) și conectați-vă.

1. Selectați **Creare resursă**.

1. Căutați **Spațiu de lucru Studio pentru Învățare programată Azure** și selectați **Creați**.

1. Introduceți detaliile necesare la [creați spațiul de lucru](/azure/machine-learning/studio/create-workspace). Alegeți **Nivelul de preț al planului de servicii web** pe baza cantității de date pe care intenționați să le importați. Pentru cele mai bune performanțe, selectați **Locația** cea mai apropiată geografic de dvs.

1. După crearea resursei, va apărea tabloul de bord al spațiului de lucru Machine Learning Studio. Selectați **Lansați Machine Learning Studio**.

   ![Interfața de utilizator a Studio pentru Învățare programată Azure.](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Lucrul cu Studio pentru Învățare programată Azure

Acum puteți crea un experiment nou sau puteți importa un model de experiment existent din galeria de eșantioane. Există exemple de experimente pentru trei scenarii standard:

- [Predicția scăderii](#churn-analysis)

- [Valoarea pe viață a clientului](#customer-lifetime-value-prediction)

- [Recomandare produs sau următoarea cea mai bună acțiune](#productrecommendation-or-next-best-action)

1. Dacă creați un nou experiment sau utilizați un șablon de experiment din galerie, trebuie să configurați proprietatea **Importați date**. Utilizați experiența ghidată sau furnizați direct detalii pentru a accesa stocarea Azure Blob care conține datele dvs.  

   ![Experiment cu Studio pentru Învățare programată Azure.](media/azure-machine-learning-studio-experiment.png)

1. Acum puteți construi un canal de procesare personalizată pentru curățarea și preprocesarea datelor, extragerea funcțiilor și instruirea unui model adecvat.

1. Testați și optimizați performanța modelului.

1. Când sunteți mulțumit de calitatea unui model, selectați **Configurați serviciul web** > **Serviciul web predictiv**. Această opțiune importă modelul instruit și canalul featurizării din experimentul de instruire într-un serviciu predictiv. Serviciul predictiv poate lua un alt set de date de intrare cu schema folosită în experimentul de instruire pentru a face predicții.

   ![Configurați un serviciu web predictiv.](media/predictive-webservice-control.png)

1. După ce experimentul de servicii web predictiv are succes, îl puteți implementa pentru planificarea automată. Pentru ca serviciul web să funcționeze cu Customer Insights, selectați **Implementați serviciul Web** > **Previzualizare Implementați serviciul web [Nou]**. [Aflați mai multe despre implementarea de servicii web](/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![Implementați un serviciu web predictiv.](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Modele de exemple din galerie

Vom folosi un scenariu fictiv de Contoso Hotel pentru modelele din acest articol. Hotelul Contoso adună următoarele date:

- Date CRM constând în activitatea de ședere la hotel. Setul de date include informații despre datele de ședere pentru fiecare client înregistrat. De asemenea, conține informații despre rezervare, tipuri de cameră, detalii despre cheltuieli și așa mai departe. Datele se întind pe patru ani, din ianuarie 2014 până în ianuarie 2018.
- Profilele clienților oaspeților hotelului. Aceste profiluri conțin informații despre fiecare client, inclusiv numele, data nașterii, adresa poștală, sexul și numărul de telefon.
- Utilizarea serviciilor oferite de hotel, cum ar fi spa, spălătorie, WiFi sau curier. Aceste informații sunt înregistrate pentru fiecare client înregistrat. De obicei, utilizarea serviciilor este legată de ședere. În unele cazuri, serviciile pot fi utilizate de clienți fără a sta la hotel.

## <a name="churn-analysis"></a>Analiza scăderii

Analiza scăderii se aplică diferitelor domenii de afaceri. În acest exemplu, vom analiza schimbul de servicii, în special în contextul serviciilor hoteliere descrise mai sus. Oferă un exemplu de lucru al unui canal complet, care poate fi folosit ca punct de plecare pentru orice alt tip de model al scăderii.

### <a name="definition-of-churn"></a>Definiția scăderii

Definiția scăderii poate diferi în funcție de scenariu. În acest exemplu, un oaspete care nu a vizitat hotelul în ultimul an ar trebui să fie etichetat ca fiind redus.  

Modelul de experiment poate fi importat din galerie. În primul rând, asigurați-vă că importați datele pentru **Activitate de ședere la hotel**, **Date despre consumator**, și **Date de utilizare a serviciului** din stocarea Azure Blob.

   ![Importați datele pentru modelul de redus.](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Featizarea

Pe baza definiției scăderii, identificăm mai întâi caracteristicile brute care vor influența eticheta. Apoi, procesăm aceste caracteristici brute în caracteristici numerice care pot fi utilizate cu modele de învățare programată. Integrarea datelor are loc în Customer Insights, astfel încât să putem alătura aceste tabele folosind *ID client*.

   ![Alăturați-vă datele importate.](media/join-imported-data.png)

Crearea de caracteristici pentru construirea modelului pentru analiza puterii poate fi un pic dificilă. Datele sunt o funcție de timp, iar noua activitate hotelieră este înregistrată zilnic. În timpul featurizării, dorim să generăm caracteristici statice din datele dinamice. În acest caz, generăm multiple caracteristici din activitatea hotelului cu o fereastră glisantă de un an. De asemenea, extindem caracteristicile în funcție de categorie, cum ar fi tipul camerei sau tipul de rezervare, în funcții separate, utilizând o codare unică.  

Lista finală de caracteristici:

| **Număr**  | **Original_Column**          | **Caracteristici derivate**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Tipul camerei                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Tip de rezervare                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Categoria de călătorie              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Dolari cheltuiți                | TotalDollarSpent                                                                                                                          |
| 5           | Date de Arhivare și Finalizare  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Utilizare serviciu                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Selectare model

Acum trebuie să alegem algoritmul optim pe care să-l utilizăm. În acest caz, majoritatea funcțiilor se bazează pe caracteristici în funcție de categorie. De obicei, modelele bazate pe arbori de decizie funcționează bine. Dacă există doar caracteristici numerice, rețelele neuronale ar putea fi o alegere mai bună. Mașina vectorială de asistență (SVM) este, de asemenea, un candidat bun în astfel de situații; cu toate acestea, are nevoie de un pic de ajustare pentru a extrage cele mai bune performanțe. Noi alegem **Arborele de decizie stimulat de două clase** ca primul model de alegere urmat de **SVM cu două clase** ca al doilea model. Azure Machine Learning Studio vă permite să faceți teste A/B, așa că este benefic să începeți cu două modele și nu cu unul singur.

Următoarea imagine arată canalul de formare și evaluare a modelului de la Studio pentru Învățare programată Azure:

![Modelul de retragere în Studio pentru Învățare programată Azure.](media/azure-machine-learning-model.png)

De asemenea, aplicăm o tehnică numită **Importanța caracteristicilor de permutare**, un aspect important al optimizării modelului. Modelele încorporate au prea puțin detaliu sau nu au deloc asupra impactului vreunei funcții specifice pe predicția finală. Calculatorul pentru importanța caracteristicilor folosește un algoritm personalizat pentru a calcula influența caracteristicilor individuale asupra rezultatului unui model specific. Importanța caracteristicii este normalizată între +1 și -1. O influență negativă înseamnă că caracteristica corespunzătoare are o influență contra-intuitivă asupra rezultatului și ar trebui eliminată din model. O influență pozitivă indică faptul că caracteristica contribuie puternic la predicție. Aceste valori nu sunt coeficienți de corelație, deoarece sunt valori diferite. Pentru mai multe informații, consultați [Importanța caracteristicii de permutare](/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Întregul [experiment de scădere este disponibil în Azure AI Gallery](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Predicția valorii pe viață a clientului

Calculul valorii de viață a clientului (CLTV) este una dintre valorile cheie pe care o întreprindere le poate utiliza pentru a-și evalua și segmenta clienții. Pentru afacerile hoteliere, este esențial să cunoaștem clienții. De exemplu, înțelegerea factorilor care formează clienți buni este o informație crucială. Aceasta ajută conducerea hotelului să evalueze care sunt caracteristicile pe care trebuie să se concentreze și să le îmbunătățească pentru a satisface clienții cu plată ridicată. Aceste decizii pot avea un impact direct asupra vânzărilor și câștigurilor.  

### <a name="definition-of-cltv"></a>Definiție a CLTV

Pentru acest exemplu, definim CLTV-ul unui client ca suma totală în dolari pe care clientul trebuie să o cheltuiască în următoarele 365 de zile. Vom folosi datele din ultimii trei ani pentru toți clienții pentru a prezice această valoare.

### <a name="featurization"></a>Featizarea

În acest caz, featizarea va fi asemănătoare scenariului de transformare. Cu toate acestea, etichetele și valorile prezise sunt diferite decât cele definite mai sus.

### <a name="model-selection"></a>Selectare model

Prezicerea CLTV este o problemă de regresie, deoarece valoarea prevăzută este o variabilă continuă evaluată pozitiv. Pe baza proprietăților caracteristicilor, selectăm **Regresia stimulată a arborelui de decizie** ca un algoritm și **Regresia rețelei neuronale** ca un alt algoritm de formare a modelului.

## <a name="product-recommendation-or-next-best-action"></a>Recomandare produs sau următoarea cea mai bună acțiune

Recomandarea produsului într-un scenariu hotelier este interpretată ca recomandând serviciile oferite de către hotel clienților. Obiectivul este de a alege serviciile adecvate pentru clienți, astfel încât utilizarea acestora să fie maximizată. Este similar cu recomandările filmelor pentru utilizatorii serviciilor de streaming video.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Recomandarea definiției de produs sau următoarea cea mai bună acțiune

Definim obiectivul ca maximizarea sumei în dolari a utilizării serviciilor oferind cele mai bune servicii potrivind clienții hotelului în funcție de interesul lor.

### <a name="featurization"></a>Featurizarea

La fel ca modelul de scădere, ne alăturăm serviciului hotelier ServiceCustomerID cu CustomerID pentru a crea recomandări în mod constant per CustomerID.

![Caracterizarea modelului de recomandare.](media/azure-machine-learning-model-featurization.png)

Datele sunt furnizate de la trei entități diferite și funcțiile sunt derivate din ele. Featurizarea problemei de recomandare este diferită în comparație cu scenariile de declin sau CLTV. Modelul de recomandare are nevoie de date de intrare sub forma a trei seturi de caracteristici.

### <a name="model-selection"></a>Selectare model

Prezicem produse sau servicii folosind algoritmul numit **Recomandare pentru potrivirea de instruiri** pentru a instrui modelul de recomandare.

![Algoritm Recomandări produs.](media/azure-machine-learning-model-recommendation-algorithm.png)

Cele trei porturi de intrare pentru modelul **Recomandare pentru potrivirea de instruiri** preiau datele de utilizare a serviciului de instruire, descrierea clientului (opțional) și descrierea serviciului. Există trei moduri diferite de notare a modelului. Unul este pentru evaluarea modelului în care se calculează un scor normalizat cu câștiguri cumulative cu reducere (NDCG) pentru a obține punctele clasificate. În acest experiment, scorul NDCG este 0,97. Celelalte două opțiuni sunt notarea modelului pe întregul catalog de servicii recomandabil sau punctarea numai pe elementele pe care utilizatorii nu le-au folosit până acum.

Privind mai departe distribuțiile recomandărilor pe întregul catalogul de servicii, observăm că telefonul, WiFi-ul și curierul sunt serviciile de top care trebuie recomandate. Acest lucru este în concordanță cu ceea ce am găsit din distribuțiile datelor privind consumul de servicii:

![Model de recomandare de ieșire.](media/azure-machine-learning-model-output.png)

Întregul [experiment de recomandare a produsului poate fi accesat în Azure AI Gallery.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Integrați modele particularizate

Pentru a utiliza aceste predicții în Customer Insights, trebuie să **exportați** previziunile împreună cu ID-urile clientului. [Exportați-le în aceeași locație de stocare Azure Blob](/azure/storage/common/storage-import-export-data-from-blobs) către care exportați datele sursă. Serviciul web predictiv poate fi programat să ruleze în mod regulat și să actualizeze scorurile.

Datele generate de modelul personalizat pot fi utilizate pentru a vă îmbogăți și mai mult datele despre clienți. Pentru mai multe informații, consultați [Modelele de învățare programată particularizate](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]