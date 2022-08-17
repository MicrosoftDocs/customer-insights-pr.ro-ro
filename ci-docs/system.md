---
title: Vedeți configurația sistemului
description: Aflați mai multe despre setările de sistem din Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2498814a3d2e6330124fb97c036b9b310bcf1f7a
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246262"
---
# <a name="view-system-configuration"></a>Vedeți configurația sistemului

Vizualizați informații despre sistem, starea sistemului și utilizarea API-ului.

## <a name="view-api-usage"></a>Vedeți utilizarea API-ului

Vizualizați detalii despre utilizarea API-ului în timp real și vedeți ce evenimente au avut loc într-un interval de timp dat.

1. Mergi la **Admin** > **Sistem** și selectați **Utilizarea API-ului** fila.

1. **Selectați un interval de timp** A vedea.

   The **Utilizarea API-ului** pagina contine trei sectiuni:

   - **Apeluri API** - o diagramă care vizualizează numărul agregat de apeluri către API în intervalul de timp selectat.
   - **Transfer de date** - o diagramă care arată cantitatea de date care a fost transferată prin API în intervalul de timp selectat.
   - **Operațiuni** - un tabel cu rânduri pentru fiecare operațiune API disponibilă și detalii despre utilizarea operațiunilor. Selectați un nume de operație la care să mergeți [referința API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operațiuni care folosesc [asimilarea datelor în timp real](real-time-data-ingestion.md) conține un simbol binocular pentru a vizualiza în timp real utilizarea API-ului.

   1. Selectați binoclul pentru a deschide **Utilizare API în timp real** panoul care conține detalii de utilizare pentru operațiune.
   1. **Selectați un interval de timp** A vedea.
   1. Folosește **A se grupa cu** casetă pentru a alege cum să vă prezentați cel mai bine interacțiunile în timp real. Grupați datele după API **Metodă**, **calificat al entității** (entitate ingerată), **Creat de** (sursa evenimentului), **Rezultat** (succes sau eșec) sau **Coduri de eroare**. Datele sunt disponibile ca un grafic istoric și ca un tabel.

## <a name="view-system-information"></a>Vizualizați informații despre sistem

Vizualizați numele afișat al mediului, ID-ul, regiunea, tipul și ID-ul sesiunii.

1. Mergi la **Admin** > **Sistem** și selectați **Despre** fila.

1. Pentru a vizualiza limba și țara/regiunea, selectați **General** fila.

### <a name="update-preferred-language-or-countryregion"></a>Actualizați limba sau țara/regiunea preferată

Informații despre clienți [acceptă multe limbi](/dynamics365/get-started/availability). Aplicația vă folosește preferințele de limbă pentru a afișa elemente precum meniul, textul de etichete și mesajele de sistem în limba dvs. preferată.

Datele și informațiile importate și pe care le-ați introdus manual nu sunt traduse.

1. Mergi la **Admin** > **Sistem** și selectați **General** fila.

1. Pentru a schimba limba preferată, alegeți o **Limbă** din lista verticală.

1. Pentru a schimba formatarea dvs. preferată pentru date, oră și numere, utilizați lista verticală **Format țară/regiune**. Este afișată o previzualizare a formatării. Sistemul sugerează automat o selecție atunci când alegeți o nouă limbă.

1. Selectați **Salvare**.

## <a name="view-system-status"></a>Vedeți starea sistemului

Urmăriți progresul sarcinilor, asimilarea datelor, exporturile de date și alte câteva procese importante ale produsului. Examinați informațiile pentru a vă asigura că sarcinile și procesele dvs. active sunt complete.

1. Mergi la **Admin** > **Sistem** și selectați **stare** fila.

   Afișează starea și procesarea informațiilor pentru diferite procese. Vizualizați **Nume** a sarcinii, cel **stare** din cea mai recentă rulare și când a fost **Ultima actualizare**.

1. Pentru a vizualiza detaliile ultimelor rulări, selectați sarcina sau numele procesului.

1. Pentru a vedea detaliile progresului unei sarcini, selectați starea. The **Detalii despre progres** afișează panoul.

   :::image type="content" source="media/system-progress-details.png" alt-text="Panoul de detalii despre progresul sistemului":::

1. Pentru a vedea detaliile progresului pentru toate sarcinile, selectați **Întregul flux de lucru**.

### <a name="status-definitions"></a>Definiții de stare

Sistemul utilizează următoarele stări pentru sarcini și procese:

|Status  |Definiție  |
|---------|---------|
|Anulat |Sarcina sau procesul a fost anulat de utilizator înainte de a se termina.   |
|Nereușite   |Sarcina sau procesul a întâmpinat erori.         |
|Eşec  |Sarcina sau procesul a eșuat.  |
|Neînceput   |Sursă de date nu are încă date ingerate sau sarcina este încă în modul ciornă.         |
|Se prelucrează  |Sarcina sau procesul este în curs.  |
|Se reîmprospătează    |Sarcina sau procesul este în curs. Pentru a anula această operațiune, selectați **Înviorător** și **Anulează jobul**. Oprirea reîmprospătării unei sarcini sau proces va reveni la ultima stare de reîmprospătare.       |
|Ignorate  |Sarcina sau procesul a fost omis. Unul sau mai multe dintre procesele din aval de care depinde această sarcină eșuează sau sunt omise.|
|Reușit  |Sarcină sau proces finalizat cu succes. Pentru sursele de date, indică faptul că datele au fost ingerate cu succes dacă este menționată o oră în **Odihnit** coloană.|
|Plasată în coadă | Procesarea este pusă în coadă și va începe odată ce toate sarcinile și procesele din amonte sunt finalizate. Pentru mai multe informații, vezi [Procesele de reîmprospătare](#refresh-processes).|

### <a name="refresh-processes"></a>Procesele de reîmprospătare

Reîmprospătarea sarcinilor și proceselor se execută în conformitate cu [programul configurat](schedule-refresh.md).

|Proces  |Descriere  |
|---------|---------|
|Activitate  |Funcționează manual (reîmprospătare o singură dată). Depinde de procesul de îmbinare. Detaliile depind de procesarea acestuia.|
|Legare analiză |Funcționează manual (reîmprospătare o singură dată). Depinde de segmente.  |
|Pregătire analiză |Funcționează manual (reîmprospătare o singură dată). Depinde de segmente.  |
|Pregătire date   |Are nevoie de o entitate pe care să ruleze. Sursă de date entitățile depind de ingerare. Entitățile îmbogățite depind de îmbogățiri. Entitatea Client depinde de fuziune.  |
|Surse de date   |Nu depinde de niciun alt proces. Potrivirea depinde de finalizarea cu succes a acestui proces.  |
|Îmbogățiri   |Funcționează manual (reîmprospătare o singură dată). Depinde de procesul de îmbinare. |
|Destinații de export |Funcționează manual (reîmprospătare o singură dată). Depinde de segmente.  |
|Detalii |Funcționează manual (reîmprospătare o singură dată). Depinde de segmente.  |
|Intelligence   |Depinde de fuziune.   |
|Corespondență |Depinde de procesarea surselor de date utilizate în definiția potrivirii.      |
|Măsuri  |Funcționează manual (reîmprospătare o singură dată). Depinde de procesul de îmbinare.  |
|Îmbinare   |Depinde de finalizarea procesului de potrivire. Segmentele, măsurile, îmbogățirea, căutarea, activitățile, predicțiile și pregătirea datelor depind de finalizarea cu succes a acestui proces.   |
|Profiluri   |Funcționează manual (reîmprospătare o singură dată). Depinde de procesul de îmbinare. |
|Căutarea   |Funcționează manual (reîmprospătare o singură dată). Depinde de procesul de îmbinare. |
|Segmente  |Funcționează manual (reîmprospătare o singură dată). Depinde de procesul de îmbinare. Detaliile depind de procesarea acestuia.|
|Sistem   |Depinde de finalizarea procesului de potrivire. Segmentele, măsurile, îmbogățirea, căutarea, activitățile, predicțiile și pregătirea datelor depind de finalizarea cu succes a acestui proces.   |
|User  |Funcționează manual (reîmprospătare o singură dată). Depinde de entitati.  |

Selectați starea unui proces pentru a vedea detaliile despre progresul întregii sarcini în care a fost. Procesele de reîmprospătare de mai sus vă pot ajuta să înțelegeți ce puteți face pentru a aborda a **Sarit peste** sau **În așteptare** sarcină sau proces.


[!INCLUDE [footer-include](includes/footer-banner.md)]
