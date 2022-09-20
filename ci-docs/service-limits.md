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
ms.openlocfilehash: c3863b1a72fd92ddc87755699feda11371ec9214
ms.sourcegitcommit: dfba60e17ae6dc1e2e3830e6365e2c1f87230afd
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/09/2022
ms.locfileid: "9463234"
---
# <a name="service-limits-in-customer-insights"></a>Limite de servicii în Customer Insights

 Customer Insights are limite încorporate concepute pentru a asigura fiabilitatea și stabilitatea serviciului. Orice solicitări de modificare pot fi făcute prin intermediul [Forum de idei](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Suprafață  | Limite  | Note |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmente, măsuri și previziuni | 300  | Numărul total de [segmente](segments.md),[măsuri](measures.md), și [previziuni](predictions-overview.md) combinate nu pot depăși 300.  |
| Relaţii | 20 de niveluri de profunzime a relațiilor în căile entității. | Când creați [segmente](segments.md) sau [măsuri](measures.md) utilizând interfața constructor, căile entității pot avea până la 20 de relații de salturi între entitatea de pornire și entitatea țintă.  |
|Ingestie date| Evaluări concurente pentru Power Query sursele de date sunt limitate. | Customer Insights are același lucru [limitele de reîmprospătare, cum ar fi Fluxuri de date în PowerBI.com](/power-query/power-query-online-limits#refresh-limits). |

## <a name="fair-scheduling-of-jobs"></a>Programarea corectă a locurilor de muncă

Customer Insights este un serviciu SaaS care utilizează resurse Azure partajate. Clienții tind să aibă sarcini de lucru de intensitate variabilă și pe programe diferite. Pentru a asigura accesul corect la resursele de bază, ne asigurăm că procesele de sistem sunt executate în ordine corectă. Exemple de procese de sistem sunt joburile legate de unificarea datelor, actualizările de segmente sau calcularea măsurătorilor. Programarea corectă vă protejează de la coadă pentru resurse dacă există o creștere a locurilor de muncă solicitate. În același timp, Customer Insights nu garantează că toate lucrările pe care le puneți în coadă sunt procesate în paralel.

[!INCLUDE [footer-include](includes/footer-banner.md)]
