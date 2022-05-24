---
title: Asociați entitățile pentru unificarea datelor
description: Asociați entitățile pentru a crea profiluri de clienți unificate.
recommendations: false
ms.date: 05/05/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: bc470dd932c2c981adc5840bb52d60f8dfe0de61
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740964"
---
# <a name="match-conditions"></a>Condiții de meci

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Acest pas în unificare definește ordinea de potrivire și regulile pentru potrivirea între entități. Acest pas necesită cel puțin două entități.

> [!NOTE]
> Odată ce ați creat condițiile de potrivire și selectați **Următorul**, nu puteți elimina o entitate sau un atribut selectat. Dacă este necesar, selectați **Înapoi** pentru a revizui entitățile și atributele selectate înainte de a continua.

## <a name="include-enriched-entities-preview"></a>Includeți entități îmbogățite (previzualizare)

Dacă ați îmbogățit entități la nivelul sursă de date pentru a vă îmbunătăți rezultatele unificării, selectați-le. Pentru mai multe informații, vezi [Îmbogățirea surselor de date](data-sources-enrichment.md). Dacă ați selectat entități îmbogățite pe **Înregistrări duplicate** pagina, nu trebuie să le selectați din nou.

1. Pe **Condiții de potrivire** pagina, selectați **Utilizați entități îmbogățite** În partea de sus a paginii.

1. De la **Utilizați entități îmbogățite** panoul, alegeți una sau mai multe entități îmbogățite.

1. Selectați **Terminat**.

## <a name="specify-the-match-order"></a>Specificați ordinea de potrivire

Fiecare potrivire unifică două sau mai multe entități într-o singură entitate consolidată. În același timp, păstrează înregistrările unice ale clienților. Ordinea de potrivire indică ordinea în care sistemul încearcă să potrivească înregistrările.

> [!IMPORTANT]
> Prima entitate din listă se numește entitate primară. Entitatea principală servește drept bază pentru setul de date unificat de profiluri. Entitățile suplimentare care sunt selectate vor fi adăugate la această entitate.
>
> Considerații importante:
>
> - Alegeți entitatea cu cele mai complete și de încredere date de profil despre clienții dvs. ca entitate principală.
> - Alegeți entitatea care are mai multe atribute în comun cu alte entități (de exemplu, numele, numărul de telefon sau adresa de e-mail) ca entitate principală.

1. Pe **Condiții de potrivire** pagina, utilizați săgețile de mutare în sus și în jos pentru a muta entitățile în ordinea dorită sau trageți și plasați-le. De exemplu, selectați **Contacte: eCommerce** ca entitate primară şi **CustomerLoyalty: loialitate** ca a doua entitate.

1. Pentru a avea fiecare înregistrare din entitate ca client unic, indiferent dacă este găsită o potrivire, selectați **Includeți toate înregistrările**. Orice înregistrări din această entitate care nu se potrivesc cu înregistrările din alte entități sunt incluse în profilul unificat. Înregistrările care nu au o potrivire se numesc singletons.
  
Entitatea primară *Contacte: eCommerce* este potrivit cu următoarea entitate *CustomerLoyalty: loialitate*. Setul de date care rezultă din primul pas de potrivire este asociat cu următoarea entitate dacă aveți mai mult de două entități.

:::image type="content" source="media/m3_match.png" alt-text="Captură de ecran a ordinii de potrivire selectată pentru entități." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Definiți regulile pentru perechile potrivite

Regulile de potrivire specifică logica după care se vor potrivi o anumită pereche de entități. O regulă constă din una sau mai multe condiții.

Avertismentul de lângă numele unei entități înseamnă că nu este definită nicio regulă de potrivire pentru o pereche de potrivire.

1. Selectați **Adăugați o regulă** pentru ca o pereche de entități să definească reguli de potrivire.

1. În **Adăugați o regulă** panoul, configurați condițiile pentru regulă.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Captură de ecran a panoului Adăugați reguli.":::

   - **Selectați entitate/câmp (primul rând)** : alegeți o entitate asociată și un atribut pentru a specifica o proprietate de înregistrare care este probabil unică pentru un client. De exemplu, un număr de telefon sau o adresă de e-mail. Evitați potrivirea după atributele de tip activitate. De exemplu, un ID de achiziție nu va găsi probabil nicio potrivire în alte tipuri de înregistrări.

   - **Selectați entitate/câmp (al doilea rând)** : Alegeți un atribut care se referă la atributul entității specificate în primul rând.

   - **Normalizare**: Selectați din următoarele opțiuni de normalizare pentru atributele selectate.
     - **Numerale** : convertește alte sisteme numerice, cum ar fi cifrele romane, în cifre arabe. *VIII* devine *8*.
     - **Simboluri** : elimină toate simbolurile și caracterele speciale. *Head&Shoulder* devine *HeadShoulder*.
     - **Text în minuscule** : Convertește toate caracterele în minuscule. *TOATE MAJUSCULE și majuscule* devine *toate majuscule și majuscule*.
     - **Tip (Telefon, Nume, Adresă, Organizație)** : standardizează numele, titlurile, numerele de telefon, adresele și organizațiile.
     - **Unicode la ASCII** : Convertește notația Unicode în caractere ASCII. */u00B2* devine *2*.
     - **Spatiu alb** : elimină toate spațiile. *Hello   World* devine *HelloWorld*.

   - **Precizie**: Setați nivelul de precizie care trebuie aplicat pentru această condiție.
     - **De bază** : Alege din *Scăzut (30%)*, *(60%)*, *(80%)*, și *Exact (100%)*. Selectați **Corect** pentru a potrivi numai înregistrările care se potrivesc 100 la sută.
     - **Particularizat**: Setați un procent care trebuie să corespundă înregistrărilor. Sistemul va potrivi doar înregistrările care depășesc acest prag.

   - **Nume** : Nume pentru regulă.

1. Pentru a potrivi entitățile numai dacă atributele îndeplinesc mai multe condiții, selectați **Adăuga** > **Adăugați o condiție** pentru a adăuga mai multe condiții la o regulă de potrivire. Condițiile sunt conectate cu un operator AND logic și astfel executate numai dacă sunt îndeplinite toate condițiile.

1. Opțional, luați în considerare opțiuni avansate, cum ar fi [excepții](#add-exceptions-to-a-rule) sau [condiții de potrivire personalizate](#specify-custom-match-conditions).

1. Selectați **Terminat** pentru a finaliza regula.

1. Opțional, [adăugați mai multe reguli](#add-rules-to-a-match-pair).

1. Faceți clic pe **Următorul**.

> [!div class="nextstepaction"]
> [Următorul pas: Unificați câmpurile](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Adăugați reguli unei perechi potrivite

Regulile de potrivire reprezintă seturi de condiții. Pentru a potrivi entitățile după condiții bazate pe mai multe atribute, adăugați mai multe reguli.

1. Selectați **Adăugați o regulă** pe entitatea la care doriți să adăugați reguli.

1. Urmați pașii din [Definiți regulile pentru perechile de potriviri](#define-rules-for-match-pairs).

> [!NOTE]
> Ordinea regulilor contează. Algoritmul de potrivire încearcă să se potrivească cu o anumită înregistrare de client pe baza primei reguli și continuă cu cea de-a doua regulă numai dacă nu au fost identificate potriviri cu prima regulă.

## <a name="advanced-options"></a>Opțiuni complexe

### <a name="add-exceptions-to-a-rule"></a>Adăugați excepții la o regulă

În cele mai multe cazuri, potrivirea entității duce la profiluri unice de clienți cu date consolidate. Pentru a aborda în mod dinamic cazuri rare de fals pozitive și fals negative, puteți defini excepții pentru o regulă de potrivire. Excepțiile sunt aplicate după procesarea regulilor de potrivire și se evită potrivirea tuturor înregistrărilor, care îndeplinesc criteriile de excepție.

De exemplu, dacă regula de potrivire combină nume de familie, orașul și data nașterii, sistemul va identifica gemeni cu același nume de familie care locuiesc în același oraș cu același profil. Puteți specifica o excepție care nu se potrivește cu profilurile dacă prenume din entitățile pe care le combinați nu sunt aceleași.

1. În **Editați regula** panou, selectați **Adăuga** > **Adăugați o excepție**.

1. Specificați criteriile de excepție.

1. Selectați **Terminat** pentru a salva regula.

### <a name="specify-custom-match-conditions"></a>Specificați condițiile de potrivire personalizate

Puteți specifica condiții care înlocuiesc logica de potrivire implicită. Există patru opțiuni disponibile:

|Opțiune  |Descriere |Exemplu  |
|---------|---------|---------|
|Se potrivesc întotdeauna     | Definește valori care se potrivesc întotdeauna.         |  Mereu potriviți *Mike* și *MikeR*.       |
|Nu se potrivesc niciodată     | Definește valori care nu se potrivesc niciodată.        | Nu se potrivește niciodată *Ioan* și *Jonathan*.        |
|Bypass particularizat     | Definește valori pe care sistemul ar trebui să le ignore întotdeauna în faza de potrivire. |  Ignorați valorile *11111* și *Necunoscut* în timpul meciului.        |
|Mapare de alias    | Definirea valorilor pe care sistemul ar trebui să le considere ca fiind aceeași valoare.         | Considera *Joe* a fi egal cu *Iosif*.        |

1. Selectați **Particularizat**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Buton personalizat":::

1. Alege **Tip personalizat** și selectați **Descărcați șablonul**. Aveți nevoie de un șablon separat pentru fiecare opțiune de potrivire.

1. Deschideți fișierul șablon descărcat și completați detaliile. Șablonul conține câmpuri pentru a specifica entitatea și valorile cheie primare ale entității de utilizat în potrivirea particularizată. De exemplu, dacă doriți cheia primară *12345* din entitatea *Vânzări* să se potrivească întotdeauna cu cheia primară *34567* din entitatea *Persoană de contact*, completați șablonul:
    - Entity1: Vânzări
    - Entity1Key: 12345
    - Entity2: Persoană de contact
    - Entity2Key: 34567

   Același fișier șablon poate specifica înregistrări de potrivire particularizată de la mai multe entități.

   Dacă doriți să specificați potrivirea personalizată pentru deduplicare pe o entitate, furnizați aceeași entitate ca și Entity1 și Entity2 și setați diferitele valori ale cheii primare.

1. După ce ați adăugat toate înlocuirile, salvați fișierul șablon.

1. Accesați **Date** > **Surse de date** și ingerați fișierele șablon ca entități noi.

1. După încărcarea fișierelor, selectați **Personalizat** din nou opțiunea. Selectați entitățile necesare din meniul drop-down și selectați **Terminat**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Captură de ecran a dialogului pentru a alege suprascrierea pentru un scenariu de potrivire particularizat.":::

1. Aplicarea potrivirii personalizate depinde de opțiunea de potrivire pe care doriți să o utilizați.

   - Pentru **Mereu potriviți** sau **Nu se potrivește niciodată**, treceți la pasul următor.
   - Pentru **Bypass** sau **Maparea aliasului**, Selectați **Editați | ×** pe o regulă de potrivire existentă sau creați o regulă nouă. În meniul derulant Normalizări, alegeți **Bypass personalizat** sau **Maparea aliasului** opțiunea și selectați **Terminat**.

1. Selectați **Terminat** pe **Personalizat** panoul pentru a aplica configurația personalizată de potrivire.

> [!div class="nextstepaction"]
> [Următorul pas: Unificați câmpurile](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
