---
title: Începeți cu iOS SDK
description: Aflați cum să particularizați și să rulați iOS SDK
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 09/15/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e4d0555d2fc377fae62ff5db64c032fcebcb04
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226230"
---
# <a name="get-started-with-the-ios-sdk"></a>Începeți cu iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Acest tutorial vă ghidează cu instrumentarea aplicației iOS cu o aplicație Dynamics 365 Customer Insights SDK de detalii despre implicare. Veți începe să vedeți evenimente în portalul dvs. în cinci minute sau mai devreme.

## <a name="configuration-options"></a>Opțiuni de configurare

Următoarele opțiuni de configurare pot fi transmise către SDK prin intermediul celor furnizate de fișierul `EIConfig.plist`:

- **ingestionKey**: Cheia de ingestie este utilizată pentru a trimite evenimente în proiectul dvs.
- **autocollectAction** : O valoare Boolean pentru a activa sau dezactiva instrumentarea automată a evenimentului de acțiune.
- **autocollectView**: O valoare Boolean pentru a activa sau dezactiva instrumentarea automată a evenimenului de acțiune.
- **endpointUrl** : Adresa URL a punctului final către care vor fi direcționate evenimentele.

## <a name="prerequisites"></a>Cerințe preliminare

- Xcode versiunea 9+
- iOS versiunea 8.2+
- O cheie de ingestie (consultați instrucțiunile de mai jos pentru a o obține)

## <a name="integrate-the-sdk-into-your-application"></a>Integrați kitul SDK în aplicația dvs.

Începeți procesul selectând un spațiu de lucru, în care să lucrați, selectând platforma mobilă iOS și descărcarea fișierului SDK.

- Utilizați comutatorul spațiului de lucru din panoul de navigare din stânga pentru a vă selecta spațiul de lucru.

- Dacă nu aveți un spațiu de lucru existent, selectați  **Spațiu de lucru nou** și urmați pașii pentru a crea un [spațiu de lucru nou](create-workspace.md).

- După ce creați un spațiu de lucru, accesați **Administrator** > **Spațiu de lucru** și apoi selectați **Ghid de instalare**.

## <a name="configure-the-sdk"></a>Configurarea SDK-ului

După ce descărcați SDK-ul, puteți lucra cu acesta în Xcode pentru a activa și defini evenimente. Există două moduri de a face asta

### <a name="option-1-using-cocoapods-recommended"></a>Opțiunea 1: Utilizarea CocoaPods (recomandat)
CocoaPods este un manager de dependență pentru proiectele Swift și Objective-C Cocoa. Utilizarea acestuia face mai ușoară integrarea SDK-urilor de implicare pentru iOS. CocoaPods vă permite, de asemenea, să faceți upgrade la cea mai recentă versiune a SDK-ului Statistici de implicare. Iată cum să utilizați CocoaPods pentru a integra SDK-urile de implicare în proiectul dvs. Xcode. 

1. Instalați CocoaPods. 

1. Creați un fișier nou numit Podfile în directorul rădăcină al proiectului dvs. și adăugați următoarele instrucțiuni. Înlocuiți YOUR_TARGET_PROJECT_NAME cu numele proiectului dvs. Xcode. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
Configurația podului de mai sus conține atât versiunile de depanare, cât și versiunea SDK. Alegeți unul dintre cele mai bune pentru proiectul dvs.

1. Instalați podul executând următoarea comandă: `pod install --repo-update `

### <a name="option-2-using-download-link"></a>Opțiunea 2: Folosind linkul de descărcare

1. Descărcați [detaliile de implicare iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) și plasați fișierul `EIObjC.xcframework` în folderul `Frameworks`.

1. În cazul în care un folder `Frameworks` nu există, creați unul în folderul proiectului.

## <a name="enable-auto-instrumentation"></a>Activați instrumentarea automată
 
Puteți activa cu ușurință instrumentarea automată fără codificare. Când rulează proiectul, acesta va urmări automat fișierul `view` și evenimente `action` folosind cheia de ingestie configurată. 

1. Actualizați și includeți fișierul `EIConfig.plist` furnizat în directorul de director al proiectului pentru următoarele câmpuri:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = DA
    - autocollectAction = DA

2. Apoi adăugați fișierul `EIConfig.plist` în proiectul dvs. în Xcode. 



Pentru a dezactiva instrumentarea automată, actualizați următoarele câmpuri în fișierul încorporat `EIConfig.plist` din folderul director al proiectului. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Implementați evenimente particularizate

1. Deschideți proiectul dvs. Xcode și navigați la setările **Generale**. 
1. Adăugați `EIObjC.xcframework` la proiect în secțiunea „Cadre, Biblioteci și Conținut încorporat”.

1. Importați fișierul antet cadru în AppDelegate.m cu următorul fragment:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Inițializați detaliile de implicare SDK din aplicație: didFinishLaunchingWithOptions.
1. Copiază XML fragment din **Ghid de instalare**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Urmăriți un eveniment:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Setați detaliile utilizatorului pentru evenimentul dvs.

SDK vă permite să definiți informații despre utilizator care pot fi trimise cu fiecare eveniment. Puteți specifica informațiile de utilizator apelând API `setUser:(nonnull EIUser *)user` pe SDK.

Specificarea detaliilor utilizatorului pe nivelul `Analytics` înseamnă că toate telemetriile vor avea aceste informații. Cu toate acestea, dacă specificați la nivel de eveniment apelând API `setUser:(nonnull EIUser *)user` pe obiectul EIEvent, doar acel eveniment specific va conține informațiile.

Clasa de date `EIUser` conține următoarele proprietăți NSString.

- **localId**: ID-ul local al utilizatorului.
- **authId**: ID-ul de utilizator autentificat.
- **authType**: Tipul de autentificare utilizat pentru a obține ID-ul de utilizator autentificat.
- **Nume**: Numele utilizatorului.
- **e-mail**: Adresa de e-mail a utilizatorului.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
