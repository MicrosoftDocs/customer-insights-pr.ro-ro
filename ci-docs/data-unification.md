---
title: Creați o vizualizare unificată a clienților dvs.
description: Parcurgeți procesul de unificare a datelor cu datele dvs. pentru a crea un singur set de date principale de profiluri de cont sau de clienți.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304442"
---
# <a name="data-unification-overview"></a>Prezentare generală a unificării datelor

După [configurarea surselor de date](data-sources.md), puteți unifica datele. Unificarea datelor vă permite să unificați sursele de date odată diferite într-un singur set de date principal care oferă o vizualizare unificată a datelor respective.

Pentru consumatorii individuali (B-to-C) în care datele sunt centrate în jurul persoanelor fizice, unificarea oferă o vedere unificată a clienților dvs. Pentru conturile de afaceri (B-to-B) în care datele sunt centrate pe conturi, unificarea oferă o vizualizare unificată a conturilor dvs. [Unificarea contactelor (previzualizare)](data-unification-contacts.md) permite ca contactele respectivelor conturi să fie unificate separat și asociate cu conturile.

Datele pot fi unificate pe o singură entitate sau pe mai multe entități.

# <a name="individual-consumers-b-to-c"></a>[Consumatori individuali (B2C)](#tab/b2c)

Procesul de unificare mapează datele clienților din sursele dvs. de date, elimină duplicatele, potrivește datele între entități și creează un profil unificat. Unificarea se realizează în următoarea ordine:

1. [Câmpurile sursă](map-entities.md) (denumită anterior Hartă): în pasul câmpuri sursă, selectați entitățile și câmpurile de inclus în procesul de unificare. Mapează câmpurile la un tip semantic comun care descrie scopul câmpului.

1. [Înregistrări duplicate](remove-duplicates.md) (anterior parte a potrivirii): în pasul de înregistrări duplicate, definiți opțional reguli pentru a elimina înregistrările duplicate ale clienților din fiecare entitate.

1. [Condiții de potrivire](match-entities.md) (numit anterior Potrivire): în pasul condițiilor de potrivire, definiți reguli care potrivesc înregistrările clienților între entități. Când un client este găsit în două sau mai multe entități, este creată o singură înregistrare consolidată cu toate coloanele și datele din fiecare entitate.

1. [Câmpuri unificate pentru clienți](merge-entities.md) (denumit anterior Îmbinare): în pasul Câmpuri unificate pentru clienți, determinați ce câmpuri sursă trebuie incluse, excluse sau îmbinate într-un profil de client unificat.  

1. [Revizuire](review-unification.md) și creați profilul unificat.

# <a name="business-accounts-b-to-b"></a>[Conturi de afaceri (B2B)](#tab/b2b)

Procesul de unificare mapează datele contului din sursele dvs. de date, elimină duplicatele, potrivește datele între entități și creează un profil unificat. Unificarea se realizează în următoarea ordine:

1. [Câmpurile sursă](map-entities.md) (denumită anterior Hartă): în pasul câmpuri sursă, selectați entitățile și câmpurile de inclus în procesul de unificare a contului. Mapează câmpurile la un tip semantic comun care descrie scopul câmpului.

1. [Înregistrări duplicate](remove-duplicates.md) (anterior parte din Potrivire): în pasul de înregistrări duplicate, definiți opțional reguli pentru a elimina înregistrările de cont duplicate din fiecare entitate.

1. [Condiții de potrivire](match-entities.md) (numit anterior Potrivire): în pasul condițiilor de potrivire, definiți reguli care potrivesc înregistrările de cont între entități. Când un cont este găsit în două sau mai multe entități, este creată o singură înregistrare consolidată cu toate coloanele și datele din fiecare entitate.

1. [Câmpuri unificate pentru clienți](merge-entities.md) (denumit anterior Îmbinare): în pasul Câmpuri unificate pentru clienți, determinați ce câmpuri sursă trebuie incluse, excluse sau îmbinate într-un profil de client unificat.  

1. [Revizuire](review-unification.md) și creați profilul unificat.

După unificarea conturilor, puteți opțional [unificați contactele (previzualizare)](data-unification-contacts.md) pentru acele conturi și conectați contactele unificate la conturile unificate.

---

După finalizarea unificării datelor, puteți opțional:

- [Stabiliți relații între entități](relationships.md) pentru a crea segmente sofisticate.
- [Îmbogățiți-vă datele](enrichment-hub.md) pentru a obține o gamă mai largă de informații despre clienții dvs.
- [Definiți activități](activities.md) din unele dintre atributele ingerate.
- [Construiți măsuri](measures.md) pentru a înțelege mai bine comportamentele clienților și performanța afacerii.

[!INCLUDE [footer-include](includes/footer-banner.md)]
