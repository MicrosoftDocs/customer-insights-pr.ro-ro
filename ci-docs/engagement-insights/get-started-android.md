---
title: Începeți cu Android SDK
description: Aflați cum să particularizați și să rulați Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036933"
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

## <a name="step-1-integrate-the-sdk-into-your-application"></a>Pasul 1. Integrați kitul SDK în aplicația dvs.
Începeți procesul selectând un spațiu de lucru, selectând platforma mobilă Android și descărcarea fișierului Android SDK.

- Utilizați comutatorul spațiului de lucru din panoul de navigare din stânga pentru a vă selecta spațiul de lucru.

- Dacă nu aveți un spațiu de lucru existent, selectați  **Spațiu de lucru nou** și urmați pașii pentru a crea un [spațiu de lucru nou](create-workspace.md).

## <a name="step-2-configure-the-sdk"></a>Pasul 2. Configurarea SDK-ului

1. După ce creați un spațiu de lucru, accesați **Administrator** > **Spațiu de lucru** și apoi selectați  **Ghid de instalare**. 

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

1. Configurați configurația SDK statistici de implicare prin intermediul fișierului `AndroidManifest.xml` aflat sub folderul `manifests`. 
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

1. (Opțional) Alte configurații includ setarea adresei URL a colectorului de punct final. Acestea pot fi adăugate sub metadatele cheie de ingestie în `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>Pasul 3. Inițializați SDK-ul din MainActivity 

După ce inițializați kitul SDK, puteți lucra cu evenimente și proprietățile acestora în mediul MainActivity.

    
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

### <a name="set-user-details-for-your-event-optional"></a>Setați detaliile utilizatorului pentru evenimentul dvs. (opțional)

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
