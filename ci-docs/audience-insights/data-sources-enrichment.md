---
title: Sursă de date îmbogățire
description: Îmbogățiți sursele de date înainte de a trece prin procesul de unificare a datelor.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: eebaaf18795e80dd1ba16a15a23844d685c94c6e
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373071"
---
# <a name="enrichment-for-data-sources-preview"></a>Îmbogățirea surselor de date (previzualizare)

Utilizați date din surse precum Microsoft și alți parteneri pentru a vă îmbogăți datele clienților înainte de unificarea datelor. Îmbogățirile sursă de date ajută la obținerea unei complete și a unei calități mai mari a datelor, care pot ajuta la obținerea unor rezultate mai bune odată ce vă unificați datele. De exemplu, utilizarea unui format normalizat și standardizat pentru adrese crește calitatea rezultatelor potrivirii. Pentru o listă de îmbogățiri acceptate, consultați [opțiuni de îmbogățire sursă de date acceptate](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Îmbogățiți un sursă de date

Trebuie să aveți permisiuni de Colaborator sau Administrator pentru a crea sau edita îmbogățiri. Pentru mai multe informații, consultați [Permisiuni](permissions.md).  

1. Mergi la **Date** > **Unifica**. Selectați entitatea pe care doriți să o îmbogățiți și selectați un atribut ca cheie primară pentru entitate. Pentru mai multe informații, vezi [Selectați cheia primară](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Accesați **Date** > **Surse de date**.
 
1. Selectați punctele de suspensie verticale de lângă sursă de date pe care doriți să o îmbogățiți și selectați **Îmbogăţi**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Pagina de îmbogățire a surselor de date.":::

   The **Descoperi** fila afișează [opțiuni de îmbogățire sursă de date acceptate](#supported-data-source-enrichments).

1. Selectați **Îmbogățiți-mi datele** pentru a configura o îmbogățire sursă de date. Numele entității de ieșire este completat automat.

## <a name="supported-data-source-enrichments"></a>Îmbogățirile sursă de date acceptate

Următoarele îmbogățiri sunt disponibile în prezent pentru sursele de date. Consultați pașii detaliați pentru îmbogățire pentru a afla cum să o configurați.

- [Adrese optimizate](enrichment-enhanced-addresses.md)
- [Date de identitate de la LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Gestionați îmbogățirile existente sursă de date

Accesați fila **Îmbogățirile mele** pentru a vedea toate îmbogățirile configurate.

Selectați îmbogățirea pentru a vedea opțiunile disponibile. De asemenea, puteți selecta punctele de suspensie (...) pe un element din listă pentru a vedea opțiunile. Dacă ați configurat mai multe îmbogățiri, puteți utiliza caseta de căutare pentru a o găsi rapid.

Puteți vizualiza, edita, rula sau șterge o îmbogățire sursă de date. Pentru mai multe informații, vezi [Gestionați îmbogățirile existente](enrichment-hub.md).
