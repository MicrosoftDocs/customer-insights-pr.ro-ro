---
title: Înțelegeți și gestionați măsurile
description: Aflați cum măsurile ajută la analiza și reflectarea performanței afacerii dvs.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: c46fcc3baba1d6c92c2c0fe459a62277343cc0e4
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359802"
---
# <a name="measures-overview"></a>Prezentare generală a măsurilor

Măsurile vă ajută să înțelegeți mai bine comportamentele clienților și performanța afacerii. Se uită la valorile relevante din [profiluri unificate](data-unification.md). De exemplu, o companie vrea să vadă *cheltuielile totale per client* pentru a înțelege istoricul sau măsura achizițiilor unui client individual *vânzările totale ale companiei* pentru a înțelege veniturile la nivel agregat din întreaga afacere.  

Se creează măsuri [folosind constructorul de măsură](measure-builder.md), o platformă de interogare a datelor cu diverși operatori și opțiuni simple de cartografiere. Vă permite să filtrați datele, să grupați rezultatele, să detectați [căile relației entității](relationships.md), și previzualizați ieșirea. Puteți [utilizați șabloane predefinite](measure-templates.md) pentru a configura eficient măsurile utilizate în mod obișnuit.

Utilizați instrumentul de măsurare pentru a planifica activități comerciale prin interogarea datelor despre clienți și extragerea de informații. De exemplu, crearea unei măsuri de *cheltuieli totale per client* și *returnare totală per client* ajută la identificarea unui grup de clienți cu cheltuieli mari, dar cu randament ridicat. Puteți [creați un segment](segments.md) pe baza acestor măsuri pentru a conduce următoarele cele mai bune acțiuni. 

## <a name="manage-your-measures"></a>Gestionați-vă măsurile

Puteți găsi lista măsurilor pe pagina **Măsuri**.

Veți găsi informații despre tipul de măsură, creatorul, data creării, starea și starea. Când selectați o măsură din listă, puteți previzualiza ieșirea și descărca un fișier CSV.

Pentru a vă reîmprospăta toate măsurile în același timp, selectați **Reîmprospătați tot** fără a selecta o anumită măsură.

:::image type="content" source="media/measure-actions.png" alt-text="Acțiuni de gestionare a măsurilor unice.":::

Selectați o măsură din listă pentru următoarele opțiuni:

- Selectați numele măsurii pentru a vedea detaliile acesteia.
- **Editați** configurația măsurii.
- **Reîmprospătați** măsura pe baza celor mai recente date.
- **Redenumiți** măsura.
- **Ștergeți** măsura.
- **Activați** sau **Dezactivați**. Măsurile inactive nu vor fi reîmprospătate în timpul unei [reîmprospătări planificate](system.md#schedule-tab).

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Pasul următor

Puteți utiliza măsurile existente pentru a crea [un segment de clienți](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
