---
title: Limite de servicii în Customer Insights
description: Înțelegeți limitele și restricțiile din serviciul Customer Insights SaaS.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 421e1aa41a54a4b8c34ac27fc7c02e510d2bb588
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387171"
---
# <a name="service-limits-in-customer-insights"></a>Limite de servicii în Customer Insights

 Customer Insights are limite încorporate concepute pentru a asigura fiabilitatea și stabilitatea serviciului. Orice solicitări de modificare pot fi făcute prin intermediul [Forum de idei](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Suprafață  | Limite  | Note |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmente, măsuri și previziuni | 300  | Numărul total de [segmente](segments.md),[măsuri](measures.md), și [previziuni](predictions.md) combinate nu pot depăși 300.  |
| Relaţii | 20 de niveluri de profunzime a relațiilor în căile entității. | Când creați [segmente](segments.md) sau [măsuri](measures.md) utilizând interfața constructor, căile entității pot avea până la 20 de relații de salturi între entitatea de pornire și entitatea țintă.  |

## <a name="fair-scheduling-of-jobs"></a>Programarea corectă a locurilor de muncă

Customer Insights este un serviciu SaaS care utilizează resurse Azure partajate. Clienții tind să aibă sarcini de lucru de intensitate variabilă și pe programe diferite. Pentru a asigura accesul corect la resursele de bază, ne asigurăm că procesele de sistem sunt executate în ordine corectă. Exemple de procese de sistem sunt joburile legate de unificarea datelor, actualizările de segmente sau calcularea măsurătorilor. Programarea corectă vă protejează de la coadă pentru resurse dacă există o creștere a locurilor de muncă solicitate. În același timp, Customer Insights nu garantează că toate lucrările pe care le puneți în coadă sunt procesate în paralel.

[!INCLUDE [footer-include](includes/footer-banner.md)]
