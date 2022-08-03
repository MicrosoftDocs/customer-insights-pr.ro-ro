---
title: Segmente sugerate în funcție de activitate (previzualizare)
description: Lăsați ca învățarea programată să vă ajute să găsiți segmente noi și interesante pe baza activității clienților.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170604"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Segmente sugerate în funcție de activitate (previzualizare)

Descoperiți segmente interesante ale clienților pe baza datelor despre activitatea clienților care sunt ingerate în Customer Insights. Ca exemple de date despre activitate ar fi tranzacțiile, durata apelului de asistență, achizițiile sau returnările. Pentru a sugera segmente, datele de activitate sunt analizate din punct de vedere al caracterului recență, frecvență și valoare monetară (sau durată). Ca alternativă, puteți genera [segmente sugerate pentru a îmbunătăți o măsură sau a înțelege mai bine ce anume influențează un atribut](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Fila Segmente sugerate ce prezintă sugestii de segmente pentru segmente bazate pe activitate și bazate pe atribute.":::

## <a name="categorize-customers-by-activity"></a>Clasificați clienții după activitate

Cu [datele despre activitate](activities.md) disponibile în Customer Insights, putem genera sugestii care reprezintă grupuri de clienți:

- cei mai activi clienți 
- clienții care au făcut cele mai multe achiziții 
- clienții care au generat cele mai multe venituri 
- clienții care nu au fost activi în ultima perioadă 
- clienții care interacționează frecvent cu afacerea dvs.  

Dacă aveți o afacere de retail, ați putea afla care clienți generează cele mai multe venituri și îi puteți recompensa cu un cupon. Sau puteți să identificați clienții ocazionali și le puteți oferi posibilitatea să se alăture unui program de recompense, astfel încât să vă viziteze afacerea mai des.
Dacă oferiți asistență medicală publică și scopul dvs. este de a minimiza cheltuielile pentru pacienți individuali, puteți încerca să reduceți vizitele recurente, oferind cea mai bună îngrijire posibilă în cât mai puține vizite posibil. În acest caz, obiectivul dvs. este de a menține frecvența de vizitare scăzută și să reduceți costurile recurente pentru pacienți. Sau puteți să identificați segmente de pacienți care au rezervări frecvente și costuri recurente ridicate și puteți analiza aceste cazuri pentru a îmbunătăți tratamentul persoanei.

## <a name="required-data"></a>Date necesare

Sugestiile sunt generate pe baza datelor de intrare selectate.

- Profiluri de clienți: toți clienții sau membri ai unui anumit segment.

- Perioada de timp: luna trecută, anul trecut sau orice alt interval de timp particularizat.

- Tipul de activitate: achiziții, tranzacții retail, tranzacții online, cazuri de asistență pentru clienți, abonamente etc.  

- Entitatea din Customer Insights care conține datele despre activitate: entitatea UnifiedActivity sau entitatea pentru o anumită activitate.

- Dimensiuni care trebuie incluse: caracter recent, frecvență sau dimensiune monetară, în funcție de cerințele afacerii dvs.

## <a name="generate-suggested-segments"></a>Generați segmente sugerate

1. Mergi la **Segmente** și selectați **Sugestii (previzualizare)** fila.

1. Selectați **Găsiți noi sugestii** și alegeți **Vedeți sau anticipați comportamentul clienților**. Selectați **Start**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Primul pas al expertului de configurare pentru un segment sugerat pe baza activității.":::

1. Furnizați datele de intrare necesare și selectați **Următorul**.

   - Alegeți clienții: includeți toți clienții sau un anumit segment.
   - Alegeți activitatea: selectați tipul de activitate și entitățile care descriu activitatea.
   - Preferințe: setați perioada de timp de luat în considerare, factorii pentru sugestii și mapați atributele.

1. Revizuiți datele introduse și selectați **Rulare** pentru a rula modelul și a genera sugestii.

În funcție de numărul de profiluri ale clienților și de activitățile selectate, finalizarea poate dura câteva minute.

După generarea sugestiilor, puteți să le filtrați după dimensiune sau valoarea care vă interesează cel mai mult.

## <a name="manage-suggested-segments"></a>Gestionați segmentele sugerate

Mergi la **Segmente** și selectați **Sugestii (previzualizare)** fila. În **Sugestii bazate pe activitate** secțiune, selectați un segment sugerat pentru a vedea acțiunile disponibile.

- **Vezi sugestia** pentru a vizualiza detaliile segmentului respectiv, cum ar fi amploarea fiecărei dimensiuni în comparație cu grupul țintă. De asemenea, evidențiază numărul de membri potențiali din segment și procentul corespunzător din totalul clienților.
- **Creați un segment** pentru a salva cele sugerate ca segment. Se afișează pe **Toate segmentele** filă și poate fi [reîmprospătat sau șters](segments.md). Nu puteți edita detaliile segmentului. Cu toate acestea, puteți modifica criteriile de intrare pentru sugestii și puteți genera sugestii diferite.
- **Editați sugestiile** pentru a modifica atributele configurate care vor înlocui sugestiile curente.
- **Actualizează sugestiile** pentru a reîmprospăta sugestiile păstrând în același timp atributele configurate.

[!INCLUDE [footer-include](includes/footer-banner.md)]
