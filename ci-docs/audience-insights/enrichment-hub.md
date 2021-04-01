---
title: Îmbogățire profiluri de clienți unificate
description: Folosiți capacitățile pentru a vă îmbogăți datele clienților.
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597710"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Îmbogățirea profilurilor clienților (previzualizare)

Utilizați date din surse precum Microsoft și de la alți parteneri pentru a vă îmbogăți datele clienților.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pagină hub de îmbogățire":::

În statisticile publicului, accesați **Date** > **Îmbogățire** pentru a lucra cu opțiuni de îmbogățire.    
Trebuie să aveți permisiuni de Colaborator sau Administrator pentru a crea sau edita îmbogățirile. Pentru mai multe informații, consultați [Permisiuni](permissions.md).

Pe fila **Descoperire**, veți găsi următoarele îmbogățiri:

- [Mărcile](enrichment-microsoft-graph.md) furnizate de Microsoft Graph
- [Interesele](enrichment-microsoft-graph.md) furnizate de Microsoft Graph
- [Datele companiei](enrichment-leadspace.md) furnizate de Leadspace
- [Date demografice](enrichment-experian.md) furnizate de Experian
- [Date despre locație](enrichment-here.md) furnizate de HERE Technologies
- [Date particularizate](enrichment-SFTP-custom-import.md) prin Protocol de transfer securizat al fișierelor (SFTP)

Pe fila **Îmbogățirile mele**, puteți vedea îmbogățirile pe care le-ați configurat și le puteți edita proprietățile.

## <a name="manage-existing-enrichments"></a>Gestionarea îmbogățirilor existente

Accesați **Îmbogățirile mele** pentru a vedea toate îmbogățirile configurate. Fiecare îmbogățire este reprezentată ca un rând care include informații suplimentare despre îmbogățire.

Selectați o îmbogățire pentru a vedea opțiunile disponibile. Alternativ, puteți selecta elipsele (...) de pe un element din listă pentru a vedea opțiunile.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opțiuni de gestionare a îmbogățirilor din lista îmbogățirilor":::

- **Vizualizare** detalii de îmbogățire cu numărul de profiluri de clienți îmbogățite.
- **Editați** configurația de îmbogățire.
- **Rulați** îmbogățirea pentru actualizarea profilurilor clienților cu cele mai recente date.
- **Dezactivați** o îmbogățire existentă pentru a o opri din actualizarea automată cu fiecare actualizare programată. Datele din ultima actualizare reușită vor continua să fie disponibile. **Activați** o îmbogățire inactivă pentru a reporni actualizarea automată cu fiecare actualizare programată.
- **Ștergeți** o îmbogățire.

Puteți rula sau dezactiva mai multe îmbogățiri simultan selectându-le în listă. Opțiunile de vizualizare și editare nu sunt disponibile ca acțiune în bloc și funcționează doar pentru câte o îmbogățire pe rând.


[!INCLUDE[footer-include](../includes/footer-banner.md)]