---
title: Exportați segmente în Microsoft Advertising (previzualizare)
description: Aflați cum să configurați conexiunea și exportul la Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196547"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Exportați segmente în Microsoft Advertising (previzualizare)

Exportați segmentele Customer Insights în Microsoft Advertising pentru a crea segmente de public Matched Audiences. Utilizați aceste segmente de public pentru campaniile dvs. publicitare.

## <a name="prerequisites"></a>Cerințe preliminare

- A [Cont Microsoft Advertising](https://ads.microsoft.com/) și acreditările de administrator corespunzătoare.
- ID-ul de client și ID-ul contului Microsoft Advertising. Găsiți ID-ul clientului (`cid`) și ID contului (`aid`) în parametrii adresei URL atunci când sunteți conectat la Microsoft Advertising.
- Termenii de utilizare pentru potrivirea clienților sunt acceptați.
- [Segmente configurate](segments.md) în Customer Insights.
- Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Până la 500.000 de profiluri de clienți per export către Microsoft Advertising, ceea ce poate dura până la 10 minute.
- Numai segmente.

## <a name="set-up-connection-to-microsoft-advertising"></a>Configurați conexiunea la Microsoft Advertising

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Microsoft Advertising**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit sunt administratorii. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți **ID de client Microsoft Advertising**.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Conectați** pentru a inițializa conexiunea.

1. Selectați **Autentificare cu Microsoft Advertising** și furnizați acreditările de administrator pentru Microsoft Advertising.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Microsoft Advertising. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. Selectați segmentele pentru export. Audiențele de potrivire după clienți din Microsoft Advertising sunt create automat cu numele segmentelor selectate pentru export. Fiecare segment va avea ca rezultat un public separat Matched audience.

1. Introduceți **ID client Microsoft Advertising și ID cont**.

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul cu adresa de e-mail a unui client.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
