---
title: Entități în Customer Insights
description: Vizualizați datele pe pagina Entități.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 0beaa46d47545ac195ced876b509dfc57821bfaf
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183587"
---
# <a name="entities-in-customer-insights"></a>Entități în Customer Insights

După [configurarea surselor de date](data-sources.md), accesați pagina **Entități** pentru a evalua calitatea datelor ingerate. Entitățile sunt considerate seturi de date. Capacități multiple ale Dynamics 365 Customer Insights sunt construite în jurul acestor entități. Revizuirea acestora îndeaproape vă poate ajuta să validați rezultatele acestor funcții.

Pe măsură ce lucrați în Customer Insights, îmbogățindu-vă datele sau creând segmente, măsuri și activități, entitățile care sunt create din acele acțiuni se afișează pe **Entități** pagină.

## <a name="view-a-list-of-entities"></a>Vizualizați o listă de entități

Mergi la **Date** > **Entități** pentru a vizualiza o listă de entități. Următoarele informații sunt afișate pentru fiecare entitate.

- **Nume** : Numele entității de date. Dacă vedeți un simbol de avertizare lângă un nume de entitate, înseamnă că datele pentru acea entitate nu s-au încărcat cu succes.
- **Sursă** : Tipul de sursă de date care a ingerat entitatea.
- **La curent** : Ora la care entitatea a fost actualizată ultima dată.
- **stare** : Detalii despre ultima actualizare a entității.

## <a name="explore-a-specific-entitys-data"></a>Explorați datele unei entități specifice

1. Mergi la **Date** > **Entități**.
1. Selectați o entitate pentru a deschide pagina de detalii.  
1. Explorați diferitele câmpuri și înregistrări incluse pentru acea entitate.

- The **Atribute** fila este selectată în mod implicit și arată detalii pentru entitatea selectată, cum ar fi numele câmpurilor, tipurile și tipurile de date. Coloana **Tip** prezintă tipurile asociate Common Data Model, care sunt fie identificate automat de sistem sau [mapate manual](map-entities.md) de către utilizatori. Aceste tipuri sunt tipuri semantice care pot diferi de tipurile de date ale atributelor. De exemplu, câmpul *E-mail* de mai jos are un tip de date *Şir* dar tipul său (semantic) Common Data Model ar putea fi *E-mail*, *de e-mail*, sau *Identitate.Serviciul.E-mail*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Tabelul câmpurilor.":::

   > [!NOTE]
   > Această pagină afișează doar o mostră de date ale entității dvs. Pentru a vizualiza setul complet de date, accesați **Surse de date** pagina, selectați o entitate, selectați **Editați | ×**, apoi vizualizați datele acestei entități cu Power Query editor așa cum este explicat în [Surse de date](data-sources.md).

   Pentru a afla mai multe despre datele ingerate în entitate, the **rezumat** coloana furnizează câteva caracteristici importante ale datelor, cum ar fi valorile nule, valorile lipsă, valorile unice, numărul și distribuțiile, indiferent de ceea ce este aplicabil datelor dvs. Selectați pictograma diagramă pentru a vedea rezumatul datelor.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Tabel rezumat al datelor.":::

- The **Date** fila arată detalii despre înregistrările individuale ale entității. Detaliile enumerate depind de tipul de date al entității.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Selectați o entitate.":::

- The **Rapoarte** fila (disponibilă pentru unele entități) vă permite să vă vizualizați datele prin crearea unui raport, care include aceste coloane:

  - **Numele raportului** : Numele raportului.
  - **Creat de** : Numele persoanei care a creat entitatea.
  - **Creată** : Data și ora creării entității.
  - **Editat de** : Numele persoanei care a modificat entitatea.
  - **Editat** : Data și ora modificării entității.

## <a name="entity-specific-information"></a>Informații specifice entității

Următoarea secțiune oferă informații despre unele entități create de sistem.

### <a name="corrupted-data-sources"></a>Surse de date deteriorate

Câmpurile dintr-o sursă de date ingerate pot conține date deteriorate. Înregistrările cu câmpuri deteriorate sunt expuse în entități create de sistem. Cunoașterea înregistrărilor deteriorate vă ajută să identificați ce date să revizuiți și să actualizați pe sistemul sursă. După următoarea reîmprospătare a sursă de date, înregistrările corectate sunt ingerate către Customer Insights și transmise proceselor din aval. 

De exemplu, o coloană „zi de naștere” are tipul de date setat ca „dată”. Înregistrarea unui client are ziua de naștere înregistrată ca „01/01/19777”. Sistemul va semnaliza această înregistrare ca fiind deteriorată. Cineva poate schimba acum ziua de naștere din sistemul sursă în „1977”. După o reîmprospătare automată a surselor de date, câmpul are acum un format valid și înregistrarea va fi eliminată din entitatea deteriorată.

Accesați **Date** > **Entități** și căutați entitățile deteriorate în secțiunea **Sistem**. Schema de denumire a entităților deteriorate: „DataSourceName_EntityName_corrupt”. Selectați o entitate coruptă pentru a identifica câmpurile corupte și motivul la nivel de înregistrare individuală.

   :::image type="content" source="media/corruption-reason.png" alt-text="Motivul corupției.":::

Customer Insights procesează încă înregistrări deteriorate. Cu toate acestea, acestea pot cauza probleme atunci când lucrați cu datele unificate.

Următoarele verificări rulează pe datele ingerate pentru a expune înregistrările deteriorate:

- Valoarea unui câmp nu se potrivește cu tipul de date al coloanei sale.
- Câmpurile conțin caractere care fac ca coloanele să nu se potrivească cu schema așteptată. De exemplu: ghilimele formatate incorect, ghilimele fără scăpare sau caracterele cu linie nouă.
- Dacă există coloane datetime/date/datetimeoffset, formatul acestora trebuie specificat în model dacă nu respectă formatul ISO standard.

[!INCLUDE [footer-include](includes/footer-banner.md)]
