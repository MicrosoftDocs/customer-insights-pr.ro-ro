---
title: Începeți cu Android SDK
description: Aflați cum să personalizați și să rulați SDK-ul Android
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c678c2dafbb77926269b5602bca363c678ec6b3f
ms.sourcegitcommit: ef823f3d7fa28d3a90cfde9409be9465ffa2cf09
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/19/2021
ms.locfileid: "7655357"
---
# <a name="get-started-with-the-android-sdk"></a>Începeți cu Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Acest tutorial vă ghidează prin procesul de instrumentare a aplicației dvs. Android cu un SDK pentru informații despre implicare Dynamics 365 Customer Insights. Veți începe să vedeți evenimente în portalul dvs. în cinci minute sau mai devreme.

## <a name="configuration-options"></a>Opțiuni de configurare
Următoarele opțiuni de configurare pot fi transmise SDK-ului:

- **ingestionKey**: Cheia de ingestie este utilizată pentru a trimite evenimente în spațiul dvs. de lucru.

## <a name="prerequisites"></a>Cerințe preliminare

- Android Studio

- Nivel minim API Android: 16 (Jelly Bean)

- O cheie de ingestie (a se vedea mai jos pentru instrucțiuni despre cum să o obțineți)

## <a name="integrate-the-sdk-into-your-application"></a>Integrați kitul SDK în aplicația dvs.
Începeți procesul selectând un spațiu de lucru, selectând platforma mobilă Android și descarcând SDK-ul Android.

- Utilizați comutatorul spațiului de lucru din panoul de navigare din stânga pentru a vă selecta spațiul de lucru.

- Dacă nu aveți un spațiu de lucru existent, selectați  **Spațiu de lucru nou** și urmați pașii pentru a crea un [spațiu de lucru nou](create-workspace.md).

- După ce creați un spațiu de lucru, accesați **Administrator** > **Spațiu de lucru** și apoi selectați  **Ghid de instalare**.

## <a name="configure-the-sdk"></a>Configurarea SDK-ului

După ce descărcați SDK-ul, puteți lucra cu el în Android Studio pentru a activa și defini evenimente. Există două moduri de a face asta:
### <a name="option-1-use-jitpack-recommended"></a>Opțiunea 1: Utilizați JitPack (recomandat)
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
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>Opțiunea 2: Utilizați linkul de descărcare
1. Descărcați [statistici privind implicarea Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip), și plasați`eiandroidsdk-debug.aar` dosar în`libs` pliant.

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

## <a name="enable-auto-instrumentation"></a>Activați instrumentarea automată

1. Adăugați permisiunea pentru rețea și internet în fișierul `AndroidManifest.xml` aflat sub folderul `manifests`.
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. Configurați detaliile de implicare SDK prin fișierul dvs. `AndroidManifest.xml`.

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

1. Activați sau dezactivați captarea automată a evenimentelor `View` setând câmpul `autoCapture` de mai sus la `true` sau `false`. 

   >[!NOTE]
   >`Action` evenimentele trebuie adăugate manual.

1. (Opțional) Alte configurații includ setarea adresei URL a colectorului de punct final. Ele pot fi adăugate sub metadatele cheii de asimilare în `AndroidManifest.xml`.

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
