---
title: Eșantion Android SDK
description: Exemplu de proiect pentru a afla despre SDK-ul pentru Android
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035841"
---
# <a name="run-the-android-sdk-sample"></a>Rulați eșantionul Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Acest eșantion de proiect Android vă ajută să înțelegeți cum funcționează SDK într-o aplicație. Nu trebuie să scrieți cod. Doar adăugați cheia de ingestie și puteți vedea evenimentele în spațiul dvs. de lucru imediat.

## <a name="prerequisites"></a>Cerințe preliminare

- [Android Studio](https://developer.android.com/studio)
- [Cheia de ingestie](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Descărcați eșantionul de Android SDK

1. [Descărcați detaliile de implicaare eșantion Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Dezarhivați fișierul comprimat `ei-android-sample.zip`.
1. Deschideți folderul dezarhivat în Android Studio.
1. În fișierul `AndroidManifest.xml` înlocuiți șirul `"Your-Ingestion-Key"` cu cheia de ingestie a spațiului de lucru din detaliile de implicare de sub **Administrator** > **Spațiu de lucru** > **Ghid de instalare**. 

   > [!NOTE]
   > Nu trebuie să înlocuiți secțiunea `${applicationId}`. Este populată automat.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Selectați **Rulare** pentru a începe proiectul eșantion.
1. Vizualizați evenimentele din spațiul dvs. de lucru.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
