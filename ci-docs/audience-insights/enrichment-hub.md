---
title: Îmbogățire profiluri de clienți unificate
description: Folosiți capacitățile pentru a vă îmbogăți datele clienților.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5d5e12ee44dfa40c470738eaee5c68fdf23d1b2d
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617570"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Îmbogățirea profilurilor clienților (previzualizare)

Utilizați date din surse precum Microsoft și de la alți parteneri pentru a vă îmbogăți datele clienților.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pagină hub de îmbogățire.":::

În statisticile publicului, accesați **Date** > **Îmbogățire** pentru a lucra cu opțiuni de îmbogățire.  

Trebuie să aveți permisiuni de Colaborator sau Administrator pentru a crea sau edita îmbogățirile. Pentru mai multe informații, consultați [Permisiuni](permissions.md).

Pe fila **Descoperiți**, veți găsi toate opțiunile de îmbogățire acceptate.

# <a name="individual-customers-b2c"></a>[Clienți individuali (B2C)](#tab/b2c)

- [Branduri](enrichment-microsoft.md) furnizate de Microsoft
- [Interese](enrichment-microsoft.md) furnizate de Microsoft
- [Adrese îmbunătățite](enrichment-enhanced-addresses.md) furnizate de Microsoft 
- [Date demografice](enrichment-experian.md) furnizate de Experian
- [Date particularizate](enrichment-SFTP-custom-import.md) prin Protocol de transfer securizat al fișierelor (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) furnizat de Microsoft

# <a name="business-accounts-b2b"></a>[Conturi de business (B2B)](#tab/b2b)

- [Datele companiei](enrichment-leadspace.md) furnizate de Leadspace
- [Adrese îmbunătățite](enrichment-enhanced-addresses.md) furnizate de Microsoft 
- [Date despre locație](enrichment-here.md) furnizate de HERE Technologies 
- [Date particularizate](enrichment-SFTP-custom-import.md) prin Protocol de transfer securizat al fișierelor (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) furnizat de Microsoft

---

Pe fila **Îmbogățirile mele**, puteți vedea îmbogățirile pe care le-ați configurat și le puteți edita proprietățile.

## <a name="manage-existing-enrichments"></a>Gestionarea îmbogățirilor existente

Accesați fila **Îmbogățirile mele** pentru a vedea toate îmbogățirile configurate. Fiecare îmbogățire este reprezentată ca un rând care include informații suplimentare despre îmbogățire.

Selectați îmbogățirea pentru a vedea opțiunile disponibile. De asemenea, puteți selecta punctele de suspensie (...) pe un element din listă pentru a vedea opțiunile. Dacă ați configurat mai multe îmbogățiri, puteți utiliza caseta de căutare pentru a o găsi rapid.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opțiuni de gestionare a îmbogățirilor din lista îmbogățirilor.":::

- **Vizualizare** detalii de îmbogățire cu numărul de profiluri de clienți îmbogățite.
- **Editați** configurația de îmbogățire.
- **Rulați** îmbogățirea pentru actualizarea profilurilor clienților cu cele mai recente date.
- **Dezactivați** o îmbogățire existentă pentru a o opri din actualizarea automată cu fiecare actualizare programată. Datele din ultima actualizare reușită vor continua să fie disponibile. **Activați** o îmbogățire inactivă pentru a reporni actualizarea automată cu fiecare actualizare programată.
- **Ștergeți** îmbogățirea.

Rulați sau dezactivați mai multe îmbogățiri simultan selectându-le în listă. Opțiunile de vizualizare și editare nu sunt disponibile ca acțiune în bloc. Lucrează doar pentru o singură îmbogățire la un moment dat.

## <a name="enrichments-and-connections"></a>Îmbogățiri și conexiuni

Îmbogățirile terților sunt configurate folosind [conexiuni](connections.md), pe care un administrator le înființează cu acreditări și oferă consimțământul pentru transferurile de date. Conexiunile pot fi utilizate de administratori și cei care contribuie pentru a configura îmbogățiri.  

## <a name="multiple-enrichments-of-the-same-type"></a>Îmbogățiri multiple de același tip

Entitatea care urmează să fie îmbogățită este specificată în timpul configurației de îmbogățire, care vă permite să îmbogățiți doar un subset de profiluri. De exemplu, îmbogățiți datele numai pentru un anumit segment. Puteți configura mai multe îmbogățiri de același tip și reutiliza aceeași conexiune. Unele îmbogățiri vor avea limite la numărul de îmbogățiri de același tip care pot fi create. Limitele și utilizarea curentă pot fi văzute pe pagina **Îmbogățire**.

## <a name="see-the-progress-of-the-enrichment-process"></a>Vedeți progresul procesului de îmbogățire

Puteți găsi detalii despre procesarea unei îmbogățiri, inclusiv starea acesteia și problemele potențiale în timp ce este reîmprospătată sau după finalizarea unei reîmprospătări. Înțelegeți ce procese sunt implicate pentru a reîmprospăta o îmbogățire și cât timp a durat pentru a rula procesele. Starea de îmbogățire este acceptată pentru Experian, Leadspace, HERE Technologies, SFTP Import și Azure Maps.

Pentru a vedea starea de îmbogățire

1. Accesați **Date** > **Îmbogățire**. 
1. În fila **Îmbogățirile mele**, selectați starea unei îmbogățiri pentru a deschide un panou lateral. 
1. În panoul **Detalii despre progres**, extindeți secțiunea **Îmbogățiri**. 
1. Sub îmbogățirea pe care doriți să vedeți progresul, selectați **Vezi detalii**. 
1. În panoul **Detalii despre activitate**, selectați **Arată detaliile** pentru a vedea procesele care sunt implicate în actualizarea îmbogățirii și a statutului lor. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
