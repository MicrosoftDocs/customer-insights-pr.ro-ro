---
title: Entități și seturi de date
description: Vizualizați datele pe pagina Entități.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 383523bad5105e08e57758838e90a49e805b5f9b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596422"
---
# <a name="entities-in-audience-insights"></a>Entități în Detalii despre audiență

După [configurarea surselor de date](data-sources.md), accesați pagina **Entități** pentru a evalua calitatea datelor ingerate. Entitățile sunt considerate seturi de date. Capacități multiple ale Dynamics 365 Customer Insights sunt construite în jurul acestor entități. Revizuirea acestora îndeaproape vă poate ajuta să validați rezultatele acestor funcții.

Pagina **Entități** listează entitățile și include mai multe coloane:

- **Nume**: Numele entității dvs. de date. Dacă vedeți un simbol de avertizare lângă un nume de entitate, înseamnă că datele pentru acea entitate nu s-au încărcat cu succes.
- **Sursa**: tipul sursei de date care au ingerat entitatea
- **Creat de**: numele persoanei care a creat entitatea
- **Creată**: Data și ora creării entității
- **Actualizată de**: numele persoanei care a actualizat entitatea
- **Ultima actualizare**: Data și ora ultimei actualizări a entității
- **Ultima actualizare**: Data și ora ultimei actualizări de date

## <a name="exploring-a-specific-entitys-data"></a>Explorarea datelor unei entități specifice

Selectați o entitate pentru a explora diferitele câmpuri și înregistrări incluse în acea entitate.

> [!div class="mx-imgBorder"]
> ![Selectați o entitate](media/data-manager-entities-data.png "Selectați o entitate")

- Fila **Date** este selectată implicit și arată un tabel cu detalii despre înregistrările individuale ale entității.

> [!div class="mx-imgBorder"]
> ![Tabelul câmpurilor](media/data-manager-entities-fields.PNG "Tabelul câmpurilor")

- Fila **Câmpuri** arată un tabel pentru a revizui detaliile pentru entitatea selectată, cum ar fi numele câmpurilor, tipurile de date și tipurile. Coloana **Tip** prezintă tipurile asociate Common Data Model, care sunt fie identificate automat de sistem sau [mapate manual](map-entities.md) de către utilizatori. Acestea sunt tipuri semantice care pot diferi de tipurile de date ale atributelor - de exemplu, câmpul *E-mail* de mai jos are un tip de date *Text* dar tipul său (semantic) de Common Data Model ar putea fi *E-mail* sau *EmailAddress*.

> [!NOTE]
> Ambele tabele prezintă doar un eșantion de date ale entității dvs. Pentru a vizualiza setul complet de date, accesați pagina **Surse de date**, selectați o entitate, selectați **Editați**, apoi vizualizați datele acestei entități cu editorul Power Query, așa cum este explicat în [Surse de date](data-sources.md).

Pentru a afla mai multe despre datele ingerate în entitate, coloana **Rezumat** vă oferă câteva caracteristici importante ale datelor, cum ar fi valorile Null, valori lipsă, valori unice, numărări și distribuții, după cum se aplică datelor dumneavoastră.

Selectați pictograma diagramă pentru a vedea rezumatul datelor.

> [!div class="mx-imgBorder"]
> ![Simbol rezumat](media/data-manager-entities-summary.png "Tabel Rezumat date")

### <a name="next-step"></a>Următorul pas

Consultați subiectul [Unificare](data-unification.md) pentru a afla despre cum să *mapați*, *potriviți*, și *combinați* datele ingerate.


[!INCLUDE[footer-include](../includes/footer-banner.md)]