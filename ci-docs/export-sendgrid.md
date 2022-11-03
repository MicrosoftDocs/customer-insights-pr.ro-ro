---
title: Exportați segmente către SendGrid (previzualizare)
description: Aflați cum să configurați conexiunea și să exportați la SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 855e77055eeb24a2c6cff0d45cd23edf93cc0581
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724863"
---
# <a name="export-segments-to-sendgrid-preview"></a>Exportați segmente către SendGrid (previzualizare)

Exportați segmente de profiluri unificate ale clienților în SendGrid și utilizați-le pentru campanii și marketing prin e-mail în SendGrid.

## <a name="prerequisites"></a>Cerințe preliminare

- A [cont SendGrid](https://sendgrid.com/) și acreditările de administrator corespunzătoare.
- [Liste de contacte existente în SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) și ID-urile corespunzătoare.
- A [Cheia API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Segmente configurate](segments.md) în Customer Insights.
- Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Linkul privat în combinație cu Bring your own storage (BYOS) nu este acceptat.
- Până la 100.000 de profiluri de clienți în total pentru SendGrid, care poate dura până la câteva ore. Numărul de profiluri de clienți pe care le puteți exporta în SendGrid depinde de contractul dvs. cu SendGrid.
- Numai segmente.

## <a name="set-up-connection-to-sendgrid"></a>Configurarea conexiunii la SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **SendGrid**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți **Cheia API SendGrid**.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Conectați** pentru a inițializa conexiunea.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea SendGrid. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. Introduceți **ID-ul listei SendGrid**.

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client.

1. Opțional, selectați câmpuri precum **prenume**, **de familie**, **/Regiune**, **·**, **·**, și **Cod poștal**.

1. Selectați segmentele pe care doriți să le exportați urmând limitările cunoscute.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
