---
title: Exportați datele Customer Insights către Azure Data Lake Storage Gen2
description: Aflați cum să configurați conexiunea la Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477194"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Conector pentru Azure Data Lake Storage Gen2 (previzualizare)

Stocați datele Customer Insights în Azure Data Lake Storage Gen2 sau utilizați-le pentru a transfera datele către alte aplicații.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Configurați conectorul pentru Azure Data Lake Storage Gen2

1. În Detalii despre audiență, accesați **Administrator** > **Destinații export**.

1. Sub **Azure Data Lake Storage Gen2**, selectați **Configurare**.

1. Dați destinației dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.

1. Introduceți **Nume de cont**, **Cheia contului**, și **Recipient** pentru Azure Data Lake Storage Gen2 dvs.
    - Pentru a afla cum să creați un cont de stocare cu care să utilizați Azure Data Lake Storage Gen2, consultați [Creați un cont de stocare](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account). 
    - Pentru a afla mai multe despre cum să găsiți numele contului și cheia de cont de stocare Azure Data Lake Gen2, consultați [Gestionați setările contului de stocare în portalul Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. Selectați **Următorul**.

1. Selectați caseta de lângă fiecare dintre entitățile pe care doriți să le exportați la această destinație.

1. Selectați **Salvare**.

## <a name="export-the-data"></a>Exportați datele

Puteți [exporta date la cerere](export-destinations.md#export-data-on-demand). Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).
