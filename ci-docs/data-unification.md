---
title: Creați o vizualizare unificată a clienților dvs.
description: Parcurgeți procesul de unificare a datelor cu datele dvs. pentru a crea un singur set de date de profiluri unificate de clienți.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: bb8da6f4b9f92f2b265ff9807e04638edae4f814
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755749"
---
# <a name="data-unification-overview"></a>Prezentare generală a unificării datelor

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

După [configurarea surselor de date](data-sources.md), puteți unifica datele. Unificarea datelor vă permite să unificați sursele de date odată diferite într-un singur set de date principal care oferă o vizualizare unificată a datelor respective. Pentru consumatorii individuali (B-to-C) în care datele sunt centrate în jurul persoanelor fizice, unificarea oferă o vedere unificată a clienților dvs. Pentru conturile de afaceri (B-to-B) în care datele sunt centrate pe conturi, unificarea oferă o vizualizare unificată a conturilor dvs.

Datele pot fi unificate pe o singură entitate sau pe mai multe entități. Unificarea se realizează în următoarea ordine:

1. [Câmpurile sursă](map-entities.md) (denumită anterior Hartă): în pasul câmpuri sursă, selectați entitățile și câmpurile de inclus în procesul de unificare. Mapează câmpurile la un tip semantic comun care descrie scopul câmpului.

1. [Înregistrări duplicate](remove-duplicates.md) (anterior parte a potrivirii): în pasul de înregistrări duplicate, definiți opțional reguli pentru a elimina înregistrările duplicate ale clienților din fiecare entitate.

1. [Condiții de potrivire](match-entities.md) (numit anterior Potrivire): în pasul condițiilor de potrivire, definiți reguli care potrivesc înregistrările clienților între entități. Când un client este găsit în două sau mai multe entități, este creată o singură înregistrare consolidată cu toate coloanele și datele din fiecare entitate.

1. [Câmpuri unificate pentru clienți](merge-entities.md) (numit anterior Îmbinare): în pasul Câmpuri unificate pentru clienți, determinați ce câmpuri sursă trebuie incluse, excluse sau îmbinate într-un profil de client unificat.  

1. [Revizuire](review-unification.md) și creați profilul unificat.

După finalizarea unificării datelor, puteți opțional:

- [Stabiliți relații între entități](relationships.md) pentru a crea segmente sofisticate.
- [Îmbogățiți-vă datele](enrichment-hub.md) pentru a obține o gamă mai largă de informații despre clienții dvs.
- [Definiți activități](activities.md) din unele dintre atributele ingerate.
- [Construiți măsuri](measures.md) pentru a înțelege mai bine comportamentele clienților și performanța afacerii.

[!INCLUDE [footer-include](includes/footer-banner.md)]