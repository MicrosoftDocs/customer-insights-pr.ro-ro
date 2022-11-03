---
title: Exportați segmente în Monitor de campanie (previzualizare)
description: Aflați cum să configurați conexiunea și exportul la Monitor de campanie.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 82303c7bcb269ee68419c9639ee743e13451f273
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724699"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Exportați segmente în Monitor de campanie (previzualizare)

Exportați segmente de profiluri de clienți unificate în Monitor de campanie și folosiți-le pentru activități de marketing.

## <a name="prerequisites"></a>Cerințe preliminare

- A [cont Campaign Monitor](https://www.campaignmonitor.com/) și acreditările de administrator corespunzătoare.
- A [ID-ul listei de monitorizare a campaniei](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- A [Cheie API generată](https://www.campaignmonitor.com/api/getting-started/) din **Setările contului** în Campaign Monitor pentru a obține ID-ul listei API.
- [Segmente configurate](segments.md) în Customer Insights.
- Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Linkul privat în combinație cu Bring your own storage (BYOS) nu este acceptat.
- Până la 1 milion de profiluri de clienți per export către Campaign Monitor, care poate dura până la 20 de minute. Numărul de profiluri de clienți pe care le puteți exporta în Campaign Monitor depinde de contractul dvs. cu Campaign Monitor.
- Numai segmente.

## <a name="set-up-connection-to-campaign-monitor"></a>Configurați conexiunea la Monitor de campanie

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Monitor campanie**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Conectați** pentru a inițializa conexiunea la Monitor de campanie.

1. Selectați **Autentificare cu Monitor de campanie** și furnizați acreditările de administrator pentru Monitor de campanie.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Monitor de campanie. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. Introduceți **ID-ul listei de monitorizare a campaniei**.

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client. Este necesar să exportați segmente către Monitor de campanie.

1. Selectați segmentele pe care doriți să le exportați.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
