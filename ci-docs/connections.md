---
title: Prezentare generală a conexiunilor (previzualizare)
description: Conexiuni la alte servicii de la Customer Insights.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 4a0bc5dd4100b462a26660a0c51fda1fe92b6bb9
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195189"
---
# <a name="connections-preview-overview"></a>Prezentare generală a conexiunilor (previzualizare)

Conexiunile sunt cheia pentru a permite partajarea datelor către și de la Customer Insights. Fiecare conexiune stabilește partajarea datelor cu un anumit serviciu. Conexiunile stau la baza [configurare îmbogățiri terțe](enrichment-hub.md) și [configurare exporturi](export-destinations.md). Aceeași conexiune poate fi utilizată de mai multe ori. De exemplu, o conexiune la Dynamics 365 Marketing funcționează pentru exporturi multiple și o conexiune Leadspace poate fi utilizată pentru mai multe îmbogățiri.

Salt la **Administrator** > **Conexiuni** pentru a crea și vizualiza conexiuni.

Fila **Conexiuni** vă arată toate conexiunile active. Lista arată un rând pentru fiecare conexiune.

Obțineți o prezentare rapidă, o descriere și aflați ce puteți face cu fiecare opțiune de extensibilitate de pe fila **Descoperire**.

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către terți sau alte produse Microsoft, permiteți transferul de date în afara limitei de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi Datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru a vă asigura că terța parte îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Ta Dynamics 365 Customer Insights administratorul poate elimina oricând conexiunea pentru a întrerupe utilizarea funcționalității.

## <a name="exports"></a>Exporturi

Numai administratorii pot configura conexiuni noi, dar pot acorda acces contribuitorilor pentru a utiliza conexiunile existente. Administratorii controlează unde pot merge datele, contribuitorii definesc sarcina utilă și frecvența potrivită nevoilor lor. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](#allow-contributors-to-use-a-connection-for-exports).

## <a name="enrichments"></a>Îmbogățiri

Numai administratorii pot configura conexiuni noi, dar conexiunile create sunt întotdeauna disponibile atât pentru administratori, cât și pentru contribuitori. Administratorii gestionează acreditările și își dau consimțământul transferurilor de date. Conexiunile pot fi apoi utilizate pentru îmbogățiri atât de administratori, cât și de contribuitori.

## <a name="add-a-new-connection"></a>Adăugați o conexiune nouă

Pentru a adăuga conexiuni, trebuie să aveți [permisiuni de administrator](permissions.md). Dacă vă conectați la alte servicii Microsoft, presupunem că ambele servicii se află în aceeași organizație.

1. Salt la **Administrator** > **Conexiuni (previzualizare)**.

1. Selectați **Adăugare conexiune** pentru a crea o nouă conexiune. Alegeți din meniul derulant ce tip de conexiune doriți să creați.

1. În panoul **Configurarea conexiunii**, furnizați detaliile necesare.
   1. **Numele afișat** și tipul conexiunii descriu o conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta acestei conexiuni.
   1. Câmpurile exacte depind de serviciul la care vă conectați. Puteți afla detalii despre un anumit tip de conexiune din articolul despre serviciul țintă.
   1. Dacă [vă utilizați propria Key Vault](use-azure-key-vault.md) pentru a stoca secrete, activați **Utilizați Kay Vault** și alegeți secretul din listă.

1. Pentru a crea conexiunea, selectați **Salvare**.

Puteți selecta, de asemenea **Configurare** pe o dală de pe fila **Descoperire**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi

Când configurați sau editați o conexiune de export, alegeți căror utilizatori le este permis să utilizeze această conexiune specifică pentru a defini [exporturi](export-destinations.md). În mod implicit, o conexiune este disponibilă pentru utilizatorii cu rol de administrator. Puteți modifica această setare în **Alegeți cine poate utiliza această conexiune** și puteți permite utilizatorilor cu rol de contribuitor să utilizeze această conexiune.

- Contribuitorii nu vor putea vizualiza sau edita conexiunea. Ei vor vedea numai numele afișat și tipul acestuia atunci când creează un export.
- Prin partajarea unei conexiuni, permiteți colaboratorilor să utilizeze o conexiune. Contribuitorii vor vedea conexiuni partajate atunci când configurează exporturile. Ei pot gestiona fiecare export care utilizează această conexiune specifică.
- Puteți modifica această setare păstrând în același timp exporturile care au fost deja definite de contribuitori.

## <a name="edit-a-connection"></a>Editarea unei conexiuni

1. Salt la **Administrator** > **Conexiuni (previzualizare)**.

1. Mergeți la fila **Conexiuni**.

1. Selectați elipsa verticală (&vellip;) pentru conexiunea pe care doriți să o editați.

1. Selectați **Editare**.

1. Schimbați valorile pe care doriți să le actualizați și selectați **Salvați**.

## <a name="remove-a-connection"></a>Eliminați o conexiune

Dacă conexiunea pe care o eliminați este folosită de îmbogățiri sau exporturi, mai întâi trebuie să le detașați sau să le eliminați. Dialogul de eliminare vă va ghida către îmbogățirea sau exporturile relevante.

Îmbogățirile și exporturile detașate devin inactive. Le reactivați adăugându-le o altă conexiune pe pagina [Îmbogățiri](enrichment-hub.md) sau [Exporturi](export-destinations.md).

1. Salt la **Administrator** > **Conexiuni (previzualizare)**.

1. Mergeți la fila **Conexiuni**.

1. Selectați elipsa verticală (&vellip;) pentru conexiunea pe care doriți să o eliminați.

1. Selectați **Eliminare** din meniul vertical. Apare un dialog de confirmare.

   1. Dacă există îmbogățiri sau exporturi care utilizează această conexiune, selectați butonul pentru a vedea ce folosește conexiunea.
      - **Exporturi:** Puteți alege să eliminați sau să deconectați exporturile pentru a putea elimina conexiunea. Pentru a deconecta un export, administratorii pot utiliza acțiunea **Deconectat**. Această acțiune este disponibilă pentru exporturile individuale și multiple selectate. Prin deconectare, păstrați configurația de export, dar nu va fi rulată până când nu i se adaugă o altă conexiune.
      - **Îmbogățiri:** Puteți alege să eliminați sau să dezactivați îmbogățirile pentru a putea elimina conexiunea.
   1. Odată ce conexiunea nu mai are dependențe, reveniți la **Administrator** > **Conexiuni** și încercați să eliminați din nou conexiunea.

1. Pentru a confirma ștergerea selectați **Ștergere**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Configurați conexiuni cu secrete gestionate de propria Key Vault

Unele conexiuni au nevoie de secrete, cum ar fi cheile API sau parolele. Unele conexiuni acceptă secretele stocate în propria Key Vault. Aflați mai multe despre conexiunile acceptate și despre cum să le configurați [propriul tău Key Vault pentru Customer Insights](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
