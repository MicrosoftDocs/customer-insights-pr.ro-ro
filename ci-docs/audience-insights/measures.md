---
title: Crearea și gestionarea măsurilor
description: Definiți măsuri pentru a analiza și reflecta performanța afacerii dvs.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a83caf2428f3dbd9791b9f746d00d370362a508c
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304818"
---
# <a name="define-and-manage-measures"></a>Definiți și gestionați măsurile

Măsurile vă ajută să înțelegeți mai bine comportamentele clienților și performanța afacerii. Se uită la valorile relevante din [profiluri unificate](data-unification.md). De exemplu, o companie vrea să vadă *cheltuielile totale per client* pentru a înțelege istoricul sau măsura achizițiilor unui client individual *vânzările totale ale companiei* pentru a înțelege veniturile la nivel agregat din întreaga afacere.  

Măsurile sunt create folosind generatorul de măsuri, o platformă de interogare a datelor cu diverși operatori și opțiuni simple de mapare. Vă permite să filtrați datele, să grupați rezultatele, să detectați [căile relației entității](relationships.md), și previzualizați ieșirea.

Utilizați instrumentul de măsurare pentru a planifica activități comerciale prin interogarea datelor despre clienți și extragerea de informații. De exemplu, crearea unei măsuri de *cheltuieli totale per client* și *returnare totală per client* ajută la identificarea unui grup de clienți cu cheltuieli mari, dar cu randament ridicat. Puteți [crea un segment](segments.md) pentru a conduce următoarele cele mai bune acțiuni. 

## <a name="build-your-own-measure-from-scratch"></a>Construiți propria măsură de la zero

Această secțiune vă ajută să creați o nouă măsură de la zero. Puteți construi o măsură cu atribute de date de la entități de date care au o relație configurată pentru a se conecta cu entitatea Client. 

1. În Detalii despre public, accesați **Măsuri**.

1. Selectați **Nou** și alegeți **Construiți una proprie**.

1. Selectați **Editează nume** și furnizați un **Nume** pentru măsură. 
   > [!NOTE]
   > Dacă noua dvs. configurație de măsurare are doar două câmpuri—de exemplu, CustomerID și un singur calcul—rezultatul va fi adăugat ca o nouă coloană la entitatea generată de sistem numită Customer_Measure. Și veți putea vedea valoarea măsurii în profilul de client unificat. Alte măsuri își vor genera propriile entități.

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
  
   1. În secțiunea **Adăugați atribut** a panoului **Filtre**, selectați atributul pe care doriți să îl utilizați pentru a crea filtre.
   1. Setați operatorii de filtrare să definească filtrul pentru fiecare atribut selectat.
   1. Selectați **Aplicare** pentru a adăuga filtrele la măsură.

1. Pentru a adăuga dimensiuni, selectați **Dimensiune** în zona de configurare. Dimensiunile vor fi afișate ca coloane în entitatea de ieșire de măsurare.
 
   1. Selectați **Editați dimensiunile** pentru a adăuga atribute de date pe care doriți să le grupați valorile măsurate. De exemplu, oraș sau sex. În mod implicit, dimensiunea *CustomerID* este selectată pentru a crea *măsuri la nivel de client*. Puteți elimina dimensiunea implicită dacă doriți să creați *măsuri la nivel de afaceri*.
   1. Selectați **Gata** pentru a adăuga dimensiunile la măsură.

1. Dacă există date în datele dvs. pe care trebuie să le înlocuiți cu un număr întreg—de exemplu, înlocuiți *nul* cu *0*—selectați **Reguli**. Configurați regula și asigurați-vă că alegeți numai numere întregi ca înlocuitoare.

1. Dacă există mai multe căi între entitatea de date pe care ați mapat-o și entitatea *Client* trebuie să alegeți una dintre [căile relației entității](relationships.md) identificate. Rezultatele măsurătorilor pot varia în funcție de calea selectată. 
   
   1. Selectați **Preferințe de date** și alegeți calea entității care ar trebui utilizată pentru a vă identifica măsura. Dacă există doar o singură cale către entitatea *Client*, acest control nu se va afișa.
   1. Selectați **Terminat** pentru a aplica selecția dvs. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Selectați entitatea cale pentru măsură.":::

1. Pentru a adăuga mai multe calcule pentru măsură, selectați **Calcul nou**. Puteți utiliza entități pe aceeași cale de entitate numai pentru noi calcule. Mai multe calcule vor fi afișate drept coloane dnoi în entitatea de ieșire de măsurare.

1. Selectați **...** asupra calculului la **Duplicat**, **Redenumiți**, sau **Eliminați** un calcul dintr-o măsură.

1. În zona **Previzualizare**, veți vedea schema de date a entității de ieșire a măsurii, inclusiv filtre și dimensiuni. Previzualizarea reacționează dinamic la schimbările din configurație.

1. Selectați **Rulare** pentru a calcula rezultatele pentru măsura configurată. Selectați **Salvați și închideți** dacă doriți să păstrați configurația curentă și să executați măsura mai târziu.

1. Accesați **Măsuri** pentru a vedea măsurarea nou creată în listă.

## <a name="use-a-template-to-build-a-measure"></a>Utilizați un șablon pentru a construi o măsură

Puteți utiliza șabloane predefinite de măsuri utilizate în mod obișnuit pentru a le crea. Descrieri detaliate ale șabloanelor și o experiență ghidată vă ajută la crearea eficientă a măsurilor. Șabloanele se bazează pe date cartografiate din entitatea *Activitate unificată*. Deci, asigurați-vă că ați configurat [activitățile clienților](activities.md) înainte de a crea o măsură dintr-un șablon.

Șabloane de măsură disponibile: 
- Valoarea medie a tranzacției (ATV)
- Valoarea totală a tranzacțiilor
- Venitul mediu zilnic
- Venitul mediu anual
- Numărul de tranzacții
- Puncte de fidelitate câștigate
- Puncte de fidelitate valorificate
- Soldul punctelor de fidelitate
- Durată activă a ciclului de viață a clientului
- Durata apartenenței la programul de fidelitate
- Timp de la ultima achiziție

Următoarea procedură prezintă pașii pentru a construi o nouă măsură folosind un șablon.

1. În Detalii despre public, accesați **Măsuri**.

1. Selectați **Nou** și selectați **Alegeți un șablon**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Captură de ecran a meniului derulant atunci când creați o nouă măsură cu evidențiere pe șablon.":::

1. Găsiți șablonul care se potrivește nevoilor dvs. și selectați **Alegeți șablonul**.

1. Examinați datele necesare și selectați **Începeți** dacă aveți toate datele la locul lor.

1. În panoul **Editați nume**, setați numele măsurii dvs. și entitatea de ieșire. 

1. Selectați **Terminat**.

1. În secțiunea **Setați perioada de timp**, definiți intervalul de timp al datelor de utilizat. Alegeți dacă doriți ca noua măsură să acopere întregul set de date selectând **Tot timpul**, sau dacă doriți ca măsura să se concentreze pe o **Anumită perioadă de timp**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captură de ecran care arată secțiunea perioadei de timp la configurarea unei măsuri dintr-un șablon.":::

1. În secțiunea următoare, selectați **Adăugați date** pentru a alege activitățile și pentru a mapa datele corespunzătoare din entitatea *Activitate unificată*.

    1. Pasul 1 din 2: Sub **Tipul activității**, alegeți tipul entității pe care doriți să o utilizați. Pentru **Activități**, selectați entitățile pe care doriți să le mapați.
    1. Pasul 2 din 2: Alegeți atributul din entitatea *Activitate unificată* pentru componenta cerută de formulă. De exemplu, pentru Valoarea medie a tranzacției, este atributul care reprezintă valoarea tranzacției. Pentru **Marcaj de timp al activității**, alegeți atributul din entitatea de activitate unificată care reprezintă data și ora activității.
   
1. Odată ce maparea datelor are succes, puteți vedea starea drept **Finalizată** și numele activităților și atributelor mapate.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Captură de ecran a unei configurații completate a șablonului de măsură.":::

1. Acum puteți selecta **Rulare** pentru a calcula rezultatele măsurii. Pentru a-l rafina mai târziu, selectați **Salvați schița**.

## <a name="manage-your-measures"></a>Gestionați-vă măsurile

Puteți găsi lista măsurilor pe pagina **Măsuri**.

Veți găsi informații despre tipul de măsură, creatorul, data creării, starea și starea. Când selectați o măsură din listă, puteți previzualiza ieșirea și descărca un fișier CSV.

Pentru a vă reîmprospăta toate măsurile în același timp, selectați **Reîmprospătați tot** fără a selecta o anumită măsură.

> [!div class="mx-imgBorder"]
> ![Acțiuni de gestionare a măsurilor unice.](media/measure-actions.png "Acțiuni de gestionare a măsurilor unice.")

Selectați o măsură din listă pentru următoarele opțiuni:

- Selectați numele măsurii pentru a vedea detaliile acesteia.
- **Editați** configurația măsurii.
- **Reîmprospătați** măsura pe baza celor mai recente date.
- **Redenumiți** măsura.
- **Ștergeți** măsura.
- **Activați** sau **Dezactivați**. Măsurile inactive nu vor fi reîmprospătate în timpul unei [reîmprospătări planificate](system.md#schedule-tab).

> [!TIP]
> Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese. În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies). Puteți selecta starea unui proces pentru a vedea detalii despre evoluția întregii lucrări. După selectare **Vezi detalii** pentru una dintre activitățile operațiunii, veți găsi informații suplimentare: timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate activității.

## <a name="next-step"></a>Următorul pas

Puteți utiliza măsurile existente pentru a crea [un segment de clienți](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
