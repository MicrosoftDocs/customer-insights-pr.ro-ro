---
title: Căutați și filtrați profiluri de client
description: Găsiți rapid informații despre profilurile de clienți unificate și filtrați pentru atributele specificate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597158"
---
# <a name="customer-profiles-search--filter-index"></a>Profilurile clienților: indexul de căutare și filtrare

Rezultatul unificării datelor clientului dvs. este o entitate de profil pentru clienți care oferă o vizualizare unificată în baza dvs. totală de clienți. Pentru [găsirea rapidă a informațiilor despre un anumit client sau grup de clienți](customer-profiles.md), puteți configura capabilitățile **Căutare** și **Filtru** pe pagina **Clienți**. Citiți mai departe pentru a afla cum pot edita administratorii atributele de pe pagina **Index de căutare și filtrare**, care sunt disponibile utilizatorilor pentru căutare și filtrare.

> [!div class="mx-imgBorder"]
> ![Filtru de căutare](media/search-filter.png "Filtru de căutare")

## <a name="add-fields-and-specify-attributes"></a>Adăugați câmpuri și specificați atributele

Dacă este prima dată când definiți atribute căutabile ca administrator, trebuie să definiți mai întâi câmpurile indexate. Vă sugerăm să alegeți toate atributele prin care utilizatorii pot căuta și filtra clienții pe pagina **Clienți**. Puteți specifica doar atribute care există în entitatea Profil client pe care le-ați creat în timpul procesului de unificare a datelor.

1. Deschideți pagina **Clienți** și selectați **Index de căutare și filtrare**.

2. Selectați **+ Adăugare** pentru specificarea câmpurilor indexate.

3. Selectați atributele din lista pe care doriți să le adăugați ca câmpuri indexate. Puteți adăuga întotdeauna mai multe atribute selectând **Adăugare**. De asemenea, puteți elimina orice atribute selectate selectând simbolul **Eliminare**.

## <a name="explore-the-indexed-customer-fields-table"></a>Explorați tabelul câmpurilor indexate pentru clienți

Următoarele informații sunt prezentate în tabel.

- **Nume**: Reprezintă numele atributului așa cum apare în entitatea Profil client.
- **Tip de date**: Specifică dacă tipul de date este un șir, un număr sau o dată.
- **Inclus în căutare**: Specifică dacă acest atribut poate fi utilizat pentru căutarea clienților pe pagina **Clienți** folosind câmpul de **Căutare**.
- **Adăugare filtru**: Control pentru a defini modul în care acest atribut poate fi utilizat pentru filtrare pe pagina **Clienți**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Editarea opțiunilor de filtrare pentru un atribut dat

Meniul **Filtru** din pagina **Clienți** poate include un număr diferit de niveluri de atribute (de exemplu, diferite grupe de vârstă pentru filtrarea clienților).

1. Selectați **Adăugare filtru** pentru un atribut dat pe pagina **Indice de căutare și filtrare**. Puteți defini numărul de rezultate și ordinea în care vor fi organizate. În funcție de tipul de date al atributului, apare unul dintre următoarele panouri.

- Atribute de tip string: specificați numărul de rezultate dorite pe panoul **Opțiuni filtru string** și politica de comandă prin care vor fi organizate.

- Atribute de tip numeric: specificați inervalele incluse pe panoul **Opțiuni filtru număr** și politica de comandă prin care vor fi organizate.

- Atribute de tip date: specificați inervalele incluse pe panoul **Opțiuni filtru date** și politica de comandă prin care vor fi organizate.

2. Selectați **Salvare** pentru a vă aplica modificările.

3. Selectați **Executare** odată ce sunteți gata să vă aplicați setările.

## <a name="next-steps"></a>Pașii următori

Accesați pagina **Clienți** pentru a căuta profiluri de clienți sau utilizați câmpurile indexate pentru a vedea un subset al tuturor profilurilor de clienți.


[!INCLUDE[footer-include](../includes/footer-banner.md)]