---
title: Entități în Customer Insights
description: Vizualizați datele pe pagina Entități.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610113"
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
   > Această pagină arată doar o mostră de date ale entității dvs. Pentru a vizualiza setul complet de date, accesați **Surse de date** pagina, selectați o entitate, selectați **Editați | ×**, apoi vizualizați datele acestei entități cu Power Query editor așa cum este explicat în [Surse de date](data-sources.md).

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

[!INCLUDE [footer-include](includes/footer-banner.md)]
