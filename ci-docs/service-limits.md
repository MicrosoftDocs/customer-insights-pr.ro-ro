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
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350422"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Limitele de serviciu în capabilitățo Customer Insights

Acest articol descrie limitele încorporate ale serviciului Customer Insights, care sunt concepute pentru a asigura fiabilitatea și stabilitatea serviciului. Orice solicitări de modificare pot fi făcute prin intermediul [Forum de idei](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Detalii despre public

| Suprafață  | Limite  | Note |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmente, măsuri și previziuni | 300  | Numărul total de [segmente](audience-insights/segments.md),[măsuri](audience-insights/measures.md), și [previziuni](audience-insights/predictions.md) combinate nu pot depăși 300.  |
| Relaţii | 20 de niveluri de profunzime a relațiilor în căile entității. | Când creați [segmente](audience-insights/segments.md) sau [măsuri](audience-insights/measures.md) utilizând interfața constructor, căile entității pot avea până la 20 de relații de salturi între entitatea de pornire și entitatea țintă.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
