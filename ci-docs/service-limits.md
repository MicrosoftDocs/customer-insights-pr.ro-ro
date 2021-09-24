---
title: Limitele serviciului în Dynamics 365 Customer Insights
description: Înțelegeți limitele și restricțiile.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483699"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Limitele de serviciu în capabilitățo Customer Insights

Acest articol descrie limitele încorporate ale serviciului Customer Insights, care sunt concepute pentru a asigura fiabilitatea și stabilitatea serviciului. Orice solicitări de modificare pot fi făcute prin intermediul [Forum de idei](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Detalii despre public

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Limite de serviciu în capabilitatea de detalii despre public din Dynamics 365 Customer Insights

| Zonă  | Limite  | Note |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmente și măsuri | 100 de segmente sau măsuri. | Numărul total de [segmente](audience-insights/segments.md) active și [măsuri](audience-insights/measures.md) combinate nu poate depăși 100.  |
| Relații | 20 de niveluri de profunzime a relațiilor în căile entității. | Când creați [segmente](audience-insights/segments.md) sau [măsuri](audience-insights/measures.md) utilizând interfața constructor, căile entității pot avea până la 20 de relații de salturi între entitatea de pornire și entitatea țintă.  |


## <a name="engagement-insights"></a>Detalii despre angajamente

### <a name="workspace-and-event-quotas"></a>Cote de spațiu de lucru și evenimente

Detalii despre angajamente este o aplicație foarte scalabilă, care poate suporta milioane de evenimente pe secundă. În timpul versiunii preliminare publice, evenimentele au un prag de volum. Există, de asemenea, o limită a numărului de spații de lucru dintr-o organizație.

### <a name="engagement-insights-limits"></a>Limite de detalii despre angajamente

- Volumul maxim de evenimente pe spațiu de lucru = 100 de evenimente pe secundă

- Numărul maxim de spații de lucru pe organizație = 100

Atunci când evenimentele depășesc pragul, poate duce la pierderea datelor din rapoarte bazate pe acele evenimente. Puteți să [contactați asistența](https://go.microsoft.com/fwlink/?linkid=2145734) pentru a solicita o creștere a volumului înainte de a depăși limitele. Vom colabora cu dvs. pentru a determina nevoia dvs. de creștere a volumului și pentru a vă susține solicitarea.


[!INCLUDE[footer-include](includes/footer-banner.md)]