---
title: Lucrul cu conturi de business
description: Aflați despre conturile de afaceri ca public țintă principal în Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: abb77a720ab737520a905b0c93b65573e669109f
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303931"
---
# <a name="work-with-business-accounts"></a>Lucrul cu conturi de business

The Dynamics 365 Customer Insights vă permite să vă configurați mediul pentru diferite audiențe țintă primare: consumatori individuali (B-to-C) și conturi de afaceri (B-to-B). În scenariile B la C, datele sunt centrate în jurul persoanelor. Pentru scenarii B la B, principalele segmente de public vizate sunt conturile - organizații sau companii - și contactele. Acest articol vă ajută să începeți cu un mediu pentru conturile de afaceri. Listează diferențele pentru zonele caracteristice din Customer Insights, în funcție de concentrarea asupra mediului. Pentru mai multe informații despre diferențe, consultați documentele din zonele de caracteristici. 

## <a name="create-an-environment-for-business-accounts"></a>Creați un mediu pentru conturi de business

Administratorii pot [crea un mediu într-o organizație existentă](create-environment.md). Un pas în procesul de creare a unui mediu nou solicită administratorilor publicul țintă principal al mediului. În cazul în care este configurarea inițială după achiziționarea unei licențe, o experiență ghidată ajută la crearea primului mediu.

Apoi puteți [ingera date](data-sources.md) pentru conturi de business și contacte conexe ca surse de date din toate sursele acceptate.

 [Unifica](data-unification.md) datele contului dvs. urmate de datele dvs. de contact pentru a conecta contactul și entitățile de cont.

## <a name="switch-between-primary-target-audience"></a>Comutați între publicul țintă principal

Dacă organizația dvs. menține medii pentru clienți individuali și conturi de afaceri, puteți utiliza comutatorul din panoul din stânga pentru a alege publicul țintă principal.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Comutator pentru a schimba publicul țintă principal între clienții individuali și conturile de business.":::

## <a name="supported-feature-areas"></a>Zone cu caracteristică acceptată

- [Activități](activities.md): Asistență pentru conturi și contacte conexe pentru a crea activități și a le arăta într-o cronologie.
- [Relații](relationships.md): Expertul pentru activități vă ajută să creați relații între entități, astfel încât vizualizarea contului poate afișa toate activitățile din contacte. Persoanele de contact se pot detalia pentru a vedea vizualizarea de contact, iar ierarhiile pot fi utilizate pentru agregările activității contului.
- [Măsuri](measures.md): Acceptă măsurile create din generatorul de măsuri cu un singur calcul. O setare opțională permite completarea pentru conturi secundare atunci când se creează măsuri.
- [Segmente](segments.md): Acceptă segmente create de la zero cu ajutorul constructorului de segmente. Segmentele pot fi bazate pe conturi sau contacte.
- [Ingerarea datelor](data-sources.md): Toate funcțiile din acest domeniu sunt identice pentru conturile de afaceri și pentru clienții individuali.
- Unificarea datelor B-to-B este foarte similară cu unificarea datelor B-to-C, dar are un pas suplimentar pentru unificarea contactelor după unificarea contului. Vedea [Conturi de afaceri (B-to-B)](data-unification.md).
- [Îmbogăţire](enrichment-hub.md): Unele tipuri de îmbogățire sunt disponibile numai pentru scenarii individuale ale clienților, în timp ce altele sunt disponibile exclusiv pentru conturile de afaceri.
- [Predicții și modele predefinite](predictions-overview.md): Predicția de retragere tranzacțională conține pași suplimentari pentru conturile de afaceri. Alte predicții sunt disponibile numai pentru clienții individuali.
- [Activare și export](export-destinations.md): Exporturile sunt disponibile pentru conturi de afaceri și clienți individuali. Unele exporturi necesită configurații suplimentare și informații de contact proiectate în segmentele subiacente pentru a fi valabile pentru conturile de afaceri.
- [Setări de sistem](system.md) și [gestionare utilizator](permissions.md): toate caracteristicile din această zonă sunt aceleași pentru conturile de business și pentru clienții individuali.

[!INCLUDE [footer-include](includes/footer-banner.md)]
