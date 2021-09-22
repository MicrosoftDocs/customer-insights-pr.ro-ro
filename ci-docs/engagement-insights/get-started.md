---
title: Începeți să utilizați capacitatea Detalii despre angajamente
description: O prezentare generală a resurselor de ajutor pentru a începe rapid.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405373"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Începeți cu capacitate Detalii despre angajamente Dynamics 365 Customer Insights (versiune preliminară publică)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Capacitatea Detalii despre angajamente vă permite să colectați și să măsurați comportamentul clienților pe site-ul dvs. web. Aceasta se integrează cu capacitatea de analiză a publicului, astfel încât să puteți vedea analize comportamentale bogate în timp real, alături de rapoartele de profil ale clienților. Linkurile din acest articol vă ajută să vă configurați și să configurați rapid mediul.

## <a name="step-1-review-prerequisites"></a>Pasul 1: Revizuiți cerințele preliminare

În primul rând, trebuie să aveți un contul activ de utilizator Microsoft Azure Active Directory. Apoi, citiți articolele următoare înainte de a configura un spațiu de lucru Engagements insights.

- Examinați și acceptați [Termenii serviciului](terms-of-service.md) cu Microsoft.  
- Citiți articolul [Gestionați cookie-urile și consimțământul utilizatorului](user-consent-storage.md). După citirea acestui articol, evaluați dacă trebuie să vă actualizați notificarea de consimțământ a utilizatorului. Dacă anterior nu ați avut cookie-uri „neesențiale”, este posibil că va trebui să vă actualizați politica site-ului.
- Examinați [glosar](glossary.md) pentru o introducere rapidă a termenilor și conceptelor cheie.

## <a name="step-2-explore-engagement-insights"></a>Pasul 2: Explorați Detalii despre angajamente

Prima dată când vizitați Detalii despre angajamente, puteți configura setări, puteți examina politicile și puteți explora produsul.

1. Conectați-vă la [portalul despre capacitatea Detalii despre angajamente](https://pi.dynamics.com) folosind contul dvs. de utilizator Microsoft Azure Active Directory. (Poate fi contul dvs. de școală sau de muncă.)

1. Selectați regiunea și utilizați caseta de selectare pentru a indica dacă doriți să vă înscrieți pentru a primi actualizări și oferte prin e-mail.

1. Revizuiți **Condiții de utilizare Detalii despre angajamente (versiune preliminară)** și **Angajament de respectare a confidențialității**, apoi selectați **Explorați demonstrația** pentru a le accepta.

1. Explorați produsul folosind un set de date eșantion.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Pasul 3: Configurați un spațiu de lucru și adăugați cod pe site-ul dvs. web

Spațiul de lucru este locul în care puteți vizualiza activitatea utilizatorilor în timp real și puteți stoca și gestiona rapoarte. Adăugați cod pe site-ul dvs. web pentru a începe colectarea de *evenimente*, datele despre activitate care vin de la utilizatori.

1. [Creați un spațiu de lucru](create-workspace.md) și adăugați membri.

1. [Adăugați cod pe site-ul dvs. web](instrument-website.md) sau [aplicație mobilă](developer-resources.md#capture-events-from-mobile-apps) pentru a vedea activitatea utilizatorului care ajunge în spațiul dvs. de lucru.

1. Vizualizați un [raport în timp real](view-reports.md) care afișează utilizatorii activi după browser, dispozitiv, sistem de operare, locație și limbă. De asemenea, puteți crea [rapoarte particularizate](custom-reports.md) pentru a vă crea propriile vizualizări.
    
## <a name="step-4-export-data-to-other-channels"></a>Pasul 4: Exportați date pe alte canale

Puteți crea *evenimente rafinate* (o vizualizare virtuală) a datelor dvs. de analiză web. Apoi filtrați și exportați datele la Azure Data Lake Storage. Puteți ingera datele exportate ca sursă de date. Pentru mai multe informații, consultați [Creați o legătură între detaliile despre public și detalii despre angajament](integrate-audience-insights-engagement-insights.md).

1. [Creați evenimente rafinate](refined-events.md) pentru export.

1. [Exportați datele](export-events.md) la Data Lake Storage.

1. Aflați cum să [ștergeți și să exportați date despre evenimente care conțin informații personale](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Pasul 5: Să păstrăm legătura

Apreciem participarea dvs. activă și intenționăm să luăm în considerare toate feedback-urile relevante în dezvoltarea lansărilor viitoare. Distribuiți feedback-ul dvs. și raportați problemele pe unul dintre aceste canale:
- [Comunitate](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Oferiți feedback](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Solicitați asistență](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
