---
title: Exportați date într-un Azure Blob Storage (previzualizare)
description: Aflați cum să configurați conexiunea și să exportați într-un spațiu de stocare de bloburi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195719"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Exportați date într-un Azure Blob Storage (previzualizare)

Stocați datele Customer Insights într-o stocare de bloburi sau utilizați-le pentru a transfera datele către alte aplicații.

## <a name="prerequisites"></a>Cerințe preliminare

- Un [Cont Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) nume și cheie de cont. Pentru a găsi numele și cheia, consultați [Gestionați setările contului de stocare în portalul Azure](/azure/storage/common/storage-account-manage).
- Un [Container Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Limitări cunoscute

- Pentru Azure Blob Storage, alegeți între [Performanță standard și nivel de performanță Premium](/azure/storage/blobs/storage-blob-performance-tiers). Dacă alegeți nivelul de performanță Premium, selectați [bloburi bloc premium ca tip de cont](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Configurați conexiunea la Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Azure Blob Storage**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți **Nume de cont**, **Cheie de cont** și **Recipient** pentru contul dvs. de stocare bloburi.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

Pentru a configura acest export, trebuie să aveți [permisiune](export-destinations.md#set-up-a-new-export) pentru acest tip de conexiune.

> [!IMPORTANT]
> Dacă ai pornit [setare de ștergere soft](/azure/storage/blobs/soft-delete-blob-enable) pentru contul Azure Blob Storage, exporturile vor eșua. Dezactivați ștergerea soft pentru a exporta date în bloburi.

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Stocare bloburi Azure. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. Introduceți numele folderului pentru stocarea blob.

1. Selectați caseta de lângă fiecare dintre entitățile pe care doriți să le exportați la această destinație.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Datele exportate sunt stocate în recipientul de stocare bloburi pe care l-ați configurat. Următoarele căi de foldere sunt create automat în containerul dvs.:

- Pentru entitățile sursă și entitățile generate de sistem:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Exemplu: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5 /BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Exportul de entități care conțin o cantitate mare de date poate duce la mai multe fișiere CSV în același folder pentru fiecare export. Împărțirea exporturilor are loc din motive de performanță, pentru a minimiza timpul necesar pentru finalizarea unui export.

- Model.json pentru entitățile exportate se află la *%ExportDestinationName%* nivel.  
  
  Exemplu: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5 /BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
