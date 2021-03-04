---
title: Crearea și gestionarea măsurilor
description: Definiți măsuri pentru a analiza și reflecta performanța afacerii dvs.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269943"
---
# <a name="define-and-manage-measures"></a>Definiți și gestionați măsurile

Măsurile vă ajută să înțelegeți mai bine comportamentele clienților și performanța afacerii prin recuperarea valorilor relevante din [profiluri unificate](data-unification.md). De exemplu, o companie vrea să vadă *cheltuieli totale per client* pentru a înțelege istoricul achizițiilor clientului individual. Sau măsurați *vânzările totale ale companiei* pentru a înțelege veniturile la nivel agregat din întreaga afacere.  

Măsurile sunt create folosind generatorul de măsuri, o platformă de interogare a datelor cu diverși operatori și opțiuni simple de mapare. Vă permite să filtrați datele, să grupați rezultatele, să detectați [căile relației entității](relationships.md), și previzualizați ieșirea.

Utilizați instrumentul de măsurare pentru a planifica activități comerciale prin interogarea datelor despre clienți și extragerea de informații. De exemplu, crearea unei măsuri de *cheltuieli totale per client* și *returnare totală per client* ajută la identificarea unui grup de clienți cu cheltuieli mari, dar cu randament ridicat. Puteți [crea un segment](segments.md) pentru a conduce următoarele cele mai bune acțiuni. 

## <a name="create-a-measure"></a>Crearea unei măsuri

Această secțiune vă ajută să creați o nouă măsură de la zero. Puteți construi o măsură cu atribute de date de la entități de date care au o relație configurată pentru a se conecta cu entitatea Client. 

1. În Detalii despre public, accesați **Măsuri**.

1. Selectați **Nou**.

1. Selectați **Editează nume** și furnizați un **Nume** pentru măsură. 
   > [!NOTE]
   > Dacă noua dvs. configurație de măsurare are doar două câmpuri, de exemplu, CustomerID și un singur calcul, rezultatul va fi adăugat ca o nouă coloană la entitatea generată de sistem numită Customer_Measure. Și veți putea vedea valoarea măsurii în profilul de client unificat. Alte măsuri își vor genera propriile entități.

1. În zona de configurare, alegeți funcția de agregare din meniul derulant **Selectați Funcție**. Funcțiile de agregare includ: 
   - **Sum**
   - **Medie**
   - **Contor**
   - **Număr unic**
   - **Max**
   - **Min**
   - **Primul**: ia prima valoare a înregistrării de date
   - **Ultimul**: ia ultima valoare care a fost adăugată la înregistrarea de date

   :::image type="content" source="media/measure-operators.png" alt-text="Operatori pentru calcule de măsură.":::

1. Selectați **Adăugați un atribut** pentru a selecta datele de care aveți nevoie pentru a crea această măsură.
   
   1. Selectați fila **Atribute**. 
   1. Entitate de date: alegeți entitatea care include atributul pe care doriți să îl măsurați. 
   1. Atribut de date: alegeți atributul pe care doriți să îl utilizați în funcția de agregare pentru a calcula măsura. Puteți selecta doar un singur atribut o dată.
   1. De asemenea, puteți selecta un atribut de date dintr-o măsură existentă selectând fila **Măsuri**. Sau puteți căuta o entitate sau un nume de măsură. 
   1. Selectați **Adăuga** pentru a adăuga atributul selectat la măsură.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Selectați un atribut de utilizat în calcule.":::

1. Pentru a construi măsuri mai complexe, puteți adăuga mai multe atribute sau puteți utiliza operatori matematici în funcția de măsurare.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Creați o măsură complexă cu operatori matematici.":::

1. Pentru a adăuga filtre, selectați **Filtru** în zona de configurare. 
  
   1. În secțiunea **Adăugați un atribut** din panoul **Filtre**, selectați atributul pe care doriți să îl utilizați pentru a crea filtre.
   1. Setați operatorii de filtrare să definească filtrul pentru fiecare atribut selectat.
   1. Selectați **Aplicare** pentru a adăuga filtrele la măsură.

1. Pentru a adăuga dimensiuni, selectați **Dimensiune** în zona de configurare. Dimensiunile vor fi afișate ca coloane în entitatea de ieșire de măsurare.
   1. Selectați **Editați dimensiunile** pentru a adăuga atribute de date pe care doriți să le grupați valorile măsurate. De exemplu, oraș sau sex. În mod implicit, dimensiunea *CustomerID* este selectată pentru a crea *măsuri la nivel de client*. Puteți elimina dimensiunea implicită dacă doriți să creați *măsuri la nivel de afaceri*.
   1. Selectați **Gata** pentru a adăuga dimensiunile la măsură.

1. Dacă există mai multe căi între entitatea de date pe care ați mapat-o și entitatea Client, trebuie să alegeți una dintre [căile relației entității](relationships.md) identificate. Rezultatele măsurătorilor pot varia în funcție de calea selectată.
   1. Selectați **Preferințe de date** și alegeți calea entității care ar trebui utilizată pentru a vă identifica măsura.
   1. Selectați **Terminat** pentru a aplica selecția dvs. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Selectați entitatea cale pentru măsură.":::

1. Pentru a adăuga mai multe calcule pentru măsură, selectați **Calcul nou**. Puteți utiliza entități pe aceeași cale de entitate numai pentru noi calcule. Mai multe calcule vor fi afișate drept coloane dnoi în entitatea de ieșire de măsurare.

1. Selectați **...** asupra calculului la **Duplicat**, **Redenumiți**, sau **Eliminați** un calcul dintr-o măsură.

1. În zona **Previzualizare**, veți vedea schema de date a entității de ieșire a măsurii, inclusiv filtre și dimensiuni. Previzualizarea reacționează dinamic la schimbările din configurație.

1. Selectați **Rulare** pentru a calcula rezultatele pentru măsura configurată. Selectați **Salvați și închideți** dacă doriți să păstrați configurația curentă și să executați măsura mai târziu.

1. Accesați **Măsuri** pentru a vedea măsurarea nou creată în listă.

## <a name="manage-your-measures"></a>Gestionați-vă măsurile

După ce [creați o măsură](#create-a-measure), veți vedea o listă de măsuri pe pagina **Măsuri**.

Veți găsi informații despre tipul de măsură, creatorul, data creării, starea și starea. Când selectați o măsură din listă, puteți previzualiza rezultatul și descărca un fișier .CSV.

Pentru a vă reîmprospăta toate măsurile în același timp, selectați **Reîmprospătați tot** fără a selecta o anumită măsură.

> [!div class="mx-imgBorder"]
> ![Acțiuni de gestionare a măsurilor unice](media/measure-actions.png "Acțiuni de gestionare a măsurilor unice")

Selectați o măsură din listă pentru următoarele opțiuni:

- Selectați numele măsurii pentru a vedea detaliile acesteia.
- **Editați** configurația măsurii.
- **Reîmprospătați** măsura pe baza celor mai recente date.
- **Redenumiți** măsura.
- **Ștergeți** măsura.
- **Activați** sau **Dezactivați**. Măsurile inactive nu vor fi reîmprospătate în timpul unei [reîmprospătări planificate](system.md#schedule-tab).

> [!TIP]
> Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese. În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies). Puteți selecta starea unui proces pentru a vedea detalii despre evoluția întregii lucrări. După selectarea **Vizualizare detalii** pentru una dintre sarcinile jobului, găsiți informații suplimentare: timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate sarcinii.

## <a name="next-step"></a>Următorul pas

Utilizați cam măsurile existente pentru a crea [un segment de clienți](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]