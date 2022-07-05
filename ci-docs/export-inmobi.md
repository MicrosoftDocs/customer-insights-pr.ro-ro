---
title: Exportați datele despre Customer Insights în InMobi
description: Aflați cum să configurați conexiunea și să exportați în InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9059616"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Exportați lista de segmente și alte date în InMobi (previzualizare)

Exportați liste de segmente sau alte date din instanța dvs. Customer Insights către [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Cerințe preliminare

1. Ai un [cont InMobi](https://www.inmobi.com/) și acreditările de administrator.
1. Aveți un nume de cont de stocare Azure Blob și cheia de cont corespunzătoare. Pentru mai multe informații, vezi [Gestionați setările contului de stocare în portalul Azure](/azure/storage/common/storage-account-manage). Există un container în contul de stocare pentru a exporta datele inMobi. Pentru mai multe informații, vezi [Creați un container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi va crea o conexiune directă la stocarea blob și va configura un import automat al datelor dvs. în InMobi. Contactați reprezentantul dvs. InMobi pentru a iniția procesul.

## <a name="known-limitations"></a>Limitări cunoscute

1. Pentru Azure Blob Storage, puteți alege între [Performanță standard și nivel de performanță Premium](/azure/storage/blobs/storage-blob-performance-tiers). Dacă alegeți nivelul de performanță Premium, selectați [bloburi bloc premium ca tip de cont](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Configurați conexiunea la Azure Blob Storage și configurați un export

1. Urmați instrucțiunile pentru [configurați o conexiune la Azure Blob Storage](export-azure-blob-storage.md).
2. Urmați instrucțiunile pentru [configurați un export](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
