---
title: Configurarea sistemului în Detalii despre public
description: Aflați despre setările de sistem în funcția de statistici privind publicul Dynamics 365 Customer Insights.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1b790106f8b9617d0c1f244e1d15a74c7ef9a82b
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732385"
---
# <a name="system-configuration"></a>Configurare sistem

Pentru a accesa configurațiile sistemului în informații despre public, din bara de navigare din stânga selectați **Admin** > **Sistem** pentru a vizualiza o listă de sarcini și procese de sistem.

Pagina **Sistem** include următoarele file:
- [Status](#status-tab)
- [Planificare](#schedule-tab)
- [Utilizare API](#api-usage-tab)
- [Despre](#about-tab)
- [General](#general-tab)
- [Securitate](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Filele de setări pe pagina de sistem.":::

## <a name="status-tab"></a>Fila Stare

The **Fila Stare** vă permite să urmăriți progresul sarcinilor, asimilarea datelor, exporturile de date și alte câteva procese importante ale produsului. Examinați informațiile din această filă pentru a vă asigura că sarcinile și procesele dvs. active sunt complete.

Această filă include tabele cu informații de stare și procesare pentru diferite procese. Fiecare tabel urmărește **Numele** activității și entitatea corespunzătoare, **Starea** celei mai recente rulări și când a fost **Ultima actualizare**. Puteți vizualiza detaliile ultimelor rulări selectând sarcina sau numele procesului. 

Selectați starea de lângă sarcină sau proces din **stare** coloana pentru a deschide **Detalii despre progres** panou.

   :::image type="content" source="media/system-progress-details.png" alt-text="Panoul cu detalii despre progresul sistemului":::

### <a name="status-definitions"></a>Definiții de stare

Sistemul utilizează următoarele stări pentru sarcini și procese:

|Status  |Definiție  |
|---------|---------|
|Anulat |Procesarea a fost anulată de utilizator înainte de a se termina.   |
|Nereușite   |Ingerarea de date s-a efectuat cu erori.         |
|Eşec  |Procesarea a eșuat.  |
|Neînceput   |Sursa de date nu are încă date ingerate sau este încă în modul schiță.         |
|Se prelucrează  |Sarcina sau procesul este în desfășurare.  |
|Se reîmprospătează    |Ingestia datelor este în curs. Aveți posibilitatea de a revoca această operațiune selectând **Oprire reîmprospătare** în coloana **Acțiuni**. Oprirea reîmprospătării unei surse de date o va readuce la ultima stare de reîmprospătare.       |
|Ignorate  |Sarcina sau procesul a fost omis. Unul sau mai multe dintre procesele din aval de care depinde această sarcină eșuează sau sunt omise.|
|Reușit  |Sarcină sau proces finalizat cu succes. Pentru sursele de date, indică faptul că datele au fost ingerate cu succes dacă o oră este menționată în **Odihnit** coloană.|
|Plasată în coadă | Procesarea este pusă în coadă și va începe odată ce toate sarcinile și procesele din amonte sunt finalizate. Pentru mai multe informații, vezi [Procesele de reîmprospătare](#refresh-processes).|

### <a name="refresh-processes"></a>Procesele de reîmprospătare

Reîmprospătarea sarcinilor și proceselor se execută în conformitate cu [programul configurat](#schedule-tab). 

|Proces  |Descriere  |
|---------|---------|
|Activitate  |Funcționează manual (reîmprospătare o singură dată). Depinde de procesul de îmbinare. Detaliile depind de procesarea acestuia.|
|Legare analiză |Funcționează manual (reîmprospătare o singură dată). Depinde de segmente.  |
|Pregătire analiză |Funcționează manual (reîmprospătare o singură dată). Depinde de segmente.  |
|Pregătire date   |Depinde de fuziune.   |
|Surse de date   |Nu depinde de niciun alt proces. Potrivirea depinde de finalizarea cu succes a acestui proces.  |
|Îmbogățiri   |Funcționează manual (reîmprospătare o singură dată). Depinde de procesul de îmbinare. |
|Destinații de export |Funcționează manual (reîmprospătare o singură dată). Depinde de segmente.  |
|Detalii |Funcționează manual (reîmprospătare o singură dată). Depinde de segmente.  |
|Informații   |Depinde de fuziune.   |
|Corespondență |Depinde de procesarea surselor de date utilizate în definiția potrivirii.      |
|Măsuri  |Funcționează manual (reîmprospătare o singură dată). Depinde de procesul de îmbinare.  |
|Îmbinare   |Depinde de finalizarea procesului de potrivire. Segmentele, măsurile, îmbogățirea, căutarea, activitățile, predicțiile și pregătirea datelor depind de finalizarea cu succes a acestui proces.   |
|Profiluri   |Funcționează manual (reîmprospătare o singură dată). Depinde de procesul de îmbinare. |
|Căutare   |Funcționează manual (reîmprospătare o singură dată). Depinde de procesul de îmbinare. |
|Segmente  |Funcționează manual (reîmprospătare o singură dată). Depinde de procesul de îmbinare. Detaliile depind de procesarea acestuia.|
|Sistem   |Depinde de finalizarea procesului de potrivire. Segmentele, măsurile, îmbogățirea, căutarea, activitățile, predicțiile și pregătirea datelor depind de finalizarea cu succes a acestui proces.   |
|Utilizator  |Funcționează manual (reîmprospătare o singură dată). Depinde de entitati.  |

Selectați starea unui proces pentru a vedea detaliile de progres ale întregului job în care a fost. Procesele de reîmprospătare de mai sus vă pot ajuta să înțelegeți ce puteți face pentru a aborda a **Sărit** sau **În așteptare** sarcină sau proces.

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

Puteți schimba limba și formatul de țară/regiune pe fila **General**.

Informații despre clienți [acceptă multe limbi](/dynamics365/get-started/availability). Aplicația vă folosește preferințele de limbă pentru a afișa elemente precum meniul, textul de etichete și mesajele de sistem în limba dvs. preferată.

Datele și informațiile importate și pe care le-ați introdus manual nu sunt traduse.

### <a name="update-the-settings"></a>Actualizați setările

Pentru a schimba limba preferată, alegeți o **Limbă** din lista verticală.

Pentru a schimba formatarea dvs. preferată pentru date, oră și numere, utilizați lista verticală **Format țară/regiune**. O previzualizare de formatare este afișată sub acest câmp. Sistemul va sugera automat o selecție atunci când alegeți o nouă limbă.

Selectați **Salvare** pentru a confirma selecțiile.

## <a name="api-usage-tab"></a>Filă utilizare API

Găsiți detalii despre utilizarea API-ului în timp real și vedeți ce evenimente s-au întâmplat într-un anumit interval de timp. Alegeți intervalul de timp în meniul derulant **Selectați un interval de timp**. 

**Utilizarea API** conține trei secțiuni: 
- **Apeluri API** - o diagramă care vizualizează numărul agregat de apeluri către API în intervalul de timp selectat.

- **Transfer de date** - o diagramă care arată cantitatea de date care a fost transferată prin API în intervalul de timp selectat.

-  **Operațiuni** - un tabel cu rânduri pentru fiecare operațiune API disponibilă și detalii despre utilizarea operațiunilor. Puteți selecta un nume de operație pentru a accesa [referința API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operațiuni care folosesc [asimilarea datelor în timp real](real-time-data-ingestion.md) conține un buton cu un simbol binocular pentru a vedea utilizarea API-ului în timp real. Selectați butonul pentru a deschide un panou lateral care conține detalii de utilizare pentru utilizarea API-ului în timp real în mediul curent.   
   Utilizați caseta **Grupare după** din panoul **Utilizare API în timp real** pentru a alege cum să vă prezentați cel mai bine interacțiunile în timp real. Puteți grupa datele după metoda API, numele calificat de entitate (entitatea ingerată), creat de (sursa evenimentului), rezultat (succes sau eșec) sau coduri de eroare. Datele sunt disponibile ca un grafic istoric și ca un tabel.

## <a name="security-tab"></a>Fila Securitate

Fila **Securitate** vă permite să vă conectați și să vă gestionați propriul [Seif de chei Azure](/azure/key-vault/general/basic-concepts) la mediu.
Seiful de chei dedicat poate fi utilizat pentru a etapiza și a folosi secrete în limita de conformitate a unei organizații. Statisticile publicului pot folosi secretele din Azure Key Vault pentru a [configura conexiuni](connections.md) către sisteme terțe.

Pentru mai multe informații, vedeți [Aduceți-vă propriul seif de chei Azure](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
