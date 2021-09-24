---
title: Începeți să utilizați capacitatea Detalii despre angajamente
description: O prezentare generală a resurselor de ajutor pentru a începe rapid.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 644b125f5d140627d357630ded88dd6838d6edb7
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494609"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Începeți cu capacitate Detalii despre angajamente Dynamics 365 Customer Insights (versiune preliminară publică)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Capacitatea Detalii despre angajamente vă permite să colectați și să măsurați comportamentul clienților pe site-ul dvs. web. Aceasta se integrează cu capacitatea de analiză a publicului, astfel încât să puteți vedea analize comportamentale bogate în timp real, alături de rapoartele de profil ale clienților. Linkurile din acest articol vă ajută să vă configurați și să configurați rapid mediul.

## <a name="step-1-review-prerequisites"></a>Pasul 1: Revizuiți cerințele preliminare

În primul rând, trebuie să aveți un contul activ de utilizator Microsoft Azure Active Directory (AAD). Apoi, citiți articolele următoare înainte de a configura un spațiu de lucru Engagements insights.

- Examinați și acceptați [Termenii serviciului](terms-of-service.md) cu Microsoft.  
- Citiți articolul [Gestionați cookie-urile și consimțământul utilizatorului](user-consent-storage.md). Ulterior, evaluați dacă trebuie să vă actualizați notificarea de consimțământ a utilizatorului. Dacă anterior nu ați avut cookie-uri „neesențiale”, este posibil că va trebui să vă actualizați politica site-ului.
- Examinați [glosar](glossary.md) pentru o introducere rapidă a termenilor și conceptelor cheie.

## <a name="step-2-explore-engagement-insights"></a>Pasul 2: Explorați Detalii despre angajamente

Prima dată când accesați statistici privind publicul, puteți configura setările, revizui politici și explora capabilitatea.

1. Conectați-vă la [portal de capacități de perspectivă de implicare](https://home.ci.ai.dynamics.com/app/engagement-insights) utilizând contul dvs. de utilizator Microsoft AAD (școală sau serviciu).

1. Selectați regiunea și bifați caseta dacă doriți să vă înscrieți pentru a primi actualizări și oferte prin e-mail.

1. Examinați **statistici despre angajament (previzualizare) Condiții de utilizare** și **Declarație de confidențialitate**, apoi selectați **Explorează demonstrația** pentru a accepta aceste setări.

1. Explorați produsul folosind un set de date eșantion.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Pasul 3: Configurați un spațiu de lucru și adăugați cod pe site-ul dvs. web

Un spațiu de lucru este locul în care puteți vizualiza activitatea utilizatorului în timp real și puteți stoca și gestiona rapoarte. Adăugați cod pe site-ul dvs. web pentru a începe colectarea de *evenimente*, datele despre activitate care vin de la utilizatori.

1. [Creați un spațiu de lucru](create-workspace.md) și adăugați membri.

1. [Adăugați cod pe site-ul dvs. web](instrument-website.md) sau [aplicație mobilă](developer-resources.md#capture-events-from-mobile-apps) pentru a vedea activitatea utilizatorului care ajunge în spațiul dvs. de lucru.

1. Vizualizați un [raport în timp real](view-reports.md) care arată utilizatorii activi după browser, dispozitiv, sistem de operare, locație și limbă. De asemenea, puteți crea [rapoarte particularizate](custom-reports.md) pentru a vă crea propriile vizualizări.
    
## <a name="step-4-export-data-to-other-channels"></a>Pasul 4: Exportați date pe alte canale

Puteți crea *evenimente rafinate* (o vizualizare virtuală) a datelor dvs. de analiză web. Apoi filtrați și exportați datele la Azure Data Lake Storage. Puteți ingera datele exportate ca sursă de date. Pentru mai multe informații, consultați [Creați o legătură între detaliile despre public și detalii despre angajament](integrate-audience-insights-engagement-insights.md).

1. [Creați evenimente rafinate](refined-events.md) pentru export.

1. [Exportați datele](export-events.md) la Data Lake Storage.

1. [Creați o legătură între statistici despre public și statistici despre implicare](integrate-audience-insights-engagement-insights.md) pentru a partaja date între cele două capabilități.

1. Aflați cum să [ștergeți și să exportați date despre evenimente care conțin informații personale](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Pasul 5: Să păstrăm legătura

Apreciem participarea dvs. activă și luăm în considerare toate feedback-urile relevante în dezvoltarea viitoarelor versiuni. Distribuiți feedback-ul dvs. și raportați problemele pe unul dintre aceste canale:
- [Comunitate](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Oferiți feedback](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Solicitați asistență](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
