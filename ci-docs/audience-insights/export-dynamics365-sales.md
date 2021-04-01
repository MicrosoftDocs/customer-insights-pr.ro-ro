---
title: Exportați datele Customer Insights către Dynamics 365 Sales
description: Aflați cum puteți configura conexiunea la Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598124"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Conector pentru Dynamics 365 Sales (previzualizare)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Utilizați datele clienților pentru a crea liste de marketing, a urmări fluxuri de lucru și a trimite promoții cu Dynamics 365 Sales.

## <a name="prerequisite"></a>Cerințe preliminare

1. Înregistrările de contact trebuie să fie prezente în Dynamics 365 Sales înainte de a putea exporta un segment din Customer Insights în Sales. Citiți mai multe despre cum să efectuați ingestia persoanelor de contact în [Dynamics 365 Sales folosind Common Data Services](connect-power-query.md).

   > [!NOTE]
   > Exportul de segmente din perspectivele publicului către Sales nu va crea noi înregistrări de contact în instanțele de Sales. Înregistrările de contact din Sales trebuie să fie ingerate în statistici ale publicului și utilizate ca sursă de date. De asemenea, trebuie să fie incluse în entitatea Client unificată pentru a identifica ID-urile clienților cu ID-urile de contact înainte ca segmentele să poată fi exportate.

## <a name="configure-the-connector-for-sales"></a>Configurați conectorul pentru Vânzări

1. În Detalii despre audiență, accesați **Administrator** > **Destinații export**.

1. Sub **Dynamics 365 Sales**, selectați **Configurare**.

1. Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.

1. Introduceți adresa URL de vânzări a organizației dvs. în câmpul **Adresa serverului**.

1. În secțiunea **Cont administrator server**, selectați **Conectare** și alegeți un cont Dynamics 365 Sales.

1. Mapați un câmp ID client la ID-ul de contact Dynamics 365.

1. Selectați **Următorul**.

1. Alegeți unul sau mai multe segmente.

1. Selectați **Salvare**.

## <a name="export-the-data"></a>Exportați datele

Puteți [exporta date la cerere](export-destinations.md). Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]