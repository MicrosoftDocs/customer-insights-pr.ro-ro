---
title: Exportați segmente în Criteo (previzualizare)
description: Aflați cum să configurați conexiunea și să exportați în Criteo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d7c8d6f0121fe18a6c886ba3776109a1a592ef33
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195351"
---
# <a name="export-segments-to-criteo-preview"></a>Exportați segmente în Criteo (previzualizare)

Exportați segmente de profiluri de clienți unificate pentru a genera campanii, a oferi marketing prin e-mail și a utiliza anumite grupuri de clienți cu Criteo.

## <a name="prerequisites"></a>Cerințe preliminare

- A [Cont Criteo Dynamics Retargeting](https://www.criteo.com/login/) și acreditările de administrator corespunzătoare.
- [Segmente configurate](segments.md).
- Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Până la 1 milion de profiluri de clienți per export către Criteo, care poate dura până la 30 de minute. Numărul de profiluri de clienți pe care le puteți exporta în Criteo depinde de contractul dvs. cu Criteo.
- Numai segmente.

## <a name="set-up-connection-to-criteo"></a>Configurați conexiunea la Criteo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Criteo**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Conectați** pentru a inițializa conexiunea.

1. Selectați **Autentificați-vă cu Criteo** și furnizați numele de utilizator și acreditările dvs. de administrator pentru Criteo.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În **Conexiune pentru export** câmp, alegeți o conexiune din secțiunea Criteo. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client.

1. Opțional, exportați **ID agent de publicitate** și **Nume**.

1. Selectați segmentele pe care doriți să le exportați.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
