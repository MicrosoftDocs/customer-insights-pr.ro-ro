---
title: Crearea și gestionarea segmentelor
description: Creați segmente de clienți pentru a îi grupa pe baza diferitelor atribute.
ms.date: 07/18/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a19661abea42618ef1848110c05d635a925c68f
ms.sourcegitcommit: c45b094072cbe3fbf61d1e9e7d220e1f29ffebd0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/29/2021
ms.locfileid: "6685477"
---
# <a name="create-and-manage-segments"></a>Crearea și gestionarea segmentelor

> [!IMPORTANT]
> Există câteva modificări care au fost lansate în experiența de creare a segmentului în septembrie 2021: 
> - Constructorul de segmente va arăta ușor diferit cu elemente restilizate și un flux de utilizatori îmbunătățit.
> - Operatorii noi datetime și un selector de date îmbunătățit sunt activate în generatorul de segmente.
> - Veți putea adăuga sau elimina condiții și reguli din segmente. 
> - Regulile imbricate care încep cu o condiție SAU vor deveni disponibile. Nu mai aveți nevoie de o afecțiune AND la nivelul cel mai exterior.
> - Un panou lateral pentru selectarea atributelor va fi disponibil în mod constant.
> - O opțiune pentru a selecta căile relației entității.
> Pentru a încerca noul constructor de segmente, trimiteți un e-mail cu subiectul „Solicitați activarea noului constructor de segmente” la cihelp [at] microsoft.com. Includeți numele organizației dvs. și ID-ul mediului dvs. sandbox.

Definiți filtre complexe pe baza entității client unificate și a entităților conexe. Fiecare segment, după procesare, creează un set de înregistrări ale clienților pe care le puteți exporta și pe care puteți acționa. Segmentele sunt gestionate pe pagina **Segmente**. 

Următorul exemplu ilustrează capabilitatea de segmentare. Am definit un segment pentru clienții care au comandat cel puțin $500 de bunuri în ultimele 90 de zile *și* care au fost implicați într-un apel serviciu pentru relații cu clienții care a fost escaladat.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Captură de ecran a interfeței UI a generatorului de segmente cu două grupuri care specifică un segment de clienți.":::

## <a name="create-a-new-segment"></a>Crearea unui nou segment

Sunt mai multe moduri de a crea un segment nou. Această secțiune descrie modul de a crea un *segment necompletat* de la zero. De asemenea, puteți să creați un *segment rapid* pe baza entităților existente sau să valorificați modelele de învățare programată pentru a obține *segmente sugerate*. Mai multe informații: [Prezentare generală a segmentelor](segments.md).

Când creați un segment, puteți salva o schiță. Aceasta va fi salvată ca segment inactiv și nu se poate activa, se va termina cu o configurație validă.

1. Salt la pagina **Segmente**.

1. Selectați **Nou** > **Segment necompletat**.

1. În panoul **Segment nou**, alegeți un tip de segment:

   - **Segmente dinamice** [reîmprospătați](segments.md#refresh-segments) după o Planificare recurentă.
   - **Segmente statice** se rulează o dată când le creați.

1. Dați un **Numele al entității de ieșire** pentru segment. Opțional, furnizați un nume afișat și o descriere care ajută la identificarea segmentului.

1. Selectați **Următorul** pentru a ajunge la pagina **Generator de segmente** unde definiți un grup. Un grup este un grup de clienți.

1. Alegeți entitatea care include atributul pe care doriți să îl segmentați.

1. Alegeți atributul pentru care utilizați segmentul. Acest atribut poate avea unul dintre cele patru tipuri de valori: numeric, șir, dată sau boolean.

1. Alegeți un operator și o valoare pentru atributul selectat.

   > [!div class="mx-imgBorder"]
   > ![Particularizați filtrul de grup.](media/customer-group-numbers.png "Filtrul de grup de clienți")

   |Număr |Definiție  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atribut          |
   |3    |Operator         |
   |4    |Valoare         |

   1. Pentru a adăuga mai multe condiții unui grup, puteți utiliza doi operatori logici:

      - Operator **ȘI**: Ambele condiții trebuie îndeplinite ca parte a procesului de segmentare. Această opțiune este cea mai utilă atunci când definiți condiții pentru diferite entități.

      - Operatorul **SAU**: Fiecare dintre condiții trebuie îndeplinită ca parte a procesului de segmentare. Această opțiune este cea mai utilă atunci când definiți condiții multiple pentru aceeași entitate.

      > [!div class="mx-imgBorder"]
      > ![Operatorul SAU unde fiecare condiție trebuie îndeplinită.](media/segmentation-either-condition.png "Operatorul SAU unde fiecare condiție trebuie îndeplinită")

      În prezent este posibil să imbricați un operator **SAU** sub unul **ȘI**, dar nu și invers.

   1. Fiecare grup se potrivește cu un set de clienți. Puteți combina mai multe grupuri pentru a include clienții necesari pentru cazul dvs. de afaceri.    
   Selectați **Adăugați un grup**.

      > [!div class="mx-imgBorder"]
      > ![Grup Adăugare grup de clienți.](media/customer-group-add-group.png "Grup Adăugare grup de clienți")

   1. Selectați unul dintre operatorii de mulțimi: **Reuniune**, **Intersecție** sau **Cu excepția**.

   > [!div class="mx-imgBorder"]
   > ![Uniune Adăugare grup de clienți.](media/customer-group-union.png "Uniune Adăugare grup de clienți")

   - **Uniune** unește cele două grupuri.

   - **Intersectare** suprapune cele două grupuri. Doar datele care *sunt comune* pentru ambele grupuri sunt reținute în grupul unificat.

   - **Excepție** combină cele două grupuri. Doar datele din grupul A care *nu sunt comune* cu datele din grupul B sunt reținute.

1. Dacă entitatea este conectată la entitatea client unificată prin [relații](relationships.md), trebuie să definiți calea relației pentru a crea un segment valid. Adăugați entitățile din calea relației până când puteți selecta entitatea **Client: CustomerInsights** din meniul listă verticală. Apoi alegeți **Toate înregistrările** pentru fiecare pas.

   > [!div class="mx-imgBorder"]
   > ![Calea relației în timpul creării segmentului.](media/segments-multiple-relationships.png "Calea relației în timpul creării segmentului")

1. În mod implicit, segmentele generează o entitate de ieșire care conține toate atributele profilurilor clienților care se potrivesc cu filtrele definite. Dacă un segment se bazează pe alte entități decât entitatea *Client*, puteți adăuga mai multe atribute de la aceste entități la entitatea de ieșire. Selectați **Atributele proiectului** pentru a alege atributele care vor fi anexate entității de ieșire.  
  
   Exemplu: un segment se bazează pe o entitate care conține date despre activitatea clienților care sunt legate de entitatea *Client*. Segmentul caută toți clienții care au apelat la serviciul de asistență în ultimele 60 de zile. Puteți alege să adăugați durata apelului și numărul de apeluri la toate înregistrările de clienți care se potrivesc în entitatea de ieșire. Aceste informații ar putea fi utile pentru a trimite un e-mail cu linkuri utile către articole de ajutor online și întrebări frecvente către clienții care au sunat frecvent.

   > [!NOTE]
   > - Atributele proiectate vor funcționa doar pentru entitățile care au o relație unu-la-mulți cu entitatea client. De exemplu, un client poate avea mai multe abonamente.
   > - Puteți să proiectați atribute numai de la o entitate care este utilizată în fiecare grup de interogări de segmente creat.
   > - Atributele proiectate sunt luate în calcul atunci când se utilizează operatori de mulțimi.

1. Selectați **Salvare** pentru a vă salva segmentul. Segmentul dvs. va fi salvat și procesat dacă toate cerințele sunt validate. În caz contrar, acesta va fi salvat ca schiță.

1. Selectați **Înapoi la segmente** pentru a reveni la pagina **Segmente**.



## <a name="quick-segments"></a>Segmente rapide

Segmentele rapide permit crearea de segmente simple cu un singur operator rapid pentru informații mai rapide.

1. Pe pagina **Segmente**, selectați **Nou** > **Creare din**.

   - Selectați opțiunea **Profiluri** pentru a construi un segment care se bazează pe entitatea *Client unificat*.
   - Selectați opțiunea **Măsuri** pentru a construi un segment în jurul măsurilor pe care le-ați creat anterior.
   - Selectați opțiunea **Inteligență** pentru a construi un segment în jurul uneia dintre entitățile de ieșire pe care le-ați generat folosind fie capabilități **Predicții** sau **Modele particularizate**.

2. În caseta de dialog **Segment rapid nou**, selectați un atribut din lista verticală **Câmp**.

3. Sistemul va oferi câteva informații suplimentare care vă vor ajuta să creați segmente mai bune de clienți.
   - Pentru câmpurile categorice, vom afișa 10 numere de clienți de top. Alegeți o **Valoare** și selectați **Revizuire**.

   - Pentru un atribut numeric, sistemul va arăta ce valoare a atributului se încadrează sub percentila fiecărui client. Alegeți un **Operator** și o **Valoare**, apoi selectați **Revizuire**.

4. Sistemul vă va oferi o **Dimensiunea estimată segment**. Puteți alege dacă vreți să generați segmentul pe care l-ați definit sau să îl revizuiți mai întâi pentru a obține o dimensiune diferită a segmentului.

    > [!div class="mx-imgBorder"]
    > ![Numele și estimarea pentru un segment rapid.](media/quick-segment-name.png "Numele și estimarea pentru un segment rapid")

5. Furnizați un **Nume** pentru segmentul dvs. Opțional, furnizați un **Nume afișat**.

6. Selectați **Salvare** pentru a crea segmentul.

7. După ce segmentul a terminat procesarea, îl puteți vizualiza ca orice alt segment creat.

## <a name="next-steps"></a>Pașii următori

[Exportați un segment](export-destinations.md) și explorați [Card client](customer-card-add-in.md) și [Conectori](export-power-bi.md) pentru a obține informații despre nivelul clientului.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
