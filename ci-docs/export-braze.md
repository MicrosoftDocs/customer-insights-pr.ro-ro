---
title: Exportați segmente în Braze (previzualizare)
description: Aflați cum să configurați conexiunea și să exportați în Braze.
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 2f52eb8196e057f934c8d2b5ac0518ce121606b6
ms.sourcegitcommit: 003c1929f730d7d505c108aba84f6269f4c98978
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/12/2022
ms.locfileid: "9655303"
---
# <a name="export-segments-to-braze-preview"></a>Exportați segmente în Braze (previzualizare)

Exportați segmente de profiluri de clienți unificate în Braze și utilizați-le pentru activități de marketing.

## <a name="prerequisites"></a>Cerințe preliminare

- A [cont Braze](https://www.braze.com/) și acreditările de administrator corespunzătoare.
- A [Cheia API Braze](https://www.braze.com/docs/api/basics/)
- Ta [Braze REST Endpoint](https://www.braze.com/docs/api/basics/#api-definitions) 
- [Segmente configurate](segments.md) în Customer Insights.
- Profilurile unificate ale clienților din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail și un ID de client Braze.

## <a name="known-limitations"></a>Limitări cunoscute

- Până la 1 milion de profiluri de clienți pentru Braze, care poate dura până la 40 de minute. Numărul de profiluri de clienți pe care le puteți exporta în Braze depinde de contractul dvs. cu Braze.
- Numai segmente.
- Azure Private Link nu este acceptat pentru exportul Braze.

## <a name="set-up-connection-to-braze"></a>Configurați conexiunea la Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Braze**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Furnizați cheia API Braze pentru a continua să vă conectați.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Conectați** pentru a inițializa conexiunea.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În **Conexiune pentru export** câmp, alegeți o conexiune din secțiunea Braze. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți punctul final REST în **Nume gazdă** câmp în următorul format:`rest.iad-03.braze.com`.

1. Introduceți un nume pentru export.

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client. În **Număr de înregistrare client** câmp, selectați câmpul care reprezintă ID-ul Braze al clientului. Segmentele din Braze vor fi create cu același nume al segmentului ca în Dynamics 365 Customer Insights. Puteți alege mai multe câmpuri opționale pentru datele de potrivire.

1. Selectați entitățile sau segmentele pe care doriți să le exportați.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
