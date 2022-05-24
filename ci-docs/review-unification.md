---
title: Examinați unificarea datelor
description: Examinați pașii de unificare a datelor, creați profiluri de clienți unificate și examinați rezultatele
ms.date: 05/04/2022
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
ms.openlocfilehash: 4c709dfb55bf079dd2fe99e41adb4c77c2bece4b
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/11/2022
ms.locfileid: "8743033"
---
# <a name="review-data-unification"></a>Examinați unificarea datelor

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Acest ultim pas al procesului de unificare arată un rezumat al pașilor din proces și oferă șansa de a face modificări înainte de a crea profilul unificat.

:::image type="content" source="media/m3_review.png" alt-text="Captură de ecran a Examinează și creează profiluri de clienți.":::

## <a name="review-the-data-unification-steps"></a>Examinați pașii de unificare a datelor

1. Selectați **Editați | ×** pe oricare dintre pașii de unificare a datelor pentru a revizui și a face orice modificări.

1. Dacă sunteți mulțumit de selecțiile dvs., selectați **Creați profiluri de clienți**. The **Unifica** pagina se afișează în timp ce se creează profilul unificat de client. Algoritmul de unificare durează ceva timp pentru a se finaliza și nu puteți modifica configurația până când nu se finalizează.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

Când procesul de unificare se încheie, entitatea unificată a profilului clientului a sunat *Client*, este listat pe **Entități** pagina din **Profiluri** secțiune. Prima rundă de unificare cu succes creează unificatul *Client* entitate. Toate rulările ulterioare extind acea entitate.

## <a name="review-the-results-of-data-unification"></a>Examinați rezultatele unificării datelor

După unificare, cel **Date** > **Unifica** pagina arată numărul de profiluri de clienți unificate. Rezultatele fiecărui pas din procesul de unificare sunt afișate pe fiecare țiglă. De exemplu, **Câmpurile sursă** arată numărul de atribute (câmpuri) mapate și **Înregistrări duplicate** arată numărul de înregistrări duplicate găsite.

:::image type="content" source="media/m3_unified.png" alt-text="Captură de ecran a paginii Data Unify după unificarea datelor.":::

> [!TIP]
> The **Condiții de potrivire** țigla se afișează numai dacă au fost selectate mai multe entități.

Vă recomandăm să revizuiți rezultatele, în special calitatea dvs [regulile de potrivire](data-unification-update.md#manage-match-rules) și rafinați-le dacă este necesar.

Când e nevoie, [efectuați modificări la setările de unificare](data-unification-update.md) și rulați din nou profilul unificat.

## <a name="next-step"></a>Următorul pas

Configurați [Activități](activities.md),[îmbogăţire](enrichment-hub.md),[relatii](relationships.md), sau [măsuri](measures.md) pentru a obține mai multe informații despre clienții dvs.

[!INCLUDE[footer-include](includes/footer-banner.md)]
