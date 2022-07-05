---
title: Prezentare generală privind îmbogățirea datelor (previzualizare).
description: Utilizați capabilitățile de la Microsoft și alte servicii terțe pentru a vă îmbogăți datele clienților.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 6b6daab480db5e37830ff58b71dcdd3bbdbe46da
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053895"
---
# <a name="data-enrichment-preview-overview"></a>Prezentare generală privind îmbogățirea datelor (previzualizare).

Utilizați date din surse precum Microsoft și de la alți parteneri pentru a vă îmbogăți datele clienților. Îmbogățirile terților sunt configurate folosind [conexiuni](connections.md), pe care un administrator le înființează cu acreditări și oferă consimțământul pentru transferurile de date. Conexiunile pot fi utilizate de administratori și cei care contribuie pentru a configura îmbogățiri.  

## <a name="multiple-enrichments-of-the-same-type"></a>Îmbogățiri multiple de același tip

Entitatea care urmează să fie îmbogățită este specificată în timpul configurației de îmbogățire, care vă permite să îmbogățiți doar un subset de profiluri. De exemplu, îmbogățiți datele numai pentru un anumit segment. Puteți configura mai multe îmbogățiri de același tip și reutiliza aceeași conexiune. Unele îmbogățiri vor avea limite la numărul de îmbogățiri de același tip care pot fi create. Limitele și utilizarea curentă pot fi văzute pe fiecare țiglă de pe **Descoperi** fila din **Îmbogăţire** pagină.

## <a name="enrich-data-sources-before-unification"></a>Îmbogățiți sursele de date înainte de unificare

Vă puteți îmbogăți datele clienților înainte de unificarea datelor pentru a ajuta la creșterea calității potrivirii datelor. Pentru mai multe informații, vezi [sursă de date îmbogățire](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Creați o îmbogățire

Trebuie să aveți Contributor sau Administrator [permisiuni](permissions.md) pentru a crea sau edita îmbogățiri.

Accesați **Date** > **Îmbogățire**. The **Descoperi** fila arată toate opțiunile de îmbogățire acceptate.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pagină hub de îmbogățire.":::

# <a name="individual-consumers-b-to-c"></a>[Consumatori individuali (B2C)](#tab/b2c)

- [Identitatea AbiliTec](enrichment-liveramp.md) oferit de LiveRamp AbiliTec
- [Branduri](enrichment-microsoft.md) furnizate de Microsoft
- [Date demografice](enrichment-experian.md) furnizate de Experian
- [Adrese îmbunătățite](enrichment-enhanced-addresses.md) furnizate de Microsoft
- [Interese](enrichment-microsoft.md) furnizate de Microsoft
- [Date despre locație](enrichment-azure-maps.md) furnizat de Microsoft Azure Hărți
- [Date despre locație](enrichment-here.md) furnizate de HERE Technologies
- [Date personalizate SFTP](enrichment-SFTP-custom-import.md) prin Secure File Transfer Protocol (SFTP)

# <a name="business-accounts-b-to-b"></a>[Conturi de afaceri (B2B)](#tab/b2b)

- [Date despre implicarea contului](enrichment-office.md) furnizate de Microsoft
- [Datele companiei](enrichment-dnb.md) oferit de Dun & Bradstreet
- [Datele companiei](enrichment-leadspace.md) furnizate de Leadspace
- [Adrese îmbunătățite](enrichment-enhanced-addresses.md) furnizate de Microsoft
- [Date îmbunătățite ale companiei](enrichment-enhanced-company-data.md) furnizate de Microsoft
- [Date despre locație](enrichment-azure-maps.md) furnizat de Microsoft Azure Hărți
- [Date despre locație](enrichment-here.md) furnizate de HERE Technologies
- [Date personalizate SFTP](enrichment-SFTP-custom-import.md) prin Secure File Transfer Protocol (SFTP)

---

## <a name="manage-existing-enrichments"></a>Gestionarea îmbogățirilor existente

Accesați **Date** > **Îmbogățire**. Pe **Îmbogățirile mele** fila, vizualizați îmbogățirile configurate, starea acestora, numărul de clienți îmbogățiți și ultima dată când datele au fost reîmprospătate. Puteți sorta lista de îmbogățiri după orice coloană sau puteți utiliza caseta de căutare pentru a găsi îmbogățirea pe care doriți să o gestionați.

Selectați îmbogățirea pentru a vedea acțiunile disponibile.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opțiuni de gestionare a îmbogățirilor din lista îmbogățirilor.":::

- **Vizualizare** detalii de îmbogățire cu numărul de profiluri de clienți îmbogățite.
- **Editați** configurația de îmbogățire.
- [**Alerga**](#run-or-refresh-enrichments) îmbogățirea pentru a actualiza profilurile clienților cu cele mai recente date. Rulați mai multe îmbogățiri simultan, selectându-le în listă.
- **Activati** sau **Dezactivați** o îmbogățire. Îmbogățirile inactive nu vor fi reîmprospătate în timpul unui [reîmprospătare programată](system.md#schedule-tab).
- **Ștergeți** îmbogățirea.

De asemenea, puteți crea [segmente](segments.md) sau [măsuri](measures.md) din îmbogăţiri.

## <a name="run-or-refresh-enrichments"></a>Rulați sau reîmprospătați îmbogățirile

Odată executate, îmbogățirile pot fi reîmprospătate într-un program automat sau reîmprospătate manual la cerere.

1. Pentru a reîmprospăta manual una sau mai multe îmbogățiri, selectați-le și alegeți **Alerga**. La [programați o reîmprospătare automată](system.md#schedule-tab), mergi la **Admin** > **Sistem** > **Programa**. Timpul de procesare depinde de dimensiunea datelor clienților dvs.

1. Opțional, [vezi progresul procesului de îmbogățire](#see-the-progress-of-the-enrichment-process).

1. După finalizarea procesului de îmbogățire, accesați **Îmbogățirile mele** pentru a examina datele profilurilor client nou îmbogățite, ora ultimei actualizări și numărul de profiluri îmbogățite.

1. Selectați îmbogățirea pentru a vedea [rezultate de îmbogățire](#view-enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Vedeți progresul procesului de îmbogățire

Puteți găsi detalii despre procesarea unei îmbogățiri, inclusiv starea acesteia și problemele potențiale în timp ce este reîmprospătată sau după finalizarea unei reîmprospătări. Înțelegeți ce procese sunt implicate pentru a reîmprospăta o îmbogățire și cât timp a durat pentru a rula procesele. Starea de îmbogățire este acceptată pentru Experian, Leadspace, HERE Technologies, SFTP Import și Azure Maps.

1. Accesați **Date** > **Îmbogățire**.
1. În **Îmbogățirile mele** fila, selectați starea îmbogățirii pentru a deschide un panou lateral.
1. În panoul **Detalii despre progres**, extindeți secțiunea **Îmbogățiri**.
1. Sub îmbogățirea pe care doriți să vedeți progresul, selectați **Vezi detalii**.
1. În panoul **Detalii despre activitate**, selectați **Arată detaliile** pentru a vedea procesele care sunt implicate în actualizarea îmbogățirii și a statutului lor.

## <a name="view-enrichment-results"></a>Vedeți rezultatele îmbogățirii

După o rundă de îmbogățire completă, examinați rezultatele îmbogățirii.

1. Accesați **Date** > **Îmbogățire**.
1. În **Îmbogățirile mele** fila, selectați îmbogățirea pe care doriți să o vizualizați.

Toate îmbogățirile arată informații de bază, cum ar fi numărul de profiluri îmbogățite și numărul de profiluri îmbogățite în timp. The **Previzualizarea clienților îmbogățiți** țigla arată un eșantion al entității de îmbogățire generată. Pentru a vedea o vizualizare detaliată, selectați **Vezi mai mult** și selectați **Date** fila.

:::image type="content" source="media/enrichments-results.png" alt-text="Pagina cu rezultate îmbogățiri.":::

Dacă este disponibil, **Număr de clienți îmbogățiți pe domeniu** oferă o detaliere a acoperirii fiecărui câmp îmbogățit.

Unele îmbogățiri prezintă și informații specifice tipului de îmbogățire. Pentru mai multe informații, consultați documentația aferentă.

[!INCLUDE [footer-include](includes/footer-banner.md)]
