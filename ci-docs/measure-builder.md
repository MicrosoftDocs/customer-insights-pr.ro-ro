---
title: Creați măsuri cu generatorul de măsuri
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
ms.openlocfilehash: fac00b8a1b4ca6e09dd29abe46dfe240adcc029e
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170878"
---
# <a name="create-measures-with-measure-builder"></a>Creați măsuri cu generatorul de măsuri

Measure Builder vă permite să definiți calcule folosind operatori matematici, funcții de agregare și filtre. Definiți măsuri folosind atribute de la entități care sunt legate de unificat *Client* entitate.

Crearea de măsuri în mediile B-to-C și B-to-B funcționează în același mod. Cu toate acestea, dacă mediul dvs. B-to-B [folosește conturi cu ierarhii](relationships.md#set-up-account-hierarchies), alegeți dacă să agregați măsura în subconturi asociate.

# <a name="individual-consumers-b-to-c"></a>[Consumatori individuali (B2C)](#tab/b2c)

Creați măsuri la nivelul clienților individuali (atributul clientului, măsura clientului) sau la nivelul afacerii/organizației (măsurarea afacerii). Atributul și măsura clientului vă permit să urmăriți performanța per client. De exemplu, cheltuielile totale ale fiecărui client. Măsurile de afaceri urmăresc performanța per companie. De exemplu, venitul total al companiei.

- Atribut client: generează rezultate ca un nou atribut, care este salvat ca o coloană nouă în entitatea generată de sistem numită *Customer_Measure*. La reîmprospătarea unui atribut de client, toate celelalte atribute de client din *Customer_Measure* reîmprospătarea entității simultan. În plus, atributele clientului sunt afișate în cardul de profil al clientului. Odată executat sau salvat, nu puteți modifica un atribut de client într-o măsură de client.

- Măsurarea clientului: generează rezultate ca entitate proprie și nu o puteți schimba într-un atribut de client odată executată sau salvată. Măsurile clienților nu apar în cardul de profil al clientului.

- Măsura de afaceri: generează rezultate ca entitate proprie și se afișează pe pagina de pornire a mediului dumneavoastră Customer Insights.

1. Mergi la **Măsuri**.

1. Selectați **Nou** > **Construiește-ți propriul**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Ecran de configurare gol pentru o măsură B-to-C." lightbox="media/measure-b2c.png":::

1. Selectați **Editează detaliile** lângă Măsura fără titlu. Furnizați un nume pentru măsura. Opțional, adăugați [Etichete](work-with-tags-columns.md#manage-tags) la masura.

   :::image type="content" source="media/measures_edit_details.png" alt-text="caseta de dialog Editare detalii.":::

1. Selectați **Terminat**.

1. Pentru a urmări performanța la nivel de afaceri, comutați **Tipul de măsură** la **Nivel de afaceri**. **Nivelul clientului** este selectat implicit. **Nivelul clientului** adaugă automat *Număr de înregistrare client* atribuie Dimensiuni în timp ce **Nivel de afaceri** îl îndepărtează automat.

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

1. Selectați **Adăugați un atribut** pentru a selecta datele pentru a crea această măsură.

   1. Selectați fila **Atribute**.
   1. Entitate de date: alegeți entitatea care include atributul pe care doriți să îl măsurați.
   1. Atribut de date: alegeți atributul pe care doriți să îl utilizați în funcția de agregare pentru a calcula măsura. Puteți selecta doar un singur atribut o dată.
   1. Opțional, alegeți un atribut de date dintr-o măsură existentă selectând **Măsuri** fila sau căutați un nume de entitate sau măsură.
   1. Selectați **Adăugare**.

1. Pentru a construi măsuri mai complexe, adăugați mai multe atribute sau utilizați operatori matematici în funcția de măsurare.

1. Pentru a adăuga filtre, selectați **Filtru** în zona de configurare. Aplicarea filtrelor va folosi numai înregistrările care se potrivesc cu filtrele pentru a calcula măsura.
  
   1. În secțiunea **Adăugați atribut** a panoului **Filtre**, selectați atributul pe care doriți să îl utilizați pentru a crea filtre.
   1. Setați operatorii de filtrare să definească filtrul pentru fiecare atribut selectat.
   1. Selectați **Se aplică**.

1. Selectați **Dimensiune** pentru a alege mai multe câmpuri de adăugat ca coloane la entitatea de ieșire a măsurătorilor.

   1. Selectați **Editați dimensiunile** pentru a adăuga atribute de date pe care doriți să le grupați valorile măsurate. De exemplu, oraș sau sex.
      > [!TIP]
      > Dacă ați selectat **Nivelul clientului** dupa cum **Tipul de măsură** cel *Număr de înregistrare client* atributul este deja adăugat. Dacă eliminați atributul, **Tipul de măsură** comută la **Nivel de afaceri**.
   1. Selectați **Terminat**.

1. Dacă există valori în datele dvs. care trebuie înlocuite cu un număr întreg, selectați **Reguli**. Configurați regula și asigurați-vă că alegeți numai numere întregi ca înlocuitoare. De exemplu, înlocuiți *nul* cu *0*.

1. Dacă există mai multe căi între entitatea de date pe care ați mapat-o și *Client* entitate, alegeți unul dintre cei identificați [căi de relație cu entitate](relationships.md). Rezultatele măsurătorilor pot varia în funcție de calea selectată.

   1. Selectați **Calea relației** și alegeți calea entității care ar trebui utilizată pentru a vă identifica măsura. Dacă există doar o singură cale către entitatea *Client*, acest control nu se va afișa.
   1. Selectați **Terminat**.

1. Pentru a adăuga mai multe calcule pentru măsură, selectați **Calcul nou**. Utilizați numai entități de pe aceeași cale de entitate pentru calcule noi. Mai multe calcule vor fi afișate drept coloane dnoi în entitatea de ieșire de măsurare. Opțional, selectați **Editeaza numele** pentru a crea un nume pentru calcul.

1. Selectați elipsa verticală (&vellip;) asupra calculului la **Duplicat** sau **Elimina** un calcul dintr-o măsură.

1. În zona **Previzualizare**, veți vedea schema de date a entității de ieșire a măsurii, inclusiv filtre și dimensiuni. Previzualizarea reacționează dinamic la schimbările din configurație.

1. Selectați **Rulare** pentru a calcula rezultatele pentru măsura configurată. Selectați **Salvați și închideți** dacă doriți să păstrați configurația curentă și să executați măsura mai târziu. The **Măsuri** afișează pagina.

# <a name="business-accounts-b-to-b"></a>[Conturi de afaceri (B2B)](#tab/b2b)

Creați măsuri la nivelul conturilor individuale (măsură client) sau la nivelul tuturor conturilor (măsură business).

- Măsurarea clientului: generează rezultate ca entitate proprie. Măsurile clienților nu apar în cardul de profil al clientului.

- Măsura de afaceri: generează rezultate ca entitate proprie și se afișează pe pagina de pornire a mediului dumneavoastră Customer Insights.

1. Mergi la **Măsuri**.

1. Selectați **Nou**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Ecran de configurare gol pentru o măsură B-to-B.":::

1. Selectați **Editează detaliile** lângă Măsura fără titlu. Furnizați un nume pentru măsura. Opțional, adăugați [Etichete](work-with-tags-columns.md#manage-tags) la masura. 
   :::image type="content" source="media/measures_edit_details.png" alt-text="caseta de dialog Editare detalii.":::

1. Selectați **Terminat**.

1. În zona de configurare, alegeți funcția de agregare din **Selectați funcția** meniu derulant. Funcțiile de agregare includ:
   - **Sum**
   - **Medie**
   - **Contor**
   - **Număr unic**
   - **Max**
   - **Min**
   - **Primul**: ia prima valoare a înregistrării de date
   - **Ultimul**: ia ultima valoare care a fost adăugată la înregistrarea de date

1. Selectați **Adăugați un atribut** pentru a selecta datele pentru a crea această măsură.

   1. Selectați fila **Atribute**.
   1. Entitate de date: alegeți entitatea care include atributul pe care doriți să îl măsurați.
   1. Atribut de date: alegeți atributul pe care doriți să îl utilizați în funcția de agregare pentru a calcula măsura. Puteți selecta doar un singur atribut o dată.
   1. Opțional, alegeți un atribut de date dintr-o măsură existentă selectând **Măsuri** fila sau căutați un nume de entitate sau măsură.
   1. Selectați **Adăuga** pentru a adăuga atributul selectat la măsură.

1. Pentru a construi măsuri mai complexe, adăugați mai multe atribute sau utilizați operatori matematici în funcția de măsurare.

1. Pentru a adăuga filtre, selectați **Filtru** în zona de configurare. Aplicarea filtrelor va folosi numai înregistrările care se potrivesc cu filtrele pentru a calcula măsura.
  
   1. În secțiunea **Adăugați atribut** a panoului **Filtre**, selectați atributul pe care doriți să îl utilizați pentru a crea filtre.
   1. Setați operatorii de filtrare să definească filtrul pentru fiecare atribut selectat.
   1. Selectați **Aplicare** pentru a adăuga filtrele la măsură.

1. Selectați **Dimensiune** pentru a alege mai multe câmpuri de adăugat ca coloane la entitatea de ieșire a măsurătorilor.

   1. Selectați **Editați dimensiunile** pentru a adăuga atribute de date pe care doriți să le grupați valorile măsurate. De exemplu, oraș sau sex.
      > [!TIP]
      > The *Număr de înregistrare client* Atributul este deja adăugat, indicând că acesta este un tip de măsură la nivel de client. Dacă eliminați atributul, tipul de măsură se schimbă la nivelul afacerii.
   1. Selectați **Gata** pentru a adăuga dimensiunile la măsură.

1. Dacă există valori în datele dvs. care trebuie înlocuite cu un număr întreg, selectați **Reguli**. Configurați regula și asigurați-vă că alegeți numai numere întregi ca înlocuitoare. De exemplu, înlocuiți *nul* cu *0*.

1. Daca tu [utilizați conturi cu ierarhii](relationships.md#set-up-account-hierarchies), revizuire **Acumulați sub-conturi**.
   - Dacă este setat la **Dezactivat**, măsura este calculată pentru fiecare cont. Fiecare cont are propriul rezultat.
   - Dacă este setat la **Pornit**, selectați **Editați** pentru a alege ierarhia contului în funcție de ierarhiile ingerate. Măsura va produce un singur rezultat, deoarece este agregată cu subconturi.

1. Dacă există mai multe căi între entitatea de date pe care ați mapat-o și *Client* entitate, alegeți unul dintre cei identificați [căi de relație cu entitate](relationships.md). Rezultatele măsurătorilor pot varia în funcție de calea selectată.

   1. Selectați **Calea relației** și alegeți calea entității care ar trebui utilizată pentru a vă identifica măsura. Dacă există doar o singură cale către entitatea *Client*, acest control nu se va afișa.
   1. Selectați **Terminat** pentru a aplica selecția dvs.

1. Selectați elipsa verticală (&vellip;) asupra calculului la **Duplicat** sau **Elimina** un calcul dintr-o măsură.

1. În zona **Previzualizare**, veți vedea schema de date a entității de ieșire a măsurii, inclusiv filtre și dimensiuni. Previzualizarea reacționează dinamic la schimbările din configurație.

1. Selectați **Rulare** pentru a calcula rezultatele pentru măsura configurată. Selectați **Salvați și închideți** dacă doriți să păstrați configurația curentă și să executați măsura mai târziu. The **Măsuri** afișează pagina.

---

## <a name="next-step"></a>Pasul următor

Utilizați măsurile existente pentru a crea [un segment de clienți](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
