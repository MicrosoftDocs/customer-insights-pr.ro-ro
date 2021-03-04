---
title: Exportați datele Customer Insights către Dynamics 365 Marketing
description: Aflați cum puteți configura conexiunea la Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269069"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Conector pentru Dynamics 365 Marketing (previzualizare)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Utilizați [segmentele](segments.md) pentru a genera campanii și a contacta anumite grupuri de clienți cu Dynamics 365 Marketing. Pentru mai multe informații, consultați [Utilizați segmente din Dynamics 365 Customer Insights cu Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Cerințe preliminare

- Înregistrările de contact trebuie să fie prezente în Dynamics 365 Marketing înainte de a putea exporta un segment din Customer Insights în Marketing. Citiți mai multe despre cum să efectuați ingestia persoanelor de contact în [Dynamics 365 Marketing folosind Common Data Services](connect-power-query.md).

  > [!NOTE]
  > Exportul de segmente din perspectivele publicului către Marketing nu va crea noi înregistrări de contact în instanțele de Marketing. Înregistrările de contact din Marketing trebuie să fie ingerate în statistici ale publicului și utilizate ca sursă de date. De asemenea, trebuie să fie incluse în entitatea Client unificată pentru a identifica ID-urile clienților cu ID-urile de contact înainte ca segmentele să poată fi exportate.

## <a name="configure-the-connector-for-marketing"></a>Configurați conectorul pentru marketing

1. În Detalii despre audiență, accesați **Administrator** > **Destinații export**.

1. Sub **Dynamics 365 Marketing**, selectați **Configurare**.

1. Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.

1. Introduceți adresa URL de marketing a organizației dvs. în câmpul **Adresa serverului**.

1. În secțiunea **Cont administrator server**, selectați **Conectare** și alegeți un cont Dynamics 365 Marketing.

1. Mapați un câmp ID client la ID-ul de contact Dynamics 365.

1. Selectați **Următorul**.

1. Alegeți unul sau mai multe segmente.

1. Selectați **Salvare**.

## <a name="export-the-data"></a>Exportați datele

Puteți [exporta date la cerere](export-destinations.md). Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]