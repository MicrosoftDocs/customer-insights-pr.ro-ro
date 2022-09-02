---
title: Exemple de interogări OData pentru API-urile Customer Insights
description: Exemple utilizate în mod obișnuit pentru Protocolul de date deschise (OData) pentru a interoga API-urile Customer Insights pentru a examina datele.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 26e56a3bab01ba55284a52e72efbcbfbaadaad6f
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387217"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Exemple de interogări OData pentru API-urile Customer Insights

Protocolul de date deschise (OData) este un protocol de acces la date construit pe protocoale de bază precum HTTP. Folosește metodologii acceptate în mod obișnuit, cum ar fi REST pentru web. Există diferite tipuri de biblioteci și instrumente care pot fi utilizate pentru a consuma serviciile OData.

Pentru a vă ajuta să vă construiți propriile implementări bazate pe [API-uri Customer Insights](apis.md) , examinați câteva exemple de interogări frecvent solicitate.

Modificați mostrele de interogare pentru a le face să funcționeze în mediile țintă:

- {serviceRoot}:`https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` Unde{instanceId} este GUID-ul mediului Customer Insights pe care doriți să îl interogați. The [Operațiunea ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) vă permite să găsiți{InstanceId} ai acces la.
- {CID}: GUID-ul unei înregistrări unificate de client. Exemplu:`ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Identificatorul cheii primare a înregistrării unui client într-un sursă de date. Exemplu: `CNTID_1002`
- {DSname}: șir cu numele entității unui sursă de date care este ingerat în Customer Insights. Exemplu:`Website_contacts`.
- {SegmentName}: șir cu numele entității de ieșire a unui segment în Customer Insights. Exemplu:`Male_under_40`.

## <a name="customer"></a>client

Exemple de interogări pentru *Client* entitate.

|Tip interogare |Exemplu  | Notă  |
|---------|---------|---------|
|ID client unic     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|cheie alternativă    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Cheile alternative persistă în entitatea client unificată       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|În    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|cheie alternativă + In   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Căutarea  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Returnează primele 10 rezultate pentru un șir de căutare      |
|Segmentul de membru  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Returnează un număr prestabilit de rânduri de la entitatea de segmentare.      |
|Segmentează calitatea de membru pentru un client | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | Returnează profilul clientului dacă este membru al segmentului dat     |

## <a name="unified-activity"></a>Activitate unificată

Exemple de interogări pentru *Activitate unificată* entitate.

|Tip interogare |Exemplu  | Notă  |
|---------|---------|---------|
|Activitatea CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Listează activitățile unui anumit profil de client |
|Intervalul de timp al activității    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Activitățile unui profil de client într-un interval de timp       |
|Tip de activitate    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Activitate după numele afișat     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Sortarea activității    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Sortați activitățile crescător sau descendent       |
|Activitatea sa extins de la apartenența la segment  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Alte exemple

Exemple de interogări pentru alte entități.

|Tip interogare |Exemplu  | Notă  |
|---------|---------|---------|
|Măsuri ale CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Mărci îmbogățite ale CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Interesele îmbogățite ale CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-Clause + Extinde     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Interogări OData nu sunt acceptate

Următoarele interogări nu sunt acceptate de Customer Insights:

- `$filter` asupra entităților sursă ingerate. Puteți rula interogări $filter numai pe entitățile de sistem pe care le creează Customer Insights.
- `$expand` de la a`$search` interogare. Exemplu: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` din`$select` dacă este selectat doar un subset de atribute. Exemplu: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` marcă îmbogățită sau afinități de interes pentru un anumit client. Exemplu: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Interogați entitățile de ieșire a modelului predicție prin cheie alternativă. Exemplu: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
