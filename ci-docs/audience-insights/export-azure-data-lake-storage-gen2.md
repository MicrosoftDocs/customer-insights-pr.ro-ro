---
title: Exportați datele Customer Insights către Azure Data Lake Storage Gen2
description: Aflați cum să configurați conexiunea la Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 934c396559d4c4be8e640917d2265805753eb62d
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605918"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Exportați lista de segmente și alte date în Azure Data Lake Storage Gen2 (versiune preliminară)

Stocați datele Customer Insights într-un cont Azure Data Lake Storage Gen2 sau le utilizați pentru a transfera datele la alte aplicații.

## <a name="known-limitations"></a>Limitări cunoscute

1. Pentru Azure Data Lake Storage Gen2 puteți alege între [Performanță standard și nivel de performanță Premium](/azure/storage/blobs/create-data-lake-storage-account) când creați un cont de stocare pentru depozitul dvs. de date. Dacă alegeți nivelul de performanță Premium, selectați bloburi bloc premium ca tip de cont. 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Configurați conexiunea la Azure Data Lake Storage Gen2 


1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Azure Data Lake Gen 2** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți **Nume de cont**, **Cheia contului**, și **Recipient** pentru Azure Data Lake Storage Gen2 dvs.
    - Pentru a afla cum să creați un cont de stocare cu care să utilizați Azure Data Lake Storage Gen2, consultați [Creați un cont de stocare](/azure/storage/blobs/create-data-lake-storage-account). 
    - Pentru a afla mai multe despre numele contului de stocare Azure Data Lake Gen2 și cheia de cont, consultați [Gestionați setările contului de stocare în portalul Azure](/azure/storage/common/storage-account-manage).

1. Selectați **Salvare** pentru a finaliza conexiunea. 

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea **Azure Data Lake**. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

1. Selectați caseta de lângă fiecare dintre entitățile pe care doriți să le exportați la această destinație.

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 

Datele exportate sunt stocate în recipientul de stocare Azure Data Lake Gen 2 pe care l-ați configurat. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
