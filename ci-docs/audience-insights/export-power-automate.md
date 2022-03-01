---
title: Conector Power Automate | Microsoft Docs
description: Creați fluxuri în Microsoft Power Automate din Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406662"
---
# <a name="power-automate-connector-preview"></a>Conector Power Automate (previzualizare)

Declanșați evenimente specifice care să aibă loc automat atunci când datele se modifică și gestionați fluxurile mai complexe direct în [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>declanșatoare Power Automate

Puteți utiliza o varietate de declanșatoare care vă permit să creați fluxuri pentru a automatiza sarcini repetitive, cum ar fi notificări sau acțiuni mai avansate. 

- Se declanșează atunci când o reîmprospătare pentru o sursă de date eșuează. 
- Se declanșează atunci când o reîmprospătare pentru o sursă de date reușește.
- Se declanșează atunci când un prag este trecut pe un segment. Declanșatorul se limitează la trecerea peste prag.
- Se declanșează atunci când un prag este trecut pe o măsură de business. Declanșatorul se limitează la trecerea peste prag.
- Declanșați când se finalizează o reîmprospătare completă (surse de date, segmente, măsuri,...).
- Se declanșează când este finalizată o reîmprospătare a procesului de unificare (hartă, potrivire, îmbinare).

[Configurați declanșatoarele în Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>acțiuni Power Automate
Conectorul Power Automate oferă alte acțiuni decât declanșatoarele disponibile. Pentru mai multe informaţii, consultaţi [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Creează un flux Power Automate în Detalii despre audiență

1. În Detalii despre audiență, accesați **Administrator** > **Sistem**.

1. Pe pagina **Sistem**, selectați fila **Stare**.

1. În secțiunea **Surse de date**, selectați **Fluxuri** și selectați **Creați un flux** din lista verticală.
   > [!div class="mx-imgBorder"]
   > Conectorul ![Power Automate care arată Crearea unei acțiuni de flux](media/power-automate-connector-create-flow.png "Conectorul Power Automate care arată Crearea unei acțiuni de flux")

1. În Power Automate, selectați unul dintre declanșatorii disponibili pentru a crea fluxul preferat. Când creați primul flux, trebuie să vă autentificați cu mai întâi cu conectorul Power Automate.
