---
title: Exportați segmente în MoEngage
description: Aflați cum să configurați conexiunea și să exportați în MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: df38e9e88a9c116252fba26983b5f3711b46f051
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725281"
---
# <a name="export-segments-to-moengage-preview"></a>Exportați segmente în MoEngage (previzualizare)

Exportați segmente de profiluri de clienți unificate în MoEngage și utilizați-le pentru marketing prin e-mail în MoEngage.

## <a name="prerequisites-for-a-connection"></a>Cerințe preliminare pentru o conexiune

- [cont MoEngage](https://www.moengage.com/) și acreditările de administrator corespunzătoare.
- Cheia API MoEngage din Setări > API din MoEngage.
- [Segmente configurate](segments.md) în Customer Insights.

## <a name="known-limitations"></a>Limitări cunoscute

- Linkul privat în combinație cu Bring your own storage (BYOS) nu este acceptat.
- Până la 100.000 de profiluri de clienți per export către MoEngage, ceea ce poate dura până la 15 minute. Numărul de profiluri de clienți pe care le puteți exporta în MoEngage depinde de contractul dvs. cu MoEngage.
- Numai segmente.

## <a name="set-up-connection-to-moengage"></a>Configurați conexiunea la MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **MoEngage** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți [ID-ul API MoEngage Data și cheia API](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Conectați** pentru a inițializa conexiunea la MoEngage.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare export**.

1. În **Conexiune pentru export** câmp, alegeți o conexiune din secțiunea MoEngage. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client. Repetați aceiași pași pentru alte câmpuri opționale.

1. Selectați segmentele pe care doriți să le exportați. Vom crea unul sau mai multe segmente cu același nume ca și segmentele selectate în MoEngage sub **Segmente** > **Segmente personalizate**.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
