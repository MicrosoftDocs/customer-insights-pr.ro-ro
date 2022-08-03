---
title: Power Automate conector (previzualizare) | Microsoft Docs
description: Creați fluxuri în Microsoft Power Automate din Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196133"
---
# <a name="power-automate-connector-preview"></a>Conector Power Automate (previzualizare)

Declanșați evenimente specifice care să aibă loc automat atunci când datele se modifică și gestionați fluxurile mai complexe direct în [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Limitări cunoscute

- Maximum 100 de apeluri pe 60 de secunde. Folosește [parametru $skip](/connectors/customerinsights/#get-items-from-an-entity) pentru a apela punctul final API de mai multe ori.

## <a name="power-automate-triggers"></a>declanșatoare Power Automate

Utilizați declanșatoarele pentru a crea fluxuri cloud și pentru a automatiza sarcini repetitive, cum ar fi notificări sau acțiuni mai avansate. Utilizați declanșatorii atunci când:

- O reîmprospătare sursă de date eșuează.
- O reîmprospătare sursă de date reușește.
- Se trece un prag pe un segment. Declanșatorul se limitează la trecerea peste prag.
- Este depășit un prag pentru o măsură de afaceri. Numai măsurile de business fără o dimensiune sunt acceptate. Declanșatorul se limitează la trecerea peste prag.
- O reîmprospătare programată completă este finalizată. Acest declanșator nu funcționează pentru reîmprospătările pornite manual.
- O reîmprospătare a procesului de unificare este finalizată.

[Configurați declanșatoarele în Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>acțiuni Power Automate

Conectorul Power Automate oferă alte acțiuni decât declanșatoarele disponibile. Pentru mai multe informaţii, consultaţi [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Creați un flux Power Automate

1. Salt la **Administrator** > **Conexiuni**.

1. Pe dala **Power Automate**, selectați **Configurare**.

1. Se deschide conectorul Customer Insights (previzualizare) în Power Automate. **Conectare** la Power Automate.

1. Alegeți unul dintre declanșatoarele disponibile și adăugați mai mulți pași la noul dvs. flux. Pentru mai multe informații, consultați [Creați un flux pentru cloud în Power Automate](/power-automate/get-started-logic-flow).

Exemple de utilizare a fluxurilor: 
- Postează un mesaj către un canal Microsoft Teams dacă o reîmprospătare sursă de date eșuează. 
- Trimiteți un e-mail proprietarilor de date atunci când este trecut un prag pe un segment.

[!INCLUDE [footer-include](includes/footer-banner.md)]
