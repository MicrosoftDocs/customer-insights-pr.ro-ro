---
title: Exportați segmente în Klaviyo (previzualizare)
description: Aflați cum să configurați conexiunea și să exportați către Klaviyo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 075e6758f2c6992a1185756f9beecf852fdd0a96
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724648"
---
# <a name="export-segments-to-klaviyo-preview"></a>Exportați segmente în Klaviyo (previzualizare)

Exportați segmente de profiluri unificate ale clienților în Klaviyo și folosiți-le pentru activități de marketing.

## <a name="prerequisites"></a>Cerințe preliminare

- A [contul Klaviyo](https://www.klaviyo.com/) și acreditările de administrator corespunzătoare.
- A [Cheia API Klaviyo](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys).
- A [ID-ul listei Klaviyo](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).
- [Segmente configurate](segments.md) în Customer Insights.
- Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Linkul privat în combinație cu Bring your own storage (BYOS) nu este acceptat.
- Până la 1 milion de profiluri de clienți per export către Klaviyo, care poate dura până la 20 de minute. Numărul de profiluri de clienți pe care le puteți exporta în Klaviyo depinde de contractul dvs. cu Klaviyo.
- Numai segmente.

## <a name="set-up-connection-to-klaviyo"></a>Configurați conexiunea la Klaviyo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Klaviyo**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Furnizați Cheia API Klaviyo pentru a continua conectarea.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Conectați** pentru a inițializa conexiunea.

1. Selectați **Autentificați-vă cu Klaviyo** și furnizați acreditările de administrator pentru Klaviyo.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Klaviyo. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. Introduceți **ID-ul listei Klaviyo**.

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client.

1. Selectați segmentele pe care doriți să le exportați.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
