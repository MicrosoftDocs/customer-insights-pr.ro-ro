---
title: Conectați datele Common Data Model la un cont Azure Data Lake
description: Lucrați cu datele Common Data Model folosind Azure Data Lake Storage.
ms.date: 05/24/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 2e8564950a3269180a85f80fb736d2dcbd1b03b6
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833400"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Conectați-vă la un folder Common Data Model folosind un cont Azure Data Lake

Acest articol oferă informații despre cum să ingerați date în Dynamics 365 Customer Insights dintr-un folder Common Data Model folosind dvs Azure Data Lake Storage cont Gen2.

## <a name="important-considerations"></a>Considerații importante

- Datele din Azure Data Lake trebuie să urmeze standardul Common Data Model. Alte formate nu sunt acceptate în acest moment.

- Ingestia de date acceptă exclusiv conturi Azure Data Lake Storage *Gen2*. Nu puteți utiliza conturile Azure Data Lake Storage Gen1 pentru a ingera date.

- Contul de stocare Azure Data Lake trebuie să aibă [spațiu de nume ierarhic activat](/azure/storage/blobs/data-lake-storage-namespace).

- Pentru a vă autentifica cu o entitate principală de serviciu Azure, asigurați-vă că este configurat în entitatea găzduită. Pentru mai multe informații, vezi [Conectați-vă la un Azure Data Lake Storage Cont Gen2 cu un principal de serviciu Azure](connect-service-principal.md).

- Azure Data Lake la care doriți să vă conectați și să ingerați date trebuie să fie în aceeași regiune Azure ca și mediul Dynamics 365 Customer Insights. Conexiunile la un director Common Data Model dintr-un data lake dintr-o altă regiune Azure nu sunt acceptate. Pentru a cunoaște regiunea Azure a mediului, accesați **Admin** > **Sistem** > **Despre** în Customer Insights.

- Datele stocate în serviciile online pot fi stocate într-o locație diferită de cea în care sunt procesate sau stocate datele Dynamics 365 Customer Insights.Prin importul sau conectarea la datele stocate în serviciile online, sunteți de acord că datele pot fi transferate și stocate cu Dynamics 365 Customer Insights . [Aflați mai multe la Centrul de încredere Microsoft](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-common-data-model-folder"></a>Conectare la un folder Common Data Model

1. Accesați **Date** > **Surse de date**.

1. Selectați **Adăugați sursa de date**.

1. Selectați **Stocare Azure Data Lake**, introduceți a **Nume** pentru sursă de date, apoi selectați **Următorul**.

   - Dacă vi se solicită, selectați unul dintre seturile de date eșantion care se referă la industria dvs., apoi selectați **Următorul**.

1. Puteți alege între utilizarea unei opțiuni bazate pe resurse și o opțiune bazată pe abonament pentru autentificare. Pentru mai multe informații, vezi [Conectați-vă la un Azure Data Lake Storage Cont Gen2 cu un principal de serviciu Azure](connect-service-principal.md). Introduceți **Adresa serverului**, Selectați **Autentificare**, apoi selectați **Următorul**.
   > [!div class="mx-imgBorder"]
   > ![Casetă de dialog pentru a introduce noi detalii de conexiune pentru Azure Data Lake.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Aveți nevoie de unul dintre următoarele roluri fie pentru containerul din contul de stocare și pentru a crea sursă de date:
   >
   >  - Storage Blob Data Reader este suficient pentru a citi dintr-un cont de stocare și pentru a asimila datele în Customer Insights. 
   >  - Colaboratorul sau proprietarul datelor blob de stocare este necesar dacă doriți să editați fișierele manifest direct în Customer Insights.

1. În dialogul **Selectați un director Common Data Model**, selectați fișierul model.json sau manifest.json din care să importați date și selectați **Următorul**.
   > [!NOTE]
   > Orice fișier model.json sau manifest.json asociat cu o altă sursă de date din mediu nu va apărea în listă.

1. Veți vedea o listă de entități disponibile în fișierul model.json sau manifest.json selectat. Examinați și selectați din lista de entități disponibile, apoi selectați **Salvați**. Toate entitățile selectate vor fi ingerate din noua sursă de date.
   > [!div class="mx-imgBorder"]
   > ![Casetă de dialog care arată o listă de entități dintr-un fișier model.json.](media/review-entities.png)

1. Indicați ce entități de date doriți să activați profilarea datelor, apoi selectați **Salvați**. Profilarea datelor permite analiza și alte capacități. Puteți selecta întreaga entitate, care selectează toate atributele din entitate, sau puteți selecta anumite atribute dorite. În mod implicit, nu este activată nicio entitate pentru profilarea datelor.
   > [!div class="mx-imgBorder"]
   > ![Casetă de dialog care prezintă o profilare a datelor.](media/dataprofiling-entities.png)

1. După salvarea selecțiilor, se deschide pagina **Surse de date**. Acum ar trebui să vedeți conexiunea folderului Common Data Model ca o sursă de date.

> [!NOTE]
> Un fișier model.json sau manifest.json se poate asocia doar cu o singură sursă de date în același mediu. Cu toate acestea, același fișier model.json sau manifest.json poate fi utilizat pentru surse de date în medii multiple.

## <a name="edit-a-common-data-model-folder-data-source"></a>Editați o sursă de date a folderului Common Data Model

Puteți actualiza cheia de acces pentru contul de stocare care conține directorul Common Data Model. De asemenea, puteți schimba fișierul model.json sau manifest.json. Pentru a conecta la un container diferit de contul de stocare sau să modificați numele contului, trebuie să [creați o nouă conexiune la sursa de date](#connect-to-a-common-data-model-folder).

1. Accesați **Date** > **Surse de date**.

2. Lângă sursă de date pe care doriți să o actualizați, selectați punctele de suspensie verticale (&vellip;).

3. Selectați opțiunea **Editare** din listă.

4. Opțional, actualizați **Cheie de acces** și selectați **Următorul**.

   ![Dialog pentru a edita și a actualiza o cheie de acces pentru o sursă de date existentă.](media/edit-access-key.png)

5. Opțional, puteți actualiza de la o conexiune cu cheie de cont la o conexiune bazată pe resurse sau bazată pe abonament. Pentru mai multe informații, vezi [Conectați-vă la un Azure Data Lake Storage Cont Gen2 cu un principal de serviciu Azure](connect-service-principal.md). Nu puteți schimba informațiile legate de **Recipient** la actualizarea conexiunii.
   > [!div class="mx-imgBorder"]

   > ![Casetă de dialog pentru a introduce detaliile conexiunii pentru Azure Data Lake la un cont de stocare existent.](media/enter-existing-storage-details.png)

6. Opțional, alegeți un fișier model.json sau manifest.json diferit cu un set diferit de entități din container.

7. Opțional, puteți selecta entități suplimentare de ingerat. De asemenea, puteți elimina orice entități deja selectate dacă nu există dependențe.

   > [!IMPORTANT]
   > Dacă există dependențe de fișierul model.json sau manifest.json existent și setul de entități, veți vedea un mesaj de eroare și nu puteți selecta un fișier model.json sau manifest.json diferit. Eliminați aceste dependențe înainte de a schimba fișierul model.json sau manifest.json sau creați un nou sursă de date cu fișierul model.json sau manifest.json pe care doriți să îl utilizați pentru a evita eliminarea dependențelor.

8. Opțional, puteți selecta atribute sau entități suplimentare pentru a activa profilarea datelor sau să le dezactivați pe cele deja selectate.

[!INCLUDE [footer-include](includes/footer-banner.md)]
