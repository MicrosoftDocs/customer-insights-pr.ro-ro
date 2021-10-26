---
title: Începeți să utilizați capacitatea Detalii despre angajamente
description: O prezentare generală a resurselor de ajutor pentru a începe rapid.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3505c15c4319c8cc8823bcd89d3b8adc944a87dd
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623692"
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

1. Revizuiți detaliile de angajament (versiune preliminară) **Termeni și condiții** și **Declarație de confidențialitate** și apoi selectați **Explorați demonstrația** pentru a accepta aceste setări.

1. Explorați produsul folosind un set de date eșantion.

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>Pasul 3: configurați un spațiu de lucru și creați rapoarte

Un spațiu de lucru este locul în care puteți vizualiza activitatea utilizatorului în timp real și puteți stoca și gestiona rapoarte. Adăugați cod pe site-ul dvs. web pentru a începe colectarea de *evenimente*, datele despre activitate care vin de la utilizatori.

1. [Creați un spațiu de lucru](create-workspace.md) și adăugați membri.

1. Adăugați codul la [site-ul dvs. web](instrument-website.md) sau [aplicație mobilă](developer-resources.md#capture-events-from-mobile-apps) pentru a vedea activitatea utilizatorului care ajunge în spațiul dvs. de lucru.

1. Vizualizați un [raport în timp real](view-reports.md) care arată utilizatorii activi după browser, dispozitiv, sistem de operare, locație și limbă. De asemenea, puteți crea [rapoarte particularizate](custom-reports.md) pentru a vă crea propriile vizualizări.

1. Creați [dimensiuni](dimensions.md) pentru a sorta vizitatorii după utilizatorii noi și recenți, [măsurători](metrics.md) pentru a ajuta la înțelegerea mai bună a comportamentului utilizatorilor și [segmente](segments.md) pentru a identifica subseturi de vizitatori pe baza caracteristicilor sau interacțiunilor site-ului web.
    
## <a name="step-4-export-data-to-other-channels"></a>Pasul 4: Exportați date pe alte canale

Puteți crea *evenimente rafinate* (o vizualizare virtuală) a datelor dvs. de analiză web. Apoi filtrați și exportați datele la Azure Data Lake Storage. Puteți ingera datele exportate ca sursă de date.

1. [Creați evenimente rafinate](refined-events.md) pentru export.

1. [Exportați datele](export-events.md) la Azure Data Lake Storage.

1. [Creați o legătură între statistici despre public și statistici despre implicare](integrate-audience-insights-engagement-insights.md) pentru a partaja date între cele două capabilități.

1. [Recunoașteți evenimentele web de la utilizatori autentificați anterior](unknown-to-known.md) cu caracteristica **necunoscut la cunoscut**.

1. Aflați cum să [ștergeți și să exportați date despre evenimente care conțin informații personale](delete-export-personal-data.md).

## <a name="step-5-create-and-manage-funnel-reports"></a>Pasul 5: creați și gestionați rapoarte de canalizare

Un raport pâlnie colectează informații despre pașii care apar în timpul unui călătoria clientului prin site-ul dvs. web sau aplicația mobilă. Pe lângă crearea de rapoarte de profil și rapoarte personalizate, puteți crea un raport de canal pentru a identifica căile pe care le parcurg clienții dvs. înainte de a face o achiziție. 

1. [Creați un raport pâlnie](funnel-reports.md) pentru a informa deciziile și să identifice domeniile de optimizare și îmbunătățiri ale proceselor.

1. Creați rapoarte de pâlnie pe mai multe canale, după ce ați instrumentat aplicația mobilă cu ajutorul detaliilor de angajament [Android SDK](get-started-android.md) sau [SDK iOS](get-started-ios.md).

1. Utilizați [detalii despre pâlnie](funnel-reports.md#funnel-insights) pentru a obține detalii mai amănunțite despre comportamentul clientului cu privire la pașii din raportul de pâlnie.
 
## <a name="step-6-stay-connected"></a>Pasul 6: Să păstrăm legătura

Apreciem participarea dvs. activă și luăm în considerare toate feedback-urile relevante în dezvoltarea viitoarelor versiuni. Distribuiți feedback-ul dvs. și raportați problemele pe unul dintre aceste canale:
- [Comunitate](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Oferiți feedback](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Solicitați asistență](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
