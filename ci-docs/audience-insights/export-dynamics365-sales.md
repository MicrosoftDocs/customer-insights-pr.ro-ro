---
title: Exportați datele Customer Insights către Dynamics 365 Sales
description: Aflați cum puteți configura conexiunea la Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643833"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Conector pentru Dynamics 365 Sales (previzualizare)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Utilizați datele clienților pentru a crea liste de marketing, a urmări fluxuri de lucru și a trimite promoții cu Dynamics 365 Sales.

## <a name="prerequisite"></a>Cerințe preliminare

Înregistrări de contact [din Dynamics 365 Sales ingerate folosind Common Data Service](connect-power-query.md).

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
