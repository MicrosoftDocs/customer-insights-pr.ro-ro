---
title: Actualizați setările de unificare pentru clienți, conturi sau contacte
description: Actualizați regulile duplicate, regulile de potrivire sau câmpurile unificate din setările de unificare a clienților sau a contului.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: f2c14c169f5973b5f400989b9eeea593eba09182
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304350"
---
# <a name="update-unification-settings"></a>Actualizați setările de unificare

Pentru a revizui sau modifica orice setări de unificare după ce a fost creat un profil unificat, parcurgeți următorii pași.

1. Mergi la **Date** > **Unifica**.

   Pentru clienții individuali (B-to-C), the **Unifica** pagina afișează numărul de profiluri unificate de clienți și de piese pentru fiecare dintre pașii de unificare.

   :::image type="content" source="media/m3_unified.png" alt-text="Captură de ecran a paginii Data Unify după unificarea datelor." lightbox="media/m3_unified.png":::

   Pentru conturile de afaceri (B-to-B), the **Unifica** pagina afișează numărul de profiluri de cont unificate și de dale pentru fiecare dintre pașii de unificare a contului. Dacă contactele au fost unificate, se afișează numărul de profiluri de contact unificate și de plăci pentru fiecare dintre pașii de unificare a contactului. Alegeți țigla potrivită dedesubt **Unificați conturile** sau **Unificare contacte (previzualizare)** în funcție de ceea ce doriți să actualizați.

   :::image type="content" source="media/b2b_unified.png" alt-text="Captură de ecran a paginii Data Unify după unificarea datelor de cont și de contact." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > The **Condiții de potrivire** țigla se afișează numai dacă au fost selectate mai multe entități.

1. Alegeți ce doriți să actualizați:
   - [Câmpurile sursă](#edit-source-fields) pentru a adăuga entități sau atribute sau pentru a modifica tipurile de atribute.
   - [Înregistrări duplicate](#manage-deduplication-rules) pentru a gestiona regulile de deduplicare sau preferințele de îmbinare.
   - [Condiții de potrivire](#manage-match-rules) pentru a actualiza regulile de potrivire pentru două sau mai multe entități.
   - [Câmpuri unificate pentru clienți](#manage-unified-fields) pentru a combina sau exclude câmpuri. De asemenea, puteți grupa profilurile asociate în grupuri.
   - [Câmpuri semantice](#manage-semantic-fields-for-unified-contacts) pentru a gestiona tipurile semantice pentru câmpurile de contact unificate.
   - [Relații](#manage-contact-and-account-relationships) pentru a gestiona relația contact-cont.

1. După ce ați făcut modificările, alegeți următoarea opțiune:

   - [Rulați condiții de potrivire](#run-matching-conditions) pentru a evalua rapid calitatea condițiilor de potrivire (deduplicare și reguli de potrivire) fără a actualiza profilul unificat. The **Rulați numai condiții de potrivire** opțiunea nu se afișează pentru o singură entitate.
   - [Unificați profilurile](#run-updates-to-the-unified-profile) pentru a rula condiții de potrivire și pentru a actualiza entitatea de profil unificat fără a afecta dependențele (cum ar fi îmbogățirile, segmentele sau măsurile). Procesele dependente nu sunt rulate, dar vor fi reîmprospătate pe măsură ce [definite în programul de reîmprospătare](schedule-refresh.md).
   - [Unificați profilurile și dependențele](#run-updates-to-the-unified-profile) pentru a rula condiții de potrivire, pentru a actualiza entitatea de profil unificat și pentru a actualiza toate dependențele (cum ar fi îmbogățirile, segmentele sau măsurile). Toate procesele sunt reluate automat. În B-to-B, unificarea se desfășoară atât pe cont, cât și pe entitățile de contact care actualizează profilurile unificate.

## <a name="edit-source-fields"></a>Editați câmpurile sursă

Nu puteți elimina un atribut sau o entitate dacă acestea au fost deja unificate.

1. Selectați **Editați | ×** pe **Câmpurile sursă** ţiglă.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Captură de ecran a paginii Câmpuri sursă care arată numărul de chei primare, câmpuri mapate și nemapate":::

   Afișează numărul de câmpuri mapate și nemapate.

1. Pentru a adăuga alte atribute sau entități, selectați **Selectați entitățile și câmpurile**.

1. Opțional, puteți modifica cheia primară pentru o entitate, tipurile de atribute și comutați **Cartografiere inteligentă** pornit sau oprit. Pentru mai multe informații, vezi [Selectați câmpurile sursă](map-entities.md).

1. Selectați **Următorul** pentru a modifica regulile de deduplicare sau selectați **Salveaza si inchide** si revin la [Actualizați setările de unificare](#update-unification-settings).

## <a name="manage-deduplication-rules"></a>Gestionați regulile de deduplicare

1. Selectați **Editați | ×** pe **Înregistrări duplicate** ţiglă.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Captură de ecran a paginii Înregistrări duplicate care arată numărul de înregistrări duplicate" lightbox="media/m3_duplicates_edit.png":::

   Numărul de înregistrări duplicate găsite este afișat sub **Duplicate**. The **Înregistrările au fost deduplicate** coloana arată ce entități au avut înregistrări duplicate și procentul de înregistrări duplicate.

1. Pentru a utiliza o entitate îmbogățită, selectați **Utilizați entități îmbogățite**. Pentru mai multe informații, vezi [Îmbogățirea surselor de date](data-sources-enrichment.md).

1. Pentru a gestiona regulile de deduplicare, alegeți oricare dintre următoarele opțiuni:
   - **Creați o nouă regulă** : Selectați **Adăugați o regulă** sub entitatea corespunzătoare. Pentru mai multe informații, vezi [Definiți regulile de deduplicare](remove-duplicates.md#define-deduplication-rules).
   - **Schimbați condițiile regulilor** : Selectați regula și apoi **Editați | ×**. Schimbați câmpuri, adăugați sau eliminați condiții sau adăugați sau eliminați excepții.
   - **previzualizare** : Selectați regula și apoi **previzualizare** pentru a vizualiza rezultatele ultimei rulări pentru această regulă.
   - **Dezactivați o regulă** : Selectați regula și apoi **Dezactivați** pentru a păstra o regulă de deduplicare în timp ce o excludeți din procesul de potrivire.
   - **Duplicați o regulă** : Selectați regula și apoi **Duplicat** pentru a crea o regulă similară cu modificări.
   - **Ștergeți o regulă** : Selectați regula și apoi **Șterge**.

1. Pentru a modifica preferințele de îmbinare, selectați entitatea. Puteți modifica preferințele numai dacă este creată o regulă.
   1. Selectați **Editați preferințele de îmbinare** și schimbați **Înregistrare de păstrat** opțiune.
   1. Pentru a modifica preferințele de îmbinare pentru atributele individuale ale unei entități, selectați **Avansat** și faceți modificările necesare.

   1. Selectați **Terminat**.

1. Selectați **Următorul** pentru a modifica condițiile de potrivire sau selectați **Salveaza si inchide** si revin la [Actualizați setările de unificare](#update-unification-settings).

## <a name="manage-match-rules"></a>Gestionare reguli de potrivire

Puteți reconfigura și regla fin majoritatea parametrilor de potrivire. Nu puteți adăuga sau șterge entități. Regulile de potrivire nu se aplică unei singure entități.

1. Selectați **Editați | ×** pe **Condiții de potrivire** ţiglă.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Captură de ecran a paginii Reguli și condiții de meci cu statistici." lightbox="media/m3_match_edit.png":::

   Pagina afișează ordinea de potrivire și regulile definite și următoarele statistici:
   - **Înregistrări surse unice** afișează numărul de înregistrări sursă individuale care au fost procesate în ultimul meci.
   - **Înregistrări potrivite și nepotrivite** evidențiați câte înregistrări unice rămân după procesarea regulilor de meci.
   - **Numai înregistrările potrivite** arată numărul de potriviri din toate perechile tale de potriviri.

1. Pentru a vedea rezultatele tuturor regulilor și scorurile acestora, selectați **Vezi ultima rulare**. Se afișează rezultatele, inclusiv ID-urile de contact alternative. Puteți descărca rezultatele.

1. Pentru a vizualiza rezultatele și scorurile unei anumite reguli, selectați regula și apoi **previzualizare**. Se afișează rezultatele. Puteți descărca rezultatele.

1. Pentru a vedea rezultatele unei anumite condiții pe o regulă, selectați regula și apoi **Editați | ×**. În panoul Editare, selectați **previzualizare** sub conditia. Puteți descărca rezultatele.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Reprezentare grafică a înregistrărilor nepotrivite și potrivite, inclusiv o listă a datelor.":::

1. Dacă ați adăugat o entitate îmbogățită, selectați **Utilizați entități îmbogățite**. Pentru mai multe informații, vezi [Îmbogățirea surselor de date](data-sources-enrichment.md).

1. Pentru a gestiona regulile, alegeți oricare dintre următoarele opțiuni:
   - **Creați o nouă regulă** : Selectați **Adăugați o regulă** sub entitatea corespunzătoare. Pentru mai multe informații, vezi [Definiți reguli pentru perechile de potrivire](match-entities.md#define-rules-for-match-pairs).
   - **Schimbați ordinea regulilor dvs** dacă ați definit mai multe reguli: trageți și plasați regulile în ordinea dorită. Pentru mai multe informații, vezi [Specificați ordinea de potrivire](match-entities.md#specify-the-match-order).
   - **Schimbați condițiile regulilor** : Selectați regula și apoi **Editați | ×**. Schimbați câmpuri, adăugați sau eliminați condiții sau adăugați sau eliminați excepții.
   - **Dezactivați o regulă** : Selectați regula și apoi **Dezactivați** pentru a păstra o regulă de potrivire în timp ce o excludeți din procesul de potrivire.
   - **Duplicați o regulă** : Selectați regula și apoi **Duplicat** pentru a crea o regulă similară cu modificări.
   - **Ștergeți o regulă** : Selectați regula și apoi **Șterge**.

1. Selectați **Următorul** pentru a efectua modificări câmpurilor unificate sau selectați **Salveaza si inchide** si revin la [Actualizați setările de unificare](#update-unification-settings).

## <a name="manage-unified-fields"></a>Gestionați câmpurile unificate

1. Selectați **Editați | ×** pe **Câmpuri unificate pentru clienți** ţiglă.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Captură de ecran a câmpurilor unificate pentru clienți":::

1. Examinați câmpurile combinate și excluse și faceți modificările necesare. Adăugați sau editați cheia CustomerID sau profilurile de grup în grupuri. Pentru mai multe informații, vezi [Unificați câmpurile clienților](merge-entities.md).

1. Pentru clienți sau conturi, selectați **Următorul** a revizui și [actualizați profilul unificat și dependențele](#run-updates-to-the-unified-profile). Sau selectați **Salveaza si inchide** si revin la [Actualizați setările de unificare](#update-unification-settings) pentru a face mai multe modificări.

   Pentru contacte, selectați **Următorul** pentru a gestiona câmpurile semantice. Sau selectați **Salveaza si inchide** si revin la [Actualizați setările de unificare](#update-unification-settings) pentru a face mai multe modificări.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Gestionați câmpurile semantice pentru contactele unificate

1. Selectați **Editați | ×** pe **Câmpuri semantice** ţiglă.

1. Pentru a schimba tipul semantic pentru un câmp unificat, selectați un nou tip. Pentru mai multe informații, vezi [Definiți câmpurile semantice pentru contactele unificate](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts).

1. Selectați **Următorul** pentru a gestiona contul și relația de contact sau selectați **Salveaza si inchide** si revin la [Actualizați setările de unificare](#update-unification-settings) pentru a face mai multe modificări.

## <a name="manage-contact-and-account-relationships"></a>Gestionați relațiile de contact și de cont

1. Selectați **Editați | ×** pe **Relații** ţiglă.

1. Pentru a modifica relația de contact și de cont, modificați oricare dintre următoarele informații:

   - **Cheie străină de la entitatea de contact** : alegeți atributul care conectează entitatea dvs. de contact la cont.
   - **Pentru entitate de cont** : Alegeți entitatea de cont asociată contactului.

1. Selectați **Următorul** pentru a revizui setările de unificare și [actualizați profilul unificat și dependențele](#run-updates-to-the-unified-profile), sau selectați **Salveaza si inchide** si revin la [Actualizați setările de unificare](#update-unification-settings) pentru a face mai multe modificări.

## <a name="run-matching-conditions"></a>Rulați condiții de potrivire

Run matching conditions rulează numai deduplicarea și potrivirea regulilor și actualizează *Deduplicare_* * și *ConflationMatchPair* entitati.

1. De la **Date** > **Unifica** pagina, selectați **Rulați numai condiții de potrivire**.

   The **Înregistrări duplicate** și **Condiții de potrivire** faianta arată **În așteptare** sau **Înviorător** stare.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Când procesul de potrivire se încheie, selectați **Editați | ×** pe **Condiții de potrivire** ţiglă.

   :::image type="content" source="media/match-KPIs.png" alt-text="Captură de ecran decupată a valorilor cheie din pagina Potrivire cu numere și detalii.":::

1. Pentru a face modificări, vezi [Gestionați regulile de deduplicare](#manage-deduplication-rules) sau [Gestionați regulile de meci](#manage-match-rules).

1. Rulați din nou procesul de potrivire sau [rulați actualizări ale profilului](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Rulați actualizări ale profilului unificat

- Pentru a rula condiții de potrivire și pentru a actualiza entitatea de profil unificat *fără* care afectează dependențele (cum ar fi cardurile clienților, îmbogățirile, segmentele sau măsurile), selectați **Unificați profilurile clienților**. Pentru conturi, selectați **Unificați conturile** > **Unificați profilurile**. Pentru contacte, selectați **Unificați contactele (previzualizare)** > **Unificați profilurile**. Procesele dependente nu sunt rulate, dar vor fi reîmprospătate pe măsură ce [definite în programul de reîmprospătare](schedule-refresh.md).
- Pentru a rula condiții de potrivire, actualizați profilul unificat și rulați toate dependențele, selectați **Unificați profilurile și dependențele clienților**. Toate procesele sunt reluate automat. Pentru conturi și contacte, selectați **Unificați conturile** > **Unificați profilurile și dependențele**. Condițiile de potrivire sunt executate atât pentru conturi, cât și pentru persoanele de contact, actualizează atât profilurile unificate, cât și toate celelalte dependențe.

Toate plăcile, cu excepția **Câmpurile sursă** spectacol **În așteptare** sau **Înviorător**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Rezultatele unei rulări de succes sunt afișate pe **Unifica** pagină care arată numărul de profiluri unificate.
