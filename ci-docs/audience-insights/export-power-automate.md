---
title: Conector Power Automate | Microsoft Docs
description: Creați fluxuri în Microsoft Power Automate din Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976103"
---
# <a name="power-automate-connector-preview"></a>Conector Power Automate (previzualizare)

Declanșați evenimente specifice care să aibă loc automat atunci când datele se modifică și gestionați fluxurile mai complexe direct în [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>declanșatoare Power Automate

Utilizați declanșatoarele pentru a crea fluxuri cloud și pentru a automatiza sarcini repetitive, cum ar fi notificări sau acțiuni mai avansate. 

- Se declanșează atunci când o reîmprospătare pentru o sursă de date eșuează. 
- Se declanșează atunci când o reîmprospătare pentru o sursă de date reușește.
- Se declanșează atunci când un prag este trecut pe un segment. Declanșatorul se limitează la trecerea peste prag.
- Se declanșează atunci când un prag este trecut pe o măsură de business. Numai măsurile de business fără o dimensiune sunt acceptate. Declanșatorul se limitează la trecerea peste prag.
- Declanșați când se finalizează o reîmprospătare completă (surse de date, segmente, măsuri,...).
- Se declanșează când este finalizată o reîmprospătare a procesului de unificare (hartă, potrivire, îmbinare).

[Configurați declanșatoarele în Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>acțiuni Power Automate
Conectorul Power Automate oferă alte acțiuni decât declanșatoarele disponibile. Pentru mai multe informaţii, consultaţi [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Creați un flux Power Automate

1. În Detalii despre audiență, accesați **Administrator** > **Destinații export**.

1. Pe dala **Power Automate**, selectați **Configurare**.

1. Se deschide conectorul Customer Insights (previzualizare) în Power Automate. **Conectare** la Power Automate.

1. Alegeți unul dintre declanșatoarele disponibile și adăugați mai mulți pași la noul dvs. flux. Pentru mai multe informații, consultați [Creați un flux pentru cloud în Power Automate](/power-automate/get-started-logic-flow).

Exemple de utilizare a fluxurilor: 
- Postează un mesaj către un canal Microsoft Teams dacă o reîmprospătare sursă de date eșuează. 
- Trimiteți un e-mail proprietarilor de date atunci când este trecut un prag pe un segment.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
