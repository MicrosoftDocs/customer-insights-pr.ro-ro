---
title: Rularea unui eșantion web SDK
description: Aflați cum să personalizați și să rulați un eșantion web SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606258"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Rulați eșantionul web SDK pentru capacitatea Dynamics 365 Customer Insights Detalii despre angajamente

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Biblioteca web SDK pentru Detalii despre angajamente este o bibliotecă JavaScript cu eșantioane de cod pe care le puteți utiliza pe site-ul dvs. web.

## <a name="prerequisites"></a>Cerințe preliminare

- Instalați [Visual Studio Code](https://code.visualstudio.com/).
- [Instalați extensia Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) în Visual Studio Code și familiarizați-vă cu cum să rulați Live Server.
- Trebuie să aveți un [spațiu de lucru pentru perspectivele de angajament](create-workspace.md).

## <a name="run-sample"></a>Rulați eșantionul

1. [Descărcați eșantionul web SDK](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Dezarhivați fișierul comprimat `ei_websdk_sample.zip`.

1. Deschideți folderul dezarhivat în Visual Studio Code.

1. Accesați portalul de informații despre angajament pentru spațiul dvs. de lucru. Selectați **Administrator** > **Spațiu de lucru**  și apoi **Ghid de instalare**. Urmați prima opțiune și selectați **Copiați codul** pentru a copia fragmentul de cod JavaScript.

1. În fișierul `ei_websdk_sample.html`, lipiți fragment de cod pe care tocmai l-ați copiat sub această linie:

   - <-- LIPIȚI FRAGMENTUL DE COD JAVASCRIPT DIN PORTALUL DE INFORMAȚII PRIVIND ACHIZIȚIA AICI SUB ACEASTĂ LINIE ->

1. Deschideți fișierul `ei_websdk_sample.html` folosind Live Server în Visual Studio Code prin selectarea **Treceți în direct** din bara de stare.

1. La deschiderea paginii, ar trebui trimis automat un eveniment de vizualizare. Dacă faceți clic pe oricare din butoanele de pe pagină, veți trimite evenimente de acțiune. Butonul **Urmăriți evenimentele** de asemenea, va trimite evenimente personalizate. Selectarea butonului **Accesare Bing** va trimite un eveniment de acțiune înainte de a naviga la site-ul web Bing.

1. Priviți evenimentele care se desfășoară atunci când navigați la spațiul de lucru. Acest spațiu de lucru este asociat cu cheia de ingestie introdusă la pasul 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
