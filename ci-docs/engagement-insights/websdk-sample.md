---
title: Rularea unui eșantion web SDK
description: Aflați cum să personalizați și să rulați un eșantion web SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036618"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Rulați eșantionul web SDK pentru capacitatea Dynamics 365 Customer Insights Detalii despre angajamente

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Biblioteca web SDK pentru Detalii despre angajamente este o bibliotecă JavaScript cu eșantioane de cod pe care le puteți utiliza pe site-ul dvs. web.

## <a name="prerequisites"></a>Cerințe preliminare

- Instalați [Visual Studio Code](https://code.visualstudio.com/).
- [Instalați extensia Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) în Visual Studio Code și familiarizați-vă cu cum să rulați Live Server.
- Trebuie să aveți [cheia de ingestie](instrument-website.md).

## <a name="run-sample"></a>Rulați eșantionul

1. [Descărcați eșantionul web SDK](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Dezarhivați fișierul comprimat `ei_websdk_sample.zip`.

1. Deschideți folderul dezarhivat în Visual Studio Code.

1. În fișierul `ei_websdk_sample.html`, înlocuiți șirul „INGESTION_KEY” cu cheia de ingestie de pe portalul Detalii despre angajamente și șirul „NAME” cu numele global în care doriți să fie instanțiat SDK-ul. Asigurați-vă că înlocuiți toate aparițiile.

1. Deschideți fișierul `ei_websdk_sample.html` folosind Live Server în Visual Studio Code prin selectarea **Treceți în direct** din bara de stare.

1. La deschiderea paginii, ar trebui trimis automat un eveniment de vizualizare. Dacă faceți clic pe oricare din butoanele de pe pagină, veți trimite evenimente de acțiune. Butonul **Urmăriți evenimentele** de asemenea, va trimite evenimente personalizate. Selectarea butonului **Accesare Bing** va trimite un eveniment de acțiune înainte de a naviga la site-ul web Bing.

1. Priviți evenimentele care se desfășoară atunci când navigați la spațiul de lucru. Acest spațiu de lucru este asociat cu cheia de ingestie introdusă la pasul 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]