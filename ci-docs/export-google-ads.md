---
title: Exportați segmente în Google Ads (previzualizare)
description: Aflați cum să configurați conexiunea și să exportați la Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a46623e609665f8031f223593a6644147e5209d8
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725093"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportați segmente în Google Ads (previzualizare)

Exportați segmente de profiluri de clienți unificate într-o listă de public pentru Google Ads și folosiți-le pentru a face publicitate în Căutarea Google, Gmail, YouTube și Google Display Network.

## <a name="prerequisites"></a>Cerințe preliminare

- A [cont Google Ads](https://ads.google.com/) și acreditările de administrator corespunzătoare.
- A [ID de client Google Ads](https://support.google.com/google-ads/answer/1704344).
- Cerințele de [Politica de potrivire după clienți](https://support.google.com/adspolicy/answer/6299717) sunt întâlniți.
- Cerințele de [dimensiunile listelor de remarketing](https://support.google.com/google-ads/answer/7558048) sunt întâlniți.
- [Segmente configurate](segments.md).
- Profilurile unificate ale clienților din segmentele exportate conțin câmpuri care reprezintă o adresă de e-mail, un telefon, un ID de agent de publicitate mobil, un ID de utilizator terță parte sau o adresă.

## <a name="known-limitations"></a>Limitări cunoscute

- Linkul privat în combinație cu Bring your own storage (BYOS) nu este acceptat.
- Exportați până la 1 milion de profiluri de clienți per export în Google Ads, care poate dura până la 30 de minute din cauza limitărilor din partea furnizorului.
- Numai segmente.
- Potrivirea în Google Ads poate dura până la 48 de ore.

## <a name="set-up-connection-to-google-ads"></a>Configurarea conexiunii la Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Google Ads**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți codul dvs. de client Google Ads.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Autentificare cu Google Ads** și furnizați acreditările dvs. Google Ads.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Google Ads. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. Alegeți dacă doriți să utilizați un public existent sau să creați unul nou:
   - Pentru a actualiza un public Google Ads existent, introduceți dvs [ID de public Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - Pentru a crea un public nou, lăsați necompletat câmpul Google Audience ID. Customer Insights va crea automat un nou public în contul dvs. Google Ads și va folosi numele segmentului exportat.

1. În **Potrivirea datelor** secțiunea, selectați unul sau mai multe câmpuri de date de exportat și selectați câmpul care reprezintă câmpurile de date corespunzătoare în Customer Insights.

1. Selectați segmentele pe care doriți să le exportați.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
