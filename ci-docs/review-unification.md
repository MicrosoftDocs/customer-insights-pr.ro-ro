---
title: Examinați unificarea datelor
description: Examinați pașii de unificare a datelor, creați profiluri unificate de clienți și examinați rezultatele
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303982"
---
# <a name="review-data-unification"></a>Examinați unificarea datelor

Examinați rezumatul modificărilor, creați profilul unificat și examinați rezultatele.

## <a name="review-and-create-customer-profiles"></a>Examinați și creați profiluri de clienți

Acest ultim pas al procesului de unificare arată un rezumat al pașilor din proces și oferă șansa de a face modificări înainte de a crea profilul unificat.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Captură de ecran a Revizuiți și creați profiluri de clienți.":::

1. Selectați **Editați | ×** pe oricare dintre pașii de unificare a datelor pentru a revizui și a face orice modificări.

1. Dacă sunteți mulțumit de selecțiile dvs., selectați **Creați profiluri de clienți** (sau **Creați profiluri de cont** pentru B-to-B). The **Unifica** pagina se afișează în timp ce se creează profilul unificat de client.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Captură de ecran a paginii Unify, cu dale afișând în coadă sau în curs de reîmprospătare.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Algoritmul de unificare durează ceva timp pentru a se finaliza și nu puteți modifica configurația până nu se finalizează.

## <a name="view-the-results-of-data-unification"></a>Vedeți rezultatele unificării datelor

După unificare, cel **Date** > **Unifica** pagina arată numărul de profiluri de clienți unificate (sau profiluri de cont pentru B-to-B). Rezultatele fiecărui pas din procesul de unificare sunt afișate pe fiecare țiglă. De exemplu, **Câmpurile sursă** arată numărul de atribute (câmpuri) mapate și **Înregistrări duplicate** arată numărul de înregistrări duplicate găsite.

:::image type="content" source="media/m3_unified.png" alt-text="Captură de ecran a paginii Data Unify după unificarea datelor.":::

> [!TIP]
> The **Condiții de potrivire** țigla se afișează numai dacă au fost selectate mai multe entități.

Vă recomandăm să revizuiți rezultatele, în special calitatea dvs [regulile de potrivire](data-unification-update.md#manage-match-rules) și rafinați-le dacă este necesar.

Când e nevoie, [efectuați modificări la setările de unificare](data-unification-update.md) și rulați din nou profilul unificat.

### <a name="verify-output-entities-from-data-unification"></a>Verificați entitățile de ieșire din unificarea datelor

Mergi la **Date** > **Entități** pentru a verifica entitățile de ieșire.

Entitatea unificată a profilului clientului, numită *Client*, afișează în **Profiluri** secțiune. Prima rundă de unificare cu succes creează unificatul *Client* entitate. Toate rulările ulterioare extind acea entitate.

Entitățile de deduplicare și combinare sunt create și afișate în **Sistem** secțiune. Cu numele este creată o entitate deduplicată pentru fiecare dintre entitățile sursă **Deduplication_DataSource_Entity**. The **ConflationMatchPairs** entitatea conține informații despre potrivirile între entități.

O entitate de ieșire de deduplicare conține următoarele informații:
- ID-uri / Chei
  - Câmpurile cheie primară și ID alternativ. Câmpul ID alternativ este format din toate ID-urile alternative identificate pentru o înregistrare.
  - Câmpul Deduplication_GroupId arată grupul sau clusterul identificat în cadrul unei entități care grupează toate înregistrările similare pe baza câmpurilor de deduplicare specificate. Este utilizat în scopuri de procesare a sistemului. Dacă nu sunt specificate reguli de deduplicare manuală și se aplică reguli de deduplicare definite de sistem, este posibil să nu găsiți acest câmp în entitatea de ieșire a deduplicării.
  - Deduplication_WinnerId: Acest câmp conține ID-ul câștigător din grupurile sau clusterele identificate. Dacă Deduplication_WinnerId este aceeași cu valoarea cheii principale pentru o înregistrare, înseamnă că înregistrarea este înregistrarea câștigătoare.
- Câmpuri utilizate pentru definirea regulilor de deduplicare.
- Câmpurile Regulă și Scor pentru a indica care dintre regulile de deduplicare s-au aplicat și scorul returnat de algoritmul de potrivire.

## <a name="next-step"></a>Următorul pas

- Pentru B-to-B, opțional executați [unificarea contactelor](data-unification-contacts.md).

- Pentru B-to-C, configurați [Activități](activities.md),[îmbogățiri](enrichment-hub.md),[relatii](relationships.md), sau [măsuri](measures.md) pentru a obține mai multe informații despre clienții dvs.

[!INCLUDE[footer-include](includes/footer-banner.md)]
