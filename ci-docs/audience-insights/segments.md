---
title: Segmente din statisticile publicului
description: Prezentare generală a segmentelor și modul de creare și gestionare a acestora.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a7fa6515bd6e79dedfb21aa0f0b8e24b873a6771
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034027"
---
# <a name="segments-overview"></a>Prezentare generală a segmentelor

Segmentele vă permit să vă grupați clienții pe baza atributelor demografice, tranzacționale sau comportamentale. Puteți utiliza segmentele pentru a viza campanii promoționale, activități de vânzare și acțiuni de asistență pentru clienți pentru a vă atinge obiectivele de business.

Profilurile clienților care corespund filtrelor unei definiții de segmente sunt denumite *membrii* ai unui segment. Se aplică unele [limite ale serviciului](service-limits.md).

## <a name="create-a-new-segment"></a>Crearea unui nou segment

Sunt mai multe moduri de a crea un segment nou: 

- Segment complex cu constructor de segmente: [Segment gol](segment-builder.md#create-a-new-segment)
- Segmente simple cu un singur operator: [Segment rapid](segment-builder.md#quick-segments)
- Modalitate bazată pe AI pentru a găsi clienți similari: [Clienți similari](find-similar-customer-segments.md)
- Sugestii bazate pe AI bazate pe măsuri sau atribute: [Segmente sugerate pentru îmbunătățirea măsurilor](suggested-segments.md)
- Sugestii bazate pe activități: [Segmente sugerate pe baza activității clienților](suggested-segments-activity.md)

## <a name="get-insights-on-existing-segments"></a>Obțineți informații despre segmentele existente

Descoperiți informații suplimentare despre segmentele dvs. existente cu [Statistici de segment](segment-insights.md). Aflați ce diferențiază două segmente sau ce au în comun.

## <a name="find-similar-customers"></a>Găsiți clienți similari

Găsiți clienți care sunt similari cu membrii unui segment selectat cu ajutorul inteligenței artificiale. Pentru informaţii suplimentare, consultaţi [clienți similari ](find-similar-customer-segments.md).

## <a name="manage-existing-segments"></a>Gestionarea segmentelor existente

Mergeș la **Segmente** pagina, pentru a vizualiza toate segmentele salvate și a le gestiona.

Fiecare segment este reprezentat de un rând care include informații suplimentare despre segment.

> [!div class="mx-imgBorder"]
> ![Opțiuni de gestionare a unui segment existent](media/segments-selected-segment.png "Opțiuni de gestionare a unui segment existent")

Următoarea acțiune este disponibilă când selectați un segment:

- **Vizualizați** detaliile segmentului, incluzând tendința numărului de membri o previzualizare a membrilor segmentului.
- **Editați** segmentul pentru a-i schimba proprietățile.
- **Creați duplicat** pentru un segment. Puteți alege să editați proprietățile imediat sau pur și simplu să salvați duplicatul.
- **Reîmprospătați** segmentul pentru a include cele mai recente date.
- **Activarea** sau **Dezactivarea** segmentului. Segmentele au două stări posibile - active sau inactive. Aceste stări sunt utile la editarea unui segment. Pentru segmentele inactive, definiția segmentului există, dar nu conține încă clienți. Când activați un segment, starea acestuia se schimbă din „inactiv” în „activ” și începe să caute clienți care se potrivesc cu definiția segmentului. În cazul în care o [reîmprospătare programată](system.md#schedule-tab) este configurată, segmentele inactive au **Starea** listată drept **Omis**, indicând că nici măcar nu a fost încercată o reîmprospătare. Când este activat un segment inactiv, acesta se va reîmprospăta și va fi inclus în reîmprospătările programate.
  Alternativ, puteți utiliza funcționalitatea **Planifică mai târziu** în lista derulantă **Activare/Dezactivare** pentru a specifica data și ora viitoare pentru activarea și dezactivarea unui anumit segment.
- **Redenumire** segment.
- **Descarcați** lista membrilor ca fișier .CSV.
- Opțiunea **Adăugare la** trimite lista ID-urilor de clienți din segment pentru procesare într-o altă aplicație.
- **Se șterge** segmentul.

## <a name="refresh-segments"></a>Se reîmprospătează segmentele

Puteți reîmprospăta toate segmentele simultan, selectând **Reîmprospătați toate** pe pagina **Segmente** sau puteți reîmprospăta unul sau mai multe segmente atunci când le selectați și alegeți **Reîmprospătare** din opțiuni. În mod alternativ, puteți configura o actualizare recurentă în **Administrator** > **Sistem** > **Planificare**.

> [!TIP]
> Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese. În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies). Puteți selecta starea unui proces pentru a vedea detalii despre evoluția întregii lucrări. După selectarea **Vizualizare detalii** pentru una dintre sarcinile jobului, găsiți informații suplimentare: timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate sarcinii.

## <a name="view-processing-history-and-segment-members"></a>Vizualizați istoricul procesării și membrii segmentului

Puteți vedea date consolidate despre un segment trecând în revistă detaliile acestuia.

În pagina **Segmente**, selectați segmentul pe care doriți să-l revizuiți.

Partea superioară a paginii include un grafic de tendințe care vizualizează modificările numărului de membri. Treceți peste punctele de date pentru a vedea numărul de membri la o anumită dată.

Puteți actualiza intervalul de timp al vizualizării.

> [!div class="mx-imgBorder"]
> ![Intervalul de timp al segmentului](media/segment-time-range.png "Intervalul de timp al segmentului")

Partea inferioară conține o listă a membrilor segmentului.

> [!NOTE]
> Câmpurile care apar în această listă se bazează pe atributele entităților segmentului dvs.
>
>Lista este o previzualizare a membrilor segmentului care se potrivesc și arată primele 100 de înregistrări ale segmentului dvs., astfel încât să puteți evalua rapid și să revizuiți definițiile, dacă este necesar. Pentru a vedea toate înregistrările potrivite, trebuie să [Exportați segmentul](export-destinations.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
