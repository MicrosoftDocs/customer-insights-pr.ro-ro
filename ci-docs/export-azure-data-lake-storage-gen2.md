---
title: Exportați datele în Azure Data Lake Storage Gen2 (previzualizare)
description: Aflați cum să configurați conexiunea la Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196455"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Exportați datele în Azure Data Lake Storage Gen2 (previzualizare)

Stocați datele Customer Insights într-un cont Azure Data Lake Storage Gen2 sau le utilizați pentru a transfera datele la alte aplicații.

## <a name="prerequisites"></a>Cerințe preliminare

- A [cont de stocare de utilizat cu Azure Data Lake Gen2](/azure/storage/blobs/create-data-lake-storage-account). Pentru a găsi numele și cheia contului de stocare, consultați [Gestionați setările contului de stocare în portalul Azure](/azure/storage/common/storage-account-manage).
- Un [Container Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Limitări cunoscute

- Pentru Azure Data Lake Storage Gen2, alege între [Performanță standard și nivel de performanță Premium](/azure/storage/blobs/create-data-lake-storage-account). Dacă alegeți nivelul de performanță Premium, selectați [bloburi bloc premium ca tip de cont](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Configurați conexiunea la Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Azure Data Lake Gen 2**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți **Nume de cont**, **Cheia contului**, și **Recipient** pentru Azure Data Lake Storage Gen2 dvs.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În **Conexiune pentru export** câmp, alegeți o conexiune din secțiunea Azure Data Lake. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. Introduceți numele folderului pentru Azure Data Lake Storage Stocare Gen2.

1. Selectați caseta de lângă fiecare dintre entitățile pe care doriți să le exportați la această destinație.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Datele exportate sunt stocate în recipientul de stocare Azure Data Lake Gen 2 pe care l-ați configurat.

> [!TIP]
> Exportul de entități care conțin o cantitate mare de date poate duce la mai multe fișiere CSV în același folder pentru fiecare export. Împărțirea exporturilor are loc din motive de performanță, pentru a minimiza timpul necesar pentru finalizarea unui export.

[!INCLUDE [footer-include](includes/footer-banner.md)]
