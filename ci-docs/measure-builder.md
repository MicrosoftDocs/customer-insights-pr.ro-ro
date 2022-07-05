---
title: Creați măsuri noi cu generatorul de măsuri
description: Construiți măsuri de la zero pentru a analiza valorile cheie despre afacerea dvs.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: f3ec86806074a12c1107648303ed2d65e97ebc69
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083022"
---
# <a name="create-new-measures-with-the-measure-builder"></a>Creați măsuri noi cu generatorul de măsuri

Acest articol explică cum să creați un nou [măsura](measures.md) de la zero. Generatorul de măsură vă permite să definiți calcule folosind operatori matematici, funcții de agregare și filtre. Puteți construi o măsură cu atribute de la entități care sunt legate de unificat *Client* entitate.

Crearea de măsuri în mediile B-to-C și B-to-B funcționează în același mod. Cu toate acestea, dacă sunteți în mediul B-to-B [folosește conturi cu ierarhii](relationships.md#set-up-account-hierarchies), puteți alege să agregați măsura în subconturi asociate.

De asemenea, puteți crea rapid o măsură alegând dintr-un set de măsuri utilizate în mod obișnuit și predefinite. Pentru mai multe informații, vezi [Utilizați un șablon pentru a construi o măsură](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Consumatori individuali (B2C)](#tab/b2c)

Puteți crea măsuri la nivelul clienților individuali (atribut client, măsura client) sau la nivelul afacerii/organizației (măsură business). Atributul clientului și măsura clientului sunt două tipuri care vă permit să urmăriți performanța per client. De exemplu, cheltuielile totale ale fiecărui client. Măsurile de afaceri vă permit să urmăriți performanța per companie. De exemplu, venitul total al companiei.

- Atribut client: generează rezultate ca un nou atribut, care este salvat ca o coloană nouă în entitatea generată de sistem numită *Customer_Measure*. La reîmprospătarea unui atribut de client, toate celelalte atribute de client din *Customer_Measure* reîmprospătarea entității simultan. În plus, atributele clientului sunt afișate în cardul de profil al clientului. Odată executat sau salvat, atributul clientului nu îl puteți schimba într-o măsură de client.

- Măsurarea clientului: generează rezultate ca entitate proprie și nu o puteți schimba într-un atribut de client odată rulat sau salvat. Măsurile clienților nu apar în cardul de profil al clientului.

- Măsura de afaceri: generează rezultate ca entitate proprie și se afișează pe pagina de pornire a mediului dumneavoastră Customer Insights.

1. Mergi la **Măsuri**.

1. Selectați **Nou** și alegeți **Construiți una proprie**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Ecran de configurare gol pentru o măsură B-to-C." lightbox="media/measure-b2c.png":::

1. Pentru a urmări performanța la nivel de afaceri, comutați **Tipul de măsură** la **Nivel de afaceri**. **Nivelul clientului** este selectat implicit. **Nivelul clientului** adaugă automat *Număr de înregistrare client* atribuie dimensiunilor în timp ce **Nivel de afaceri** îl îndepărtează automat.

1. În zona de configurare, alegeți funcția de agregare din **Selectați funcția** meniu derulant. Funcțiile de agregare includ:
   - **Sum**
   - **Medie**
   - **Contor**
   - **Număr unic**
   - **Max**
   - **Min**
   - **Primul**: ia prima valoare a înregistrării de date
   - **Ultimul**: ia ultima valoare care a fost adăugată la înregistrarea de date
   - **ArgMax** : găsește înregistrarea de date care oferă valoarea maximă dintr-o funcție țintă
   - **ArgMin** : găsește înregistrarea de date care oferă valoarea minimă dintr-o funcție țintă

1. Selectați **Adăugați un atribut** pentru a selecta datele de care aveți nevoie pentru a crea această măsură.

   1. Selectați fila **Atribute**.
   1. Entitate de date: alegeți entitatea care include atributul pe care doriți să îl măsurați.
   1. Atribut de date: alegeți atributul pe care doriți să îl utilizați în funcția de agregare pentru a calcula măsura. Puteți selecta doar un singur atribut o dată.
   1. De asemenea, puteți selecta un atribut de date dintr-o măsură existentă selectând fila **Măsuri**, sau puteți căuta o entitate sau un nume de măsură.
   1. Selectați **Adăuga** pentru a adăuga atributul selectat la măsură.

1. Pentru a construi măsuri mai complexe, puteți adăuga mai multe atribute sau puteți utiliza operatori matematici în funcția de măsurare.

1. Pentru a adăuga filtre, selectați **Filtru** în zona de configurare. Aplicarea filtrelor va folosi numai înregistrările care se potrivesc cu filtrele pentru a calcula măsura.
  
   1. În secțiunea **Adăugați atribut** a panoului **Filtre**, selectați atributul pe care doriți să îl utilizați pentru a crea filtre.
   1. Setați operatorii de filtrare să definească filtrul pentru fiecare atribut selectat.
   1. Selectați **Aplicare** pentru a adăuga filtrele la măsură.

1. Selectați **Dimensiune** pentru a alege mai multe câmpuri care sunt adăugate ca coloane la entitatea de ieșire a măsurătorilor.

   1. Selectați **Editați dimensiunile** pentru a adăuga atribute de date pe care doriți să le grupați valorile măsurate. De exemplu, oraș sau sex.
   > [!TIP]
   > Dacă ați selectat **Nivelul clientului** dupa cum **Tipul de măsură** cel *Număr de înregistrare client* atributul este deja adăugat. Dacă eliminați atributul, **Tipul de măsură** comută la **Nivel de afaceri**.
   1. Selectați **Gata** pentru a adăuga dimensiunile la măsură.

1. Dacă există date în datele dvs. pe care trebuie să le înlocuiți cu un număr întreg, selectați **Reguli**. Configurați regula și asigurați-vă că alegeți numai numere întregi ca înlocuitoare. De exemplu, înlocuiți *nul* cu *0*.

1. Dacă există mai multe căi între entitatea de date pe care ați mapat-o și entitatea *Client* trebuie să alegeți una dintre [căile relației entității](relationships.md) identificate. Rezultatele măsurătorilor pot varia în funcție de calea selectată.

   1. Selectați **Calea relației** și alegeți calea entității care ar trebui utilizată pentru a vă identifica măsura. Dacă există doar o singură cale către entitatea *Client*, acest control nu se va afișa.
   1. Selectați **Terminat** pentru a aplica selecția dvs.

1. Pentru a adăuga mai multe calcule pentru măsură, selectați **Calcul nou**. Puteți utiliza entități pe aceeași cale de entitate numai pentru noi calcule. Mai multe calcule vor fi afișate drept coloane dnoi în entitatea de ieșire de măsurare.

1. Selectați elipsa verticală (&vellip;) asupra calculului la **Duplicat**, **·**, sau **Elimina** un calcul dintr-o măsură.

1. În zona **Previzualizare**, veți vedea schema de date a entității de ieșire a măsurii, inclusiv filtre și dimensiuni. Previzualizarea reacționează dinamic la schimbările din configurație.

1. Selectați **Editează detaliile** lângă Măsura fără titlu. Furnizați un nume pentru măsura. Opțional, adăugați [Etichete](work-with-tags-columns.md#manage-tags) la masura.

   :::image type="content" source="media/measures_edit_details.png" alt-text="caseta de dialog Editare detalii.":::

1. Selectați **Rulare** pentru a calcula rezultatele pentru măsura configurată. Selectați **Salvați și închideți** dacă doriți să păstrați configurația curentă și să executați măsura mai târziu.

1. Accesați **Măsuri** pentru a vedea măsurarea nou creată în listă.

# <a name="business-accounts-b-to-b"></a>[Conturi de afaceri (B2B)](#tab/b2b)

Puteți crea măsuri la nivelul conturilor individuale (măsură client) sau la nivelul tuturor conturilor (măsură business).

- Măsurarea clientului: generează rezultate ca entitate proprie. Măsurile clienților nu apar în cardul de profil al clientului.

- Măsura de afaceri: generează rezultate ca entitate proprie și se afișează pe pagina de pornire a mediului dumneavoastră Customer Insights.

1. Mergi la **Măsuri**.

1. Selectați **Nou**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Ecran de configurare gol pentru o măsură B-to-B.":::

1. În zona de configurare, alegeți funcția de agregare din **Selectați funcția** meniu derulant. Funcțiile de agregare includ:
   - **Sum**
   - **Medie**
   - **Contor**
   - **Număr unic**
   - **Max**
   - **Min**
   - **Primul**: ia prima valoare a înregistrării de date
   - **Ultimul**: ia ultima valoare care a fost adăugată la înregistrarea de date

1. Selectați **Adăugați un atribut** pentru a selecta datele de care aveți nevoie pentru a crea această măsură.

   1. Selectați fila **Atribute**.
   1. Entitate de date: alegeți entitatea care include atributul pe care doriți să îl măsurați.
   1. Atribut de date: alegeți atributul pe care doriți să îl utilizați în funcția de agregare pentru a calcula măsura. Puteți selecta doar un singur atribut o dată.
   1. De asemenea, puteți selecta un atribut de date dintr-o măsură existentă selectând fila **Măsuri**, sau puteți căuta o entitate sau un nume de măsură.
   1. Selectați **Adăuga** pentru a adăuga atributul selectat la măsură.

1. Pentru a construi măsuri mai complexe, puteți adăuga mai multe atribute sau puteți utiliza operatori matematici în funcția de măsurare.

1. Pentru a adăuga filtre, selectați **Filtru** în zona de configurare. Aplicarea filtrelor va folosi numai înregistrările care se potrivesc cu filtrele pentru a calcula măsura.
  
   1. În secțiunea **Adăugați atribut** a panoului **Filtre**, selectați atributul pe care doriți să îl utilizați pentru a crea filtre.
   1. Setați operatorii de filtrare să definească filtrul pentru fiecare atribut selectat.
   1. Selectați **Aplicare** pentru a adăuga filtrele la măsură.

1. Selectați **Dimensiune** pentru a alege mai multe câmpuri care sunt adăugate ca coloane la entitatea de ieșire a măsurătorilor.

   1. Selectați **Editați dimensiunile** pentru a adăuga atribute de date pe care doriți să le grupați valorile măsurate. De exemplu, oraș sau sex.
      > [!TIP]
      > Dacă ați selectat **Nivelul clientului** dupa cum **Tipul de măsură** cel *Număr de înregistrare client* atributul este deja adăugat. Dacă eliminați atributul, **Tipul de măsură** comută la **Nivel de afaceri**.
   1. Selectați **Gata** pentru a adăuga dimensiunile la măsură.

1. Dacă există date în datele dvs. pe care trebuie să le înlocuiți cu un număr întreg, selectați **Reguli**. Configurați regula și asigurați-vă că alegeți numai numere întregi ca înlocuitoare. De exemplu, înlocuiți *nul* cu *0*.

1. Puteți utiliza **Completați sub-conturile** comutați dacă [utilizați conturi cu ierarhii](relationships.md#set-up-account-hierarchies).
   - Dacă este setat la **Dezactivat**, măsura este calculată pentru fiecare cont. Fiecare cont devine propriul rezultat.
   - Dacă este setat la **Pornit**, selectați **Editați** pentru a alege ierarhia contului în funcție de ierarhiile ingerate. Măsura va produce un singur rezultat, deoarece este agregată cu conturi secundare.

1. Dacă există mai multe căi între entitatea de date pe care ați mapat-o și entitatea *Client* trebuie să alegeți una dintre [căile relației entității](relationships.md) identificate. Rezultatele măsurătorilor pot varia în funcție de calea selectată.

   1. Selectați **Calea relației** și alegeți calea entității care ar trebui utilizată pentru a vă identifica măsura. Dacă există doar o singură cale către entitatea *Client*, acest control nu se va afișa.
   1. Selectați **Terminat** pentru a aplica selecția dvs.

1. Selectați elipsa verticală (&vellip;) asupra calculului la **Duplicat**, **·**, sau **Elimina** un calcul dintr-o măsură.

1. În zona **Previzualizare**, veți vedea schema de date a entității de ieșire a măsurii, inclusiv filtre și dimensiuni. Previzualizarea reacționează dinamic la schimbările din configurație.

1. Selectați **Editează detaliile** lângă Măsura fără titlu. Furnizați un nume pentru măsura. Opțional, adăugați [Etichete](work-with-tags-columns.md#manage-tags) la masura.

   :::image type="content" source="media/measures_edit_details.png" alt-text="caseta de dialog Editare detalii.":::

1. Selectați **Rulare** pentru a calcula rezultatele pentru măsura configurată. Selectați **Salvați și închideți** dacă doriți să păstrați configurația curentă și să executați măsura mai târziu.

1. Accesați **Măsuri** pentru a vedea măsurarea nou creată în listă.
