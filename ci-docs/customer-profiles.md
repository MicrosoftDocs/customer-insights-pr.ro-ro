---
title: Vizualizare profiluri de client
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
ms.openlocfilehash: 6cdf47e6997f230811dcb0f2cf5542f3a6db2367
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188108"
---
# <a name="view-customer-profiles"></a>Vizualizare profiluri de client

Profilurile clienților sunt disponibile odată ce dvs [creează unificatul *Client* entitate](data-unification.md). Vizualizarea combinată a profilurilor dvs. unificate de clienți se afișează pe **Clienți** pagină. Clienții pot fi persoane fizice sau organizații.

Du-te la **Clienți** pagina pentru a vă vizualiza clienții și profilurile acestora. Fiecare profil de client este reprezentat de o dală. Utilizați comenzile de paginare pentru a obține mai multe înregistrări. Cardul afișează câmpurile din entitatea *Client* definită în **Index de căutare și filtrare**. Ordinea câmpurilor din fiecare card este aleasă de sistem.

> [!NOTE]
> Dacă nu puteți vedea plăcile atunci când selectați **Clienți**, administratorul dvs. trebuie să o facă [definiți cel puțin un atribut care poate fi căutat](search-filter-index.md) în **Căutare și filtrare index**.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Pagina Clienți care arată piese de rezultat.":::

Selectați oricare dintre următoarele acțiuni:
- [Vedeți detaliile clienților](#view-customer-details)
- [Gestionați indexul de căutare și filtrare](search-filter-index.md) (doar administratorii)
- [Filtrați clienții](#filter-customers)
- **Extindeți cardurile** sau **Restrângeți cardurile** pentru a extinde sau restrânge informațiile afișate pe tigla client
- **Filtrează după** un anumit atribut
- [Căutare clienți](#search-for-customers)

  > [!NOTE]
  > Pentru a utiliza căutarea și filtrarea, un administrator trebuie să configureze atributele care pot fi căutate și să definească câmpurile filtrabile folosind indexul de căutare și filtrare.

## <a name="search-for-customers"></a>Căutare clienți

Căutați clienți introducând un nume sau un alt atribut **Căutați clienți**. Atributele care pot fi căutate sunt definite de administrator și provin din unificat *Client* entitate.

> [!NOTE]
> **Şir** este singurul tip de date care este inclus în căutare. Folosiți-l în **Căutați clienți** câmp din pagina Clienți pentru a căuta clienți.

## <a name="filter-customers"></a>Filtrați clienții

Filtrați clienții după *Client* câmpurile de entitate. Câmpurile filtrabile sunt definite de administrator.

1. Pe **Clienți** pagina, selectați **Afișați filtrele**. Se afișează panoul Filtru.

1. Bifați casetele de lângă atributele prin care doriți să filtrați clienții.

1. Eliminați toate filtrele selectând **Ștergeți filtrele** sau debifați o casetă de selectare de lângă un atribut selectat.

1. Selectați **Ascunde filtrele** pentru a închide panoul de filtrare.

1. Pentru a salva rezultatele filtrului ca a [segment](segments.md), Selectați **Salvați filtrele ca segment**.
   1. Introduceți un nume pentru segment.
   1. Selectați **Salvați** pentru a salva segmentul.
   1. Alegeți dacă să rulați segmentul acum selectând **Activati** sau rulați-l **Mai tarziu**.

## <a name="view-customer-details"></a>Vedeți detaliile clienților

Pe **Clienți** pagina, selectați o piesă de client pentru a vedea detaliile pentru clientul selectat.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Pagina de detalii client.":::

Detaliile clientului includ:

**Tigla de profil client** arată valorile diferite de la unificat *Client* entitate. Dacă un câmp nu are nicio valoare pentru profilul de client selectat, nu se va afișa, cu excepția câmpului de adresă. Dala este structurată în secțiuni:

- Prima secțiune prezintă un set predefinit de câmpuri urmat de toate câmpurile care fac parte din indexul de căutare și filtrare. Toate câmpurile legate de adresă sunt combinate într-o singură linie, care arată chiar dacă profilul nu conține informații despre adresă.
- **Contacte pentru acest client** afișare în medii pentru conturi de afaceri. Fiecare contact este afișat cu câmpurile sale. Câmpurile goale sunt ascunse.
- **Câmpuri suplimentare** afișează câmpurile rămase ale clientului selectat, cu excepția ID-urilor.
- **ID-uri** listează toate ID-urile sub numele lor de entitate corespunzător. Câmpurile sunt identificate ca ID-uri prin semantică.

**Cronologia activității** afișează date dacă ați configurat [Activități](activities.md). Vizualizarea cronologiei conține activități sortate cronologic ale clientului selectat, începând cu cea mai recentă activitate.

**Detalii**:

- **Măsuri** arata daca ai configurat [măsurile atributelor clientului](measures.md). Acestea includ indicatorii KPI calculați în jurul clienților dvs. la nivel de client individual.

- **Interese potențiale, mărci potențiale** arata daca ai configurat un [îmbogățirea afinității de marcă sau de interes](enrichment-microsoft.md). Reprezintă potențiale interese și afinități pentru mărci bazate pe alți clienți al căror profil este similar cu profilul de client selectat.

Pentru a reveni la **Clienți** pagina, selectați **Înapoi la Clienți**.

## <a name="next-steps"></a>Pașii următori

[Adăugați mai multe surse de date](data-sources.md), [îmbogățiți profilurile unificate](enrichment-hub.md), sau [creați segmente](segments.md) pentru a lucra cu profiluri de clienți unificate în alte aplicații.

[!INCLUDE [footer-include](includes/footer-banner.md)]
