---
title: Exportați segmente în RollWorks (previzualizare)
description: Aflați cum să configurați conexiunea și să exportați la RollWorks.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d857bf5d11de86521c4a9d4fc665c020496d89d2
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725140"
---
# <a name="export-segments-to-rollworks-preview"></a>Exportați segmente în RollWorks (previzualizare)

Exportați segmente de profiluri de clienți unificate în RollWorks și folosiți-le pentru publicitate.

## <a name="prerequisites"></a>Cerințe preliminare

- A [cont RollWorks](https://www.rollworks.com/) și acreditările de administrator corespunzătoare.
- A [ID-ul agentului de publicitate RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Segmente configurate](segments.md) în Customer Insights.
- Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Linkul privat în combinație cu Bring your own storage (BYOS) nu este acceptat.
- Până la 250.000 de profiluri de clienți pentru fiecare export către RollWorks, care poate dura până la 10 minute. Numărul de profiluri de clienți pe care le puteți exporta în RollWorks depinde de contractul dvs. cu RollWorks.
- Numai segmente.

## <a name="set-up-connection-to-rollworks"></a>Configurarea conexiunii la RollWorks

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **RollWorks**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune.  În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Conectați** pentru a inițializa conexiunea.

1. Selectați **Autentificare cu RollWorks** și furnizați acreditările de administrator pentru RollWorks.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea RollWorks. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. Introduceți **ID-ul agentului de publicitate RollWorks**.

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client.

1. Selectați segmentele pe care doriți să le exportați.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
