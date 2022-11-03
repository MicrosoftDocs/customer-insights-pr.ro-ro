---
title: Exportați segmente în DotDigital (previzualizare)
description: Aflați cum să configurați conexiunea și să exportați la DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f3e3378dce9177c6645b91140884ae135540243
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725001"
---
# <a name="export-segments-to-dotdigital-preview"></a>Exportați segmente în DotDigital (previzualizare)

Exportați segmente de profiluri de clienți unificate în agende DotDigital și folosiți-le pentru campanii, marketing prin e-mail și pentru a crea segmente de clienți cu DotDigital.

## <a name="prerequisites"></a>Cerințe preliminare

- A [cont DotDigital](https://dotdigital.com/) si un [utilizator API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- Un ID DotDigital de la a [nou](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) sau agenda existentă în DotDigital. ID-ul poate fi găsit în adresa URL atunci când selectați și deschideți o agendă.
- [Segmente configurate](segments.md) în Customer Insights.
- Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Linkul privat în combinație cu Bring your own storage (BYOS) nu este acceptat.
- Până la 1 milion de profiluri de clienți per export către DotDigital, care poate dura până la trei ore pentru a finaliza din cauza limitărilor din partea furnizorului. Numărul de profiluri de clienți pe care le puteți exporta în DotDigital depinde de contractul dvs. cu DotDigital.
- Numai segmente.

## <a name="set-up-connection-to-dotdigital"></a>Configurarea conexiunii la DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **DotDigital**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți **numele de utilizator API și parola DotDigital**.

1. Introduceți **ID-ul agendei DotDigital**.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Conectați** pentru a inițializa conexiunea.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea DotDigital. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client.

1. Opțional, exportați **prenume**, **de familie**, **complet**, **·**, și **Cod poștal**.

1. Selectați segmentele pe care doriți să le exportați.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

În DotDigital, găsiți-vă segmentele în [Agende DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
