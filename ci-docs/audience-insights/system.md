---
title: Configurarea sistemului în Detalii despre public
description: Aflați despre setările sistemului în capabilitatea de detalii privind publicul Dynamics 365 Customer Insights.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406706"
---
# <a name="system-configuration"></a>Configurări sistem

Pagina **Sistem** include patru file: **Stare**, **Planificare**, **Despre** și **General**.

> [!div class="mx-imgBorder"]
> ![Pagina de sistem](media/system-tabs.png "Pagina de sistem")

## <a name="status-tab"></a>Fila Stare

Fila **Stare** vă permite să urmăriți progresul ingestiei de date, exporturile de date, și mai multe procese importante ale produsului. Consultați informațiile din această filă pentru a vă asigura că procesele active sunt complete.

Această filă include tabele de stare pentru **Sursele de date**, **Procesele de sistem**, și **Pregătirea datelor**. Fiecare tabel urmărește **Numele** activității și entitatea corespunzătoare, **Starea** celei mai recente rulări și când a fost **Ultima actualizare**.

Vizualizați detaliile ultimelor câteva rulări ale activității selectând numele acesteia.

### <a name="status-types"></a>Tipuri de stări

Sunt șase tipuri de stări pentru sarcini. Următoarele tipuri de stare apar și pe paginile *Potrivire*, *Îmbinare*, *Surse de date*, *Segmente*, *Măsuri*, *Îmbogățire*, *Activități* și *Predicții*:

- **Se procesează:** Sarcina este în desfășurare. Starea se poate schimba în Reușită sau Eșec.
- **Reușită:** Sarcină finalizată cu succes.
- **Omis:** Sarcina a fost omisă. Unul sau mai multe dintre procesele din aval de care depinde această sarcină eșuează sau sunt omise.
- **Eșec:** Procesarea sarcinii a eșuat.
- **Anulat:** Procesarea a fost anulată de către utilizator înainte de finalizarea acesteia.
- **În coadă:** Prelucrarea este pusă în coadă și va începe odată ce toate sarcinile din aval sunt finalizate. Pentru mai multe informații, consultați [politici reîmprospătare](#refresh-policies).

### <a name="refresh-policies"></a>Politici de reîmprospătare

Această listă prezintă politicile de reîmprospătare pentru fiecare dintre principalele procese:

- **Surse de date:** Se execută conform cu [planificarea configurată](#schedule-tab). Nu depinde de niciun alt proces. Potrivirea depinde de finalizarea cu succes a acestui proces.
- **Potrivirea:** Se execută conform cu [planificarea configurată](#schedule-tab). Depinde de procesarea surselor de date utilizate în definiția potrivirii. Îmbinarea depinde de finalizarea cu succes a acestui proces.
- **Îmbinarea**: Se execută conform cu [planificarea configurată](#schedule-tab). Depinde de finalizarea procesului de potrivire. Segmentele, măsurile, îmbogățirea, căutarea, activitățile, predicțiile și pregătirea datelor depind de finalizarea cu succes a acestui proces.
- **Segmente**: Se execută manual (reîmprospătare unică) și în funcție de [planificarea configurată](#schedule-tab). Depinde de Îmbinare. Detaliile depind de procesarea acestuia.
- **Măsuri**: Se execută manual (reîmprospătare unică) și în funcție de [planificarea configurată](#schedule-tab). Depinde de Îmbinare.
- **Activități**: Se execută manual (reîmprospătare unică) și în funcție de [planificarea configurată](#schedule-tab). Depinde de Îmbinare.
- **Îmbogățire**: Se execută manual (reîmprospătare unică) și în funcție de [planificarea configurată](#schedule-tab). Depinde de Îmbinare.
- **Căutarea**: Se execută manual (reîmprospătare unică) și în funcție de [planificarea configurată](#schedule-tab). Depinde de Îmbinare.
- **Pregătire date:**: Se execută conform cu [planificarea configurată](#schedule-tab). Depinde de Îmbinare.
- **Detalii**: Se execută manual (reîmprospătare unică) și în funcție de [planificarea configurată](#schedule-tab). Depinde de segmente.

Selectați starea unei activități pentru a vedea detalii despre evoluția întregii lucrări în care a avut loc. Politicile de actualizare de mai sus vă pot ajuta să înțelegeți ce puteți face pentru a aborda o sarcină **Omisă** sau **În coadă**.

## <a name="schedule-tab"></a>Fila planificare

Folosiți fila **Planificare** pentru a planifica reîmprospătarea automată a tuturor [surselor de date ingerate](data-sources.md). Actualizările automate vă ajută să vă asigurați că actualizările din sursele de date sunt reflectate în profilurile dvs. de clienți unificate.

1. În detaliile despre public, accesați **Administrator** > **Sistem** și selectați fila **Planificare**.

2. Starea implicită pentru reîmprospătarea programată este **Dezactivat**. Pentru a activa actualizarea programată, schimbați comutarea din partea de sus a ecranului la **Activat**.

3. Alegeți între **Săptămânal** (implicit) și reîmprospătare **Zilnică**. Dacă intenționați să programați actualizări săptămânale, selectați una sau mai multe zile în care doriți să rulați actualizarea.

4. Setați-vă **Fusul orar**, apoi utilizați meniul vertical **Oră** pentru a seta temporizarea reîmprospătării. Când ați terminat, selectați **Setare**. Dacă doriți să programați mai multe actualizări într-o singură zi, selectați **Adăugați altă oră**.

5. Selectați **Salvare** pentru a vă aplica modificările.

## <a name="about-tab"></a>Despre filă

Fila **Despre** conține **Numele afișat** al organizației dvs., **ID de mediu** activ, **Regiunea**, și **ID sesiune**. Dacă aveți mai multe medii de lucru, ar trebui să le dați fiecăruia un nume de afișare ușor de identificat.

## <a name="general-tab"></a>Fila General

Există două opțiuni pe fila **General**, **Limba** și **Format țară/regiune**.

Aplicația [acceptă mai multe limbi](supported-languages.md). Pentru a schimba limba preferată, alegeți o **Limbă** din lista verticală.

Pentru a schimba formatarea dvs. preferată pentru date, oră și numere, utilizați lista verticală **Format țară/regiune**. O previzualizare de formatare este afișată sub acest câmp. Sistemul va sugera automat o selecție atunci când alegeți o nouă limbă.

Selectați **Salvare** pentru a confirma selecțiile.

## <a name="api-usage-tab"></a>Filă utilizare API

Găsiți detalii despre utilizarea API în timp real și vedeți ce evenimente s-au întâmplat într-un interval de timp dat. Pentru mai multe informații, consultați [Ingestie date în timp real](real-time-data-ingestion.md).
