---
title: Scheme de entități din Common Data Model
description: Lucrul cu entități din Common Data Model.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 92d37fc0950fefcb5c2a5d26214a469d3693980d
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054769"
---
# <a name="entity-schemas-in-common-data-model"></a>Scheme de entități din Common Data Model

[Common Data Model](/common-data-model/) este o specificație declarativă și o definiție a entităților standard care reprezintă concepte și activități utilizate în mod obișnuit în aplicațiile de afaceri și de productivitate. Acest model este extins și la date observaționale și analitice. Common Data Model oferă entități de afaceri bine definite, modulare și extensibile - cum ar fi Cont, unitate de afaceri, caz, persoană de contact, client potențial, oportunitate și produs - precum și interacțiuni cu furnizorii, lucrătorii și clienții - cum ar fi activități și acorduri privind nivelul serviciului. Oricine poate construi și extinde definițiile Common Data Model pentru a capta idei suplimentare specifice afacerii.

Acest model de date partajat permite aplicațiilor și integratorilor de date să colaboreze mai ușor prin furnizarea unei definiții unificate a datelor. Common Data Model include un sistem bogat de metadate cu entități standard, relații, ierarhii, trăsături și multe altele. Provine din aplicațiile Dynamics 365, cu sursă deschisă la GitHub, cu peste 260 de entități standard. Un sistem mare de parteneri interni și externi contribuie cu concepte specifice industriei la Common Data Model.

Mai multe sisteme și platforme implementează astăzi Common Data Model, inclusiv fluxuri de date Power BI și Servicii de date Azure. Este deja acceptat în Microsoft Dataverse, Dynamics 365, Power Apps, Power BI, și viitoarele servicii de date Azure, care acumulează direct valoare pentru [Inițiativa Open Data](https://dynamics.microsoft.com/en-us/open-data-initiative/).

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

Puteți vizualiza entități în [Navigator de entități Common Data Model Entity](https://microsoft.github.io/CDM/). Selectați o entitate din secțiunea Aplicație Insights pentru a obține lista entităților Customer Insights și definițiile acestora.
> [!div class="mx-imgBorder"]
> ![Navigator entitate CDM care arată entitatea CustomerActivity.](media/CDM-entity-navigator.png "Navigator entitate CDM care arată entitatea CustomerActivity")


[!INCLUDE [footer-include](includes/footer-banner.md)]
