---
title: Rulați eșantionul iOS SDK
description: Exemplu de proiect pentru a afla despre SDK-ul pentru iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bbe4ba648952a8081af4c8f2610276809fa5efeb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232857"
---
# <a name="run-the-ios-sdk-sample"></a>Rulați eșantionul iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Acest eșantion de proiect iOS vă ajută să înțelegeți cum funcționează SDK într-o aplicație. Nu trebuie să scrieți cod. Doar adăugați cheia de ingestie și puteți vedea evenimentele în spațiul dvs. de lucru imediat.

## <a name="prerequisites"></a>Cerințe preliminare

- [Xcode versiunea 9+](https://developer.apple.com/xcode/downloads/)
- [Cheia de ingestie](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Descărcați eșantionul de aplicație iOS SDK

1. [Descărcați eșantionul de detalii de implicare pentru iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Dezarhivați fișierul comprimat `ei-ios-sample.zip`.
1. Deschideți eșantionul de proiect al aplicației în Xcode.
1. În fișierul `EIConfig.plist`, înlocuiți șirul `“YOUR-INGESTION-KEY”` în câmpul `ingestionKey` cu cheia de ingestie a spațiului de lucru din detaliile de implicare de sub **Administrator** > **Spațiu de lucru** > **Ghid de implicare**.
1. Selectați **Rulare** pentru a începe proiectul eșantion.
1. Vizualizați evenimentele din spațiul dvs. de lucru.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
