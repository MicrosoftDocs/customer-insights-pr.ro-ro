---
title: Exportați segmente în Anunțuri LinkedIn (previzualizare)
description: Aflați cum să configurați conexiunea și să exportați la Anunțuri LinkedIn.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d1a9ae985043398f4bc38163be26ecf0c3c8e2ba
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196823"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Exportați segmente în Anunțuri LinkedIn (previzualizare)

Exportați segmente de profiluri de clienți unificate în Anunțuri LinkedIn pentru a crea segmente Matched Audiences. Utilizați segmentele de Matched Audiences pentru direcționarea către companii și direcționarea prin contact.

## <a name="prerequisites"></a>Cerințe preliminare

- A [LinkedIn Campaign Manager cont](https://business.linkedin.com/marketing-solutions/ads) și acreditările de administrator corespunzătoare.
- A [LinkedIn Campaign Manager Cont ID](https://www.linkedin.com/help/lms/answer/a424270).
- [Segmente configurate](segments.md) în Customer Insights.
- Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Până la 100.000 de profiluri de clienți per export către LinkedIn Ads, care poate dura până la 10 minute.
- Numai segmente. Un segment trebuie să conțină cel puțin 300 de profiluri unice.

## <a name="set-up-connection-to-linkedin-ads"></a>Configurați conexiunea la LinkedIn Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Reclame LinkedIn**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Furnizați-vă LinkedIn Campaign Manager Cont ID.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Conectați** pentru a inițializa conexiunea.

1. Selectați **Autentificare cu LinkedIn** și furnizați acreditările de administrator pentru LinkedIn Campaign Manager.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea LinkedIn. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. Alegeți dacă doriți să exportați date pentru a face [direcționarea prin contact](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) sau [direcționarea către companii](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) pe LinkedIn.

1. În secțiunea **Potrivirea datelor**, pentru direcționarea prin contact, selectați cel puțin un câmp care reprezintă adresa de e-mail a unui client, Apple Ad ID, Google Ad ID, Google User ID sau nume și prenume. Dacă alegeți direcționarea în funcție de companie, selectați cel puțin un câmp care să reprezinte numele companiei, domeniul de e-mail, adresa URL a paginii LinkedIn, simbolul stocului sau site-ul web.

1. Opțional, adăugați câmpuri pentru a defini în continuare exportul. Selectați **Adăugare atribut** pentru a mapa aceste câmpuri.

1. Selectați segmentele pe care doriți să le exportați. Publicul potrivit Matched audiences din LinkedIn Campaign Manager va fi creat automat cu numele segmentelor pe care le-ați selectat pentru export. Fiecare segment va avea ca rezultat un public separat Matched audience.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
