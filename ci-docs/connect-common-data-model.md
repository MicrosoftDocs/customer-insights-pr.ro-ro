---
title: Conectați-vă la un folder Common Data Model folosind un cont Azure Data Lake
description: Lucrați cu datele Common Data Model folosind Azure Data Lake Storage.
ms.date: 05/30/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: b1cdcb46df17d722ad49d361ae4c7ab34c83eeb1
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082266"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Conectarea la date în Azure Data Lake Storage

Ingerați date în Dynamics 365 Customer Insights folosind dvs Azure Data Lake Storage cont Gen2. Asimilarea datelor poate fi completă sau incrementală.

## <a name="prerequisites"></a>Cerințe preliminare

- Suporta ingestie de date Azure Data Lake Storage *Gen2* exclusiv conturi. Nu puteți utiliza conturi Data Lake Storage Gen1 pentru a asimila date.

- The Azure Data Lake Storage cont trebuie sa aiba [spațiu de nume ierarhic activat](/azure/storage/blobs/data-lake-storage-namespace). Datele trebuie să fie stocate într-un format de folder ierarhic care definește folderul rădăcină și are subdosare pentru fiecare entitate. Subfolderele pot avea date complete sau foldere de date incrementale.

- Pentru a vă autentifica cu o entitate principală de serviciu Azure, asigurați-vă că este configurat în entitatea găzduită. Pentru mai multe informații, vezi [Conectați-vă la un Azure Data Lake Storage Cont Gen2 cu un principal de serviciu Azure](connect-service-principal.md).

- The Azure Data Lake Storage de la care doriți să vă conectați și să ingerați date trebuie să fie în aceeași regiune Azure ca și Dynamics 365 Customer Insights mediu inconjurator. Conexiunile la un director Common Data Model dintr-un data lake dintr-o altă regiune Azure nu sunt acceptate. Pentru a cunoaște regiunea Azure a mediului, accesați **Admin** > **Sistem** > **Despre** în Customer Insights.

- Datele stocate în serviciile online pot fi stocate într-o locație diferită de cea în care sunt procesate sau stocate datele Dynamics 365 Customer Insights.Prin importul sau conectarea la datele stocate în serviciile online, sunteți de acord că datele pot fi transferate și stocate cu Dynamics 365 Customer Insights . [Aflați mai multe la Microsoft Trust Center](https://www.microsoft.com/trust-center).

- Principalul serviciu Customer Insights trebuie să aibă unul dintre următoarele roluri pentru a accesa contul de stocare. Pentru mai multe informații, vezi [Acordați permisiuni principalului serviciu pentru a accesa contul de stocare](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Cititor de date Blob de stocare
  - Proprietar de date Blob de stocare
  - Contribuitor de date blob de stocare

- Datele din Data Lake Storage trebuie să urmeze standardul Common Data Model pentru stocarea datelor dvs. și să aibă manifestul comun al modelului de date pentru a reprezenta schema fișierelor de date (*.csv sau *.parquet). Manifestul trebuie să furnizeze detaliile entităților, cum ar fi coloanele de entități și tipurile de date, precum și locația și tipul fișierului de date. Pentru mai multe informații, vezi [Manifestul Common Data Model](/common-data-model/sdk/manifest). Dacă manifestul nu este prezent, utilizatorii administratori cu acces Proprietar de date stocare blob sau Contributor de date blob stocare pot defini schema atunci când ingerează datele.

## <a name="connect-to-azure-data-lake-storage"></a>Conectarea la Azure Data Lake Storage

1. Accesați **Date** > **Surse de date**.

1. Selectați **Adăugați sursa de date**.

1. Selectați **Stocare Azure Data Lake**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Casetă de dialog pentru a introduce detaliile de conectare pentru Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. Introduceți a **Nume** pentru sursă de date și opțional **Descriere**. Numele identifică în mod unic sursă de date și este referit în procesele din aval și nu poate fi schimbat.

1. Alegeți una dintre următoarele opțiuni pentru **Conectați-vă spațiul de stocare folosind**. Pentru mai multe informații, vezi [Conectați Customer Insights la un Azure Data Lake Storage Cont Gen2 cu un principal de serviciu Azure](connect-service-principal.md).

   - **Resursa Azure** : Introduceți **ID resursă** . Opțional, dacă doriți să ingerați date dintr-un cont de stocare printr-o legătură privată Azure, selectați **Activați legătura privată**. Pentru mai multe informații, vezi [Linkuri private](security-overview.md#private-links-tab).
   - **Abonament Azure** : Selectează **Abonament** iar apoi cel **Grup de resurse** și **Cont de stocare**. Opțional, dacă doriți să ingerați date dintr-un cont de stocare printr-o legătură privată Azure, selectați **Activați legătura privată**. Pentru mai multe informații, vezi [Linkuri private](security-overview.md#private-links-tab).
  
   > [!NOTE]
   > Aveți nevoie de unul dintre următoarele roluri fie pentru container, fie pentru contul de stocare pentru a crea sursă de date:
   >
   >  - Storage Blob Data Reader este suficient pentru a citi dintr-un cont de stocare și pentru a asimila datele în Customer Insights. 
   >  - Colaboratorul sau proprietarul datelor blob de stocare este necesar dacă doriți să editați fișierele manifest direct în Customer Insights.  
  
1. Alegeți numele **Container** care conține datele și schema (fișierul model.json sau manifest.json) din care să importați date și selectați **Următorul**.
   > [!NOTE]
   > Orice fișier model.json sau manifest.json asociat cu o altă sursă de date din mediu nu va apărea în listă. Cu toate acestea, același fișier model.json sau manifest.json poate fi utilizat pentru surse de date în medii multiple.

1. Pentru a crea o nouă schemă, accesați [Creați un nou fișier de schemă](#create-a-new-schema-file).

1. Pentru a utiliza o schemă existentă, navigați la folderul care conține fișierul model.json sau manifest.cdm.json. Puteți căuta într-un director pentru a găsi fișierul.

1. Selectați fișierul json și selectați **Următorul**. Se afișează o listă de entități disponibile.

   :::image type="content" source="media/review-entities.png" alt-text="Caseta de dialog cu o listă de entități de selectat":::

1. Selectați entitățile pe care doriți să le includeți.

   :::image type="content" source="media/ADLS_required.png" alt-text="Casetă de dialog care arată Necesar pentru cheia primară":::

   > [!TIP]
   > Pentru a edita entitățile într-o interfață de editare JSON, selectați **Afișați mai multe** > **Editați fișierul schema**. Faceți modificări și selectați **Salvați**.

1. Pentru entitățile selectate care necesită asimilare incrementală, **Necesar** afișează sub **Reîmprospătare incrementală**. Pentru fiecare dintre aceste entități, a se vedea [Configurați o reîmprospătare incrementală pentru sursele de date Azure Data Lake](incremental-refresh-data-sources.md).

1. Pentru entitățile selectate pentru care nu a fost definită o cheie primară, **Necesar** afișează sub **Cheia principala**. Pentru fiecare dintre aceste entități:
   1. Selectați **Necesar**. The **Editați entitate** afișajele panoului.
   1. Alege **Cheia principala**. Cheia primară este un atribut unic pentru entitate. Pentru ca un atribut să fie o cheie primară validă, nu ar trebui să includă valori duplicate, valori lipsă sau valori nule. Atributele tipului de date șir, întreg și GUID sunt acceptate ca chei primare.
   1. Opțional, modificați modelul de partiție.
   1. Selectați **Închide** pentru a salva și a închide panoul.

1. Selectați numărul de **Atribute** pentru fiecare entitate inclusă. The **Gestionați atributele** afișează pagina.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Casetă de dialog pentru a selecta profilarea datelor.":::

   1. Creați atribute noi, editați sau ștergeți atributele existente. Puteți schimba numele, formatul datelor sau puteți adăuga un tip semantic.
   1. Pentru a activa analiza și alte capabilități, selectați **Profilarea datelor** pentru întreaga entitate sau pentru anumite atribute. În mod implicit, nu este activată nicio entitate pentru profilarea datelor.
   1. Selectați **Terminat**.

1. Selectați **Salvare**. The **Surse de date** se deschide pagina afișând noul sursă de date în **Înviorător** stare.

### <a name="create-a-new-schema-file"></a>Creați un nou fișier de schemă

1. Selectați **Fișier de schemă nou**.

1. Introduceți un nume pentru fișier și selectați **Salvați**.

1. Selectați **Noua entitate**. The **Entitate nouă** afișajele panoului.

1. Introduceți numele entității și alegeți **Locația fișierelor de date**.
   - **Mai multe fișiere .csv sau .parquet** : Navigați la folderul rădăcină, selectați tipul de model și introduceți expresia.
   - **Fișiere unice .csv sau .parquet** : Navigați la fișierul .csv sau .parquet și selectați-l.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Casetă de dialog pentru a crea o nouă entitate cu locația fișierelor de date evidențiată.":::

1. Selectați **Salvare**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Casetă de dialog pentru definirea sau generarea automată a atributelor.":::

1. Selectați **definiți atributele** pentru a adăuga manual atributele sau pentru a selecta **generați-le automat**. Pentru a defini atributele, introduceți un nume, selectați formatul de date și tipul semantic opțional. Pentru atributele generate automat:

   1. După ce atributele sunt generate automat, selectați **Atributele de revizuire**. The **Gestionați atributele** afișează pagina.

   1. Asigurați-vă că formatul datelor este corect pentru fiecare atribut.

   1. Pentru a activa analiza și alte capabilități, selectați **Profilarea datelor** pentru întreaga entitate sau pentru anumite atribute. În mod implicit, nu este activată nicio entitate pentru profilarea datelor.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Casetă de dialog pentru a selecta profilarea datelor.":::

   1. Selectați **Terminat**. The **Selectați entitățile** afișează pagina.

1. Continuați să adăugați entități și atribute, dacă este cazul.

1. După ce toate entitățile au fost adăugate, selectați **Include** pentru a include entitățile în asimilarea sursă de date.

   :::image type="content" source="media/ADLS_required.png" alt-text="Casetă de dialog care arată Necesar pentru cheia primară":::

1. Pentru entitățile selectate care necesită asimilare incrementală, **Necesar** afișează sub **Reîmprospătare incrementală**. Pentru fiecare dintre aceste entități, a se vedea [Configurați o reîmprospătare incrementală pentru sursele de date Azure Data Lake](incremental-refresh-data-sources.md).

1. Pentru entitățile selectate pentru care nu a fost definită o cheie primară, **Necesar** afișează sub **Cheia principala**. Pentru fiecare dintre aceste entități:
   1. Selectați **Necesar**. The **Editați entitate** afișajele panoului.
   1. Alege **Cheia principala**. Cheia primară este un atribut unic pentru entitate. Pentru ca un atribut să fie o cheie primară validă, nu ar trebui să includă valori duplicate, valori lipsă sau valori nule. Atributele tipului de date șir, întreg și GUID sunt acceptate ca chei primare.
   1. Opțional, modificați modelul de partiție.
   1. Selectați **Închide** pentru a salva și a închide panoul.

1. Selectați **Salvare**. The **Surse de date** se deschide pagina afișând noul sursă de date în **Înviorător** stare.


## <a name="edit-an-azure-data-lake-storage-data-source"></a>Editați un Azure Data Lake Storage sursă de date

Puteți actualiza *Conectați-vă la contul de stocare folosind* opțiune. Pentru mai multe informații, vezi [Conectați Customer Insights la un Azure Data Lake Storage Cont Gen2 cu un principal de serviciu Azure](connect-service-principal.md). Pentru a conecta la un container diferit de contul de stocare sau să modificați numele contului, trebuie să [creați o nouă conexiune la sursa de date](#connect-to-azure-data-lake-storage).

1. Accesați **Date** > **Surse de date**.

1. Lângă sursă de date pe care doriți să o actualizați, selectați **Editați | ×**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Casetă de dialog pentru a edita Azure Data Lake sursă de date.":::

1. Modificați oricare dintre următoarele informații:

   - **Descriere**
   - **Conectați-vă spațiul de stocare folosind** și informații de conectare. Nu puteți schimba informațiile legate de **Recipient** la actualizarea conexiunii.
      > [!NOTE]
      > Unul dintre următoarele roluri trebuie să fie atribuit contului de stocare sau containerului:
        > - Cititor de date Blob de stocare
        > - Proprietar de date Blob de stocare
        > - Contribuitor de date blob de stocare

   - **Activați legătura privată** dacă doriți să ingerați date dintr-un cont de stocare printr-o legătură privată Azure. Pentru mai multe informații, vezi [Linkuri private](security-overview.md#private-links-tab).

1. Selectați **Următorul**.
1. Modificați oricare dintre următoarele:
   - Navigați la un alt fișier model.json sau manifest.json cu un set diferit de entități din container.
   - Pentru a adăuga entități suplimentare de asimilat, selectați **Noua entitate**.
   - Pentru a elimina orice entitate deja selectată dacă nu există dependențe, selectați entitatea și **Șterge**.
      > [!IMPORTANT]
      > Dacă există dependențe de fișierul model.json sau manifest.json existent și setul de entități, veți vedea un mesaj de eroare și nu puteți selecta un fișier model.json sau manifest.json diferit. Eliminați aceste dependențe înainte de a schimba fișierul model.json sau manifest.json sau creați un nou sursă de date cu fișierul model.json sau manifest.json pe care doriți să îl utilizați pentru a evita eliminarea dependențelor.
   - Pentru a schimba locația fișierului de date sau cheia principală, selectați **Editați | ×**.
   - Pentru a modifica datele de asimilare incrementală, consultați [Configurați o reîmprospătare incrementală pentru sursele de date Azure Data Lake](incremental-refresh-data-sources.md)

1. Selectați **Atribute** pentru a adăuga sau modifica atribute sau pentru a activa profilarea datelor. Apoi selectați **Terminat**.

1. Clic **Salvați** pentru a aplica modificările și a reveni la **Surse de date** pagină.
