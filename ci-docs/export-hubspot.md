---
title: Exportați datele despre Customer Insights în HubSpot
description: Aflați cum să configurați conexiunea și să exportați în HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588935"
---
# <a name="export-segments-to-hubspot-preview"></a>Exportați segmente în HubSpot (previzualizare)

Exportați segmente de profiluri de clienți unificate în HubSpot și utilizați-le pentru marketing prin e-mail.

## <a name="prerequisites-for-a-connection"></a>Cerințe preliminare pentru o conexiune

- A [cont HubSpot](https://www.hubspot.com/) și acreditările de administrator corespunzătoare.
- [cheie API](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) de la HubSpot.
- [Segmente configurate](segments.md) în Customer Insights.

## <a name="known-limitations"></a>Limitări cunoscute

- Până la 100.000 de profiluri de clienți per export către HubSpot, care poate dura până la 15 minute. Numărul de profiluri de clienți pe care le puteți exporta în HubSpot depinde și este limitat de contractul dvs. cu HubSpot.
- Numai segmente.

## <a name="set-up-connection-to-hubspot"></a>Configurați conexiunea la HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **HubSpot** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți acreditările HubSpot când vi se solicită.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Conectați** pentru a inițializa conexiunea la HubSpot.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare export**.

1. În **Conexiune pentru export** câmp, alegeți o conexiune din secțiunea HubSpot. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client. Repetați aceiași pași pentru alte câmpuri opționale.

1. Selectați segmentele pe care doriți să le exportați.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
