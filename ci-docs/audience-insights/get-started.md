---
title: Începeți cu capacitatea de analiză a publicului în Dynamics 365 Customer Insights
description: O prezentare generală a statisticilor publicului ajută resursele să înceapă rapid.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 2776b2292560f9ea61a06d2b1b7bc7811d35c860
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353742"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Începeți cu capacitatea de analiză a publicului Dynamics 365 Customer Insights

Detalii despre public, vă pot ajuta să construiți o înțelegere mai profundă a clienților dvs. Conectați date din diverse surse tranzacționale, comportamentale și de observație pentru a crea o vedere a clienților la 360 de grade. Utilizați aceste informații pentru a genera experiențe și procese centrate pe client. Unificați și înțelegeți datele clienților și valorificați-le pentru detalii și acțiuni inteligente.

## <a name="step-1-create-an-environment"></a>Pasul 1: Crearea unui mediu

Pentru început, trebuie mai întâi să creați un mediu în care să lucrați. Dacă organizația dvs. a achiziționat deja o licență, consultați [Creați un mediu](create-environment.md). Pentru a începe o încercare pentru informații despre public, consultați [Configurați un mediu de încercare](../trial-signup.md). 

## <a name="step-2-explore-audience-insights"></a>Pasul 2: Explorați detalii despre public

Prima dată când vă conectați la statistici privind publicul, puteți configura setările și puteți explora produsul.

1. [Conectați-vă la statisticile publicului](https://home.ci.ai.dynamics.com) folosind contul dvs. de utilizator Microsoft Azure Active Directory (AAD).

1. [Schimbați mediul](manage-environments.md#switch-environments) pentru a vedea datele demo și [explorați detaliile publicului](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Pasul 3: ingerați, unificați și configurați relații pentru datele dvs.

Profilurile unificate reprezintă fundamentul pentru a obține informații și a lua măsuri cu privire la date. Aduceți date din diverse surse și rulați procesul de unificare a datelor pentru a combina profiluri unificate. Specificați relațiile dintre entitățile ingerate folosesc caracteristici de îmbogățire pentru a adăuga informații la profiluri. 

1. Ingerează date prin crearea de surse de date din mai multe opțiuni. Alege intre [Power Query conectori](connect-power-query.md), A [Dosarul Common Data Model](connect-common-data-model.md), sau [Microsoft Dataverse](/dynamics365/customer-insights/audience-insights/connect-dataverse-managed-lake). 

1. Rulați [procesul de unificare a datelor](data-unification.md) trecând prin fazele [mapare](map-entities.md), [potrivire](match-entities.md), și [combinare](merge-entities.md).

1. Familiarizați-vă cu [entități pe care le creează sistemul](entities.md) și creați [relațiile dintre entitățile ingerate](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Pasul 4: îmbunătățiți profilurile unificate cu predicții, activități și măsuri

Cu configurarea profilurilor unificate, vă puteți îmbunătăți datele și puteți crește în continuare informațiile pe care le furnizează.

1. Alegeți dintr-o bibliotecă în expansiune de furnizori de îmbogățire pentru a [îmbogăți datele despre clienți](enrichment-hub.md).

1. Utilizați [modele predefinite](predictions-overview.md) pentru a prezice probabilitatea de churn sau veniturile preconizate.

1. [Configurați activitățile](activities.md) pe baza datelor ingerate și vizualizați interacțiunile cu clienții dvs. într-o cronologie cronologică. 

1. [Construiți măsuri](measures.md) pentru a vă evalua obiectivele comerciale și KPI-urile.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Pasul 5: creați segmente și activați datele prin diferite opțiuni de export

Acum că datele dvs. sunt complete și conțin o gamă largă de informații despre clienții dvs., este timpul să căutați modalități de a acționa cu privire la aceste date. 

1. [Creați segmente](segments.md), subseturi ale bazei dvs. de clienți, pentru a vă asigura că acțiunile dvs. sunt relevante pentru clienții vizați.

1. Răsfoiți catalogul extins de [opțiuni de export](export-destinations.md) unde puteți utiliza datele clienților. De exemplu, puteți utiliza datele pentru a gestiona promoțiile și pentru a contacta marketingul digital.

1. Examinați opțiunile de integrare, de exemplu cu [conexiune directă cu perspectivele de implicare](../engagement-insights/integrate-audience-insights-engagement-insights.md) sau la alte aplicații Dynamics 365 cu [Program de completare pentru cardul clientului](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]