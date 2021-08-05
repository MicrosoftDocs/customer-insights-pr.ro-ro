---
title: Exportați datele Customer Insights către Dynamics 365 Marketing
description: Aflați cum să configurați conexiunea și să exportați la Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bd8189f8daee1a6aea75e75e116186f62a360ba4
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692496"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Utilizarea segmentelor în Dynamics 365 Marketing (previzualizare)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Utilizați [segmentele](segments.md) pentru a genera campanii și a contacta anumite grupuri de clienți cu Dynamics 365 Marketing. Pentru mai multe informații, consultați [Utilizați segmente din Dynamics 365 Customer Insights cu Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite-for-a-connection"></a>Cerință preliminară pentru o conexiune

- Înregistrările de contact trebuie să fie prezente în Dynamics 365 Marketing înainte de a putea exporta un segment din Customer Insights în Marketing. Citiți mai multe despre cum să efectuați ingestia persoanelor de contact în [Dynamics 365 Marketing folosind Microsoft Dataverse](connect-power-query.md).

  > [!NOTE]
  > Exportul de segmente din perspectivele publicului către Marketing nu va crea noi înregistrări de contact în instanțele de Marketing. Înregistrările de contact din Marketing trebuie să fie ingerate în statistici ale publicului și utilizate ca sursă de date. De asemenea, trebuie să fie incluse în entitatea Client unificată pentru a identifica ID-urile clienților cu ID-urile de contact înainte ca segmentele să poată fi exportate.

## <a name="set-up-connection-to-marketing"></a>Configurarea conexiunii la Marketing

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Dynamics 365 Marketing** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți adresa URL de marketing a organizației dvs. în câmpul **Adresa serverului**.

1. În secțiunea **Cont administrator server**, selectați **Conectare** și alegeți un cont Dynamics 365 Marketing.

1. Mapați un câmp ID client la ID-ul de contact Dynamics 365.

1. Selectați **Salvare** pentru a finaliza conexiunea. 

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Dynamics 365 Marketing. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

1. Alegeți unul sau mai multe segmente.

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
