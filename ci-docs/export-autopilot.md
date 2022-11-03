---
title: Exportați segmente către Autopilot (previzualizare)
description: Aflați cum să configurați conexiunea și să exportați la Autopilot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b4b14ba9de2c7e20175fac664a705f2212a411fd
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724772"
---
# <a name="export-segments-to-autopilot-preview"></a>Exportați segmente către Autopilot (previzualizare)

Exportați segmente de profiluri unificate ale clienților în Autopilot și utilizați-le pentru marketing prin e-mail în Autopilot.

## <a name="prerequisites-for-a-connection"></a>Cerințe preliminare pentru o conexiune

- Un [Cont de pilot automat](https://www.autopilothq.com/) și acreditările de administrator corespunzătoare.
- Un [Cheie API Autopilot](https://autopilot.docs.apiary.io/#)
- [Segmente configurate](segments.md) în Customer Insights.
- Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Linkul privat în combinație cu Bring your own storage (BYOS) nu este acceptat.
- Până la 100.000 de profiluri de clienți per export în Autopilot, care poate dura până la câteva ore. Numărul de profiluri de clienți pe care le puteți exporta în Autopilot depinde de contractul dvs. cu Autopilot.
- Numai segmente.

## <a name="set-up-connection-to-autopilot"></a>Configurarea conexiunii la Autopilot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Pilot automat**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți Cheie API Autopilot.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Conectați** pentru a inițializa conexiunea.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Autopilot. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client.

1. Opțional, exportați alte câmpuri, cum ar fi **prenume** și **nume de familie**.

1. Selectați segmentele pe care doriți să le exportați respectând limitările cunoscute.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
