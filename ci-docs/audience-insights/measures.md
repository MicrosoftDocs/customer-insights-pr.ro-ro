---
title: Creați și editați măsuri
description: Definiți măsurile legate de client pentru a analiza și reflecta performanța anumitor domenii de afaceri.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406705"
---
# <a name="define-and-manage-measures"></a>Definiți și gestionați măsurile

**Măsuri** reprezintă indicatori de performanță cheie (KPI) care reflectă performanța și sănătatea domeniilor de activitate specifice. Detaliile despre public oferă o experiență intuitivă pentru crearea diferitelor tipuri de măsuri, utilizând un generator de interogări care nu necesită codare sau validarea manuală a măsurilor. Aveți posibilitatea să urmăriți măsurile de afaceri pe pagina de **pornire**, să consultați măsuri pentru anumiți clienți din **cardul de client** și să utilizați măsuri pentru a defini segmentele de clienți din pagina **Segmente**.

## <a name="create-a-measure"></a>Crearea unei măsuri

Această secțiune vă ajută apoi să parcurgeți prin crearea unei măsuri de la zero. Puteți construi măsuri cu date din mai multe surse de date care sunt conectate prin entitatea Client. Se aplică unele [limite ale serviciului](service-limits.md).

1. În Detalii despre public, accesați **Măsuri**.

2. Selectați **Măsură nouă**.

3. Alegeți **Tipul** de măsură:

   - **Atribut client**: Un singur câmp per client care reflectă un scor, o valoare sau o stare pentru client. Atributele clientului sunt create ca atribute într-o nouă entitate generată de sistem numită **Customer_Measure**.

   - **Măsură client**: Statistici privind comportamentul clienților cu defalcarea în funcție de dimensiunile selectate. O entitate nouă este generată pentru fiecare măsură, potențial cu mai multe înregistrări per client.

   - **Măsură de afaceri**: Urmărește performanța afacerii și sănătatea afacerii. Măsurile de afaceri pot avea două rezultate diferite: o ieșire numerică care se afișează pe pagina **Acasă** sau o entitate nouă pe care o găsiți pe pagina **Entități**.

4. Oferiți un **Nume** și opțional **Nume afișat**, apoi selectați **Următorul**.

5. În secțiunea **Entități**, selectați prima entitate din lista derulantă. În acest moment, ar trebui să decideți dacă sunt necesare entități suplimentare ca parte a definirii măsurii.

   > [!div class="mx-imgBorder"]
   > ![Definiție măsură](media/measure-definition.png "Definiție măsură")

   Pentru a adăuga mai multe entități, selectați **Adăugați entitatea** și selectați entitățile pe care doriți să le utilizați pentru măsură.

   > [!NOTE]
   > Puteți selecta numai entitățile care au relații cu entitatea dvs. de început. Pentru informații suplimentare despre definirea relațiile, consultați [Relații](relationships.md).

6. Opțional, puteți configura variabile. În secțiunea **Variabile**, selectați **Variabilă nouă**.

   Variabilele sunt calcule care se fac pe fiecare dintre înregistrările selectate. De exemplu, însumarea punctului de vânzare (POS) și vânzările online pentru fiecare dintre înregistrările clienților.

7. Furnizați un **Nume** pentru variabile.

8. În zona **Expresie**, alegeți un câmp cu care să începeți calculul.

9. Introduceți o expresie în **Expresie** în timp ce alegeți mai multe câmpuri care vor fi incluse în calcul.

   > [!NOTE]
   > În prezent, sunt acceptate doar expresiile aritmetice. În plus, calculul variabilelor nu este acceptat pentru entități din diferite [căi de entitate](relationships.md).

10. Selectați **Terminat**.

11. În secțiunea **Definiție măsură**, veți defini modul în care entitățile alese și variabilele calculate sunt agregate într-o nouă entitate sau atribut de măsură.

12. Selectați **Dimensiune nouă**. Puteți da exemplu pentru o dimensiune ca funcție a *grupare după*. Rezultatul de date al entității sau atributului dvs. de măsurare va fi grupat după toate dimensiunile dvs. definite.

    > [!div class="mx-imgBorder"]
    > ![Alegeți ciclul agregat](media/measures-businessreport-measure-definition2.png "Alegeți ciclul agregat")

    Selectați sau introduceți următoarele informații ca parte a definiției dimensiunii dvs.:

    - **Entitate**: Dacă definiți o entitate de măsurare, aceasta ar trebui să includă cel puțin un atribut. Dacă definiți un atribut Măsură, acesta va include în mod implicit un singur atribut. Această selecție se referă la alegerea entității care include acel atribut.
    - **Câmp**: Alegeți atributul specific care trebuie inclus fie în entitatea dvs. Măsură, fie în atributul dvs.
    - **Pachet**: Alegeți dacă doriți să agregați datele zilnic, lunar sau anual. Este o selecție necesară numai dacă ați selectat un atribut de tip Date.
    - **Ca**: Definește numele noului câmp.
    - **Nume afișat**: Definește numele afișat al câmpului dvs.

    > [!NOTE]
    > Măsura dvs. de afaceri va fi salvată ca o entitate cu un singur număr și va apărea pe pagina **Acasă** dacă nu adăugați mai multe dimensiuni la măsura dvs. După adăugarea mai multor dimensiuni, măsura va *nu* va apărea pe pagina **Acasă**.

13. Opțional, adăugați funcții de agregare. Orice agregare pe care o creați are ca rezultat o nouă valoare în entitatea sau atributul dvs. Măsuri. Funcțiile de agregare acceptate sunt: **Min**, **Max**, **În medie**, **Median**, **Sumă**, **Cont unic**, **Primul** (ia prima înregistrare a unei valori a dimensiunii) și **Ultimul** (ia ultima înregistrare la o valoare a dimensiunii).

14. Selectați **Salvare** pentru a aplica modificările la măsura dvs..

## <a name="manage-your-measures"></a>Gestionați-vă măsurile

După ce creați cel puțin o măsură, veți vedea o listă de măsuri pe pagina **Măsuri**.

Veți găsi informații despre tipul de măsură, creatorul, data și ora de creare, ultima dată și oră de modificare, starea (dacă măsura este activă, inactivă sau eșuată) și ultima dată și oră de actualizare. Când selectați o măsură din listă, puteți vedea o previzualizare a rezultatului acesteia.

Pentru a vă reîmprospăta toate măsurile în același timp, selectați **Reîmprospătați tot** fără a selecta o anumită măsură.

> [!div class="mx-imgBorder"]
> ![Acțiuni de gestionare a măsurilor unice](media/measure-actions.png "Acțiuni de gestionare a măsurilor unice")

Alternativ, selectați o măsură din listă și efectuați una dintre următoarele acțiuni:

- Selectați numele măsurii pentru a vedea detaliile acesteia.
- **Editați** configurația măsurii.
- **Redenumiți** măsura.
- **Ștergeți** măsura.
- Selectați elipsele (...) și apoi **Reîmprospătați** pentru a începe procesul de reîmprospătare pentru măsură.
- Selectați elipsele (...) și apoi **Descărcați** pentru a obține un fișier .CSV al măsurii.

> [!TIP]
> Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese. În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies). Puteți selecta starea unui proces pentru a vedea detalii despre evoluția întregii lucrări. După selectarea **Vizualizare detalii** pentru una dintre sarcinile jobului, găsiți informații suplimentare: timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate sarcinii.

## <a name="next-step"></a>Următorul pas

Puteți utiliza măsuri existente pentru a crea primul segment de clienți pe pagina **Segmente**. Pentru mai multe informații, consultați [Segmente](segments.md).
