---
title: Conector Power Automate | Microsoft Docs
description: Creați fluxuri în Microsoft Power Automate din Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268839"
---
# <a name="power-automate-connector-preview"></a>Conector Power Automate (previzualizare)

Declanșați evenimente specifice care să aibă loc automat atunci când datele se modifică și gestionați fluxurile mai complexe direct în [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>declanșatoare Power Automate

Utilizați declanșatoarele pentru a crea fluxuri cloud și pentru a automatiza sarcini repetitive, cum ar fi notificări sau acțiuni mai avansate. 

- Se declanșează atunci când o reîmprospătare pentru o sursă de date eșuează. 
- Se declanșează atunci când o reîmprospătare pentru o sursă de date reușește.
- Se declanșează atunci când un prag este trecut pe un segment. Declanșatorul se limitează la trecerea peste prag.
- Se declanșează atunci când un prag este trecut pe o măsură de business. Declanșatorul se limitează la trecerea peste prag.
- Declanșați când se finalizează o reîmprospătare completă (surse de date, segmente, măsuri,...).
- Se declanșează când este finalizată o reîmprospătare a procesului de unificare (hartă, potrivire, îmbinare).

[Configurați declanșatoarele în Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>acțiuni Power Automate
Conectorul Power Automate oferă alte acțiuni decât declanșatoarele disponibile. Pentru mai multe informaţii, consultaţi [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Creați un flux Power Automate

1. În Detalii despre audiență, accesați **Administrator** > **Destinații export**.

1. Pe dala **Power Automate**, selectați **Configurare**.

1. Se deschide conectorul Customer Insights (previzualizare) în Power Automate. **Conectare** la Power Automate.

1. Alegeți unul dintre declanșatoarele disponibile și adăugați mai mulți pași la noul dvs. flux. Pentru mai multe informații, consultați [Creați un flux pentru cloud în Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).

Exemple de utilizare a fluxurilor: 
- Postează un mesaj către un canal Microsoft Teams dacă o reîmprospătare sursă de date eșuează. 
- Trimiteți un e-mail proprietarilor de date atunci când este trecut un prag pe un segment.



[!INCLUDE[footer-include](../includes/footer-banner.md)]