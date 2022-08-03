---
title: Exportați segmente în Snapchat (previzualizare)
description: Aflați cum să configurați conexiunea și să exportați la Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195397"
---
# <a name="export-segments-to-snapchat-preview"></a>Exportați segmente în Snapchat (previzualizare)

Exportați segmente de profiluri de clienți unificate în Snapchat și folosiți-le pentru publicitate.

## <a name="prerequisites"></a>Cerințe preliminare

- A [Cont Snapchat Business](https://business.snapchat.com/), A [Cont Snapchat Ads](https://ads.snapchat.com/), și acreditările de administrator corespunzătoare. Trebuie să fiți cel puțin membru al unui cont de organizație și administrator de date al unui anumit cont publicitar.
- Cel puțin un public în Snapchat Audience Manager de tip SAM (Snap Audience Match).
- The [Segmentul Snapchat/ID de public](https://businesshelp.snapchat.com/s/article/custom-audiences). ID-ul audienței poate fi găsit în adresa URL după selectarea audienței în Snapchat Audience Manager.
- [Segmente configurate](segments.md) în Customer Insights.
- Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Până la 1 milion de profiluri de clienți, care poate dura până la 15 minute.
- Numai segmente.

## <a name="set-up-connection-to-snapchat"></a>Configurarea conexiunii la Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Snapchat**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Conectați** pentru a inițializa conexiunea.

1. Selectați **Autentificare cu Snapchat** și furnizați acreditările de administrator pentru Snapchat.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Snapchat. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. Introduceți **Segmentul Snapchat/ID de public**.

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client.

1. Selectați segmentele pe care doriți să le exportați.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
