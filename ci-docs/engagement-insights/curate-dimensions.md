---
title: Utilizați dimensiunile demografice pentru divizarea datelor comportamentale (dimensiuni organizate)
description: Utilizați dimensiuni unificate de profil pentru a permite statisticilor publicului proprietățile profilului clientului.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8a3d7f9276330a6daacbe9428d84a371b81bbefe
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466363"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Utilizați dimensiunile demografice pentru divizarea datelor comportamentale

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Utilizând dimensiuni demografice ale profilului unificat, utilizatorii de statistici de implicare pot accesa proprietățile profilului de detalii despre public. Apoi puteți utiliza aceste proprietăți în analize interactive cu date comportamentale, inclusiv date capturate de detalii despre angajament pe site-ul dvs. sau aplicația mobilă.

>[!NOTE]
> Detaliile despre angajamente includ dimensiuni predefinite pentru proprietățile evenimentului. Mai multe informații: [Vizualizarea și crearea dimensiunilor](dimensions.md)

## <a name="prerequisite"></a>Cerințe preliminare

- Un mediu de informare despre implicare în care aveți detalii despre profilul de client, legate de mediul de informații despre public, în care sunt create profilurile clienților. Mai multe informații: [Creați o legătură între detaliile despre public și detalii despre angajament](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> După ce creați o legătură între mediile de public și perspectivele de angajament, este posibil să doriți doar date specifice proprietăților profilului clientului, care pot fi utile ca dimensiuni în detaliile de angajament. Pentru mai multe informații, accesați [Activați atributele și segmentele profilurilor unificate pentru statisticile publicului](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Crea un nou raport particularizat

1. În panoul din stânga, selectați **Particularizat** > **Raport nou**, apoi selectați valoarea dorită. (Pentru acest exemplu, am ales **Vizualizări de pagină pe oră**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Selectați o măsurătoare.":::

2. În editorul de vizualizare, selectați **Dimensiuni**, apoi selectați **Demografic** în meniul derulant **Tipul dimensiunii**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Selectați datele demografice.":::

3. Alegeți o dimensiune **Signal.Customer.*xxx*** dimensiune. (Acest exemplu arată Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Selectați o dimensiune.":::
  
## <a name="limitations"></a>Limitări

În prezent puteți utiliza doar dimensiunile demografice pentru divizarea datelor comportamentale.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
