---
title: Prezentare generală a segmentelor
description: Prezentare generală a segmentelor și modul de creare și gestionare a acestora.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: d4de3a6af6bc7d54305a23e3fbd3cc95d464d352
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304810"
---
# <a name="segments-overview"></a>Prezentare generală a segmentelor

Segmentele vă permit să vă grupați clienții pe baza atributelor demografice, tranzacționale sau comportamentale. Puteți utiliza segmentele pentru a viza campanii promoționale, activități de vânzare și acțiuni de asistență pentru clienți pentru a vă atinge obiectivele de business.

Profilurile de clienți sau de contact care se potrivesc cu filtrele unei definiții de segment sunt denumite *membrii* a unui segment. Se aplică unele [limite ale serviciului](/dynamics365/customer-insights/service-limits).

## <a name="create-a-segment"></a>Creați un segment

Alegeți cum să creați un segment în funcție de publicul țintă.

# <a name="individual-consumers-b-to-c"></a>[Consumatori individuali (B2C)](#tab/b2c)

- Segmente complexe cu generator de segmente: [Construiește-ți propriul](segment-builder.md)
- Segmente simple cu un singur operator: [Segment rapid](segment-quick.md)
- Mod bazat pe inteligență artificială de a găsi clienți similari: [Clienți similari](find-similar-customer-segments.md)
- Sugestii bazate pe AI bazate pe măsuri sau atribute: [Segmente sugerate pe baza măsurilor](suggested-segments.md)
- Sugestii bazate pe activități: [Segmente sugerate pe baza activității clienților](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Conturi de afaceri (B2B)](#tab/b2b)

Segment de conturi sau segment de contacte (previzualizare) cu generatorul de segmente: [Construiește-ți propriul](segment-builder.md)

> [!NOTE]
> Majoritatea destinațiilor de export necesită informații de contact în scopuri de marketing. Prin urmare, creați segmente de contacte pe care să le utilizați pentru acele exporturi.

---

## <a name="manage-existing-segments"></a>Gestionarea segmentelor existente

Du-te la **Segmente** pentru a vedea segmentele pe care le-ați creat, starea și starea acestora și ultima dată când datele au fost reîmprospătate. Puteți sorta lista de segmente după orice coloană sau puteți utiliza caseta de căutare pentru a găsi segmentul pe care doriți să îl gestionați.

> [!TIP]
> În mediile B-to-B, **Tip de public** coloana identifică dacă un segment se bazează pe conturi sau persoane de contact.

Selectați un segment pentru a vedea acțiunile disponibile.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segment selectat cu listă verticală de opțiuni și opțiuni disponibile." lightbox="media/segments-selected-segment.png":::

- [**Vedere**](#view-segment-details) detaliile segmentului, inclusiv tendința numărului de membri și o previzualizare a membrilor segmentului.
- **Descarcați** lista membrilor ca fișier .CSV.
- **Editați** segmentul pentru a-i schimba proprietățile.
- **Creați duplicat** pentru un segment. Puteți alege să editați proprietățile acestuia imediat sau să salvați duplicatul.
- [**Reîmprospăta**](#refresh-segments) segmentul să includă cele mai recente date.
- **Activarea** sau **Dezactivarea** segmentului. Segmentele inactive nu vor fi reîmprospătate în timpul unui [reîmprospătare programată](schedule-refresh.md) și au **stare** enumerate ca **Sărit**, indicând că nici măcar nu a fost încercată o reîmprospătare. Segmentele active sunt reîmprospătate în funcție de tipul lor: static sau dinamic.
- **Faceți statică** sau **Faceți dinamic** tipul de segment. Segmentele statice trebuie reîmprospătate manual. Segmentele dinamice sunt reîmprospătate automat în timpul reîmprospătărilor sistemului.
- [**Găsiți clienți similari**](find-similar-customer-segments.md) din segment.
- **Redenumire** segment.
- **Etichetă** la [gestionați etichetele](work-with-tags-columns.md#manage-tags) pentru segment.
- [**Gestionați exporturile**](#export-segments) pentru a vedea segmentele legate de export și pentru a le gestiona. [Aflați mai multe despre exporturi.](export-destinations.md)
- **Se șterge** segmentul.
- **Coloane** la [personalizați coloanele](work-with-tags-columns.md#customize-columns) acel afișaj.
- **Filtru** la [filtrează pe etichete](work-with-tags-columns.md#filter-on-tags).
- **Căutați numele** pentru a căuta după numele segmentului.

## <a name="view-segment-details"></a>Vizualizați detaliile segmentului

Pe **Segmente** pagina, selectați un segment pentru a vizualiza istoricul procesării și membrii segmentului.

Partea superioară a paginii include un grafic de tendințe care vizualizează modificările numărului de membri. Treceți peste punctele de date pentru a vedea numărul de membri la o anumită dată. Modificați intervalul de timp al vizualizării.

:::image type="content" source="media/segment-time-range.png" alt-text="Intervalul de timp al segmentului.":::

Partea inferioară conține o listă a membrilor segmentului.

> [!NOTE]
> Câmpurile care apar în această listă se bazează pe atributele entităților segmentului dvs.
>
> Lista este o previzualizare a membrilor segmentului care se potrivesc și arată primele 100 de înregistrări ale segmentului dvs., astfel încât să puteți evalua rapid și să revizuiți definițiile, dacă este necesar. Pentru a vedea toate înregistrările care se potrivesc, selectați **Vezi mai mult** care deschide [**Entități**](entities.md) pagina sau [exportați segmentul](export-destinations.md).

## <a name="refresh-segments"></a>Se reîmprospătează segmentele

Segmentele pot fi reîmprospătate în program automat sau manual, la cerere. Pentru a reîmprospăta manual unul sau mai multe segmente, selectați-le și alegeți **Reîmprospăta**.

La [programați o reîmprospătare automată](schedule-refresh.md), mergi la **Admin** > **Sistem** > **Programa**. Se aplică următoarele reguli:

- Toate segmentele cu tipul **Dinamic** sau **Expansiune** va fi reîmprospătat automat la cadența setată. Odată ce reîmprospătarea este completă, **stare** indică dacă au existat probleme la reîmprospătarea segmentului. The **Ultima reîmprospătare** afișează un marcaj temporal al ultimei reîmprospătări reușite. Dacă apare o eroare, selectați eroarea pentru a vedea detalii despre ceea ce s-a întâmplat.
- Segmente cu tipul **Static** *nu va* fi reîmprospătat automat. The **Ultima reîmprospătare** afișează un marcaj temporal al ultimei rulări sau reîmprospătare manuală a segment static.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Export segmente

Exportați segmente în alte aplicații pentru a utiliza în continuare datele. Exportați un segment din pagina de segmente sau din [pagina de exporturi](export-destinations.md).

1. Du-te la **Segmente** pagina și selectați segmentul pe care doriți să îl exportați.

1. Selectați **Gestionați exporturile**. Pagina **Exporturi (versiune preliminară) pentru segment** se deschide. Vizualizați toate exporturile configurate grupate în funcție de dacă acestea conțin sau nu segmentul curent.

   1. Pentru a adăuga segmentul selectat la un export, **Editați** exportul respectiv pentru a selecta segmentul corespunzător, apoi salvați. În mediile pentru clienți individuali, selectați exportul din listă și selectați **Adăugați un segment** pentru a obține același rezultat.

   1. Pentru a crea un nou export cu segmentul selectat, selectați **Adăugați export**. Pentru mai multe informații despre crearea exporturilor, consultați [Configurați un nou export](export-destinations.md#set-up-a-new-export).

1. Selectați **Înapoi** pentru a reveni la pagina principală pentru segmente.

## <a name="track-usage-of-a-segment"></a>Urmăriți utilizarea unui segment

Dacă utilizați segmente în aplicații care se bazează pe aceleași Microsoft Dataverse organizație care este conectată cu Customer Insights, puteți urmări utilizarea unui segment. Pentru [Segmentele Customer Insights utilizate în călătoriile clienților din Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), sistemul vă informează despre utilizarea segmentului respectiv.

Când editați un segment care este utilizat în mediul Customer Insights sau într-un călătoria clientului în Marketing, un banner în [constructor de segmente](segment-builder.md) vă informează despre dependențe. Inspectați detaliile dependenței direct din banner sau selectând **Utilizare** în constructorul de segmente.

The **Utilizarea segmentului** panoul arată detaliile despre utilizarea acestui segment în Dataverse aplicații bazate pe Pentru segmentele utilizate în călătoriile clienților, veți găsi un link pentru a inspecta călătoria în Marketing unde este utilizat acest segment. Dacă aveți permisiuni pentru a accesa aplicația Marketing, vedeți mai multe detalii acolo.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Panoul lateral cu detalii despre utilizarea segmentului în generatorul de segmente.":::

Sistemul vă informează despre utilizarea unui segment urmărit atunci când încercați să-l ștergeți. Dacă segmentul pe care urmează să îl ștergeți este folosit într-un călătoria clientului în Marketing, acea călătorie se va opri pentru toți utilizatorii din segment. Dacă călătoria face parte dintr-o campanie de marketing, ștergerea va afecta campania în sine. Cu toate acestea, puteți șterge segmentul în ciuda avertismentelor.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Casetă de dialog pentru a confirma ștergerea segmentului atunci când un segment este utilizat într-un Dataverse aplicarea.":::

### <a name="supported-apps"></a>Aplicații acceptate

Utilizarea este în prezent urmărită în următoarele Dataverse aplicații bazate pe:

- [Călătoriile clienților în Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
