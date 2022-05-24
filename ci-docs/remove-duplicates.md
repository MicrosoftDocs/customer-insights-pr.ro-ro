---
title: Eliminați duplicatele înainte de unificarea datelor
description: Al doilea pas în procesul de unificare este selectarea înregistrării pe care să o păstrați atunci când sunt găsite duplicate.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 27dff3551ab411a12c273536d7431d651c48573e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/11/2022
ms.locfileid: "8742977"
---
# <a name="remove-duplicates-before-unifying-data"></a>Eliminați duplicatele înainte de unificarea datelor

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Acest pas în unificare vă permite opțional să configurați reguli pentru gestionarea înregistrărilor duplicate într-o entitate. *Deduplicarea* identifică înregistrările duplicate și le îmbină într-o singură înregistrare. Înregistrările sursă sunt legate de înregistrarea combinată cu ID-uri alternative. Dacă regulile nu sunt configurate, se aplică regulile definite de sistem.

## <a name="include-enriched-entities-preview"></a>Includeți entități îmbogățite (previzualizare)

Dacă ați îmbogățit entități la nivelul sursă de date pentru a vă îmbunătăți rezultatele unificării, selectați-le. Pentru mai multe informații, vezi [Îmbogățirea surselor de date](data-sources-enrichment.md).

1. Pe **Înregistrări duplicate** pagina, selectați **Utilizați entități îmbogățite** În partea de sus a paginii.

1. De la **Utilizați entități îmbogățite** panoul, alegeți una sau mai multe entități îmbogățite.

1. Selectați **Terminat**.

## <a name="define-deduplication-rules"></a>Definiți regulile de deduplicare

1. Pe **Înregistrări duplicate** pagina, selectați o entitate și selectați **Adăugați o regulă** pentru a defini regulile de deduplicare.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Captură de ecran a paginilor de înregistrări duplicate cu Afișați mai multe evidențiate":::

   1. În **Adăugați o regulă** panoul, introduceți următoarele informații:
      - **Selectați câmpul** : Alegeți din lista de câmpuri disponibile din entitatea pe care doriți să o verificați pentru duplicate. Alegeți câmpuri care sunt probabil unice pentru fiecare client. De exemplu, o adresă de e-mail sau combinația dintre nume, oraș și număr de telefon.
      - **Normalizare**: Selectați din următoarele opțiuni de normalizare pentru atributele selectate.
        - **Numerale** : convertește alte sisteme numerice, cum ar fi cifrele romane, în cifre arabe. *VIII* devine *8*.
        - **Simboluri** : elimină toate simbolurile și caracterele speciale. *Head&Shoulder* devine *HeadShoulder*.
        - **Text în minuscule: convertește toate caracterele în minuscule**. *TOATE MAJUSCULE și majuscule* devine *toate majuscule și majuscule*.
        - **Tip (Telefon, Nume, Adresă, Organizație)** : Standardizează nume, titluri, numere de telefon, adrese etc.
        - **Unicode la ASCII** : Convertește notația Unicode în caractere ASCII. */u00B2* devine *2*.
        - **Spatiu alb** : elimină toate spațiile. *Hello   World* devine *HelloWorld*.
      - **Precizie**: Setați nivelul de precizie care trebuie aplicat pentru această condiție.
        - **De bază** : Alege din *Scăzut (30%)*, *(60%)*, *(80%)*, și *Exact (100%)*. Selectați **Corect** pentru a potrivi numai înregistrările care se potrivesc 100 la sută.
        - **Particularizat**: Setați un procent care trebuie să corespundă înregistrărilor. Sistemul va potrivi doar înregistrările care depășesc acest prag.
      - **Nume** : Nume pentru regulă.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Captură de ecran a panoului Adăugați reguli pentru eliminarea duplicatelor.":::

   1. Opțional, selectați **Adăuga** > **Adăugați o condiție** pentru a adăuga mai multe condiții la regulă. Condițiile sunt conectate cu un operator AND logic și astfel executate numai dacă sunt îndeplinite toate condițiile.

   1. Opțional, **Adăuga** > **Adăugați o excepție** la [adăugați excepții de la regulă](match-entities.md#add-exceptions-to-a-rule). Excepțiile sunt utilizate pentru a aborda cazuri rare de fals pozitive și fals negative.

   1. Selectați **Terminat** pentru a crea regula.

1. Opțional, [adăugați mai multe reguli](#define-deduplication-rules).

1. Selectați o entitate și apoi **Editați preferințele de îmbinare**.

1. În **Îmbinați preferințele** panou:
   1. Alegeți una dintre cele trei opțiuni pentru a determina ce înregistrare să păstrați dacă este găsit un duplicat:
      - **Cea mai completată**: Identifică înregistrarea cu cele mai populate câmpuri de atribute drept înregistrare câștigătoare. Este opțiunea implicită de combinare.
      - **Cea mai recentă**: Identifică înregistrarea câștigătoare pe baza celor mai recente. Necesită o dată sau un câmp numeric pentru a defini activitatea recentă.
      - **Cea mai puțin recentă**: Identifică înregistrarea câștigătoare pe baza celor mai puțin recente. Necesită o dată sau un câmp numeric pentru a defini activitatea recentă.
      
      În caz de egalitate, recordul de câștigător este cel cu MAX(PK) sau valoarea cheii primare mai mare.
      
   1. Opțional, pentru a defini preferințele de îmbinare pe atributele individuale ale unei entități, selectați **Avansat** în partea de jos a panoului. De exemplu, puteți alege să păstrați cel mai recent e-mail ȘI cea mai completă adresă din diferite înregistrări. Extindeți entitatea pentru a vedea toate atributele sale și definiți ce opțiune să utilizați pentru atributele individuale. Dacă alegeți o opțiune bazată pe recentitate, trebuie să specificați și un câmp de dată/ora care definește recentitatea.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Panoul de preferințe avansate de îmbinare care arată e-mailul recent și adresa completă":::

   1. Selectați **Terminat** pentru a aplica preferințele de îmbinare.

1. După definirea regulilor de deduplicare și a preferințelor de îmbinare, selectați **Următorul**.
  
> [!div class="nextstepaction"]
> [Următorul pas pentru o singură entitate: Unificarea câmpurilor](merge-entities.md)

> [!div class="nextstepaction"]
> [Următorul pas pentru mai multe entități: Condiții de potrivire](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Ieșire de deduplicare ca entitate

Procesul de deduplicare creează o nouă entitate deduplicată pentru fiecare dintre entitățile sursă. Aceste entități pot fi găsite împreună cu **ConflationMatchPairs:CustomerInsights** în secțiunea **Sistem** din pagina **Entități**, cu numele **Deduplication_DataSource_Entity**.

O entitate de ieșire de deduplicare conține următoarele informații:

- ID-uri / Chei
  - Câmpurile cheie primară și ID alternativ. Câmpul ID alternativ este format din toate ID-urile alternative identificate pentru o înregistrare.
  - Câmpul Deduplication_GroupId arată grupul sau clusterul identificat în cadrul unei entități care grupează toate înregistrările similare pe baza câmpurilor de deduplicare specificate. Este utilizat în scopuri de procesare a sistemului. Dacă nu sunt specificate reguli de deduplicare manuală și se aplică reguli de deduplicare definite de sistem, este posibil să nu găsiți acest câmp în entitatea de ieșire a deduplicării.
  - Deduplication_WinnerId: Acest câmp conține ID-ul câștigător din grupurile sau clusterele identificate. Dacă Deduplication_WinnerId este aceeași cu valoarea cheii principale pentru o înregistrare, înseamnă că înregistrarea este înregistrarea câștigătoare.
- Câmpuri utilizate pentru definirea regulilor de deduplicare.
- Câmpurile Regulă și Scor pentru a indica care dintre regulile de deduplicare s-au aplicat și scorul returnat de algoritmul de potrivire.

[!INCLUDE[footer-include](includes/footer-banner.md)]
