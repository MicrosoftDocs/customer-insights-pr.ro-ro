---
title: Exportați datele Customer Insights către Azure Data Lake Storage Gen2
description: Aflați cum să configurați conexiunea la Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760066"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a>Configurați conexiunea la Azure Data Lake Storage Gen2 (previzualizare)

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
