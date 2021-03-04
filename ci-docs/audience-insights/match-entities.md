---
title: Asociați entitățile pentru unificarea datelor
description: Asociați entitățile pentru a crea profiluri de clienți unificate.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 05afd17b7f1b34f7f24a8fa8cb2dc32c1649d40f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267493"
---
# <a name="match-entities"></a>Potrivire entități

După finalizarea fazei hărții, sunteți gata să vă potriviți entitățile. Faza de potrivire specifică modul de combinare a seturilor de date într-un set de date de profil unificat pentru clienți. Faza de potrivire necesită cel puțin [două entități mapate](map-entities.md).

## <a name="specify-the-match-order"></a>Specificați ordinea de potrivire

Accesați **Date** > **Unifica** > **Potrivire** și selectați **Setați ordinea** pentru a începe faza de potrivire.

Fiecare potrivire unifică două sau mai multe entități într-o singură entitate, persistând în același timp fiecare înregistrare unică de client. În exemplul următor, am selectat trei entități: **ContactCSV: TestData** ca entitate **Principală**, **WebAccountCSV: TestData** ca **Entitate 2** și **CallRecordSmall: TestData** ca **Entitate 3**. Diagrama de deasupra selecțiilor ilustrează modul în care va fi executată ordinea de potrivire.

> [!div class="mx-imgBorder"]
> ![Editarea ordinii de potrivire a datelor](media/configure-data-match-order-edit-page.png "Editarea ordinii de potrivire a datelor")
  
Entitatea **Principală** este potrivită cu **Entitatea 2**. Setul de date care rezultă din prima potrivire se potrivește cu **Entitatea 3**.
În acest exemplu, am selectat doar două potriviri, dar sistemul poate suporta mai multe.

> [!IMPORTANT]
> Entitatea pe care o alegeți ca entitate **Principală** va servi drept bază pentru setul dvs. de date principal unificat. Entitățile suplimentare care sunt selectate în timpul fazei de potrivire vor fi adăugate la această entitate. În același timp, acest lucru nu înseamnă că entitatea unificată va include *toate* datele incluse în această entitate.
>
> Există două considerații care vă pot ajuta să alegeți ierarhia entităților:
>
> - Ce entitate considerați că are cele mai complete și fiabile date despre clienții dvs.?
> - Entitatea pe care tocmai ați identificat-o are atribute care sunt, de asemenea, partajate de alte entități (de exemplu, nume, număr de telefon sau adresă de e-mail)? Dacă nu, alegeți a doua entitate de încredere.

Selectați **Terminat** pentru a salva ordinea de potrivire.

## <a name="define-rules-for-your-first-match-pair"></a>Definirea regulilor pentru prima pereche de potrivire

După specificarea ordinii de potrivire, veți vedea potrivirile definite pe pagina **Potrivire**. Dalele din partea de sus a ecranului vor fi goale până când executați comanda de potrivire.

> [!div class="mx-imgBorder"]
> ![Definirea regulilor](media/configure-data-match-need-rules.png "Definirea regulilor")

Avertismentul **Necesită reguli** sugerează că nu este definită nicio regulă de potrivire pentru o pereche de potrivire. Regulile de potrivire specifică logica după care se vor potrivi o anumită pereche de entități.

1. Pentru a defini prima regulă, deschideți panoul **Definiție regulă** selectând rândul de potrivire corespunzător din tabelul de potriviri (1), apoi selectând **Creare regulă nouă** (2).

   > [!div class="mx-imgBorder"]
   > ![Creare regulă nouă](media/configure-data-match-new-rule2.png "Creare regulă nouă")

2. În panoul **Editare regulă**, configurați condițiile pentru această regulă. Fiecare condiție este reprezentată de două rânduri care includ selecții obligatorii.

   > [!div class="mx-imgBorder"]
   > ![Adăugați o regulă de panou](media/configure-data-match-new-rule-condition.png "Adăugați o regulă de panou")

   Entitate/Câmp (mai întâi) - Un atribut care va fi utilizat pentru potrivirea din prima entitate pereche de potrivire. Exemplele pot include un număr de telefon sau o adresă de e-mail. Alegeți un atribut care este probabil să fie unic pentru client.

   > [!TIP]
   > Evitați potrivirea pe baza atributelor de tip activitate. Cu alte cuvinte, în cazul în care un atribut pare a fi o activitate, atunci ar putea fi un criteriu slab de potrivire.  

   Entitate/Câmp (Al doilea) - Un atribut care va fi utilizat pentru potrivirea din a doua entitate pereche de potrivire.

   Normalizare - **Metoda de normalizare**: Diferite opțiuni de normalizare sunt disponibile pentru atributele selectate. De exemplu, eliminarea semnelor de punctuație sau eliminarea spațiilor

   Pentru normalizarea numelui organizației (Previzualizare), puteți selecta, de asemenea, **Tip (Telefon, Nume, Organizație)**

   > [!div class="mx-imgBorder"]
   > ![Normalizare-B2B](media/match-normalization-b2b.png "Normalizare-B2B")

   Nivel de precizie - Nivelul de precizie care va fi utilizat pentru această condiție. Setarea unui nivel de precizie pentru o condiție de potrivire poate avea două tipuri: **De bază** și **Particularizat**.  
   - De bază: vă oferă patru opțiuni pentru a selecta de la: Scăzut, mediu, ridicat, și exact. Selectați **Exact** pentru a potrivi numai înregistrările care se potrivesc 100 la sută. Selectați unul dintre celelalte niveluri pentru a potrivi înregistrările care nu sunt 100% identice.
   - Particularizat: Utilizați glisorul pentru a defini procentul particularizat de care au nevoie înregistrările pentru a se potrivi sau pentru a introduce o valoare în câmpul **Particularizat**. Sistemul se va potrivi numai cu înregistrările care trec acest prag ca perechi de potrivire contopite. Valorile de pe glisor sunt între 0 și 1. Deci, 0.64 reprezintă 64 la sută.

3. Selectați **Terminat** pentru a salva regula.

### <a name="add-multiple-conditions"></a>Adăugarea mai multor condiții

Pentru a se potrivi cu entitățile numai dacă sunt îndeplinite mai multe condiții, adăugați mai multe condiții care sunt legate printr-un operator Și.

1. În panoul **Editare regulă**, selectați **Adăugare condiție**. De asemenea, puteți șterge condițiile selectând butonul eliminare de lângă o condiție existentă.

2. Selectați **Terminat** pentru a salva regula.

## <a name="add-multiple-rules"></a>Adăugarea mai multor reguli

Fiecare condiție se aplică unei singure perechi de atribute, în timp ce regulile reprezintă seturi de condiții. Pentru ca entitățile să fie corelate cu diferite seturi de atribute, puteți adăuga mai multe reguli.

1. În Detalii despre public, accesați **Date** > **Unificare** > **Asociere**.

2. Selectați entitatea pe care doriți să o actualizați și selectați **Adăugați reguli**.

3. Urmați procedura așa cum este descrisă în [Definire reguli pentru prima pereche de potrivire](#define-rules-for-your-first-match-pair).

> [!NOTE]
> Ordinea regulilor contează. Algoritmul de potrivire încearcă să se potrivească pe baza primei reguli și continuă cu a doua regulă numai dacă nu au fost identificate potriviri în conformitate cu prima regulă.

## <a name="define-deduplication-on-a-match-entity"></a>Definiți eliminarea informațiilor duplicate pentru o entitate de potrivire

Împreună cu specificarea regulilor de potrivire a entităților încrucișate așa cum este subliniat în secțiunile de mai sus, puteți specifica și reguli de eliminare a informațiilor duplicate. *Eliminarea informațiilor duplicate* este un proces. Identifică înregistrările duplicate, le îmbină într-o singură înregistrare și leagă toate înregistrările sursă de această înregistrare combinată cu ID-uri alternative la înregistrarea combinată.

După identificarea unei înregistrări de eliminare a informațiilor duplicate, aceasta va fi apoi utilizată în procesul de potrivire între entități. Eliminarea informațiilor duplicate este implementată la nivel de entitate și poate fi aplicată fiecărei entități utilizate în procesul de potrivire.

### <a name="add-deduplication-rules"></a>Adăugare reguli de eliminare a informațiilor duplicate

1. În Detalii despre public, accesați **Date** > **Unificare** > **Asociere**.

1. În secțiunea **Dubluri combinate**, selectați **Setare entități**.

1. În secțiunea **Combinare preferințe**, selectați entitățile cărora doriți să le aplicați eliminarea de informații duplicate.

1. Specificați cum să îmbinați înregistrările duplicate și alegeți una dintre cele trei opțiuni de îmbinare:
   - *Cea mai completată*: Identifică înregistrarea cu cele mai multe atribute completate ca înregistrare câștigătoare. Aceasta este opțiunea implicită de combinare.
   - *Cea mai recentă*: Identifică înregistrarea câștigătoare pe baza celor mai recente. Necesită o dată sau un câmp numeric pentru a defini activitatea recentă.
   - *Cea mai puțin recentă*: Identifică înregistrarea câștigătoare pe baza celor mai puțin recente. Necesită o dată sau un câmp numeric pentru a defini activitatea recentă.
 
   > [!div class="mx-imgBorder"]
   > ![Reguli de eliminare a informațiilor duplicate pasul 1](media/match-selfconflation.png "Reguli de eliminare a informațiilor duplicate pasul 1")
 
1. Odată ce entitățile sunt selectate și preferința lor de îmbinare este setată, selectați **Creare regulă nouă** pentru a defini regulile de eliminare a informațiilor duplicate la nivel de entitate.
   - **Selectare câmp** listează toate câmpurile disponibile de la acea entitate pentru care doriți să eliminați informațiile duplicate din datele sursă.
   - Specificați setările de normalizare și precizie în mod similar, așa cum se specifică în potrivirea entității încrucișate.
   - Puteți defini condiții suplimentare selectând **Adăugare condiție**.
 
   > [!div class="mx-imgBorder"]
   > ![Reguli de eliminare a informațiilor duplicate pasul 2](media/match-selfconflation-rules.png "Reguli de eliminare a informațiilor duplicate pasul 2")

  Puteți crea mai multe reguli de eliminare a informațiilor duplicate pentru o entitate. 

1. Rularea procesului de potrivire grupează acum înregistrările pe baza condițiilor definite în regulile de eliminare a informațiilor duplicate. După gruparea înregistrărilor, politica de îmbinare este aplicată pentru a identifica înregistrarea câștigătoare.

1. Această înregistrare a câștigătorului este apoi transmisă potrivirii între entități, împreună cu înregistrările non-câștigătoare (de exemplu, ID-uri alternative) pentru a îmbunătăți calitatea potrivirii.

1. Orice regulă de potrivire personalizată definită pentru potrivire întotdeauna și nu se potrivește niciodată anulează regulile de eliminare a informațiilor duplicate. Dacă o regulă de eliminare a informațiilor duplicate identifică înregistrările de potrivire și o regulă de potrivire personalizată este setată să nu se potrivească niciodată cu aceste înregistrări, atunci aceste două înregistrări nu vor fi potrivite.

1. După rularea procesului de potrivire, veți vedea statisticile de eliminare a informațiilor duplicate.
   
> [!NOTE]
> Specificarea regulilor de eliminare a informațiilor duplicate nu este obligatorie. Dacă nu sunt configurate astfel de reguli, se aplică regulile definite de sistem. Acestea restrâng toate înregistrările care partajează aceeași combinație de valori (potrivire exactă) de la cheia primară și câmpurile din regulile de potrivire într-o singură înregistrare înainte de a transfera datele entității la potrivirea între entități pentru performanță îmbunătățită și sănătatea sistemului.

## <a name="run-your-match-order"></a>Executați comanda de potrivire

După definirea regulilor de potrivire, inclusiv a regulilor de potrivire și eliminare a informațiilor duplicate între entități, puteți rula ordinea de potrivire. Pe pagina **Potrivire**, selectați **Executare** pentru a porni procesul. Algoritmul de potrivire ar putea dura ceva timp pentru a se finaliza. Nu puteți modifica proprietățile din pagina **Potrivire** până când se termină procesul de potrivire. Veți găsi entitatea de profil de client unificată care a fost creată în pagina **Entități**. Entitatea client unificată se numește **ConflationMatchPairs: CustomerInsights**.

Pentru a face modificări suplimentare și a relua pasul, puteți anula o potrivire în curs. Selectați textul **Se reîmprospătează ...** și selectați **Anulare operațiune** în partea de jos a panoului lateral care apare.

Când procesul de potrivire este finalizat, textul **Se reîmprospătează ...** se va schimba în **Reușit** și puteți folosi din nou toate funcționalitățile paginii.

Primul proces de potrivire are ca rezultat crearea unei entități principale unificate. Toate executările ulterioare au ca rezultat extinderea entității respective.

> [!TIP]
> Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese. În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies). Puteți selecta starea unui proces pentru a vedea detalii despre evoluția întregii lucrări. După selectarea **Vizualizare detalii** pentru una dintre sarcinile jobului, găsiți informații suplimentare: timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate sarcinii.

## <a name="deduplication-output-as-an-entity"></a>Ieșire de deduplicare ca entitate
În plus față de entitatea principală unificată creată ca parte a potrivirii între entități încrucișate, procesul de deduplicare generează și o entitate nouă pentru fiecare entitate din ordinul de potrivire pentru a identifica înregistrările deduplicate. Aceste entități pot fi găsite împreună cu **ConflationMatchPairs: CustomerInsights** în secțiunea **Sistem** din pagina **Entități**, cu numele **Deduplication_Datasource_Entity**.

O entitate de ieșire de deduplicare conține următoarele informații:
- ID-uri / Chei
  - Câmpul cheie primară și câmpul său ID-uri alternative. Câmpul ID-uri alternative constă din toate ID-urile alternative identificate pentru o înregistrare.
  - Câmpul Deduplication_GroupId arată grupul sau clusterul identificat în cadrul unei entități care grupează toate înregistrările similare pe baza câmpurilor de deduplicare specificate. Acesta este utilizat în scopuri de procesare a sistemului. Dacă nu sunt specificate reguli de deduplicare manuală și se aplică reguli de deduplicare definite de sistem, este posibil să nu găsiți acest câmp în entitatea de ieșire a deduplicării.
  - Deduplication_WinnerId: Acest câmp conține ID-ul câștigător din grupurile sau clusterele identificate. Dacă Deduplication_WinnerId este aceeași cu valoarea cheii principale pentru o înregistrare, înseamnă că înregistrarea este înregistrarea câștigătoare.
- Câmpuri utilizate pentru definirea regulilor de deduplicare.
- Câmpurile Regulă și Scor pentru a indica care dintre regulile de deduplicare s-au aplicat și scorul returnat de algoritmul de potrivire.

## <a name="review-and-validate-your-matches"></a>Examinați și validați-vă potrivirile

Evaluați calitatea perechilor de potrivire și rafinați-o:

- Pe pagina **Potrivire**, veți găsi două dale care afișează statistici inițiale despre datele dvs.

  - **Clienți unici**: afișează numărul de profiluri unice pe care le-a identificat sistemul.
  - **Înregistrări potrivite**: afișează numărul de potriviri din toate perechile de potrivire.

- În tabelul **Potrivire ordine**, puteți evalua rezultatele fiecărei perechi de potrivire comparând numărul de înregistrări care provin de la această entitate de potrivire în raport cu procentul de înregistrări corelate cu succes.

- În secțiunea **Reguli** a unei entități din tabelul **Potrivire ordine**, veți găsi procentul de înregistrări corelate cu succes la nivel de regulă. Selectând simbolul tabelului de lângă o regulă, aveți posibilitatea să vizualizați toate aceste înregistrări la nivel de regulă. Vă recomandăm să examinați un subset de înregistrări pentru a valida că acestea au fost potrivite corect.

- Experimentați diferite praguri de precizie în jurul condițiilor dvs. pentru a identifica valoarea optimă.

  1. Selectați punctele de suspensie (...) pentru regula perechii de potrivire cu care doriți să lucrați și selectați **Editare**.

  2. Selectați condiția cu care doriți să lucrați. Fiecare criteriu este reprezentat de un rând în panoul **Regulă de potrivire**.

  3. Ceea ce veți vedea în pagina **Previzualizare criterii** depinde de nivelul de precizie pe care l-ați selectat pentru o condiție. Găsiți numărul de înregistrări potrivite și de neegalat pentru condiția selectată.

     Obțineți o înțelegere bogată a efectelor diferitelor niveluri de prag. Aveți posibilitatea să comparați câte înregistrări vor fi corelate sub fiecare nivel de prag și să vizualizați înregistrările din fiecare opțiune. Selectați fiecare dintre dale și revizuiți datele din secțiunea tabel.

## <a name="optimize-your-matches"></a>Optimizați-vă potrivirile

Îmbunătățiți calitatea prin reconfigurarea unora dintre parametrii potrivirii:

- **Modificați ordinea de potrivire** selectând **Editare** și modificați câmpurile de ordine de potrivire.

  > [!div class="mx-imgBorder"]
  > ![Editarea ordinii de potrivire a datelor](media/configure-data-match-order-edit.png "Editarea ordinii de potrivire a datelor")

- **Modificați ordinea regulilor** dacă ați definit mai multe reguli. Aveți posibilitatea să reordonați regulile de potrivire selectând opțiunile **Mutare în sus** și **Mutare în jos** din grila de reguli de potrivire.

  > [!div class="mx-imgBorder"]
  > ![Modificați ordinea regulilor](media/configure-data-change-rule-order.png "Modificați ordinea regulilor")

- **Duplicați regulile** dacă ați definit o regulă de potrivire și doriți să creați o regulă similară cu modificări. Procedați astfel selectând **Duplicare**.

  > [!div class="mx-imgBorder"]
  > ![Duplicați o regulă](media/configure-data-duplicate-rule.png "Duplicați o regulă")

- **Dezactivați o regulă** pentru a păstra o regulă de potrivire în timp ce o excludeți din procesul de potrivire.

  > [!div class="mx-imgBorder"]
  > ![Dezactivați o regulă](media/configure-data-deactivate-rule.png "Dezactivați o regulă")

- **Editați regulile** selectând simbolul **Editare**. Puteți aplica următoarele modificări:

  - Modificați atributele pentru o condiție: Selectați noi atribute în rândul de condiții specifice.
  - Modificați pragul pentru o condiție: Reglați glisorul de precizie.
  - Modificați metoda de normalizare pentru o condiție: Actualizați metoda de normalizare.

## <a name="specify-your-custom-match-records"></a>Specificarea înregistrărilor de potrivire particularizată

Puteți specifica condițiile la care anumite înregistrări trebuie să se potrivească întotdeauna sau să nu se potrivească niciodată. Aceste reguli pot fi încărcate în bloc la procesul de potrivire.

1. Selectați opțiunea **Corespondență particularizată** din ecranul **Potrivire ordine**.

   > [!div class="mx-imgBorder"]
   > ![Creați o potrivire particularizată](media/custom-match-create.png "Creați o potrivire particularizată")

2. Dacă nu aveți entități încărcate, veți vedea o nouă casetă de dialog **Potrivire personalizată** care vă solicită să completați câteva detalii. Dacă ați furnizat aceste detalii mai devreme, treceți la pasul 8.

   > [!div class="mx-imgBorder"]
   > ![Casetă de dialog potrivire particularizată nouă](media/custom-match-new-dialog-box.png "Casetă de dialog potrivire particularizată nouă")

3. Selectați **Completați șablonul** pentru a obține un fișier șablon care poate specifica înregistrările din ce entități trebuie să se potrivească întotdeauna sau să nu se potrivească niciodată. Va trebui să completați separat înregistrările "potrivire întotdeauna" și înregistrările "nu se potrivesc niciodată" în două fișiere diferite.

4. Șablonul conține câmpuri pentru a specifica entitatea și valorile cheie primare ale entității de utilizat în potrivirea particularizată. De exemplu, dacă doriți ca cheia primară 12345 din entitatea Vânzări să se potrivească întotdeauna cu cheia primară 34567 din entitatea Persoană de contact, va trebui să specificați următoarele:
    - Entity1: Vânzări
    - Entity1Key: 12345
    - Entity2: Persoană de contact
    - Entity2Key: 34567

   Același fișier șablon poate specifica înregistrări de potrivire particularizată de la mai multe entități.
   
   Dacă doriți să specificați potrivirea personalizată pentru deduplicare pe o entitate, furnizați aceeași entitate ca și Entity1 și Entity2 și setați diferitele valori ale cheii primare.

5. După adăugarea tuturor suprascrierilor pe care doriți să le aplicați, salvați fișierul șablon.

6. Accesați **Date** > **Surse de date** și ingerați fișierele șablon ca entități noi. Odată ingerate, le puteți utiliza pentru a specifica configurația Potrivire.

7. După încărcarea fișierelor și entităților disponibile, selectați din nou opțiunea **Corespondență particularizată**. Veți vedea opțiuni pentru a specifica entitățile pe care doriți să le includeți. Selectați entitățile necesare din meniul vertical.

   > [!div class="mx-imgBorder"]
   > ![Înlocuirea suprapunerii de potrivire](media/custom-match-overrides.png "Înlocuirea suprapunerii de potrivire")

8. Selectați entitățile pe care doriți să le utilizați pentru **Se potrivește întotdeauna** și **Nu se potrivesc niciodată** selectați **Efectuat**.

9. Selectați **Salvare** pe pagina **Potrivire** pentru configurația de potrivire particularizată pe care tocmai ați configurat-o.

10. Selectați **Executare** pe pagina **Potrivire** pentru a începe procesul de potrivire și configurația potrivirii particularizate va fi pusă în aplicare. Orice reguli de potrivire de sistem sunt anulate de setul de configurare.

11. După terminarea potrivirii, puteți verifica entitatea **ConflationMatchPair** pentru a confirma că suprascrierile sunt aplicate în potrivirile de contopire.

## <a name="next-step"></a>Următorul pas

După finalizarea procesului de potrivire pentru cel puțin o pereche de potrivire, puteți rezolva posibilele contradicții din datele dvs. parcurgând subiectul [**Îmbinare**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]