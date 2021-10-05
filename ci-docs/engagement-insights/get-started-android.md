---
title: Începeți cu Android SDK
description: Aflați cum să particularizați și să rulați Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a060ac60db71a7b0fb8c0d7a3b0e266004fbee6a
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494290"
---
# <a name="get-started-with-the-android-sdk"></a>Începeți cu Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Acest tutorial vă ghidează prin procesul de instrumentare a aplicației Android cu un SDK Dynamics 365 Customer Insights detalii despre angajament. Veți începe să vedeți evenimente în portalul dvs. în cinci minute sau mai devreme.

## <a name="configuration-options"></a>Opțiuni de configurare
Următoarele opțiuni de configurare pot fi transmise SDK-ului:

- **ingestionKey**: Cheia de ingestie este utilizată pentru a trimite evenimente în spațiul dvs. de lucru.

## <a name="prerequisites"></a>Cerințe preliminare

- Android Studio

- Minimum Android Nivelul API: 16 (Jelly Bean)

- O cheie de ingestie (a se vedea mai jos pentru instrucțiuni despre cum să o obțineți)

## <a name="integrate-the-sdk-into-your-application"></a>Integrați kitul SDK în aplicația dvs.
Începeți procesul selectând un spațiu de lucru, selectând platforma mobilă Android și descărcarea fișierului Android SDK.

- Utilizați comutatorul spațiului de lucru din panoul de navigare din stânga pentru a vă selecta spațiul de lucru.

- Dacă nu aveți un spațiu de lucru existent, selectați  **Spațiu de lucru nou** și urmați pașii pentru a crea un [spațiu de lucru nou](create-workspace.md).

- După ce creați un spațiu de lucru, accesați **Administrator** > **Spațiu de lucru** și apoi selectați  **Ghid de instalare**. 

## <a name="configure-the-sdk"></a>Configurarea SDK-ului

Odată ce descărcați SDK, puteți lucra cu acesta în Android Studio pentru a activa și defini evenimente. Există două moduri de a face asta:
### <a name="option-1-using-jitpack-recommended"></a>Opțiunea 1: Utilizarea JitPack (recomandat)
1. Adăugați depozitul JitPack la rădăcina `build.gradle`:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Adăugați dependența:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-using-download-link"></a>Opțiunea 2: Folosind linkul de descărcare
1. Descărcați fișierul [detalii de implicare Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip), și așezați fișierul `eiandroidsdk-debug.aar` în folderul `libs`.

1. Deschideți fișierul la nivelul de proiect `build.gradle` și adăugați următoarele fragmente:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Adăugați permisiunea pentru rețea și internet în fișierul `AndroidManifest.xml` aflat sub folderul `manifests`. 
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```
    
1. Configurați detaliile de implicare SDK prin fișierul dvs. `AndroidManifest.xml`. 

## <a name="enable-auto-instrumentation"></a>Activați instrumentarea automată
1. Copiază XML fragment din **Ghid de instalare**. `Your-Ingestion-Key` ar trebui să fie populată automat.

   > [!NOTE]
   > Nu trebuie să înlocuiți secțiunea `${applicationId}`. Este populată automat.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Activați sau dezactivați captarea automată a evenimentelor `View` setând câmpul `autoCapture` de mai sus la `true` sau `false`. În prezent evenimentele `Action` trebuie adăugate manual.

1. (Opțional) Alte configurații includ setarea adresei URL a colectorului de punct final. Acestea pot fi adăugate sub metadatele cheie de ingestie în `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="implement-custom-events"></a>Implementați evenimente particularizate

După ce inițializați kitul SDK, puteți lucra cu evenimente și proprietățile acestora în mediul `MainActivity`.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Setați proprietatea pentru toate evenimentele (opțional)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Următoarele tipuri sunt acceptate pentru proprietățile evenimentului context:
- Șir
- Data
- Dublu
- Long
- Boolean
- UUID

### <a name="track-an-event"></a>Urmăriți un eveniment

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

## <a name="set-user-details-for-your-event-optional"></a>Setați detaliile utilizatorului pentru evenimentul dvs. (opțional)

SDK vă permite să definiți informații despre utilizator care pot fi trimise cu fiecare eveniment. Puteți specifica informații despre utilizator apelând `setUser(user: User)` API pe nivelul `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Clasa de date `User` conține următoarele proprietăți de șir:

- **localId**: ID-ul local al utilizatorului.
- **authId**: ID-ul de utilizator autentificat.
- **authType**: Tipul de autentificare utilizat pentru obținerea ID-ului de utilizator autentificat.
- **Nume**: Numele utilizatorului.
- **e-mail**: Adresa de e-mail a utilizatorului.

[!INCLUDE[footer-include](../includes/footer-banner.md)]