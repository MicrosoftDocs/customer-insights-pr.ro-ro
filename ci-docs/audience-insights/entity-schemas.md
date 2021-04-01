---
title: Scheme de entități Customer Insights din Common Data Model
description: Lucrul cu entități din Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 6667e411a1b56e13105a6b59b7b5d249bc8141ea
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596376"
---
# <a name="entity-schemas-in-common-data-model"></a>Scheme de entități din Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](/common-data-model/) este o specificație declarativă și o definiție a entităților standard care reprezintă concepte și activități utilizate în mod obișnuit în aplicațiile de afaceri și de productivitate. Acest model este extins și la date observaționale și analitice. Common Data Model oferă entități de afaceri bine definite, modulare și extensibile - cum ar fi Cont, unitate de afaceri, caz, persoană de contact, client potențial, oportunitate și produs - precum și interacțiuni cu furnizorii, lucrătorii și clienții - cum ar fi activități și acorduri privind nivelul serviciului. Oricine poate construi și extinde definițiile Common Data Model pentru a capta idei suplimentare specifice afacerii.

Acest model de date partajat permite aplicațiilor și integratorilor de date să colaboreze mai ușor prin furnizarea unei definiții unificate a datelor. Common Data Model include un sistem bogat de metadate cu entități standard, relații, ierarhii, trăsături și multe altele. Provine din aplicațiile Dynamics 365, cu sursă deschisă la GitHub, cu peste 260 de entități standard. Un sistem mare de parteneri interni și externi contribuie cu concepte specifice industriei la Common Data Model.

Mai multe sisteme și platforme implementează astăzi Common Data Model, inclusiv fluxuri de date Power BI și servicii de date Azure. Este deja acceptat în Common Data Service, Dynamics 365, Power Apps , Power BI și serviciile de date Azure viitoare, acumulând în mod direct valoare în [Open Data Initiative](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Scheme de entitate Customer Insights

Pentru a stabili o vedere la 360 de grade a clientului și pentru a face disponibile modelele Customer Insights disponibile în Common Data Model pentru extensibilitate, am publicat următoarele scheme de entitate:

| Entitate | Descriere |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Activitate realizată de un utilizator care are valoare de observație pentru companie. |
|[Profil client](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | O persoană sau organizație care fie a efectuat sau are potențialul de a se implica în activități de business. |
|[Definiție măsură](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definiția KPI-urilor partiționate cu zero sau mai multe dimensiuni (precum Utilizatori lunari activi, Cheltuieli totale pe client, Cost mediu achiziție client) |
|[Segment](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Definește un grup de membri cu caracteristici comune. |
|[Membri segment](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Membrii participanți la un anumit segment. |

Pentru informații suplimentare, consultați documentația despre [Scheme de entitate Customer Insights în Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Vizualizați entitățile care utilizează Navigator entitate Common Data Model

Puteți vizualiza entități în [Navigator de entități Common Data Model Entity](https://microsoft.github.io/CDM/). Selectați **Încărcare de la GitHub!** buton și navigați la **foundationCommon** > **crmCommon** > **soluții** > **customerInsights** unde veți găsi lista entităților Customer Insights și a definițiilor acestora.
> [!div class="mx-imgBorder"]
> ![Navigator entitate CDM care arată entitatea CustomerActivity](media/CDM-entity-navigator.png "Navigator entitate CDM care arată entitatea CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]