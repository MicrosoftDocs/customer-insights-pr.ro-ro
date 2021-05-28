---
title: Exportați datele Customer Insights într-un spațiu de stocare de bloburi Azure
description: Aflați cum să configurați conexiunea și să exportați într-un spațiu de stocare de bloburi.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976196"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Exportați lista segmentelor și alte date către Stocare de bloburi Azure (previzualizare)

Stocați datele Customer Insights într-o stocare de bloburi sau utilizați-le pentru a transfera datele către alte aplicații.

## <a name="set-up-the-connection-to-blob-storage"></a>Configurați conexiunea la spațiul de stocare de bloburi

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Stocare bloburi Azure** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți **Nume de cont**, **Cheie de cont** și **Recipient** pentru contul dvs. de stocare de bloburi.
    - Pentru a afla mai multe despre cum să aflați numele contului de stocare de bloburi și cheia de cont, consultați [Gestionați setările contului de stocare în portalul Azure](/azure/storage/common/storage-account-manage).
    - Pentru a afla cum să creați un container, consultați [Creați un container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Selectați **Salvare** pentru a finaliza conexiunea. 

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Stocare bloburi Azure. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

1. Selectați caseta de lângă fiecare dintre entitățile pe care doriți să le exportați la această destinație.

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).     
Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 

Datele exportate sunt stocate în recipientul de stocare de bloburi pe care l-ați configurat. Următoarele căi de foldere sunt create automat în containerul dvs.:

- Pentru entitățile sursă și entitățile generate de sistem: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Exemplu: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Model.json pentru entitățile exportate va fi la nivel %ExportDestinationName%
  - Exemplu: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
