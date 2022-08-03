---
title: Gestionați indexul de căutare și filtrare pentru profilurile clienților
description: Găsiți rapid informații despre profilurile de clienți unificate și filtrați pentru atributele specificate.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187924"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Gestionați indexul de căutare și filtrare pentru profilurile clienților

Rezultatul unificării datelor dvs. despre clienți este a *Client* entitate care oferă o vedere unificată asupra bazei totale de clienți. Pentru utilizatorii rapid [găsiți informații despre un anumit client sau grup de clienți](customer-profiles.md), un administrator trebuie să configureze **Căutare** și **Filtru** capabilități pentru **Clienți** pagină.

   :::image type="content" source="media/search-filter.png" alt-text="Filtru de căutare":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Definiți atributele care pot fi căutate și câmpurile indexate

Dacă este prima dată când definiți atribute care pot fi căutate ca administrator, definiți mai întâi câmpurile indexate. Vă sugerăm să alegeți toate atributele prin care utilizatorii pot căuta și filtra clienții pe pagina **Clienți**. Doar atributele care există în *Client* poate fi specificată entitate creată în timpul procesului de unificare a datelor.

1. Mergi la **Clienți** și selectați **Căutare și filtrare index**.

1. Selectați **+ Adăugați**.

1. Selectați atributele din lista pe care doriți să le adăugați ca câmpuri indexate și faceți clic **aplica**.

1. Pentru a adăuga mai multe atribute, selectați **Adăuga**. Pentru a elimina un atribut selectat, selectați atributul și apoi **Șterge**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Pagina de index de căutare și filtrare.":::

1. Selectați **Alerga** după ce sunteți gata să aplicați setările de căutare și filtrare. După procesarea modificărilor, vizualizați-le în [carduri de client pe pagina Client](customer-profiles.md).

## <a name="define-filtering-options-for-a-given-attribute"></a>Definiți opțiunile de filtrare pentru un anumit atribut

Configurați câmpurile care pot fi utilizate pentru filtrarea clienților pe **Clienți** pagină.

1. Mergi la **Clienți** și selectați **Căutare și filtrare index**.

1. Selectați un atribut și **Adăugați filtru**. Definiți numărul de rezultate și ordinea în care vor fi organizate. În funcție de tipul de date al atributului, va apărea unul dintre următoarele panouri.

   - Atribute de tip șir: specificați numărul de rezultate dorite pe **Filtru de șiruri** panoul și politica de ordine după care vor fi organizate.

   - Atribute de tip numeric: specificați intervalele incluse în **Filtru de număr** panoul și politica de ordine după care vor fi organizate.

   - Atribute tip dată: specificați intervalele incluse în **Filtru de dată** panoul și politica de ordine după care vor fi organizate.

1. Selectați **OK**. Repetați pentru toate atributele după care doriți să filtrați.

1. Selectați **Alerga** după ce sunteți gata să aplicați setările de căutare și filtrare. După procesarea modificărilor, vizualizați-le în [carduri de client pe pagina Client](customer-profiles.md).

## <a name="view-indexed-customer-fields"></a>Vizualizați câmpurile client indexate

The **Căutare și filtrare index** pagina afișează următoarele informații:

- **Nume** : Reprezintă numele atributului așa cum apare în *Client* entitate.
- **Tip de date**: Specifică dacă tipul de date este un șir, un număr sau o dată.
- **Inclus în căutare**: Specifică dacă acest atribut poate fi utilizat pentru căutarea clienților pe pagina **Clienți** folosind câmpul de **Căutare**.
- **Adăugare filtru**: Control pentru a defini modul în care acest atribut poate fi utilizat pentru filtrare pe pagina **Clienți**.

## <a name="next-steps"></a>Pașii următori

Examinați [pagina profilurilor unificate](customer-profiles.md) pentru a căuta profiluri sau pentru a utiliza câmpurile indexate pentru a vedea un subset al tuturor profilurilor unificate.

[!INCLUDE [footer-include](includes/footer-banner.md)]
