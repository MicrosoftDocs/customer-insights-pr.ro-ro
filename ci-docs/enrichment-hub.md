---
title: Îmbogățire profiluri de clienți unificate
description: Folosiți capacitățile pentru a vă îmbogăți datele clienților.
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
ms.openlocfilehash: 3bbe8b829a6698da55d84709dbab6c36aa76792a
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954056"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Îmbogățirea profilurilor clienților (previzualizare)

Utilizați date din surse precum Microsoft și de la alți parteneri pentru a vă îmbogăți datele clienților.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pagină hub de îmbogățire.":::

Mergi la **Date** > **Îmbogăţire** pentru a lucra cu opțiuni de îmbogățire.  

Trebuie să aveți permisiuni de Colaborator sau Administrator pentru a crea sau edita îmbogățirile. Pentru mai multe informații, consultați [Permisiuni](permissions.md).

Pe fila **Descoperiți**, veți găsi toate opțiunile de îmbogățire acceptate.

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

Pe fila **Îmbogățirile mele**, puteți vedea îmbogățirile pe care le-ați configurat și le puteți edita proprietățile. De asemenea, puteți crea [segmente](segments.md) sau [măsuri](measures.md) din îmbogăţiri.

## <a name="manage-existing-enrichments"></a>Gestionarea îmbogățirilor existente

Accesați fila **Îmbogățirile mele** pentru a vedea toate îmbogățirile configurate. Fiecare îmbogățire este reprezentată ca un rând care include informații suplimentare despre îmbogățire.

Selectați îmbogățirea pentru a vedea opțiunile disponibile. De asemenea, puteți selecta elipsa verticală (&vellip;) pe un element din listă pentru a vedea opțiunile. Dacă ați configurat mai multe îmbogățiri, puteți utiliza caseta de căutare pentru a o găsi rapid.

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

Entitatea care urmează să fie îmbogățită este specificată în timpul configurației de îmbogățire, care vă permite să îmbogățiți doar un subset de profiluri. De exemplu, îmbogățiți datele numai pentru un anumit segment. Puteți configura mai multe îmbogățiri de același tip și reutiliza aceeași conexiune. Unele îmbogățiri vor avea limite la numărul de îmbogățiri de același tip care pot fi create. Limitele și utilizarea curentă pot fi văzute pe fiecare țiglă de pe **Descoperi** fila din **Îmbogăţire** pagină.

## <a name="enrich-data-sources-before-unification"></a>Îmbogățiți sursele de date înainte de unificare

Vă puteți îmbogăți datele clienților înainte de unificarea datelor pentru a ajuta la creșterea calității potrivirii datelor. Pentru mai multe informații, vezi [sursă de date îmbogățire](data-sources-enrichment.md).

## <a name="run-or-refresh-enrichments"></a>Rulați sau reîmprospătați îmbogățirile

1. Pentru a începe procesul de îmbogățire, selectați **Alerga**. Sau lăsați sistemul să ruleze automat îmbogățirea ca parte a unui [reîmprospătare programată](system.md#schedule-tab). Timpul de procesare depinde de dimensiunea datelor clienților dvs.

1. Opțional, [vezi progresul procesului de îmbogățire](#see-the-progress-of-the-enrichment-process).

1. După finalizarea procesului de îmbogățire, accesați **Îmbogățirile mele** pentru a examina datele profilurilor client nou îmbogățite, ora ultimei actualizări și numărul de profiluri îmbogățite.

1. Selectați îmbogățirea pentru a vedea [rezultate de îmbogățire](#enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Vedeți progresul procesului de îmbogățire

Puteți găsi detalii despre procesarea unei îmbogățiri, inclusiv starea acesteia și problemele potențiale în timp ce este reîmprospătată sau după finalizarea unei reîmprospătări. Înțelegeți ce procese sunt implicate pentru a reîmprospăta o îmbogățire și cât timp a durat pentru a rula procesele. Starea de îmbogățire este acceptată pentru Experian, Leadspace, HERE Technologies, SFTP Import și Azure Maps.

1. Accesați **Date** > **Îmbogățire**.
1. În **Îmbogățirile mele** fila, selectați starea îmbogățirii pentru a deschide un panou lateral.
1. În panoul **Detalii despre progres**, extindeți secțiunea **Îmbogățiri**.
1. Sub îmbogățirea pe care doriți să vedeți progresul, selectați **Vezi detalii**.
1. În panoul **Detalii despre activitate**, selectați **Arată detaliile** pentru a vedea procesele care sunt implicate în actualizarea îmbogățirii și a statutului lor.

## <a name="enrichment-results"></a>Rezultate de îmbogățire

După o rundă de îmbogățire completă, examinați rezultatele îmbogățirii.

1. Accesați **Date** > **Îmbogățire**.
1. În **Îmbogățirile mele** fila, selectați îmbogățirea despre care doriți informații.

Toate îmbogățirile arată informații de bază, cum ar fi numărul de profiluri îmbogățite și numărul de profiluri îmbogățite în timp. The **Previzualizarea clienților îmbogățiți** țigla arată un eșantion al entității de îmbogățire generată. Pentru a vedea o vizualizare detaliată, selectați **Vezi mai mult** și selectați **Date** fila.

:::image type="content" source="media/enrichments-results.png" alt-text="Pagina cu rezultate îmbogățiri.":::

Dacă este disponibil, **Număr de clienți îmbogățiți pe domeniu** oferă o detaliere a acoperirii fiecărui câmp îmbogățit.

Unele îmbogățiri prezintă și informații specifice tipului de îmbogățire. Pentru mai multe informații, consultați documentația aferentă.

[!INCLUDE [footer-include](includes/footer-banner.md)]