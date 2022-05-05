---
title: Limitele serviciului în Dynamics 365 Customer Insights
description: Înțelegeți limitele și restricțiile.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641777"
---
# <a name="service-limits-in-customer-insights"></a>Limite de servicii în Customer Insights

Acest articol descrie limitele încorporate ale serviciului Customer Insights, care sunt concepute pentru a asigura fiabilitatea și stabilitatea serviciului. Orice solicitări de modificare pot fi făcute prin intermediul [Forum de idei](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Suprafață  | Limite  | Note |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmente, măsuri și previziuni | 300  | Numărul total de [segmente](segments.md),[măsuri](measures.md), și [previziuni](predictions.md) combinate nu pot depăși 300.  |
| Relaţii | 20 de niveluri de profunzime a relațiilor în căile entității. | Când creați [segmente](segments.md) sau [măsuri](measures.md) utilizând interfața constructor, căile entității pot avea până la 20 de relații de salturi între entitatea de pornire și entitatea țintă.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
