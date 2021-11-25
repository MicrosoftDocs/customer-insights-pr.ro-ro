---
title: Entități și seturi de date
description: Vizualizați datele pe pagina Entități.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 2a207a3dcad4bf192efb6ee1554195f10b19670b
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732096"
---
# <a name="entities-in-audience-insights"></a>Entități în Detalii despre audiență

După [configurarea surselor de date](data-sources.md), accesați pagina [Entități](data-sources.md) pentru a evalua calitatea datelor ingerate. Entitățile sunt considerate seturi de date. Capacitățile multiple ale Dynamics 365 Customer Insights sunt construite în jurul acestor entități. Revizuirea acestora îndeaproape vă poate ajuta să validați rezultatele acestor funcții.

Pagina **Entități** listează entitățile și include mai multe coloane:

- **Nume**: Numele entității dvs. de date. Dacă vedeți un simbol de avertizare lângă un nume de entitate, înseamnă că datele pentru acea entitate nu s-au încărcat cu succes.
- **Sursa**: tipul sursei de date care au ingerat entitatea
- **Creat de**: numele persoanei care a creat entitatea
- **Creată**: Data și ora creării entității
- **Actualizat** : Numele persoanei care a actualizat entitatea
- **stare** : Detalii despre ultima actualizare a entității

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Explorați datele unei entități specifice

Selectați o entitate pentru a explora diferitele câmpuri și înregistrări incluse în acea entitate.

> [!div class="mx-imgBorder"]
> ![Selectați o entitate.](media/data-manager-entities-data.png "Selectați o entitate")

- Fila **Date** afișează un tabel cu detalii despre înregistrările individuale ale entității.

> [!div class="mx-imgBorder"]
> ![Tabelul câmpurilor.](media/data-manager-entities-fields.PNG "Tabelul câmpurilor")

- Fila **Atribute** fila este selectată implicit și afișează un tabel pentru a examina detaliile entității selectate, cum ar fi numele câmpurilor, tipurile de date și tipurile. Coloana **Tip** prezintă tipurile asociate Common Data Model, care sunt fie identificate automat de sistem sau [mapate manual](map-entities.md) de către utilizatori. Aceste tipuri sunt tipuri semantice care pot diferi de tipurile de date ale atributelor. De exemplu, câmpul *E-mail* mai jos are un tip de date *Text* dar tipul său Common Data Model (semantic) ar putea fi *E-mail* sau *Adresa de e-mail*.

> [!NOTE]
> Ambele tabele prezintă doar un eșantion de date ale entității dvs. Pentru a vizualiza setul complet de date, accesați pagina **Surse de date**, selectați o entitate, selectați **Editați**, apoi vizualizați datele acestei entități cu editorul Power Query, așa cum este explicat în [Surse de date](data-sources.md).

Pentru a afla mai multe despre datele ingerate în entitate, coloana **Rezumat** vă oferă câteva caracteristici importante ale datelor, cum ar fi valorile Null, valori lipsă, valori unice, numărări și distribuții, după cum se aplică datelor dumneavoastră.

Selectați pictograma diagramă pentru a vedea rezumatul datelor.

> [!div class="mx-imgBorder"]
> ![Simbol rezumat.](media/data-manager-entities-summary.png "Tabel Rezumat date")

## <a name="entity-specific-information"></a>Informații specifice entității

Următoarea secțiune oferă informații despre unele entități create de sistem.

### <a name="corrupted-data-sources"></a>Surse de date deteriorate

Câmpurile dintr-o sursă de date ingerate pot conține date deteriorate. Înregistrările cu câmpuri deteriorate sunt expuse în entități create de sistem. Cunoașterea înregistrărilor deteriorate vă ajută să identificați ce date să revizuiți și să actualizați pe sistemul sursă. După următoarea reîmprospătare a sursă de date, înregistrările corectate sunt ingerate către Customer Insights și transmise proceselor din aval. 

De exemplu, o coloană „zi de naștere” are tipul de date setat ca „dată”. Înregistrarea unui client are ziua de naștere înregistrată ca „01/01/19777”. Sistemul va semnaliza această înregistrare ca fiind deteriorată. Cineva poate schimba acum ziua de naștere din sistemul sursă în „1977”. După o reîmprospătare automată a surselor de date, câmpul are acum un format valid și înregistrarea va fi eliminată din entitatea deteriorată. 

Accesați **Date** > **Entități** și căutați entitățile deteriorate în secțiunea **Sistem**. Schema de denumire a entităților deteriorate: „DataSourceName_EntityName_corrupt”.

Customer Insights procesează încă înregistrări deteriorate. Cu toate acestea, acestea pot cauza probleme atunci când lucrați cu datele unificate.

Următoarele verificări rulează pe datele ingerate pentru a expune înregistrările deteriorate: 

- Valoarea unui câmp nu se potrivește cu tipul de date al coloanei sale.
- Câmpurile conțin caractere care fac ca coloanele să nu se potrivească cu schema așteptată. De exemplu: ghilimele formatate incorect, ghilimele fără scăpare sau caracterele cu linie nouă.
- Dacă există coloane datetime/date/datetimeoffset, formatul acestora trebuie specificat în model dacă nu respectă formatul ISO standard.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
