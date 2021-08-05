---
title: Limite de serviciu
description: Înțelegeți limitele și restricțiile.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 81253332cbea3110c0b3804db3a4d03b514f92d4
ms.sourcegitcommit: 9a99e48e96dfb3d895db428f37c30ae55eea66b7
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/14/2021
ms.locfileid: "6604384"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Limite de serviciu în capabilitatea de detalii despre public din Dynamics 365 Customer Insights

Acest articol descrie limitele încorporate ale serviciului Customer Insights, care sunt concepute pentru a asigura fiabilitatea și stabilitatea serviciului. Orice solicitări de modificare pot fi făcute prin intermediul [Forum de idei](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Zonă  | Limite  | Note |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmente și măsuri | 100 de segmente sau măsuri. | Numărul total de [segmente](segments.md) active și [măsuri](measures.md) combinate nu poate depăși 100.  |
| Relații | 20 de niveluri de profunzime a relațiilor în căile entității. | Când creați [segmente](segments.md) sau [măsuri](measures.md) utilizând interfața constructor, căile entității pot avea până la 20 de relații de salturi între entitatea de pornire și entitatea țintă.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]