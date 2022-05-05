---
title: Înțelegeți și gestionați măsurile
description: Aflați cum măsurile ajută la analiza și reflectarea performanței afacerii dvs.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 84a3a10a2517258c1f895800882b9c67391ec3de
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643307"
---
# <a name="measures-overview"></a>Prezentare generală a măsurilor

Măsurile vă ajută să înțelegeți mai bine comportamentele clienților și performanța afacerii. Se uită la valorile relevante din [profiluri unificate](data-unification.md). De exemplu, o companie vrea să vadă *cheltuielile totale per client* pentru a înțelege istoricul sau măsura achizițiilor unui client individual *vânzările totale ale companiei* pentru a înțelege veniturile la nivel agregat din întreaga afacere.  

Se creează măsuri [folosind constructorul de măsură](measure-builder.md), o platformă de interogare a datelor cu diverși operatori și opțiuni simple de cartografiere. Vă permite să filtrați datele, să grupați rezultatele, să detectați [căile relației entității](relationships.md), și previzualizați ieșirea. Poti [utilizați șabloane predefinite](measure-templates.md) pentru a configura eficient măsurile utilizate în mod obișnuit.

Utilizați instrumentul de măsurare pentru a planifica activități comerciale prin interogarea datelor despre clienți și extragerea de informații. De exemplu, crearea unei măsuri de *cheltuieli totale per client* și *returnare totală per client* ajută la identificarea unui grup de clienți cu cheltuieli mari, dar cu randament ridicat. Poti [creați un segment](segments.md) pe baza acestor măsuri pentru a conduce următoarele cele mai bune acțiuni.

## <a name="manage-your-measures"></a>Gestionați-vă măsurile

Puteți găsi lista măsurilor pe pagina **Măsuri**.

Veți găsi informații despre tipul de măsură, creatorul, data creării, starea și starea. Când selectați o măsură din listă, puteți previzualiza ieșirea și descărca un fișier CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Acțiuni de gestionare a măsurilor unice."lightbox="media/measures-actions.png":::

Următoarele acțiuni sunt disponibile atunci când selectați o măsură:

- **Editați** configurația măsurii.
- **Duplicat** o masura. Puteți alege să editați proprietățile imediat sau pur și simplu să salvați duplicatul.
- **Reîmprospătați** măsura pe baza celor mai recente date. Pentru a reîmprospăta toate măsurile în același timp, selectați toate măsurile și apoi **Reîmprospăta**.
- **Redenumiți** măsura.
- **Activați** sau **Dezactivați**. Măsurile inactive nu vor fi reîmprospătate în timpul unei [reîmprospătări planificate](system.md#schedule-tab).
- **Etichetă** la [gestionați etichetele](work-with-tags-columns.md#manage-tags) pentru segment.
- **Ștergeți** măsura.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>Pasul următor

Puteți utiliza măsurile existente pentru a crea [un segment de clienți](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
