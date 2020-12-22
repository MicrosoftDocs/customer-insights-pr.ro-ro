---
title: Vizualizare profiluri de client
description: Obțineți o vizualizare combinată a datelor unificate ale clienților.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 13308c2f40cda0d7e813b4d94ab47d53b5ce2115
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653905"
---
# <a name="customer-profiles"></a>Profiluri de client

Pagina **Clienți** arată o vizualizare combinată a clienților dvs., pe baza datelor de profil colectate de la [toate sursele de date](data-sources.md). Profilele clienților sunt disponibile odată ce [creați entitatea Client unificat](data-unification.md). Asigurați-vă că finalizați procesul de unificare a datelor pentru a obține vizualizări mai bogate ale clienților. Pagina vă permite, de asemenea, să căutați clienți.

Clienții pot fi persoane fizice sau organizații (previzualizare). Fiecare profil de client sau organizație este reprezentat printr-o dală. Selectați o dală pentru a vedea informații suplimentare despre respectivul client sau organizație. Utilizați controalele de paginare din partea de jos a paginii pentru a vedea înregistrări suplimentare.

> [!div class="mx-imgBorder"] 
> ![Profiluri de clienți B2C](media/profiles-customers.png "Profiluri de clienți B2C")

Organizații (previzualizare)
> [!div class="mx-imgBorder"] 
> ![Profiluri de clienți B2B](media/profile-customers-b2b.png "Profiluri de clienți B2B")

> [!NOTE]
> Dacă nu puteți vedea dalele când selectați **Clienți** în meniul de navigare, administratorul dvs. trebuie să [definească cel puțin un atribut care poate fi căutat](search-filter-index.md) în **Index de căutare și filtrare**.

## <a name="search-for-customers"></a>Căutare clienți

Căutați clienți introducând un nume sau alt atribut în caseta de căutare. Căutarea funcționează numai în cadrul entității Profilul Clientului creat în timpul procesului de unificare a datelor.

Ca administrator, puteți configura atributele care pot fi căutate folosind pagina **Indice de căutare și filtrare**. Pentru mai multe informații, consultați [Gestionați indicele de căutare și filtrare](search-filter-index.md).

## <a name="filter-customers"></a>Filtrați clienți

Puteți filtra clienții după câmpurile entității Profilul clienților. Similar cu căutarea, administratorul dvs. va trebui mai întâi să definească câmpurile ca fiind filtrabile folosind pagina **Indice de căutare și filtrare**.

1. Selectați **Filtru** în pagina **Clienți**.

2. Bifați casetele de lângă atributele prin care doriți să filtrați clienții.

   > [!div class="mx-imgBorder"] 
   > ![Profiluri de client](media/profiles-customers3.png "Profiluri de client")

3. Eliminați filtrele selectând **Ștergere filtre** pe pagina **Clienți**.

##  <a name="customer-details-page"></a>Pagină detalii client

Selectați oricare dintre dalele clientului pentru a deschide **Pagina cu detalii despre client**. Această vizualizare conține informații unificate pentru clientul selectat.

Detaliile clientului includ:

-   **Dală profil client:** Această dală arată diferitele valori din entitatea de profil client unificat. Aceste detalii pot include adresa de e-mail, numele, orașul și așa mai departe. 

-   **Interese potențiale, mărci potențiale:** Arată dacă ați configurat o îmbogățire primară. Reprezintă potențiale interese și afinități pentru mărci pe care le poate avea un client cu un profil similar cu acest client. Pentru mai multe informații, consultați [Îmbogățiți profilurile clienților cu afinități de brand și interes](enrichment-microsoft-graph.md).

-   **Măsuri:** Arată dacă ați configurat una sau mai multe măsuri de un anumit tip: măsuri de atribut client. Acestea includ indicatorii KPI calculați în jurul clienților dvs. la nivel de client individual. Pentru mai multe informații, consultați [Definire și gestionare măsuri](measures.md).

-   **Cronologia activității:** Arată dacă ați configurat activități. Vizualizarea cronologiei conține activități sortate cronologic ale acestui client, începând cu cea mai recentă activitate. Pentru mai multe informații, consultați [Activități Client](activities.md).

Selectați **Înapoi la clienți** pentru a reveni la pagina de căutare a clienților.

## <a name="next-steps"></a>Pașii următori

[Adăugați mai multe surse de date](data-sources.md) sau [creați segmente de clienți](segments.md).
