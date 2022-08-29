---
title: Creați un profil de contact unificat (previzualizare)
description: Treceți prin procesul de unificare a datelor pentru a crea un singur set de date principal de contacte.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305075"
---
# <a name="create-a-unified-contact-profile-preview"></a>Creați un profil de contact unificat (previzualizare)

După [unificarea conturilor de afaceri](map-entities.md), puteți, opțional, să unificați contactele pentru acele conturi și să conectați contactele unificate la conturile unificate. Procesul de unificare a contactelor mapează datele de contact din mai multe surse de date, elimină duplicatele, potrivește datele între entități, stabilește maparea semantică, creează relații între contacte și conturi și apoi creează un profil de contact unificat.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

Primii pași sunt identici cu pașii de unificare a conturilor.

## <a name="prerequisites"></a>Cerințe preliminare

Înregistrările contului și ale contactelor trebuie să aibă o cheie unică (numită cheie străină) care le conectează. De exemplu, un ID de cont care există în înregistrarea contului și în înregistrarea de contact care leagă contul și contactul.

## <a name="preview-limitations"></a>Limitări de previzualizare

- Contactele fără un link către un cont sunt eliminate.
- Dacă un cont este deduplicat, se identifică o înregistrare a câștigătorului pe baza preferințelor de îmbinare. Înregistrările pierderilor nu sunt selectate și, prin urmare, sunt eliminate. Contactele asociate cu înregistrările pierdute sunt eliminate.
- Un cont poate avea mai multe persoane de contact, dar o persoană de contact este conectată la un singur cont.
- Atributele de contact mapate în pasul de mapare semantică sunt singurele atribute care pot fi afișate pe cardul Client. Cu toate acestea, sunt disponibile 17 atribute.

## <a name="select-source-fields"></a>Selectați câmpurile sursă

1. Sub **Unificați contactele (previzualizare)**, Selectați **Incepe**.

1. [Selectați entitățile și câmpurile](map-entities.md) pentru sursele de date de contact, inclusiv cheile primare și tipurile de atribute.

1. Selectați **Următorul**.

## <a name="remove-duplicate-records"></a>Eliminați înregistrările duplicate

1. Opțional, [definiți regulile de deduplicare](remove-duplicates.md) pentru entitățile selectate de dvs.

1. Selectați **Următorul**.

## <a name="match-conditions"></a>Condiții de meci

1. [Definiți ordinea de potrivire și regulile](match-entities.md) pentru potrivirea între entități.

1. Selectați **Următorul**.

## <a name="unify-contact-fields"></a>Unificați câmpurile de contact

1. [Combinați și excludeți câmpurile de contact](merge-entities.md).

1. Selectați **Următorul**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Definiți câmpurile semantice pentru persoanele de contact unificate

Acest pas din procesul de unificare mapează câmpurile dvs. de contact unificate la tipuri semantice. În B-to-B, cardurile clienților arată conturi. Când cardul este selectat, se afișează toate contactele asociate contului. Câmpurile pe care le mapați în acest pas sunt câmpurile care se vor afișa pe carduri.

1. Selectați tipul semantic care se mapează la fiecare câmp unificat. Selectați **Nici unul** dacă nu este disponibil un tip semantic.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Captură de ecran a paginii Câmpuri semantice pentru a defini tipurile semantice." lightbox="media/semantic_mapping.png":::

1. După maparea tuturor câmpurilor unificate, selectați **Următorul**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Setați relația dintre contacte și conturi

Acest pas din procesul de unificare conectează datele dvs. de contact cu datele contului corespunzătoare.

1. Pentru fiecare entitate, introduceți următoarele informații:

   - **Cheie străină de la entitatea de contact** : alegeți atributul care conectează entitatea dvs. de contact la cont.
   - **Pentru entitate de cont** : Alegeți entitatea de cont asociată contactului.

   :::image type="content" source="media/contact_relationship.png" alt-text="Captură de ecran a paginii Relații pentru a conecta entitățile de contact și de cont.":::

1. Selectați **Următorul**.

## <a name="review-contact-unification"></a>Examinați unificarea contactelor

Examinați rezumatul modificărilor, creați profilul unificat și examinați rezultatele.

### <a name="review-and-create-contact-profiles"></a>Examinați și creați profiluri ale contactelor

Acest ultim pas al procesului de unificare arată un rezumat al pașilor din proces și oferă șansa de a face modificări înainte de a crea profilul de contact unificat.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Captură de ecran pentru Examinați și creați profiluri de contact.":::

1. Selectați **Editați | ×** pe oricare dintre pașii de unificare a contactelor pentru a examina și a face orice modificări.

1. Dacă sunteți mulțumit de selecțiile dvs., selectați **Creați profiluri de contact**. The **Unifica** pagina se afișează în timp ce profilul de contact unificat este creat.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Captură de ecran a paginii Unificare Contacte cu plăci care arată În coadă sau În curs de reîmprospătare.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Algoritmul de unificare durează ceva timp pentru a se finaliza și nu puteți modifica configurația până nu se finalizează.

### <a name="view-the-results-of-contact-unification"></a>Vedeți rezultatele unificării contactelor

După finalizarea unificării, **Date** > **Unifica** pagina arată numărul de profiluri de contact unificate. Rezultatele fiecărui pas din procesul de unificare sunt afișate pe fiecare țiglă. De exemplu, **Câmpurile sursă** arată numărul de atribute (câmpuri) mapate și **Înregistrări duplicate** arată numărul de înregistrări duplicate găsite.

:::image type="content" source="media/unified_contacts.png" alt-text="Captură de ecran a paginii Data Unify după ce contactele sunt unificate.":::

> [!TIP]
> The **Condiții de potrivire** țigla se afișează numai dacă au fost selectate mai multe entități.

Vă recomandăm să revizuiți rezultatele, în special calitatea dvs [regulile de potrivire](data-unification-update.md#manage-match-rules) și rafinați-le dacă este necesar.

Când e nevoie, [efectuați modificări la setările de unificare a contactelor](data-unification-update.md) și rulați din nou profilul unificat.

### <a name="verify-output-entities-from-data-unification"></a>Verificați entitățile de ieșire din unificarea datelor

Mergi la **Date** > **Entități** pentru a verifica entitățile de ieșire.

Entitatea unificată a profilului de contact, apelată *Profil de contact*, afișează în **Entități semantice** secțiune. Prima rundă de unificare cu succes creează unificatul *Profil de contact* entitate. Toate rulările ulterioare extind acea entitate.

The *ContacteClient* entitatea (previzualizare) este creată și se afișează în **Profiluri** secțiune. Această entitate conține datele de contact fără link-uri către conturi. Această entitate este utilizată ca intrare în maparea semantică și etapele relației de unificare a contactelor.

Entitățile de deduplicare și combinare sunt create și afișate în **Sistem** secțiune. Cu numele este creată o entitate deduplicată pentru fiecare dintre entitățile sursă **Deduplication_DataSource_Entity**. The **ContacteConflationMatchPairs** entitatea conține informații despre potrivirile între entități.

O entitate de ieșire de deduplicare conține următoarele informații:
- ID-uri / Chei
  - Câmpurile cheie primară și ID alternativ. Câmpul ID alternativ este format din toate ID-urile alternative identificate pentru o înregistrare.
  - Câmpul Deduplication_GroupId arată grupul sau clusterul identificat în cadrul unei entități care grupează toate înregistrările similare pe baza câmpurilor de deduplicare specificate. Este utilizat în scopuri de procesare a sistemului. Dacă nu sunt specificate reguli de deduplicare manuală și se aplică reguli de deduplicare definite de sistem, este posibil să nu găsiți acest câmp în entitatea de ieșire a deduplicării.
  - Deduplication_WinnerId: Acest câmp conține ID-ul câștigător din grupurile sau clusterele identificate. Dacă Deduplication_WinnerId este aceeași cu valoarea cheii principale pentru o înregistrare, înseamnă că înregistrarea este înregistrarea câștigătoare.
- Câmpuri utilizate pentru definirea regulilor de deduplicare.
- Câmpurile Regulă și Scor pentru a indica care dintre regulile de deduplicare s-au aplicat și scorul returnat de algoritmul de potrivire.

## <a name="next-step"></a>Următorul pas

Configurați [Activități](activities.md),[îmbogăţire](enrichment-hub.md), sau [relatii](relationships.md) pentru a obține mai multe informații despre persoanele de contact.
