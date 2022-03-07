---
title: Scenarii web SDK complexe
description: Scenarii avansate de luat în considerare atunci când instrumentați site-ul dvs. web cu un SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 4c6646ecadbb604000d6c95b685cf6e420969a6d
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558717"
---
# <a name="advanced-web-sdk-instrumentation"></a>Instrumentare avansată SDK web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Acest articol vă ghidează prin scenarii avansate de luat în considerare la [instrumentarea site-ului dvs. web](instrument-website.md) cu capacitatea SDK Dynamics 365 Customer Insights Detalii despre angajamente.

## <a name="setting-user-details-for-your-event"></a>Setarea detaliilor utilizatorului pentru evenimentul dvs.

SDK vă permite să definiți informații despre utilizator care pot fi trimise cu fiecare eveniment. Puteți specifica detaliile utilizatorului într-o proprietate numită `user` (datele preconizate pentru această proprietate sunt obiectul `IUser`), similar cu `src`, `name` și `cfg` în configurația fragment de cod.

Obiectul `IUser` conține următoarele proprietăți de șir:

- **localId**: ID-ul local al utilizatorului.
- **authId**: ID-ul de utilizator autentificat.
- **authType**: Tipul de autentificare utilizat pentru a obține ID-ul de utilizator autentificat.
- **Nume**: Numele utilizatorului.
- **e-mail**: Adresa de e-mail a utilizatorului.

Următorul exemplu arată un fragment de cod care trimite informații despre utilizator. Unde vedeți funcții precedate de un simbol asterisc *, înlocuiți funcția cu implementarea particularizată:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

De asemenea, puteți specifica informații despre utilizator apelând API-ul `setUser(user: IUser)`. Telemetria trimisă după apelarea API-ului `setUser` va conține informațiile despre utilizator.

## <a name="adding-custom-properties-for-each-event"></a>Adăugarea de proprietăți personalizate pentru fiecare eveniment

SDK vă permite să specificați proprietăți particularizate care pot fi trimise cu fiecare eveniment. Puteți specifica proprietățile particularizate ca un obiect care conține perechi cheie-valoare (valoarea poate fi de tip `string | number | boolean`). Puteți adăuga obiectul într-o proprietate numită `props`, similar cu `src`, `name`, și `cfg` în configurația fragment de cod.

Următorul exemplu arată un fragment de cod care trimite proprietăți particularizate.

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

De asemenea, puteți specifica proprietăți particularizate specifice apelând API-ul `setProperty(name: string, value: string | number | boolean)`.

## <a name="sending-custom-events"></a>Trimiterea de evenimente personalizate

Puteți utiliza SDK pentru a trimite evenimente particularizate. Trebuie să specificați un nume pentru eveniment și proprietățile care vor fi trimise împreună cu evenimentul.

Următorul exemplu arată un fragment de cod care urmărește un eveniment particularizat. "NUME" este valoarea din cheia `name` în configurația fragment. Este, de asemenea, numele variabilei din obiectul ferestrei unde este încărcat SDK-ul.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
