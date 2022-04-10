---
title: Folosiți segmente de detalii privind publicul pentru a filtra rapoartele de detalii despre angajament
description: Utilizați segmente de statistici privind publicul în analize interactive ale datelor comportamentale capturate de statistici de angajament pe site-ul web al unui client.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9c8c7a1a9216e04ebee100c548afbc745af396ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230501"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Folosiți segmente de detalii privind publicul pentru a filtra rapoartele de detalii despre angajament

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Cu detalii despre angajament, puteți utiliza segmente de detalii despre public în analize interactive ale datelor comportamentale capturate de detaliile de angajament pe site-urile dvs. web.

## <a name="prerequisite"></a>Cerințe preliminare

- Un mediu de informare despre implicare în care aveți detalii despre segmente de public, legate de mediul de informații despre public, în care sunt create segmentele și profilurile clienților. Mai multe informații: [Creați o legătură între detaliile despre public și detalii despre angajament](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Creați segmente de statistici privind publicul 

> [!IMPORTANT]
> Pentru ca segmentele de statistici privind publicul să apară în statistici despre implicare, trebuie mai întâi să [rulați procesele de îmbinare și aval](../audience-insights/merge-entities.md). Procesele din aval sunt importante, deoarece generează un tabel unic care pregătește segmentele de informații despre public pentru a fi partajate cu datele de implicare. (Dacă este programată o reîmprospătare a sistemului, aceasta va include automat procesele din aval.)

Puteți utiliza segmente de statistici privind publicul în rapoartele de livrare personală sau rapoarte particularizate pe care le-ați creat. Pentru mai multe informații, accesați [Rapoarte de profil prestabilite](profile-reports.md) și [Creați și editați rapoarte particularizate](custom-reports.md).

**Pentru a utiliza segmente de detalii despre public în rapoartele de statistici despre angajament**

1. Din pagina dvs. **Spațiu de lucru**, selectați **Date** și apoi selectați fila **Segmente**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Selectați fila Segmente.":::

   >[!NOTE]
   > Selectarea unui segment de detalii privind publicul vă duce la statistici despre public, unde puteți afla cum a fost creat segmentul respectiv în ceea ce privește regulile și logica. Pentru mai multe informații despre segmentele de detalii despre public, accesați [Vizualizați și creați segmente](../audience-insights/segments.md).

2. Selectați un raport predefinit sau [creați un raport particularizat](custom-reports.md), apoi selectați **Adăugați o condiție**. (Pentru acest exemplu, am ales raportul **Vizualizări de pagină**.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Adăugați o condiție.":::

3. Selectați **Filtrează după segment**, extindeți lista **Tipul segmentului**, apoi selectați **Demografic**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Selectați tipul de segment demografic.":::

4. Extindeți lista **Numele segmentului**, apoi alegeți un segment de informații despre public.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Alegeți un segment.":::

5. Puteți aplica unul sau mai multe segmente, inclusiv segmente comportamentale (detalii despre angajament) și demografice (detalii despre public). 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Raportul privind vizualizările de pagină este limitat la segmentele de clienți din SUA și pagina de pornire.":::

În imaginea precedentă, **Clienții SUA** și **Pagina principala** au fost selectate segmente, ceea ce restricționează raportul **Vizualizări de pagină** pentru a afișa numai acele două segmente. 


>[!NOTE]
> Puteți utiliza segmente de detalii privind publicul pentru a filtra rapoartele predefinite, rapoarte particularizate și pâlnii în detalii despre angajament. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]