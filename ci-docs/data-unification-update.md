---
title: Actualizați setările de unificare
description: Actualizați regulile duplicate, regulile de potrivire sau câmpurile unificate în setările de unificare.
ms.date: 06/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 590a2996cf8b2b1c6def59b78583169ec1910b59
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844055"
---
# <a name="update-the-unification-settings"></a>Actualizați setările de unificare

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Pentru a revizui sau modifica orice setări de unificare odată ce un profil unificat a fost creat, parcurgeți următorii pași.

1. Mergi la **Date** > **Unifica**.

   :::image type="content" source="media/m3_unified.png" alt-text="Captură de ecran a paginii Data Unify după unificarea datelor.":::

   > [!TIP]
   > The **Condiții de potrivire** țigla se afișează numai dacă au fost selectate mai multe entități.

1. Alegeți ce doriți să actualizați:
   - [Câmpurile sursă](#edit-source-fields) pentru a adăuga entități sau atribute sau pentru a modifica tipurile de atribute.
   - [Înregistrări duplicate](#manage-deduplication-rules) pentru a gestiona regulile de deduplicare sau preferințele de îmbinare.
   - [Condiții de potrivire](#manage-match-rules) pentru a actualiza regulile de potrivire pentru două sau mai multe entități.
   - [Câmpuri unificate pentru clienți](#manage-unified-fields) pentru a combina sau exclude câmpuri. De asemenea, puteți grupa profilurile asociate în grupuri.

1. După ce ați făcut modificările, alegeți următoarea opțiune:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Captură de ecran a paginii Data Unify cu opțiunile Unify evidențiate.":::

   - [Rulați condiții de potrivire](#run-matching-conditions) pentru a evalua rapid calitatea condițiilor de potrivire (deduplicare și reguli de potrivire) fără a actualiza profilul unificat. The **Rulați numai condiții de potrivire** opțiunea nu se afișează pentru o singură entitate.
   - [Unificați profilurile clienților](#run-updates-to-the-unified-customer-profile) pentru a rula condiții de potrivire și pentru a actualiza entitatea unificată a profilului clientului fără a afecta dependențele (cum ar fi îmbogățirile, segmentele sau măsurile). Procesele dependente nu sunt rulate, dar vor fi reîmprospătate pe măsură ce [definite în programul de reîmprospătare](system.md#schedule-tab).
   - [Unificați profilurile și dependențele clienților](#run-updates-to-the-unified-customer-profile) pentru a rula condiții de potrivire și pentru a actualiza entitatea unificată a profilului clientului și toate dependențele (cum ar fi îmbogățirile, segmentele sau măsurile). Toate procesele sunt reluate automat.

## <a name="edit-source-fields"></a>Editați câmpurile sursă

Nu puteți elimina un atribut sau o entitate dacă acestea au fost deja unificate.

1. Selectați **Editați | ×** pe **Câmpurile sursă** ţiglă.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Captură de ecran a paginii Câmpuri sursă care arată numărul de chei primare, câmpuri mapate și nemapate":::

   Afișează numărul de câmpuri mapate și nemapate.

1. Selectați **Selectați entitățile și câmpurile** pentru a adăuga alte atribute sau entități. Folosiți căutarea sau derulați pentru a găsi și selecta atributele și entitățile de interes. Selectați **Se aplică**.

1. Opțional, puteți modifica cheia primară pentru o entitate, tipurile de atribute și comutați **Cartografiere inteligentă** pornit sau oprit. Pentru mai multe informații, vezi [Selectați cheia primară și tipul semantic pentru atribute](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Selectați **Următorul** pentru a modifica regulile de deduplicare sau selectați **Salveaza si inchide** și întoarce-te la [Actualizați setările de unificare](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Gestionați regulile de deduplicare

1. Selectați **Editați | ×** pe **Înregistrări duplicate** ţiglă.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Captură de ecran a paginii Înregistrări duplicate care arată numărul de înregistrări duplicate" lightbox="media/m3_duplicates_edit.png":::

   Numărul de înregistrări duplicate găsite este afișat sub **Duplicate**. The **Înregistrările au fost deduplicate** coloana arată ce entități au avut înregistrări duplicate și procentul de înregistrări duplicate.

1. Dacă ați adăugat o entitate îmbogățită, selectați **Utilizați entități îmbogățite**. Pentru mai multe informații, vezi [Îmbogățirea surselor de date](data-sources-enrichment.md).

1. Pentru a gestiona regulile de deduplicare, alegeți oricare dintre următoarele opțiuni:
   - **Creați o nouă regulă** : Selectați **Adăugați o regulă** sub entitatea corespunzătoare. Pentru mai multe informații, vezi [Definiți regulile de deduplicare](remove-duplicates.md#define-deduplication-rules).
   - **Schimbați condițiile regulilor** : Selectați regula și apoi **Editați | ×**. Modificați câmpuri, adăugați sau eliminați condiții sau adăugați sau eliminați excepții.
   - **previzualizare** : Selectați regula și apoi **previzualizare** pentru a vizualiza rezultatele ultimei rulări pentru această regulă.
   - **Dezactivați o regulă** : Selectați regula și apoi **Dezactivați** pentru a păstra o regulă de deduplicare în timp ce o excludeți din procesul de potrivire.
   - **Duplicați o regulă** : Selectați regula și apoi **Duplicat** pentru a crea o regulă similară cu modificări.
   - **Ștergeți o regulă** : Selectați regula și apoi **Șterge**.

1. Pentru a modifica preferințele de îmbinare, selectați entitatea. Puteți modifica preferințele numai dacă este creată o regulă.
   1. Selectați **Editați preferințele de îmbinare** și schimbați **Înregistrare de păstrat** opțiune.
   1. Pentru a modifica preferințele de îmbinare pentru atributele individuale ale unei entități, selectați **Avansat** și faceți modificările necesare.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Captură de ecran a preferințelor avansate de îmbinare care arată cel mai recent e-mail și cea mai completă adresă":::

   1. Selectați **Terminat**.

1. Selectați **Următorul** pentru a modifica condițiile de potrivire sau selectați **Salveaza si inchide** și întoarce-te la [Actualizați setările de unificare](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Gestionare reguli de potrivire

Puteți reconfigura și regla fin majoritatea parametrilor de potrivire. Nu puteți adăuga sau șterge entități. Regulile de potrivire nu se aplică unei singure entități.

1. Selectați **Editați | ×** pe **Condiții de potrivire** ţiglă.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Captură de ecran a paginii Reguli și condiții de meci cu statistici." lightbox="media/m3_match_edit.png":::

   Pagina afișează ordinea de potrivire și regulile definite și următoarele statistici:
   - **Înregistrări sursă unice** arată numărul de înregistrări sursă individuale care au fost procesate în ultima rundă de potrivire.
   - **Înregistrări potrivite și nepotrivite** evidențiază câte înregistrări unice rămân după procesarea regulilor de potrivire.
   - **Numai înregistrări potrivite** afișează numărul de potriviri din toate perechile dvs. de potriviri.

1. Pentru a vedea rezultatele tuturor regulilor și scorurile acestora, selectați **Vezi ultima rulare**. Se afișează rezultatele, inclusiv ID-urile de contact alternative. Puteți descărca rezultatele.

1. Pentru a vedea rezultatele și scorurile unei anumite reguli, selectați regula și apoi **previzualizare**. Se afișează rezultatele. Puteți descărca rezultatele.

1. Pentru a vedea rezultatele unei anumite condiții pe o regulă, selectați regula și apoi **Editați | ×**. În panoul Editare, selectați **previzualizare** sub conditia. Puteți descărca rezultatele.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Reprezentare grafică a înregistrărilor nepotrivite și potrivite, inclusiv o listă a datelor.":::

1. Dacă ați adăugat o entitate îmbogățită, selectați **Utilizați entități îmbogățite**. Pentru mai multe informații, vezi [Îmbogățirea surselor de date](data-sources-enrichment.md).

1. Pentru a gestiona regulile, alegeți oricare dintre următoarele opțiuni:
   - **Creați o nouă regulă** : Selectați **Adăugați o regulă** sub entitatea corespunzătoare. Pentru mai multe informații, vezi [Definiți reguli pentru perechile de potrivire](match-entities.md#define-rules-for-match-pairs).
   - **Schimbați ordinea regulilor dvs** dacă ați definit mai multe reguli: trageți și plasați regulile în ordinea dorită. Pentru mai multe informații, vezi [Specificați ordinea de potrivire](match-entities.md#specify-the-match-order).
   - **Schimbați condițiile regulilor** : Selectați regula și apoi **Editați | ×**. Modificați câmpuri, adăugați sau eliminați condiții sau adăugați sau eliminați excepții.
   - **Dezactivați o regulă** : Selectați regula și apoi **Dezactivați** pentru a păstra o regulă de potrivire în timp ce o excludeți din procesul de potrivire.
   - **Duplicați o regulă** : Selectați regula și apoi **Duplicat** pentru a crea o regulă similară cu modificări.
   - **Ștergeți o regulă** : Selectați regula și apoi **Șterge**.

1. Selectați **Următorul** pentru a modifica câmpurile unificate sau selectați **Salveaza si inchide** și întoarce-te la [Actualizați setările de unificare](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Gestionați câmpurile unificate

1. Selectați **Editați | ×** pe **Câmpuri unificate pentru clienți** ţiglă.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Captură de ecran a câmpurilor unificate pentru clienți":::

1. Examinați câmpurile combinate și excluse și faceți modificările necesare. Adăugați sau editați cheia CustomerID sau profilurile de grup în grupuri. Pentru mai multe informații, vezi [Unificați câmpurile clienților](merge-entities.md).

1. Selectați **Următorul** pentru a revizui setările de unificare și [actualizați profilul unificat și dependențele](#run-updates-to-the-unified-customer-profile), sau selectați **Salveaza si inchide** și întoarce-te la [Actualizați setările de unificare](#update-the-unification-settings) pentru a face mai multe modificări.

## <a name="run-matching-conditions"></a>Rulați condiții de potrivire

Run matching conditions rulează numai deduplicarea și potrivirea regulilor și actualizează entitatile *Deduplicare_* și *ConflationMatchPair*.

1. De la **Date** > **Unifica** pagina, selectați **Rulați numai condiții de potrivire**.

   The **Înregistrări duplicate** și **Condiții de potrivire** faianta arată **În așteptare** sau **Înviorător** stare.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Când procesul de potrivire se încheie, selectați **Editați | ×** pe **Condiții de potrivire** ţiglă.

   :::image type="content" source="media/match-KPIs.png" alt-text="Captură de ecran decupată a valorilor cheie din pagina Potrivire cu numere și detalii.":::

1. Pentru a face modificări, vezi [Gestionați regulile de deduplicare](#manage-deduplication-rules) sau [Gestionați regulile de meci](#manage-match-rules).

1. Rulați din nou procesul de potrivire sau [rulați actualizări ale profilului clientului](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Rulați actualizări ale profilului unificat de client

1. De la **Date** > **Unifica** pagina, selectați:

   - **Unificați profilurile clienților** : rulează condiții de potrivire și actualizează entitatea unificată a profilului clientului fără a afecta dependențele (cum ar fi îmbogățirile, segmentele sau măsurile). Procesele dependente nu sunt rulate, dar vor fi reîmprospătate pe măsură ce [definite în programul de reîmprospătare](system.md#schedule-tab).

   - **Unificați profilurile și dependențele clienților** : rulează condițiile potrivite și actualizează profilul unificat și toate dependențele. Toate procesele sunt reluate automat. După finalizarea tuturor proceselor din aval, profilul clientului reflectă datele actualizate.

   The **Înregistrări duplicate**, **de potrivire**, și **Câmpuri unificate pentru clienți** faianta arată **În așteptare** sau **Înviorător** stare.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Rezultatele unei rulări de succes sunt afișate pe **Unifica** pagină care arată numărul de profiluri de clienți unificate.
