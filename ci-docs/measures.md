---
title: Prezentare generală a măsurilor
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
ms.openlocfilehash: ead57ccbdcaf9f86ee54d1f15de71a63f2e1081b
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170861"
---
# <a name="measures-overview"></a>Prezentare generală a măsurilor

Măsurile vă ajută să înțelegeți mai bine comportamentele clienților și performanța afacerii. Se uită la valorile relevante din [profiluri unificate](data-unification.md). De exemplu, o companie vrea să vadă *cheltuielile totale per client* pentru a înțelege istoricul sau măsura achizițiilor unui client individual *vânzările totale ale companiei* pentru a înțelege veniturile la nivel agregat din întreaga afacere.

Creați măsuri pentru a planifica activitățile de afaceri interogând datele clienților și extrageți informații. De exemplu, creați o măsură de *cheltuieli totale per client* și *randament total per client* pentru a ajuta la identificarea unui grup de clienți cu cheltuieli mari, dar cu randament ridicat. Apoi, [creați un segment](segments.md) pe baza acestor măsuri pentru a conduce următoarele cele mai bune acțiuni.

## <a name="create-a-measure"></a>Crearea unei măsuri

Alegeți cum să creați o măsură în funcție de publicul țintă.

# <a name="individual-consumers-b-to-c"></a>[Consumatori individuali (B2C)](#tab/b2c)

- De la zero cu generatorul de măsură: [Construiește-ți propriul](measure-builder.md).
- Din măsurile utilizate în mod obișnuit: [Utilizați șabloane predefinite](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Conturi de afaceri (B2B)](#tab/b2b)

De la zero cu generatorul de măsură: [Construiește-ți propriul](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Gestionați măsurile existente

Du-te la **Măsuri** pentru a vedea măsurile pe care le-ați creat, starea acestora, tipul de măsură și ultima dată când datele au fost reîmprospătate. Puteți sorta lista de măsuri după orice coloană sau puteți utiliza caseta de căutare pentru a găsi măsura pe care doriți să o gestionați.

Selectați lângă o măsură pentru a vedea acțiunile disponibile. Selectați numele măsurătorii pentru a previzualiza rezultatul și descărcați un fișier CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Acțiuni de gestionare a măsurilor unice."lightbox="media/measures-actions.png":::

- **Editați | ×** măsura de a-și schimba proprietățile.
- **Reîmprospăta** măsura să includă cele mai recente date.
- **Redenumiți** măsura.
- **Activati** sau **Dezactivați** masura. Măsurile inactive nu vor fi reîmprospătate în timpul a [reîmprospătare programată](system.md#schedule-tab) și au **stare** enumerate ca **Sărit**, indicând că nici măcar nu a fost încercată o reîmprospătare.
- **Etichetă** la [gestionați etichetele](work-with-tags-columns.md#manage-tags) pentru masura.
- **Ștergeți** măsura.
- **Coloane** la [personalizați coloanele](work-with-tags-columns.md#customize-columns) acel afișaj.
- **Filtru** la [filtrează pe etichete](work-with-tags-columns.md#filter-on-tags).
- **Căutați numele** pentru a căuta după numele măsurării.

## <a name="refresh-measures"></a>Măsuri de reîmprospătare

Măsurile pot fi reîmprospătate după un program automat sau reîmprospătate manual la cerere. Pentru a reîmprospăta manual una sau mai multe măsuri, selectați-le și alegeți **Reîmprospăta**. La [programați o reîmprospătare automată](system.md#schedule-tab), mergi la **Admin** > **Sistem** > **Programa**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
