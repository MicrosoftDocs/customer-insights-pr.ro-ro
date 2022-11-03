---
title: Exportați segmente în ActiveCampaign
description: Aflați cum să configurați conexiunea și să exportați către ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e62888a6d618fb1154890e607d8c23d3767d35f7
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725415"
---
# <a name="export-segments-to-activecampaign-preview"></a>Exportați segmente în ActiveCampaign (previzualizare)

Exportați segmente de profiluri unificate ale clienților în ActiveCampaign și folosiți-le pentru activități de marketing.

## <a name="prerequisites"></a>Cerințe preliminare

- Un [cont ActiveCampaign](https://www.activecampaign.com/) și acreditările de administrator corespunzătoare.
- Un [ID-ul listei ActiveCampaign](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- Un [Cheia API ActiveCampaign](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) și REST Endpoint Hostname.
- [Segmente configurate](segments.md) în Customer Insights.
- Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Linkul privat în combinație cu Bring your own storage (BYOS) nu este acceptat.
- Până la 1 milion de profiluri de clienți per export către ActiveCampaign, care poate dura până la 90 de minute. Numărul de profiluri de clienți pe care le puteți exporta în ActiveCampaign depinde de contractul dvs. cu ActiveCampaign.
- Numai segmente.

## <a name="set-up-connection-to-activecampaign"></a>Configurați conexiunea la ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **ActiveCampaign**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți Cheia API ActiveCampaign și REST Endpoint Hostname. Numele de gazdă REST Endpoint este doar numele gazdei, fără https://.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Conectați** pentru a inițializa conexiunea.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea ActiveCampaign. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. Introduceți **ID-ul listei ActiveCampaign**.

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client.

1. Opțional, exportați **prenume**, **de familie**, și **Telefon** pentru a crea e-mailuri mai personalizate. Selectați **Adăugare atribut** pentru a mapa aceste câmpuri.

1. Selectați segmentele pe care doriți să le exportați.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
