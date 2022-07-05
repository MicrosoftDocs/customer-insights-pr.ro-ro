---
title: Profiluri de client
description: Vizualizați datele unificate ale clienților, inclusiv folosind căutarea și filtrarea
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 279c8e1291c6449005d593244f1979e871610a77
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052204"
---
# <a name="customer-profiles"></a>Profiluri de client

Pagina **Clienți** afișează o vizualizare combinată a profilurilor dvs. unificate de clienți. Profilurile clienților sunt disponibile odată ce [ați creat entitatea Client unificat](data-unification.md). Pagina vă permite să căutați clienți și să definiți indexul pentru căutarea respectivă.

Clienții pot fi persoane fizice sau organizații. Fiecare profil de client este reprezentat de o dală. Utilizați comenzile de paginare pentru a obține mai multe înregistrări. Cardul afișează câmpurile din entitatea *Client* definită în **Index de căutare și filtrare**. Ordinea câmpurilor din fiecare card este aleasă de sistem.

Selectați o dală pentru a vedea datele pentru clientul selectat într-o pagină dedicată numită [Pagina cu detalii despre client](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"]
> ![Pagina clienților care prezintă dale de rezultate](media/customers-page-result-tiles-B2C.png "Pagina clienților care prezintă dale de rezultate")

> [!NOTE]
> Dacă nu puteți vedea dalele atunci când selectați **Clienți** în navigare, administratorul dvs. trebuie să [definească cel puțin un atribut care poate fi căutat](search-filter-index.md) în **Index de căutare și filtrare**.

## <a name="search-for-customers"></a>Căutare clienți

Căutați clienți introducând un nume sau alt atribut în caseta de căutare. Căutarea funcționează numai în entitatea *Client* creată în timpul procesului de unificare a datelor.

Ca administrator, puteți configura atributele care pot fi căutate folosind pagina **Indice de căutare și filtrare**. Pentru mai multe informații, accesați [Geestionați index de căutare și filtrare](search-filter-index.md).

## <a name="filter-customers"></a>Filtrați clienții

Puteți filtra clienții după câmpurile entitate *Client*. Similar cu căutarea, administratorul dvs. va trebui mai întâi să definească câmpurile ca fiind filtrabile folosind pagina **Indice de căutare și filtrare**.

1. Selectați **Afișați filtrele** pe pagina **Clienți**.

1. Bifați casetele de lângă atributele prin care doriți să filtrați clienții.

1. Eliminați filtrele selectând **Ștergere filtre** pe pagina **Clienți**.

## <a name="customer-details-page"></a>Pagină detalii client

Selectați oricare dintre dalele clientului pentru a deschide **Pagina cu detalii despre client**. Această vizualizare conține informații unificate pentru clientul selectat. Detaliile despre clienți includ următorul conținut:

**Dală profil client**: Această dală arată diferitele valori față de entitatea unificată *Client*. Dacă un câmp nu are nicio valoare pentru profilul de client selectat, nu se va afișa, cu excepția câmpului pentru adresă. Dala este structurată în secțiuni:

- Prima secțiune prezintă un set predefinit de câmpuri urmat de toate câmpurile care fac parte din indexul de căutare și filtrare. Toate câmpurile legate de adresă sunt combinate într-o singură linie, care arată chiar dacă profilul nu conține informații despre adresă.
- **Contacte pentru acest client**: În mediile pentru conturi de afaceri, veți vedea toate contactele aferente pentru acest client ca a doua secțiune. Fiecare contact este afișat cu câmpurile sale. Câmpurile goale sunt ascunse.
- **Câmpuri suplimentare**: Afișează câmpurile rămase ale clientului selectat, cu excepția ID-urilor.
- **ID-uri**: Listează toate ID-urile sub numele entității corespunzătoare. Câmpurile sunt identificate ca ID-uri prin semantica lor, care le clasifică ca atare.

**Cronologia activității**: Afișează date dacă ați configurat activități. Vizualizarea cronologiei conține activități sortate cronologic ale clientului selectat, începând cu cea mai recentă activitate. Pentru mai multe informații, accesați [Activități de client](activities.md).

**Detalii**:

- **Măsuri**: Arată dacă ați configurat una sau mai multe măsuri măsuri ale atributelor clientului. Acestea includ indicatorii KPI calculați în jurul clienților dvs. la nivel de client individual. Pentru mai multe informații, accesați [Definiți și gestionați măsurile](measures.md).

- **Interese potențiale, mărci potențiale**: Arată dacă ați configurat o îmbogățire a afinității de marcă sau de interes. Reprezintă potențiale interese și afinități pentru mărci bazate pe alți clienți al căror profil este similar cu profilul de client selectat. Pentru mai multe informații, accesați [Îmbogățiți profilurile clienților cu afinități de marcă și interes](enrichment-microsoft.md).

Pentru a reveni la pagina de căutare a clienților, selectați **Înapoi la Clienți**.

## <a name="next-steps"></a>Pașii următori

[Adăugați mai multe surse de date](data-sources.md), [îmbogățiți profilurile unificate](enrichment-hub.md), sau [creați segmente](segments.md) pentru a lucra cu profiluri de clienți unificate în alte aplicații.

[!INCLUDE [footer-include](includes/footer-banner.md)]
