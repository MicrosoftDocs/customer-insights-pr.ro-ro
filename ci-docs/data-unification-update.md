---
title: Actualizați setările de unificare pentru clienți, conturi sau contacte
description: Actualizați regulile duplicate, regulile de potrivire sau câmpurile unificate din setările de unificare a clienților sau a contului.
ms.date: 08/26/2022
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
ms.openlocfilehash: e893e66fd7691b9703d51ed8f87cfad63880cc3b
ms.sourcegitcommit: 560c4ee16376a9c6fdd7860988ce2d2440194fa5
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/01/2022
ms.locfileid: "9392486"
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
   - [Câmpurile sursă](#edit-source-fields) pentru a adăuga atribute sau entități sau pentru a schimba tipurile de atribute. Pentru a elimina un atribut, vezi [Eliminați un câmp unificat](#remove-a-unified-field). Pentru a elimina o entitate, vezi [Eliminați o entitate unificată](#remove-a-unified-entity).
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

1. Selectați **Editați | ×** pe **Câmpurile sursă** ţiglă.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Captură de ecran a paginii Câmpuri sursă care arată numărul de chei primare, câmpuri mapate și nemapate":::

   Afișează numărul de câmpuri mapate și nemapate.

1. Pentru a adăuga alte atribute sau entități, selectați **Selectați entitățile și câmpurile**.

1. Opțional, puteți modifica cheia primară pentru o entitate, tipurile de atribute și comutați **Cartografiere inteligentă** pornit sau oprit. Pentru mai multe informații, vezi [Selectați câmpurile sursă](map-entities.md).

1. Selectați **Următorul** pentru a modifica regulile de deduplicare sau selectați **Salveaza si inchide** si revin la [Actualizați setările de unificare](#update-unification-settings).

### <a name="remove-a-unified-field"></a>Eliminați un câmp unificat

Pentru a elimina un câmp care a fost unificat, câmpul trebuie eliminat din orice dependențe, cum ar fi segmente, măsuri, îmbogățiri sau relații.

1. După ce toate dependențele pentru câmp au fost eliminate, accesați **Date** > **Unifica**.

1. Selectați **Editați | ×** pe **Câmpuri unificate pentru clienți** ţiglă.

1. Selectați toate aparițiile câmpului și apoi selectați **Exclude**.

   :::image type="content" source="media/m3_remove_attribute1.png" alt-text="Captură de ecran a paginii Câmpuri unificate care arată câmpurile selectate și butonul Excludeți":::

1. Selectați **Terminat** pentru a confirma și apoi selectați **Salveaza si inchide**.

   > [!TIP]
   > Dacă vedeți mesajul „Nu s-a putut salva unificarea. Resursa specificată nu poate fi modificată sau ștearsă din cauza dependențelor din aval”, atunci câmpul este încă folosit într-o dependență din aval.

1. Dacă câmpul este utilizat într-o regulă pentru înregistrări duplicate sau condiții de potrivire, efectuați următorii pași. În caz contrar, treceți la pasul următor.
   1. Selectați **Editați | ×** pe **Înregistrări duplicate** ţiglă.
   1. Eliminați câmpul din toate regulile în care este utilizat, dacă există, apoi selectați **Următorul**.
   1. Pe **Condiții de potrivire** pagina, eliminați câmpul din toate regulile în care este utilizat, dacă există, apoi selectați **Salveaza si inchide**.
   1. Selectați **Unifica** > **Unificați profilurile și dependențele clienților**. Așteptați finalizarea unificării înainte de a trece la pasul următor.

1. Selectați **Editați | ×** pe **Câmpurile sursă** ţiglă.

1. Selectați **Selectați entitățile și câmpurile** și debifați caseta de selectare de lângă fiecare apariție a câmpului.

   :::image type="content" source="media/m3_remove_attribute2.png" alt-text="Captură de ecran a casetei de dialog Selectați entități și câmpuri care arată casetele de selectare debifate":::

1. Selectați **Se aplică**.

1. Selectați **Salvați și închideți**.

1. Selectați **Unifica** > **Unificați profilurile și dependențele clienților** pentru a actualiza profilul unificat.

### <a name="remove-a-unified-entity"></a>Eliminați o entitate unificată

Pentru a elimina o entitate care a fost unificată, entitatea trebuie eliminată din orice dependențe, cum ar fi segmente, măsuri, îmbogățiri sau relații.

1. După ce toate dependențele pentru entitate au fost eliminate, accesați **Date** > **Unifica**.

1. Selectați **Editați | ×** pe **Câmpuri unificate pentru clienți** ţiglă.

1. Selectați toate câmpurile pentru entitate și apoi selectați **Exclude**.

   :::image type="content" source="media/m3_remove_entity1.png" alt-text="Captură de ecran a câmpurilor unificate cu toate câmpurile pentru o entitate selectate și butonul Exclude":::

1. Selectați **Terminat** pentru a confirma și apoi selectați **Salveaza si inchide**.

   > [!TIP]
   > Dacă vedeți mesajul „Nu s-a putut salva unificarea. Resursa specificată nu poate fi modificată sau ștearsă din cauza dependențelor din aval”, atunci entitatea este încă utilizată într-o dependență din aval.

1. Selectați **Editați | ×** pe **Înregistrări duplicate** ţiglă.

1. Eliminați toate regulile din entitate, dacă există, apoi selectați **Următorul**.

1. Pe **Condiții de potrivire** pagina, selectați entitatea și apoi selectați **Șterge**.

   :::image type="content" source="media/m3_remove_entity2.png" alt-text="Captură de ecran cu Condițiile de potrivire cu entitatea selectată și butonul Ștergere":::

1. Selectați **Salvați și închideți**.

1. Selectați **Editați | ×** pe **Câmpurile sursă** ţiglă.

1. Selectați **Selectați entitățile și câmpurile** și debifați caseta de selectare de lângă entitate.

   :::image type="content" source="media/m3_remove_entity3.png" alt-text="Captură de ecran a casetei de dialog Selectați entități și câmpuri cu caseta de selectare a entității debifată":::

1. Selectați **Se aplică**.

1. Selectați **Salvați și închideți**.

1. Selectați **Unifica** > **Unificați profilurile și dependențele clienților** pentru a actualiza profilul unificat.

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

1. Selectați **Editare** pe dala **Potrivire condiții**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Captură de ecran a paginii Potrivire reguli și condiții cu statistici." lightbox="media/m3_match_edit.png":::

   Pagina afișează ordinea de potrivire și regulile definite și următoarele statistici:
   - **Înregistrările** sursă unice afișează numărul de înregistrări sursă individuale care au fost procesate în ultima rulare a meciului.
   - **Înregistrările** potrivite și necorelate evidențiază câte înregistrări unice rămân după procesarea regulilor de potrivire.
   - **Înregistrările potrivite afișează doar** numărul de meciuri din toate perechile de meciuri.

1. Pentru a vizualiza rezultatele tuturor regulilor și scorurile acestora, selectați **Vizualizare ultima rulare**. Rezultatele se afișează, inclusiv ID-urile alternative de contact. Puteți descărca rezultatele.

1. Pentru a vizualiza rezultatele și scorurile unei anumite reguli, selectați regula, apoi **Previzualizare**. Rezultatele se afișează. Puteți descărca rezultatele.

1. Pentru a vizualiza rezultatele unei anumite condiții dintr-o regulă, selectați regula, apoi **Editați**. În panoul Editare, selectați **Previzualizare** sub condiția respectivă. Puteți descărca rezultatele.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Reprezentarea grafică a înregistrărilor de neegalat și potrivite, inclusiv o listă a datelor.":::

1. Dacă ați adăugat o entitate îmbogățită, selectați **Utilizați entități** îmbogățite. Pentru mai multe informații, vezi [Îmbogățirea surselor de date](data-sources-enrichment.md).

1. Pentru a gestiona regulile, alegeți oricare dintre următoarele opțiuni:
   - **Creați o nouă regulă** : Selectați **Adăugați o regulă** sub entitatea corespunzătoare. Pentru mai multe informații, consultați [Definirea regulilor pentru perechile de potriviri](match-entities.md#define-rules-for-match-pairs).
   - **Modificați ordinea regulilor** dacă ați definit mai multe reguli: Glisați și fixați regulile în ordinea dorită. Pentru mai multe informații, consultați [Specificarea ordinii de potrivire](match-entities.md#specify-the-match-order).
   - **Schimbați condițiile regulilor** : Selectați regula și apoi **Editați | ×**. Schimbați câmpuri, adăugați sau eliminați condiții sau adăugați sau eliminați excepții.
   - **Dezactivați o regulă**: Selectați regula, apoi **Dezactivați** pentru a păstra o regulă de potrivire, excluzând-o în același timp din procesul de potrivire.
   - **Duplicați o regulă** : Selectați regula și apoi **Duplicat** pentru a crea o regulă similară cu modificări.
   - **Ștergeți o regulă** : Selectați regula și apoi **Șterge**.

1. Selectați **Următorul** pentru a efectua modificări în câmpurile unificate sau selectați **Salvare și închidere** și reveniți la [Actualizare setări de](#update-unification-settings) unificare.

## <a name="manage-unified-fields"></a>Gestionarea câmpurilor unificate

1. Selectați **Editați | ×** pe **Câmpuri unificate pentru clienți** ţiglă.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Captură de ecran cu câmpurile Client unificat":::

1. Revizuiți câmpurile combinate și excluse și efectuați modificările după cum este necesar. Adăugați sau editați cheia CustomerID sau profilurile de grup în clustere. Pentru mai multe informații, consultați [Unificarea câmpurilor](merge-entities.md) pentru clienți.

1. Pentru clienți sau conturi, selectați **Următorul** pentru a revizui și [actualiza profilul unificat și dependențele](#run-updates-to-the-unified-profile). Sau selectați **Salvare și închidere** și reveniți la [Actualizare setări de](#update-unification-settings) unificare pentru a efectua mai multe modificări.

   Pentru persoanele de contact, selectați **Următorul** pentru a gestiona câmpurile semantice. Sau selectați **Salvare și închidere** și reveniți la [Actualizare setări de](#update-unification-settings) unificare pentru a efectua mai multe modificări.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Gestionarea câmpurilor semantice pentru persoanele de contact unificate

1. Selectați **Editare** pe dala **Câmpuri** semantice.

1. Pentru a modifica tipul semantic pentru un câmp unificat, selectați un tip nou. Pentru mai multe informații, consultați [Definirea câmpurilor semantice pentru persoanele de contact](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts) unificate.

1. Selectați **Următorul** pentru a gestiona contul și relația de contact sau selectați **Salvare și închidere** și reveniți la [Actualizare setări de](#update-unification-settings) unificare pentru a efectua mai multe modificări.

## <a name="manage-contact-and-account-relationships"></a>Gestionarea relațiilor dintre persoane de contact și cont

1. Selectați **Editare** pe dala **Relații**.

1. Pentru a modifica relația dintre persoana de contact și cea de cont, modificați oricare dintre următoarele informații:

   - **Cheie străină de la entitatea** de contact: alegeți atributul care conectează entitatea de contact la cont.
   - **Pentru entitatea** contului: alegeți entitatea de cont asociată persoanei de contact.

1. Selectați **Următorul** pentru a revizui setările de unificare și [a actualiza profilul și dependențele](#run-updates-to-the-unified-profile) unificate sau selectați **Salvare și închidere** și reveniți la [Actualizare setări de](#update-unification-settings) unificare pentru a efectua mai multe modificări.

## <a name="run-matching-conditions"></a>Rularea condițiilor de potrivire

Executați condiții de potrivire se execută deduplicare și potrivire reguli numai și actualizează entitățile *Deduplication_** și *ConflationMatchPair*.

1. **Din pagina Unificare** > **date**, selectați **Executare numai** condiții de potrivire.

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

Rezultatele unei rulări reușite se afișează pe **Unifica** pagină care arată numărul de profiluri unificate.
