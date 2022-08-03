---
title: Exportați segmente către Adobe Experience Platform (previzualizare)
description: Aflați cum să utilizați segmentele Customer Insights în Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195305"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Exportați segmente către Adobe Experience Platform (previzualizare)

Exportați segmente care vizează public relevante către Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama de proces a pașilor descriși în acest articol.":::

## <a name="prerequisites"></a>Cerințe preliminare

- Un Adobe Experience Platform licență.
- Un Adobe Licență standard pentru campanie.
- Un [Cont Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) nume și cheie de cont. Pentru a găsi numele și cheia, consultați [Gestionați setările contului de stocare în portalul Azure](/azure/storage/common/storage-account-manage).
- Un [Container Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Prezentare generală campanie

Pentru a înțelege mai bine cum puteți utiliza segmente din Customer Insights în Adobe Experience Platform, să ne uităm la un exemplu de campanie fictiv.

Să presupunem că compania dvs. oferă clienților dvs. din Statele Unite un serviciu lunar, bazat pe abonament. Doriți să identificați clienții ale căror abonamente trebuie reînnoite în următoarele opt zile, dar nu și-au reînnoit abonamentul. Pentru a păstra acești clienți, doriți să le trimiteți o ofertă promoțională prin e-mail, folosind Adobe Experience Platform.

În acest exemplu, dorim să derulăm o dată campania de e-mail promoțională. Acest articol nu acoperă cazul de utilizare al desfășurării campaniei de mai multe ori.

## <a name="identify-your-target-audience"></a>Identificați-vă publicul țintă

În scenariul nostru, presupunem că adresele de e-mail ale clienților sunt disponibile în Customer Insights și preferințele lor promoționale au fost analizate pentru a identifica membrii segmentului.

The [segment pe care l-ați definit în Customer Insights](segments.md) se numește **ChurnProneCustomers** și intenționați să trimiteți acestor clienți promoția prin e-mail.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captură de ecran a paginii segmente cu segmentul ChurnProneCustomers creat.":::

E-mailul de ofertă pe care doriți să îl trimiteți va conține prenume, nume de familie, și data de încheiere a abonamentului clientului. Acesta informează clienții despre reducerea pe care o vor primi dacă își reînnoiesc abonamentul înainte de a se încheia.

## <a name="export-your-target-audience"></a>Expportați-vă publicul țintă

Vom configura exportul din Customer Insights într-un cont Azure Blob Storage.

### <a name="set-up-connection-to-azure-blob-storage"></a>Configurați conexiunea la Azure Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Azure Blob Storage**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți **Nume de cont**, **Cheia de cont** și **Recipient** pentru contul dvs. de Stocare de bloburi în care doriți să exportați segmentul.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captură de ecran a configurării contului de stocare. ":::

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Salvare** pentru a finaliza conexiunea.

### <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Stocare bloburi Azure. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. Alegeți segmentul pe care doriți să îl exportați. În acest exemplu, este **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captură de ecran a interfeței de selectare a segmentului cu segmentul ChurnProneCustomers selectat.":::

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Asigurați-vă că numărul de înregistrări din segmentul exportat se încadrează în limita permisă a licenței dvs. Adobe Campaign Standard.

Datele exportate sunt stocate în containerul Azure Blob Storage pe care l-ați configurat. Următoarele căi de foldere sunt create automat în containerul dvs.:

- Pentru entitățile sursă și entitățile generate de sistem:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- *model.json* pentru entitățile exportate se află la nivelul *%ExportDestinationName%*.

  Exemplu: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definiți Experience Data Mode (XDM) în Adobe Experience Platform

Înainte ca datele exportate din Customer Insights să poată fi utilizate în Adobe Experience Platform, definiți schema Experience Data Model și [configurați datele pentru Profilul clientului în timp real](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Învățați [ce este XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) și înțelegeți [elementele de bază ale compoziției schemei](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importul datelor în Adobe Experience Platform

Importați datele de audiență pregătite din Customer Insights în Adobe Experience Platform.

1. [Creați o conexiune la sursă Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Configurați un flux de date](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pentru o conexiune în lot de stocare în cloud pentru a importa ieșirea segmentului din Customer Insights în Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Creați un public în Adobe Campaign Standard

Pentru a trimite e-mailul pentru această campanie, vom utiliza Adobe Campaign Standard.

1. [Creați un public](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) în Adobe Standard de campanie folosind datele din Adobe Experience Platform.

1. [Utilizați generatorul de segmente](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) în Adobe Standard de campanie pentru a defini un public pe baza datelor din Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Creați și trimiteți e-mailul utilizând Adobe Campaign Standard

Creați conținutul e-mailului și apoi [testați și trimiteți](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email-ul dvs.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exemplu de e-mail cu ofertă de reînnoire de la Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
