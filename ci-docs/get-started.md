---
title: Introducere în Dynamics 365 Customer Insights
description: O prezentare generală a Customer Insights ajută resursele să înceapă rapid.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1c925110f40319df77940d1c32f24a99504d6ec6
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011994"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Introducere în Dynamics 365 Customer Insights

Customer Insights vă poate ajuta să construiți o înțelegere mai profundă a clienților dvs. Conectați date din diverse surse tranzacționale, comportamentale și de observație pentru a crea o vedere a clienților la 360 de grade. Utilizați aceste informații pentru a genera experiențe și procese centrate pe client. Unificați și înțelegeți datele clienților și valorificați-le pentru detalii și acțiuni inteligente.

## <a name="step-1-create-an-environment"></a>Pasul 1: Crearea unui mediu

În primul rând, creați un mediu în care să lucrați. Dacă organizația dvs. a achiziționat deja o licență, consultați [Creați un mediu](create-environment.md). Pentru a începe o încercare pentru Customer Insights, consultați [Configurați un mediu de probă](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Pasul 2: Explorați statisticile clienților

Prima dată când vă conectați la Customer Insights, configurați setările și explorați produsul.

1. [conectați-vă la Customer Insights](https://home.ci.ai.dynamics.com) folosind Microsoft Azure Active Directory cont de utilizator (AAD).

1. Schimbați mediul pentru a vedea datele demonstrative și [explorați Customer Insights](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Pasul 3: ingerați, unificați și configurați relații pentru datele dvs.

Profilurile unificate reprezintă fundamentul pentru a obține informații și a lua măsuri cu privire la date. Aduceți date din diverse surse și rulați procesul de unificare a datelor pentru a combina profiluri unificate. Specificați relațiile dintre entitățile ingerate și utilizați funcțiile de îmbogățire pentru a adăuga informații la profiluri.

1. Ingerează date prin crearea de surse de date din mai multe opțiuni. Alege intre [Azure Data Lake Storage, inclusiv modelul comun de date](connect-common-data-model.md),[Azure Synapse Analytics](connect-synapse.md),[Microsoft Dataverse](connect-dataverse-managed-lake.md), sau [Power Query conectori](connect-power-query.md).

1. Rulați [procesul de unificare a datelor](data-unification.md) prin identificarea [câmpurile sursă](map-entities.md), îndepărtând [duplicate](remove-duplicates.md),[condiţii de potrivire](match-entities.md), și [unificarea câmpurilor](merge-entities.md).

1. Familiarizați-vă cu [entități pe care le creează sistemul](entities.md) și creați [relațiile dintre entitățile ingerate](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Pasul 4: îmbunătățiți profilurile unificate cu predicții, activități și măsuri

Cu profilurile unificate configurate, îmbunătățiți-vă datele și creșteți și mai mult informațiile pe care le oferă.

1. Alegeți dintr-o bibliotecă în expansiune de furnizori de îmbogățire pentru a [îmbogăți datele despre clienți](enrichment-hub.md).

1. Utilizați [modele predefinite](predictions-overview.md) pentru a prezice probabilitatea de churn sau veniturile preconizate.

1. [Configurați activitățile](activities.md) pe baza datelor ingerate și vizualizați interacțiunile cu clienții dvs. într-o cronologie cronologică.

1. [Construiți măsuri](measures.md) pentru a vă evalua obiectivele comerciale și KPI-urile.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Pasul 5: creați segmente și activați datele prin diferite opțiuni de export

Acum că datele dvs. sunt complete și conțin o gamă largă de informații despre clienții dvs., căutați modalități de a lua măsuri cu privire la aceste date.

1. [Creați segmente](segments.md), subseturi ale bazei dvs. de clienți, pentru a vă asigura că acțiunile dvs. sunt relevante pentru clienții vizați.

1. Răsfoiți catalogul extins de [opțiuni de export](export-destinations.md) unde puteți utiliza datele clienților. De exemplu, puteți utiliza datele pentru a gestiona promoțiile și pentru a contacta marketingul digital.

1. Examinați opțiunile de integrare, de exemplu cu alte aplicații Dynamics 365 cu [Supliment pentru cardul clientului](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
