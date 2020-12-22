---
title: Exportați datele Customer Insights într-un spațiu de stocare Azure Blob
description: Aflați cum puteți configura conexiunea la stocarea Azure Blob.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 925b53260e7c633e17d7f172d2dd2d581e982e10
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667154"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Conector pentru stocarea Azure Blob (previzualizare)

Stocați datele Customer Insights într-un blob Azure sau folosiți pentru transferul datelor dvs. către alte aplicații.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Configurați conectorul pentru stocarea Azure Blob

1. În Detalii despre audiență, accesați **Administrator** > **Destinații export**.

1. Sub **Depozitarea Azure Blob**, selectați **Configurare**.

1. Introduceți **Nume de cont**, **Cheia contului** și **Recipient** pentru contul dvs. de stocare Azure Blob.
    - Pentru a afla mai multe despre cum puteți găsi numele contului Stocarea de bloburi Azure și cheia contului, consultați [Gestionați setările contului de stocare în portalul Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Pentru a afla cum să creați un container, consultați [Creați un container](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Dați destinației dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.

1. Selectați **Următorul**.

1. Selectați caseta de lângă fiecare dintre entitățile pe care doriți să le exportați la această destinație.

1. Selectați **Salvare**.

Datele exportate sunt stocate în containerul de stocare Azure Blob pe care l-ați configurat. Următoarele căi de foldere sunt create automat în containerul dvs.:

- Pentru entitățile sursă și entitățile generate de sistem: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Exemplu: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- model.json pentru entitățile exportate va fi disponibil la nivelul %ExportDestinationName%
  - Exemplu: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Exportați datele

Puteți [exporta date la cerere](/export-destinations.md#export-data-on-demand). Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).
