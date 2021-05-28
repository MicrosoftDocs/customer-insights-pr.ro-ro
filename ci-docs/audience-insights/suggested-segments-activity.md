---
title: Segmente sugerate bazate pe activitate.
description: Lăsați ca învățarea programată să vă ajute să găsiți segmente noi și interesante pe baza activității clienților.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034105"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Segmente sugerate bazate pe datele de activitate (versiune preliminară)

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
Dacă vă ocupați de servicii medicale, oferind asistență medicală publică și obiectivul dvs. este de a reduce la minimum cheltuielile pentru pacienții individuali. O modalitate de a face acest lucru ar fi reducerea vizitelor recurente, oferind cea mai bună îngrijire posibilă în cât mai puține vizite. În acest caz, obiectivul dvs. este de a menține frecvența de vizitare scăzută și să reduceți costurile recurente pentru pacienți. Sau puteți să identificați segmente de pacienți care au rezervări frecvente și costuri recurente ridicate și puteți analiza aceste cazuri pentru a îmbunătăți tratamentul persoanei. 

## <a name="required-data"></a>Date necesare

Sugestiile sunt generate pe baza datelor de intrare selectate. 

- Profiluri de clienți: toți clienții sau membri ai unui anumit segment. 

- Perioada de timp: luna trecută, anul trecut sau orice alt interval de timp particularizat.

- Tipul de activitate: achiziții, tranzacții retail, tranzacții online, cazuri de asistență pentru clienți, abonamente etc.  

- Entitatea din Customer Insights care conține datele despre activitate: entitatea UnifiedActivity sau entitatea pentru o anumită activitate. 

- Dimensiuni care trebuie incluse: caracter recent, frecvență sau dimensiune monetară, în funcție de cerințele afacerii dvs.

## <a name="generate-suggested-segments"></a>Generați segmente sugerate

1. Mergeți la **Segmente**.

1. Selectați fila **Sugestii (previzualizare)**.

1. Selectați **Găsiți noi sugestii** și alegeți **Vedeți sau anticipați comportamentul clienților**. Selectați **Start** pentru a rula experiența ghidată.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Primul pas al expertului de configurare pentru un segment sugerat pe baza activității.":::

1. Dați datele de intrare necesare și selectați **Următorul** pentru a continua.

   - Alegeți clienții: includeți toți clienții sau un anumit segment.
   - Alegeți activitatea: selectați tipul de activitate și entitățile care descriu activitatea.
   - Preferințe: setați perioada de timp de luat în considerare, factorii pentru sugestii și mapați atributele.

1. Revizuiți datele introduse și selectați **Rulare** pentru a rula modelul și a genera sugestii.

1. În funcție de numărul de profiluri ale clienților și de activitățile selectate, finalizarea poate dura câteva minute. 

După generarea sugestiilor, puteți să le filtrați după dimensiune sau valoarea care vă interesează cel mai mult. 

## <a name="view-details-of-a-suggested-segment"></a>Vizualizați detaliile unui segment sugerat

După ce sugestiile sunt generate, le veți găsi listate în **Segmente** > **Sugestii (previzualizare)** în secțiunea **Sugestii bazate pe activități**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Panou lateral extins care prezintă date detaliate ale unui segment sugerat.":::

Selectați **Vedeți sugestia** pentru un segment sugerat pentru a vedea detaliile acelui segment. Panoul lateral oferă detalii precum extensia fiecărei dimensiuni în comparație cu grupul țintă. De asemenea, evidențiază numărul de membri potențiali din segment și procentul corespunzător din totalul clienților. Dacă doriți să păstrați sugestia drept segment, selectați **Creare segment**.    

## <a name="save-a-suggestion-as-a-segment"></a>Salvați o sugestie ca segment

1. Accesați **Segmente** > **Sugestii (previzualizare)**.

1. Selectați segmentul pe care doriți să-l salvați. 

1. În panoul lateral, selectați **Creare segment**. 

1. După ce salvați segmentul, acesta se va afișa în lista de segmente de pe fila **Toate segmentele**. Acum poate fi [reîmprospătat sau șters ca orice alt segment](segments.md). Nu puteți edita detaliile segmentului. Cu toate acestea, puteți modifica criteriile de intrare pentru sugestii și puteți genera sugestii diferite.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Reîmprospătați sau editați un set de sugestii

1. Accesați **Segmente** > **Sugestii (versiune preliminară)** și căutați segmentul în secțiunea **Sugestii bazate pe activități**.

1. Selectați **Reîmprospătați sugestiile** pentru a reîmprospăta sugestiile păstrând în același timp atributele configurate. Sau selectați **Editați sugestiile** pentru a modifica atributele configurate. Sistemul va relua procesul, va genera sugestii de segmente pe baza celor mai recente date și va înlocui sugestiile curente.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
