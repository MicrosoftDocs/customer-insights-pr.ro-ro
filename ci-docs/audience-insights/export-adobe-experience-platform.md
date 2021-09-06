---
title: Exportați datele Customer Insights către Adobe Experience Platform
description: Aflați cum utilizați segmentele de detalii privind publicul în Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fac976a49b1b5c5485b75e1262135738c913bd2230be7df8aa0ec12c59734053
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032132"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Utilizați segmentele Customer Insights în Adobe Experience Platform (previzualizare)

În calitate de utilizator al statisticilor publicului în Dynamics 365 Customer Insights, este posibil să fi creat segmente pentru a vă face campaniile de marketing mai eficiente, vizând segmente de public relevante. Pentru a utiliza un segment din statistici despre public în Adobe Experience Platform și aplicații precum Adobe Campaign Standard, trebuie să urmați câțiva pași descriși în acest articol.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama de proces a pașilor descriși în acest articol.":::

## <a name="prerequisites"></a>Cerințe preliminare

-   Licență Dynamics 365 Customer Insights
-   Licență Adobe Experience Platform
-   Licență Adobe Campaign Standard
-   Cont Azure Blob Storage

## <a name="campaign-overview"></a>Prezentare generală campanie

Pentru a înțelege mai bine modul în care puteți utiliza segmente din detaliile publicului Adobe Experience Platform, să ne uităm la un eșantion de campanie fictivă.

Să presupunem că compania dvs. oferă clienților dvs. din Statele Unite un serviciu lunar, bazat pe abonament. Doriți să identificați clienții ale căror abonamente trebuie reînnoite în următoarele opt zile, dar nu și-au reînnoit abonamentul. Pentru a păstra acești clienți, doriți să le trimiteți o ofertă promoțională prin e-mail, folosind Adobe Experience Platform.

În acest exemplu, dorim să derulăm o dată campania de e-mail promoțională. Acest articol nu acoperă cazul de utilizare al desfășurării campaniei de mai multe ori.

## <a name="identify-your-target-audience"></a>Identificați-vă publicul țintă

În scenariul nostru, presupunem că adresele de e-mail ale clienților sunt disponibile în statisticile publicului, iar preferințele lor promoționale au fost analizate pentru a identifica membrii segmentului.

[Segmentul pe care l-ați definit în statistici privind publicul](segments.md) se numește **ChurnProneCustomers** și intenționați să trimiteți acestor clienți promoția prin e-mail.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captură de ecran a paginii segmente cu segmentul ChurnProneCustomers creat.":::

E-mailul de ofertă pe care doriți să îl trimiteți va conține prenume, nume de familie, și data de încheiere a abonamentului clientului. Acesta informează clienții despre reducerea pe care o vor primi dacă își reînnoiesc abonamentul înainte de a se încheia.

## <a name="export-your-target-audience"></a>Expportați-vă publicul țintă

Odată cu publicul țintă identificat, putem configura exportul din statistici privind publicul către un cont de stocare Blob Azure.

### <a name="configure-a-connection"></a>Configurați o conexiune

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Stocare Blob Azure** sau selectați **Configurat** în dala **Stocare Blob Azure** pentru a configura conexiunea.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Dală de configurare pentru stocare Blob Azure."::: 

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți **Nume de cont**, **Cheia de cont** și **Recipient** pentru contul dvs. de Stocare de bloburi în care doriți să exportați segmentul.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captură de ecran a configurării contului de stocare. "::: 
   
    - Pentru a afla mai multe despre cum să aflați numele contului de Stocare de bloburi și cheia de cont, consultați [Gestionați setările contului de stocare în portalul Azure](/azure/storage/common/storage-account-manage).
    - Pentru a afla cum să creați un container, consultați [Creați un container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Selectați **Salvare** pentru a finaliza conexiunea. 

### <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Stocare bloburi Azure. Dacă nu vedeți numele acestei secțiuni, atunci nu aveți la dispoziție conexiuni de acest tip.

1. Alegeți segmentul pe care doriți să îl exportați. În acest exemplu, este **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captură de ecran a interfeței de selectare a segmentului cu segmentul ChurnProneCustomers selectat.":::

1. Selectați **Salvare**.

După salvarea destinației de export, o veți găsi pe **Date** > **Exporturi**.

Acum puteți [exporta segmentul la cerere](export-destinations.md#run-exports-on-demand). Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md).

> [!NOTE]
> Asigurați-vă că numărul de înregistrări din segmentul exportat se încadrează în limita permisă a licenței dvs. Adobe Campaign Standard.

Datele exportate sunt stocate în containerul de Stocare bloburi Azure pe care l-ați configurat mai sus. Următoarea cale a folderului este creată automat în container:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*model.json* pentru entitățile exportate se află la nivelul *%ExportDestinationName%*.

Exemplu: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definiți Experience Data Mode (XDM) în Adobe Experience Platform

Înainte de a putea folosi datele exportate din detaliile despre public în cadrul Adobe Experience Platform, trebuie să definim Experience Data Model și [configurați datele pentru Profilul clientului în timp real](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Învățați [ce este XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) și înțelegeți [elementele de bază ale compoziției schemei](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importul datelor în Adobe Experience Platform

Acum, că totul este la locul lor, trebuie să importăm datele pregătite despre public din statistici despre audiență în Adobe Experience Platform.

În primul rând, [creați o conexiune sursă Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

După definirea conexiunii sursă, [configurați un flux de date](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pentru o conexiune lot de stocare în cloud pentru a importa ieșirea segmentului din statisticile publicului în Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Creați un public în Adobe Campaign Standard

Pentru a trimite e-mailul pentru această campanie, vom utiliza Adobe Campaign Standard. După importul datelor în Adobe Experience Platform, avem nevoie să [creăm un public](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) în Adobe Campaign Standard folosind datele din Adobe Experience Platform.


Aflați cum să [utilizați generatorul de segmente](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) în Adobe Campaign Standard pentru a defini un public pe baza datelor din Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Creați și trimiteți e-mailul utilizând Adobe Campaign Standard

Creați conținutul e-mailului și apoi [testați și trimiteți](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email-ul dvs.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exemplu de e-mail cu ofertă de reînnoire de la Adobe Campaign Standard.":::
