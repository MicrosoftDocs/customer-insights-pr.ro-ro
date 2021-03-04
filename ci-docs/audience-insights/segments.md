---
title: Crearea și gestionarea segmentelor
description: Creați segmente de clienți pentru a îi grupa pe baza diferitelor atribute.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270371"
---
# <a name="create-and-manage-segments"></a>Crearea și gestionarea segmentelor

Segmentele vă permit să vă grupați clienții pe baza atributelor demografice, tranzacționale sau comportamentale. Puteți utiliza segmentele pentru a viza campanii promoționale, activități de vânzare și acțiuni de asistență pentru clienți pentru a vă atinge obiectivele de business.

Puteți defini filtre complexe în jurul entității de profil pentru clienți și entitățile sale asociate. Fiecare segment, după procesare, creează un set de înregistrări ale clienților pe care le puteți exporta și pe care puteți acționa. Se aplică unele [limite ale serviciului](service-limits.md).

Dacă nu se specifică altfel, toate segmentele sunt **Segmente dinamice**, care sunt actualizate într-o planificare recurentă.

Următorul exemplu ilustrează capabilitatea de segmentare. Am definit un segment pentru clienții care au comandat cel puțin $500 de bunuri în ultimele 90 de zile *și* care au fost implicați într-un apel serviciu pentru relații cu clienții care a fost escaladat.

> [!div class="mx-imgBorder"]
> ![Mai multe grupuri](media/segmentation-group1-2.png "Mai multe grupuri")

## <a name="create-a-new-segment"></a>Crearea unui nou segment

Segmentele sunt gestionate pe pagina **Segmente**.

1. În Detalii despre public, accesați pagina **Segmente**.

2. Selectați **Nou** > **Segment necompletat**.

3. În panoul **Segment nou**, alegeți un tip de segment și furnizați un **Nume**.

   Opțional, furnizați un nume afișat și o descriere care ajută la identificarea segmentului.

4. Selectați **Următorul** pentru a ajunge la pagina **Generator de segmente** unde definiți un grup. Un grup este un grup de clienți.

5. Alegeți entitatea care include atributul pe care doriți să îl segmentați.

6. Alegeți atributul pentru care utilizați segmentul. Acest atribut poate avea unul dintre cele patru tipuri de valori: numeric, șir, dată sau boolean.

7. Alegeți un operator și o valoare pentru atributul selectat.

   > [!div class="mx-imgBorder"]
   > ![Particularizați filtrul de grup](media/customer-group-numbers.png "Filtrul de grup de clienți")

   |Număr |Definiție  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atribut          |
   |3    |Operator         |
   |4    |Valoare         |

8. Dacă entitatea este conectată la entitatea client unificată prin [relații](relationships.md), trebuie să definiți calea relației pentru a crea un segment valid. Adăugați entitățile din calea relației până când puteți selecta entitatea **Client: CustomerInsights** din meniul listă verticală. Atunci alegeți **Toate înregistrările** pentru fiecare condiție.

   > [!div class="mx-imgBorder"]
   > ![Calea relației în timpul creării segmentului](media/segments-multiple-relationships.png "Calea relației în timpul creării segmentului")

9. Selectați **Salvare** pentru a vă salva segmentul. Segmentul dvs. va fi salvat și procesat dacă toate cerințele sunt validate. În caz contrar, acesta va fi salvat ca schiță.

10. Selectați **Înapoi la segmente** pentru a reveni la pagina **Segmente**.

## <a name="manage-existing-segments"></a>Gestionarea segmentelor existente

Pe pagina **Segmente**, puteți vedea toate segmentele salvate și le puteți gestiona.

Fiecare segment este reprezentat de un rând care include informații suplimentare despre segment.

Puteți sorta segmentele într-o coloană selectând titlul coloanei.

Folosiți caseta **Căutare** din colțul din dreapta sus pentru a filtra segmentele.

> [!div class="mx-imgBorder"]
> ![Opțiuni de gestionare a unui segment existent](media/segments-selected-segment.png "Opțiuni de gestionare a unui segment existent")

Următoarea acțiune este disponibilă când selectați un segment:

- **Vizualizați** detaliile segmentului, incluzând tendința numărului de membri o previzualizare a membrilor segmentului.
- **Editați** segmentul pentru a-i schimba proprietățile.
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

## <a name="download-and-export-segments"></a>Descărcați și exportați segmente

Puteți descărca segmentele dvs. într-un fișier CSV sau le puteți exporta către Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Descărcați segmente într-un fișier CSV

1. În Detalii despre public, accesați pagina **Segmente**.

2. Selectați elipsele din dala unui segment specific.

3. Selectați **Descărcați ca CSV** din lista derulantă de acțiuni.

### <a name="export-segments-to-dynamics-365-sales"></a>Exportare segmente în Dynamics 365 Sales

Înainte de a exporta segmente către Dynamics 365 Sales, un administrator trebuie să [creeze destinația de export](export-destinations.md) pentru Dynamics 365 Sales.

1. În Detalii despre public, accesați pagina **Segmente**.

2. Selectați elipsele din dala unui segment specific.

3. Selectați **Adăugați la** din lista de acțiuni verticală și selectați destinația de export la care doriți să trimiteți datele.

## <a name="draft-mode-for-segments"></a>Modul de schiță pentru segmente

Dacă nu sunt îndeplinite toate cerințele pentru procesarea unui segment, puteți salva segmentul ca schiță și să îl accesați din pagina **Segmente**.

Acesta va fi salvat ca un segment inactiv și nu poate fi activat până când nu este valabil.

## <a name="add-more-conditions-to-a-group"></a>Adăugați mai multe condiții unui grup

Pentru a adăuga mai multe condiții unui grup, puteți utiliza doi operatori logici:

- Operator **ȘI**: Ambele condiții trebuie îndeplinite ca parte a procesului de segmentare. Această opțiune este cea mai utilă atunci când definiți condiții pentru diferite entități.

- Operatorul **SAU**: Fiecare dintre condiții trebuie îndeplinită ca parte a procesului de segmentare. Această opțiune este cea mai utilă atunci când definiți condiții multiple pentru aceeași entitate.

   > [!div class="mx-imgBorder"]
   > ![Operatorul SAU unde fiecare condiție trebuie îndeplinită](media/segmentation-either-condition.png "Operatorul SAU unde fiecare condiție trebuie îndeplinită")

În prezent este posibil să imbricați un operator **SAU** sub unul **ȘI**, dar nu și invers.

## <a name="combine-multiple-groups"></a>Combinarea mai multor grupuri

Fiecare grup produce un set specific de clienți. Puteți combina aceste grupuri pentru a include clienții necesari pentru cazul dvs. de afaceri.

1. În detaliile despre public, accesați pagina **Segmente** și selectați un segment.

2. Selectați **Adăugați un grup**.

   > [!div class="mx-imgBorder"]
   > ![Grup Adăugare grup de clienți](media/customer-group-add-group.png "Grup Adăugare grup de clienți")

3. Selectați unul dintre următorii operatori de set: **Reuniune**, **Intersectare** sau **Excepție**.

   > [!div class="mx-imgBorder"]
   > ![Uniune Adăugare grup de clienți](media/customer-group-union.png "Uniune Adăugare grup de clienți")

   Selectați unui grop de operator vă permite să definiți un nou grup. Salvarea diferitelor grupuri pentru a determina ce date sunt menținute:

   - **Uniune** unește cele două grupuri.

   - **Intersectare** suprapune cele două grupuri. Doar datele care *sunt comune* pentru ambele grupuri sunt reținute în grupul unificat.

   - **Excepție** combină cele două grupuri. Doar datele din grupul A care *nu sunt comune* cu datele din grupul B sunt reținute.

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

## <a name="quick-segments"></a>Segmente rapide

În plus față de generatorul de segmente, există o altă cale pentru crearea de segmente. Segmentele rapide vă permit să construiți segmente simple cu un singur operator rapid și cu detalii instantanee.

1. Pe pagina **Segmente**, selectați **Nou** > **Creați rapid din**.

   - Selectați opțiunea **Profiluri** de a construi un segment care se bazează pe entitatea Client unificat.
   - Selectați opțiunea **Măsuri** pentru a construi un segment în jurul fiecăruia dintre tipurile de măsuri pe care le-ați creat anterior pe pagina **Măsuri**.
   - Selectați opțiunea **Inteligență** pentru a construi un segment în jurul uneia dintre entitățile de ieșire pe care le-ați generat folosind fie capabilități **Predicții** sau **Modele particularizate**.

2. În caseta de dialog **Segment rapid nou**, selectați un atribut din lista verticală **Câmp**.

3. Sistemul va oferi câteva informații suplimentare care vă vor ajuta să creați segmente mai bune de clienți.
   - Pentru câmpurile categorice, vom afișa 10 numere de clienți de top. Alegeți o **Valoare** și selectați **Revizuire**.

   - Pentru un atribut numeric, sistemul va arăta ce valoare a atributului se încadrează sub percentila fiecărui client. Alegeți un **Operator** și o **Valoare**, apoi selectați **Revizuire**.

4. Sistemul vă va oferi o **Dimensiunea estimată segment**. Puteți alege dacă vreți să generați segmentul pe care l-ați definit sau să îl revizuiți mai întâi pentru a obține o dimensiune diferită a segmentului.

    > [!div class="mx-imgBorder"]
    > ![Numele și estimarea pentru un segment rapid](media/quick-segment-name.png "Numele și estimarea pentru un segment rapid")

5. Furnizați un **Nume** pentru segmentul dvs. Opțional, furnizați un **Nume afișat**.

6. Selectați **Salvare** pentru a crea segmentul.

7. După ce segmentul a terminat procesarea, îl puteți vizualiza ca orice alt segment creat.

Pentru scenariile următoare, vă recomandăm să folosiți constructorul de segmente și nu capacitatea de segmente recomandată:

- Crearea de segmente cu filtre pe câmpuri categorice în care operatorul este diferit de operatorul **Este**
- Crearea de segmente cu filtre pe câmpuri numerice în care operatorul este diferit de operatorii **Între**, **Mai mare decât**, și **Mai puțin decât**
- Crearea de segmente cu filtre pe câmpurile de tip de date

## <a name="next-steps"></a>Următorii pași

[Exportați un segment](export-destinations.md) și explorați [Card client](customer-card-add-in.md) și [Conectori](export-power-bi.md) pentru a obține informații despre nivelul clientului.


[!INCLUDE[footer-include](../includes/footer-banner.md)]