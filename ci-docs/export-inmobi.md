---
title: Exportați datele despre Customer Insights în InMobi
description: Aflați cum să configurați conexiunea și să exportați în InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195903"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Exportați datele despre Customer Insights în InMobi (previzualizare)

Exportați liste de segmente sau alte date din instanța dvs. Customer Insights către [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Cerințe preliminare

- Un [cont InMobi](https://www.inmobi.com/) și acreditările de administrator.
- Un [Cont Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) nume și cheie de cont. Pentru a găsi numele și cheia, consultați [Gestionați setările contului de stocare în portalul Azure](/azure/storage/common/storage-account-manage).
- Un [Container Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) pentru a exporta datele InMobi către.
- InMobi va crea o conexiune directă la stocarea blob și va configura un import automat al datelor dvs. în InMobi. Contactați reprezentantul dvs. InMobi pentru a iniția procesul.

## <a name="known-limitations"></a>Limitări cunoscute

- Pentru Azure Blob Storage, alegeți între [Performanță standard și nivel de performanță Premium](/azure/storage/blobs/storage-blob-performance-tiers). Dacă alegeți nivelul de performanță Premium, selectați [bloburi bloc premium ca tip de cont](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Configurați conexiunea la Azure Blob Storage

[Configurați o conexiune la Azure Blob Storage](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Configurați un export

[Configurați un export](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
