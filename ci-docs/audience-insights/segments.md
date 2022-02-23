---
title: Segmente din statisticile publicului
description: Prezentare generală a segmentelor și modul de creare și gestionare a acestora.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 740d293b21f43b50201f23fcba109318823ef3af
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 01/15/2022
ms.locfileid: "7978074"
---
# <a name="segments-overview"></a>Prezentare generală a segmentelor

Segmentele vă permit să vă grupați clienții pe baza atributelor demografice, tranzacționale sau comportamentale. Puteți utiliza segmentele pentru a viza campanii promoționale, activități de vânzare și acțiuni de asistență pentru clienți pentru a vă atinge obiectivele de business.

Profilurile clienților care corespund filtrelor unei definiții de segmente sunt denumite *membrii* ai unui segment. Se aplică unele [limite ale serviciului](service-limits.md).

## <a name="create-a-new-segment"></a>Crearea unui nou segment

Sunt mai multe moduri de a crea un segment nou: 

# <a name="individual-consumers-b-to-c"></a>[Consumatori individuali (B2C)](#tab/b2c)

- Segment complex cu constructor de segmente: [Construiți-le pe ale noastre](segment-builder.md#create-a-new-segment) 
- Segmente simple cu un singur operator: [Segment rapid](segment-builder.md#quick-segments) 
- Modalitate bazată pe AI pentru a găsi clienți similari: [Clienți similari](find-similar-customer-segments.md) 
- Sugestii bazate pe AI bazate pe măsuri sau atribute: [Segmente sugerate pentru îmbunătățirea măsurilor](suggested-segments.md) 
- Sugestii bazate pe activități: [Segmente sugerate pe baza activității clienților](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Conturi de afaceri (B2B)](#tab/b2b)

- Segment complex cu constructor de segmente: [Construiți-le pe ale noastre](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Gestionarea segmentelor existente

Mergeș la **Segmente** pagina, pentru a vizualiza toate segmentele salvate și a le gestiona.

Fiecare segment este reprezentat de un rând care include informații suplimentare despre segment.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segment selectat cu listă verticală de opțiuni și opțiuni disponibile.":::

Următoarea acțiune este disponibilă când selectați un segment:

- **Vizualizați** detaliile segmentului, incluzând tendința numărului de membri o previzualizare a membrilor segmentului.
- **Editați** segmentul pentru a-i schimba proprietățile.
- **Creați duplicat** pentru un segment. Puteți alege să editați proprietățile imediat sau pur și simplu să salvați duplicatul.
- **Reîmprospătați** segmentul pentru a include cele mai recente date.
- **Activarea** sau **Dezactivarea** segmentului. Segmentele au două stări posibile - active sau inactive. Aceste stări sunt utile la editarea unui segment. Pentru segmentele inactive, definiția segmentului există, dar nu conține încă clienți. Când activați un segment, starea acestuia se schimbă din „inactiv” în „activ” și începe să caute clienți care se potrivesc cu definiția segmentului. În cazul în care o [reîmprospătare programată](system.md#schedule-tab) este configurată, segmentele inactive au **Starea** listată drept **Omis**, indicând că nici măcar nu a fost încercată o reîmprospătare. Când este activat un segment inactiv, acesta se va reîmprospăta și va fi inclus în reîmprospătările programate.
  Alternativ, puteți utiliza funcționalitatea **Planifică mai târziu** în lista derulantă **Activare/Dezactivare** pentru a specifica data și ora viitoare pentru activarea și dezactivarea unui anumit segment.
- **Redenumire** segment.
- **Descarcați** lista membrilor ca fișier .CSV.
- **Gestionați exporturile** pentru a vedea segmentul aferent exporturilor și a le gestiona. [Aflați mai multe despre exporturi.](export-destinations.md)
- **Se șterge** segmentul.

## <a name="refresh-segments"></a>Se reîmprospătează segmentele

Puteți reîmprospăta toate segmentele simultan, selectând **Reîmprospătați toate** pe pagina **Segmente** sau puteți reîmprospăta unul sau mai multe segmente atunci când le selectați și alegeți **Reîmprospătare** din opțiuni. În mod alternativ, puteți configura o actualizare recurentă în **Administrator** > **Sistem** > **Planificare**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="export-segments"></a>Export segmente

Puteți exporta un segment din pagina de segmente sau din [pagina exporturilor](export-destinations.md). 

1. Salt la pagina **Segmente**.

1. Selectați **Afișați mai multe [...]** pentru segmentul pe care doriți să-l exportați.

1. Selectați **Gestionați exporturile** din lista derulantă de acțiuni.

1. Pagina **Exporturi (versiune preliminară) pentru segment** se deschide. Puteți vedea toate exporturile configurate grupate în funcție de faptul că acestea conțin sau nu segmentul curent.

   1. Pentru a adăuga segmentul selectat la un export, **Editați** exportul respectiv pentru a selecta segmentul corespunzător, apoi salvați. În medii pentru clienți individuali, puteți selecta exportul în listă și selectați **Adăugați un segment** pentru a obține același rezultat.

   1. Pentru a crea un nou export cu segmentul selectat, selectați **Adăugați export**. Pentru mai multe informații despre crearea exporturilor, consultați [Configurați un nou export](export-destinations.md#set-up-a-new-export).

1. Selectați **Înapoi** pentru a reveni la pagina principală pentru segmente.

## <a name="view-processing-history-and-segment-members"></a>Vizualizați istoricul procesării și membrii segmentului

Puteți vedea date consolidate despre un segment trecând în revistă detaliile acestuia.

În pagina **Segmente**, selectați segmentul pe care doriți să-l revizuiți.

Partea superioară a paginii include un grafic de tendințe care vizualizează modificările numărului de membri. Treceți peste punctele de date pentru a vedea numărul de membri la o anumită dată.

Puteți actualiza intervalul de timp al vizualizării.

> [!div class="mx-imgBorder"]
> ![Intervalul de timp al segmentului.](media/segment-time-range.png "Intervalul de timp al segmentului")

Partea inferioară conține o listă a membrilor segmentului.

> [!NOTE]
> Câmpurile care apar în această listă se bazează pe atributele entităților segmentului dvs.
>
>Lista este o previzualizare a membrilor segmentului care se potrivesc și arată primele 100 de înregistrări ale segmentului dvs., astfel încât să puteți evalua rapid și să revizuiți definițiile, dacă este necesar. Pentru a vedea toate înregistrările potrivite, trebuie să [Exportați segmentul](export-destinations.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)] 
