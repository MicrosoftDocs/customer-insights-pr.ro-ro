---
title: Prezentare generală a predicțiilor
description: Predicție scenarii și opțiuni acoperite de aplicația Dynamics 365 Customer Insights.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610205"
---
# <a name="predictions-overview"></a>Prezentare generală a predicțiilor

Dynamics 365 Customer Insights vine cu o varietate de opțiuni care folosesc AI și învățare programată pentru a prezice date.

## <a name="out-of-box-models"></a>Modele predefinite

Cel mai simplu mod de a începe cu prezicerea datelor sunt modelele predefinite, adesea denumite modele predefinite. Acestea necesită doar anumite date și structură pentru a genera informații rapide. Următoarele modele sunt disponibile:

# <a name="individual-consumers-b-to-c"></a>[Consumatori individuali (B2C)](#tab/b2c)

- [Valoarea ciclului de viață a clientului](predict-customer-lifetime-value.md): Prezice veniturile potențiale ale unui client pe parcursul întregii interacțiuni cu o companie.
- [Recomandarea produsului](predict-product-recommendation.md): Sugerează seturi de recomandări predictive de produse pe baza comportamentului de cumpărare și a clienților cu modele de achiziție similare.
- [Retragere din abonament](predict-subscription-churn.md): Prezice dacă un client riscă să nu mai utilizeze produsele sau serviciile cu abonament ale firmei dvs.
- [Schimbare tranzacțională](predict-transactional-churn.md) : prezice dacă un client individual nu va mai cumpăra produsele sau serviciile dvs. într-un anumit interval de timp.
- [Analiza sentimentelor](sentiment-analysis.md) : analizează sentimentul feedback-ului clienților și identifică aspectele de afaceri care sunt menționate frecvent.

# <a name="business-accounts-b-to-b"></a>[Conturi de afaceri (B2B)](#tab/b2b)

- [Schimbare tranzacțională](predict-transactional-churn.md) : prezice dacă un cont de client nu va mai cumpăra produsele sau serviciile dvs. într-un anumit interval de timp.

---

> [!TIP]
> Vă recomandăm să reîmprospătați în mod regulat modelele gata de fabricație cu date actualizate pentru a vă asigura că acestea vă informează cu exactitate cazul de utilizare în afaceri. Datele sunt reîmprospătate ad-hoc atunci când sistemul ingerează surse de date noi sau actualizate. Cu toate acestea, modelele vor recore doar în acest caz și vor continua să utilizeze datele de antrenament existente.
>
> Configurați un **Actualizați programul** prin setarea programului de reinstruire a modelului în timpul configurării. Modelul se va reinstrui și va recalifica în acest program, pe care îl puteți schimba oricând.

## <a name="azure-machine-learning-integration"></a>Integrare pentru învățarea programată Azure

Dacă o organizație folosește deja scenarii de învățare programată pe baza experimentelor Azure de învățare programată, caracteristica modelelor personalizate din Customer Insights ajută la conectarea punctelor. Creați fluxuri de lucru care vă ajută să alegeți datele din care doriți să generați statistici și să asociați rezultatele la profilurile dvs. unificate de clienți. Pentru mai multe informații, consultați [Modelele de învățare programată particularizate](custom-models.md).

## <a name="manage-existing-predictions"></a>Gestionați previziunile existente

Du-te la **Inteligența** > **Previziuni** pagină. Pe **Previziunile mele** fila, vizualizați predicțiile pe care le-ați creat, tipul lor predicție, numele entității de ieșire, starea, ultima dată când predicție a fost editat și ultima dată când datele au fost reîmprospătate. Puteți sorta lista de predicții după orice coloană.

Selectați un predicție pentru a vedea acțiunile disponibile.

:::image type="content" source="media/predictions.png" alt-text="Pagina mea de predicții.":::

- **Editați | ×** predicție pentru a-și schimba proprietățile.
- [**Reîmprospăta**](#refresh-a-prediction) predicție pentru a include cele mai recente date.
- **Vedere** detaliile predicție.
- [**Raport de utilizare a datelor de intrare**](#view-the-input-data-usability-report) pentru a vizualiza erori, avertismente și recomandări.
- **Șterge** predicție.

### <a name="refresh-a-prediction"></a>Reîmprospătați o predicție

Predicțiile pot fi reîmprospătate pe un program automat sau reîmprospătate manual la cerere. Pentru a reîmprospăta manual toate predicțiile, selectați **Reîmprospătați totul**. Pentru a reîmprospăta manual un predicție, selectați-l și selectați **Reîmprospăta**. La [programați o reîmprospătare automată](schedule-refresh.md), mergi la **Admin** > **Sistem** > **Programa**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Vizualizați raportul de utilizare a datelor de intrare

Raportul de utilizare a datelor de intrare oferă o imagine consolidată a erorilor și avertismentelor pe care le pot genera predicțiile dvs. predefinite. De asemenea, oferă recomandări despre cum să îmbunătățiți performanța modelului.

Raportul este disponibil după ce un model a finalizat procesul de instruire. Este creat pentru fiecare model separat, indiferent dacă a finalizat antrenamentul cu succes sau nu.

Pe **Previziunile mele** fila, selectați predicție și alegeți **Raport de utilizare a datelor de intrare**. Sau din vizualizarea detaliilor predicție, selectați **Raport de utilizare a datelor de intrare**.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exemplu de raport de utilizare a datelor de intrare care prezintă un tabel cu erori, avertismente și recomandări.":::

Raportul include:

- **Nume:** Numele descriptiv al erorii, avertismentului sau recomandării.
- **Etapa:** Faza de modelare, antrenament sau scor, la care se referă informațiile.
- **Stat:** Severitatea informațiilor (eroare, avertisment, recomandare).
- **Numele coloanei:** Coloană dintr-o entitate care trebuie modificată pentru a îmbunătăți performanța modelului.
- **Numele entitatii:** Numele entității care trebuie modificată pentru a îmbunătăți performanța modelului.
- **Detalii:** Detalii despre eroare, avertisment sau recomandare.

[!INCLUDE [footer-include](includes/footer-banner.md)]
