---
title: Asociați entitățile pentru unificarea datelor
description: Potriviți entitățile pentru a combina seturi de date și a crea profiluri unificate de clienți.
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
ms.openlocfilehash: 67e17495fa6da1cfac7ee4ee165e798364f6cb27
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648223"
---
# <a name="match-entities"></a>Potrivire entități

Faza de potrivire specifică modul de combinare a seturilor de date într-un set de date de profil unificat pentru clienți. După finalizarea [pas de hartă](map-entities.md) în procesul de unificare a datelor, sunteți gata să vă potriviți cu entitățile. Faza de potrivire necesită cel puțin două entități mapate.

Pagina de potrivire este formată din trei secțiuni: 
- Valori cheie care rezumă numărul de înregistrări potrivite
- Ordinea potrivirii și regulile pentru potrivirea între entități
- Reguli pentru deduplicarea entităților de potrivire

## <a name="specify-the-match-order"></a>Specificați ordinea de potrivire

Accesați **Date** > **Unifica** > **Potrivire** și selectați **Setați ordinea** pentru a începe faza de potrivire.

Fiecare potrivire unifică două sau mai multe entități într-o singură entitate consolidată. În același timp, păstrează înregistrările unice ale clienților. De exemplu, am selectat două entități: **eCommerce: eCommerceContacts** ca entitate primară și **LoyaltyScheme: loyCustomers** ca a doua entitate. Ordinea entităților specifică în ce ordine sistemul va încerca să se potrivească cu înregistrările.

:::image type="content" source="media/match-page.png" alt-text="Captură de ecran a paginii Potrivire din zona Unificare a procesului de unificare a datelor.":::
  
Entitatea primară *eCommerce: eCommerceContacts* se potrivește cu următoarea entitate *LoyaltyScheme: loyCustomers*. Setul de date care rezultă din primul pas de potrivire este asortat cu următoarea entitate dacă aveți mai mult de două entități.

> [!IMPORTANT]
> Entitatea pe care o alegeți ca entitate principală va servi drept bază pentru setul dvs. de date ale profilelor unificate. Entitățile suplimentare care sunt selectate în timpul fazei de potrivire vor fi adăugate la această entitate. Acest lucru nu înseamnă că entitatea unificată va include *toate* datele incluse în această entitate.
>
> Există două considerații care vă pot ajuta să alegeți ierarhia entităților:
>
> - Alegeți entitatea cu cele mai complete și mai fiabile date de profil despre clienții dvs. ca entitate principală.
> - Alegeți entitatea care are mai multe atribute comune cu alte entități (de exemplu, numele, numărul de telefon sau adresa de e-mail) ca entitate principală.

După specificarea ordinii de potrivire, veți vedea perechile de potrivire definite în secțiunea **Detalii înregistrări potrivite** pe **Date** > **Unificare** > **Potrivire**. Valorile cheie vor fi goale până la finalizarea procesului de potrivire.

## <a name="define-rules-for-match-pairs"></a>Definiți regulile pentru perechile potrivite

Regulile de potrivire specifică logica după care se vor potrivi o anumită pereche de entități.

Avertizarea **Are nevoie de reguli** de lângă un nume de entitate sugerează că nu este definită nicio regulă de potrivire pentru o pereche de potrivire. 

:::image type="content" source="media/match-rule-add.png" alt-text="Captură de ecran a secțiunii Detalii înregistrare potrivită cu control pentru a adăuga reguli evidențiate.":::

1. Selectați **Adăugați reguli** sub o entitate din secțiunea **Detalii înregistrări potrivite** pentru a defini regulile de potrivire.

1. În panoul **Creați o regulă**, configurați condițiile pentru regulă.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Captură de ecran a unei reguli de potrivire deschise cu condiții adăugate.":::

   - **Entitate/Câmp (primul rând)**: Alegeți o entitate legată și un atribut pentru a specifica o proprietate de înregistrare care este probabil unică pentru un client. De exemplu, un număr de telefon sau o adresă de e-mail. Evitați potrivirea după atributele de tip activitate. De exemplu, un ID de achiziție nu va găsi probabil nicio potrivire în alte tipuri de înregistrări.

   - **Entitate/Câmp (al doilea rând)**: Alegeți un atribut care se referă la atributul entității specificate în primul rând.

   - **Normalizare**: Selectați din următoarele opțiuni de normalizare pentru atributele selectate. 
     - Spațiu alb: elimină toate spațiile. *Hello   World* devine *HelloWorld*.
     - Simboluri: elimină toate simbolurile și caracterele speciale. *Head&Shoulder* devine *HeadShoulder*.
     - Text cu minuscule: convertește toate caracterele în minuscule. *TOATE MAJUSCULE și majuscule* devine *toate majuscule și majuscule*.
     - Unicode în ASCII: convertește notația unicode în caractere ASCII. */u00B2* devine *2*.
     - Numerale: convertește alte sisteme de numere, cum ar fi numerele romane, în cifre arabe. *VIII* devine *8*.
     - Tipuri semantice: standardizează nume, titluri, numere de telefon, adrese etc. 

   - **Precizie**: Setați nivelul de precizie care trebuie aplicat pentru această condiție. 
     - **De bază**: Alege din *Scăzut*, *Mediu*, *Înalt* și *Exact*. Selectați **Exact** pentru a potrivi numai înregistrările care se potrivesc 100 la sută. Selectați unul dintre celelalte niveluri pentru a potrivi înregistrările care nu sunt 100% identice.
     - **Particularizat**: Setați un procent care trebuie să corespundă înregistrărilor. Sistemul va potrivi doar înregistrările care depășesc acest prag.

1. Furnizați un **Nume** pentru regulă.

1. [Adăugați mai multe condiții](#add-conditions-to-a-rule) sau selectați **Terminat** pentru a finaliza regula.

1. Opțional, [adăugați mai multe reguli](#add-rules-to-a-match-pair).

1. Selectați **Salvare** pentru a vă aplica modificările.

### <a name="add-conditions-to-a-rule"></a>Adăugați condiții la o regulă

Pentru a potrivi entități numai dacă atributele îndeplinesc mai multe condiții, adăugați mai multe condiții la o regulă de potrivire. Condițiile sunt conectate cu un operator AND logic și astfel executate numai dacă sunt îndeplinite toate condițiile.

1. Accesați **Date** > **Unificare** > **Potrivire** și selectați **Editare** pe regula la care doriți să adăugați condiții.

1. În panoul **Editare regulă**, selectați **Adăugare condiție**.

1. Selectați **Terminat** pentru a salva regula.

### <a name="add-rules-to-a-match-pair"></a>Adăugați reguli unei perechi potrivite

Regulile de potrivire reprezintă seturi de condiții. Pentru a potrivi entități după condiții pe baza mai multor atribute, adăugați mai multe reguli

1.  Accesați **Date** > **Unificare** > **Potrivire** și selectați **Adăugare regulă** pe entitatea la care doriți să adăugați reguli.

2. Urmați pașii din [Definiți regulile pentru perechile de potriviri](#define-rules-for-match-pairs).

> [!NOTE]
> Ordinea regulilor contează. Algoritmul de potrivire încearcă să se potrivească pe baza primei reguli și continuă la a doua regulă numai dacă nu au fost identificate potriviri cu prima regulă.

### <a name="change-the-entity-order-in-match-rules"></a>Modificați ordinea entității în regulile de potrivire

Puteți reordona entitățile pentru regulile de potrivire pentru a modifica ordinea în care sunt procesate. Regulile care sunt conflictuale din cauza unei comenzi modificate vor fi eliminate. Trebuie să recreați regulile eliminate cu o configurație actualizată.

1. Mergeți la **Date** > **Unificare** > **Potirvire** și selectați **Editați**.

1. În **Editați regula**, selectați controluk **Mutați în sus/jos** sau glisați și fixați entități pentru a modifica ordinea.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Opțiuni pentru modificarea în care entități de ordine sunt procesate în faza de potrivire.":::

1. Selectați **Terminat** pentru a salva regula.

## <a name="define-deduplication-on-a-match-entity"></a>Definiți eliminarea informațiilor duplicate pentru o entitate de potrivire

Pe lângă [reguli de potrivire între entități](#define-rules-for-match-pairs), puteți specifica și reguli de deduplicare. *Deduplicare* este un alt proces atunci când se potrivesc înregistrările. Identifică înregistrările duplicate și le îmbină într-o singură înregistrare. Înregistrările sursă sunt legate de înregistrarea combinată cu ID-uri alternative.

Înregistrările deduplicate vor fi utilizate în procesul de potrivire între entități. Deduplicarea are loc pe entități individuale și poate fi configurată fiecare entitate utilizată în perechi de potrivire.

Specificarea regulilor de eliminare a informațiilor duplicate nu este obligatorie. Dacă nu sunt configurate astfel de reguli, se aplică regulile definite de sistem. Acestea combină toate înregistrările într-o singură înregistrare înainte de a transfera datele entității la potrivirea între entități pentru o performanță îmbunătățită.

### <a name="add-deduplication-rules"></a>Adăugare reguli de eliminare a informațiilor duplicate

1. Mergeți la **Date** > **Unificare** > **Potrivire**.

1. În secțiunea **Dubluri combinate**, selectați **Setare entități**. În cazul în care regulile de deduplicare sunt deja create, selectați **Editați**.

1. În panoul **Îmbinare preferințe**, alegeți entitățile pe care doriți să rulați deduplicarea.

1. Specificați cum să combinați înregistrările duplicate și alegeți una dintre cele trei opțiuni:
   - **Cea mai completată**: Identifică înregistrarea cu cele mai populate câmpuri de atribute drept înregistrare câștigătoare. Este opțiunea implicită de combinare.
   - **Cea mai recentă**: Identifică înregistrarea câștigătoare pe baza celor mai recente. Necesită o dată sau un câmp numeric pentru a defini activitatea recentă.
   - **Cea mai puțin recentă**: Identifică înregistrarea câștigătoare pe baza celor mai puțin recente. Necesită o dată sau un câmp numeric pentru a defini activitatea recentă.
 
   > [!div class="mx-imgBorder"]
   > ![Reguli de eliminare a informațiilor duplicate pasul 1.](media/match-selfconflation.png "Reguli de eliminare a informațiilor duplicate pasul 1")
 
1. Odată ce entitățile sunt selectate și preferința lor de îmbinare este setată, selectați **Adăugați regulă** pentru a defini regulile de eliminare a informațiilor duplicate la nivel de entitate.
   - **Selectați câmpul** listează toate câmpurile disponibile de la acea entitate. Alegeți câmpul pe care doriți să îl verificați pentru duplicate. Alegeți câmpuri care sunt probabil unice pentru fiecare client. De exemplu, o adresă de e-mail sau combinația dintre nume, oraș și număr de telefon.
   - Specificați setările de normalizare și precizie.
   - Definiți mai multe condiții selectând **Adăugare condiție**.
 
   > [!div class="mx-imgBorder"]
   > ![Reguli de eliminare a informațiilor duplicate pasul 2.](media/match-selfconflation-rules.png "Reguli de eliminare a informațiilor duplicate pasul 2")

  Puteți crea mai multe reguli de eliminare a informațiilor duplicate pentru o entitate. 

1. Rularea procesului de potrivire grupează acum înregistrările pe baza condițiilor definite în regulile de eliminare a informațiilor duplicate. După gruparea înregistrărilor, politica de îmbinare este aplicată pentru a identifica înregistrarea câștigătoare.

1. Această înregistrare a câștigătorului este apoi transmisă potrivirii între entități, împreună cu înregistrările non-câștigătoare (de exemplu, ID-uri alternative) pentru a îmbunătăți calitatea potrivirii.

1. Orice regulă de potrivire personalizată definită suprascrie regulile de deduplicare. Dacă o regulă de eliminare a informațiilor duplicate identifică înregistrările de potrivire și o regulă de potrivire personalizată este setată să nu se potrivească niciodată cu aceste înregistrări, atunci aceste două înregistrări nu vor fi potrivite.

1. După [rularea procesului de potrivire](#run-the-match-process), veți vedea statisticile de deduplicare în dalele de măsurători cheie.

### <a name="deduplication-output-as-an-entity"></a>Ieșire de deduplicare ca entitate

Procesul de deduplicare creează o entitate nouă pentru fiecare entitate din perechile de potriviri pentru a identifica înregistrările deduplicate. Aceste entități pot fi găsite împreună cu **ConflationMatchPairs:CustomerInsights** în secțiunea **Sistem** din pagina **Entități**, cu numele **Deduplication_DataSource_Entity**.

O entitate de ieșire de deduplicare conține următoarele informații:
- ID-uri / Chei
  - Câmpul cheie primară și câmpul său ID-uri alternative. Câmpul ID-uri alternative constă din toate ID-urile alternative identificate pentru o înregistrare.
  - Câmpul Deduplication_GroupId arată grupul sau clusterul identificat în cadrul unei entități care grupează toate înregistrările similare pe baza câmpurilor de deduplicare specificate. Este utilizat în scopuri de procesare a sistemului. Dacă nu sunt specificate reguli de deduplicare manuală și se aplică reguli de deduplicare definite de sistem, este posibil să nu găsiți acest câmp în entitatea de ieșire a deduplicării.
  - Deduplication_WinnerId: Acest câmp conține ID-ul câștigător din grupurile sau clusterele identificate. Dacă Deduplication_WinnerId este aceeași cu valoarea cheii principale pentru o înregistrare, înseamnă că înregistrarea este înregistrarea câștigătoare.
- Câmpuri utilizate pentru definirea regulilor de deduplicare.
- Câmpurile Regulă și Scor pentru a indica care dintre regulile de deduplicare s-au aplicat și scorul returnat de algoritmul de potrivire.
   
## <a name="run-the-match-process"></a>Executați procesul de potrivire

Cu reguli de potrivire configurate, inclusiv a regulilor de potrivire și eliminare a informațiilor duplicate între entități, puteți rula procesul de potrivire. 

Accesați **Date** > **Unificare** > **Potrivire** și selectați **Rulare** pentru a începe procesul. Algoritmul de potrivire durează ceva timp pentru a fi finalizat și nu puteți modifica configurația până când nu se finalizează. Pentru a face modificări, puteți anula rularea. Selectați starea lucrării și selectați **Anulați operațiunea** pe panoul **Detalii despre progres**.

Veți găsi rezultatul unei rulări reușite, entitatea unificată a profilului de client, pe pagina **Entități**. Entitatea dvs. unificatăe de client se numește **Clienți** în secțiunea **Profiluri**. Prima rundă de potrivire reușită creează entitatea unificată *Client*. Toate rulările de potrivire ulterioare extind entitatea respectivă.

> [!TIP]
> După rularea procesului de potrivire, selectați starea procesului pentru a deschide panoul **Detalii despre activitate**. Oferă o prezentare generală despre timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate activității. Selectați **Consultați detalii** pentru a vedea ce entități au participat la procesul de potrivire, care reguli li s-au aplicat și dacă actualizările au fost publicate cu succes.  
> Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese. În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Cale de drill-down pentru a ajunge la procesarea detaliilor din legătura de stare a activității.":::

## <a name="review-and-validate-your-matches"></a>Examinați și validați-vă potrivirile

Accesați **Date** > **Unificare** > **Potrivire** pentru a evalua calitatea perechilor de potriviri și a le rafina dacă este necesar.

Dalele din partea de sus a paginii prezintă valori cheie, rezumând numărul de înregistrări și duplicate potrivite.

:::image type="content" source="media/match-KPIs.png" alt-text="Captură de ecran decupată a valorilor cheie din pagina Potrivire cu numere și detalii.":::

- **Înregistrări sursă unice** arată numărul de înregistrări sursă individuale care au fost procesate în ultima rundă de potrivire.
- **Înregistrări potrivite și nepotrivite** evidențiază câte înregistrări unice rămân după procesarea regulilor de potrivire.
- **Numai înregistrări potrivite** afișează numărul de potriviri din toate perechile dvs. de potriviri.

Puteți evalua rezultatele fiecărei perechi de potriviri și regulile sale în tabelul **Detalii înregistrări potrivite**. Comparați numărul de înregistrări provenite dintr-o pereche de potriviri cu procentul de înregistrări potrivite cu succes.

Examinați regulile unei perechi de potriviri pentru a vedea procentul de înregistrări potrivite cu succes la nivelul regulilor. Selectați punctele de suspensie (...) și apoi selectați **Previzualizare potrivire** pentru a vizualiza toate aceste înregistrări la nivel de regulă. Vă recomandăm să aruncați o privire asupra unor înregistrări pentru a verifica dacă acestea au fost potrivite corect.

Încercați diferite praguri de precizie în condiții pentru a găsi valoarea optimă.

  1. Selectați punctele de suspensie (...) pentru regula cu care doriți să experimentați și selectați **Editare**.

  2. Modificați valorile de precizie în condițiile pe care doriți să le revizuiți.

  3. Selectați **Previzualizare** deci consultați numărul de înregistrări potrivite și de neegalat pentru condiția selectată.

## <a name="manage-match-rules"></a>Gestionare reguli de potrivire

Puteți reconfigura și regla fin majoritatea parametrilor de potrivire.

:::image type="content" source="media/match-rules-management.png" alt-text="Captură de ecran a meniului derulant cu opțiuni pentru regulile de potrivire.":::

- **Modificați ordinea regulilor** dacă ați definit mai multe reguli. Puteți reordona regulile de potrivire selectând opțiunile **Mutați în sus** și **Mutați în jos** sau prin glisare și fixare.

- **Modificați condițiile regulii** prin selectarea **Editare** și alegeți câmpuri diferite.

- **Dezactivați o regulă** pentru a păstra o regulă de potrivire în timp ce o excludeți din procesul de potrivire.

- **Duplicați-vă regulile** dacă ați definit o regulă de potrivire și doriți să creați o regulă similară cu modificări, selectați **Duplicat**.

- **Ștergeți o regulă** selectând simbolul **Șterge**.

## <a name="specify-custom-match-conditions"></a>Specificați condițiile de potrivire personalizate

Puteți specifica condițiile la care anumite înregistrări trebuie să se potrivească întotdeauna sau să nu se potrivească niciodată. Aceste reguli pot fi încărcate pentru a suprascrie procesul de potrivire standard. De exemplu, dacă există în dosarele noastre John Doe I și John Doe II, sistemul s-ar putea să le potrivească ca o singură persoană. Regulile de potrivire personalizate vă permit să specificați că profilurile lor se referă la persoane diferite. 

1. Accesați **Date** > **Unificare** > **Potrivire** și selectați **Potrivire particularizată** în secțiunea **Detalii înregistrări potrivite**.

  :::image type="content" source="media/custom-match-create.png" alt-text="Captură de ecran a secțiunii regulilor de potrivire cu control de potrivire particularizat evidențiat.":::

1. Dacă nu aveți setate reguli de potrivire personalizate, veți vedea un nou panou **Potrivire personalizată** cu mai multe detalii.

1. Selectați **Completați șablonul** pentru a obține un fișier șablon care poate specifica înregistrările din ce entități trebuie să se potrivească întotdeauna sau să nu se potrivească niciodată. Va trebui să completați separat înregistrările "potrivire întotdeauna" și înregistrările "nu se potrivesc niciodată" în două fișiere diferite.

1. Șablonul conține câmpuri pentru a specifica entitatea și valorile cheie primare ale entității de utilizat în potrivirea particularizată. De exemplu, dacă doriți cheia primară *12345* din entitatea *Vânzări* să se potrivească întotdeauna cu cheia primară *34567* din entitatea *Persoană de contact*, completați șablonul:
    - Entity1: Vânzări
    - Entity1Key: 12345
    - Entity2: Persoană de contact
    - Entity2Key: 34567

   Același fișier șablon poate specifica înregistrări de potrivire particularizată de la mai multe entități.
   
   Dacă doriți să specificați potrivirea personalizată pentru deduplicare pe o entitate, furnizați aceeași entitate ca și Entity1 și Entity2 și setați diferitele valori ale cheii primare.

1. După adăugarea tuturor suprascrierilor pe care doriți să le aplicați, salvați fișierul șablon.

1. Accesați **Date** > **Surse de date** și ingerați fișierele șablon ca entități noi. Odată ingerate, le puteți utiliza pentru a specifica configurația Potrivire.

1. După încărcarea fișierelor și entităților disponibile, selectați din nou opțiunea **Corespondență particularizată**. Veți vedea opțiuni pentru a specifica entitățile pe care doriți să le includeți. Selectați entitățile necesare din meniul derulant.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Captură de ecran a dialogului pentru a alege suprascrierea pentru un scenariu de potrivire particularizat.":::

1. Selectați entitățile pe care doriți să le utilizați pentru **Se potrivește întotdeauna** și **Nu se potrivesc niciodată** selectați **Efectuat**.

1. Selectați **Salvare** pe **Potrivire** pentru a aplica configurația de potrivire personalizată.

1. Selectați **Rulare** pe pagina **Potrivire** pentru a începe procesul de potrivire. Alte reguli de potrivire specificate sunt suprascrise de configurația de potrivire personalizată.

> [!TIP]
> Accesați **Date** > **Entități** și revizuiți entitatea **ConflationMatchPair** pentru a confirma că suprascrierile sunt aplicate.

## <a name="next-step"></a>Următorul pas

După finalizarea procesului de potrivire pentru cel puțin o pereche de potrivire, puteți rezolva posibilele contradicții din datele dvs. parcurgând subiectul [**Îmbinare**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
