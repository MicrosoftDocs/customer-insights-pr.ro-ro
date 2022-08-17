---
title: Prezentare generală a conexiunilor (previzualizare)
description: Conexiuni la alte servicii de la Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245526"
---
# <a name="connections-preview-overview"></a>Prezentare generală a conexiunilor (previzualizare)

Conexiunile sunt cheia pentru a permite partajarea datelor către și de la Customer Insights. Fiecare conexiune stabilește partajarea datelor cu un anumit serviciu. Utilizați conexiuni pentru [configurați îmbogățiri de la terți](enrichment-hub.md) și [configurați exporturile](export-destinations.md). Aceeași conexiune poate fi utilizată de mai multe ori. De exemplu, o conexiune la Dynamics 365 Marketing funcționează pentru exporturi multiple și o conexiune Leadspace poate fi utilizată pentru mai multe îmbogățiri.

## <a name="export-connections"></a>Exportați conexiuni

Numai administratorii pot configura conexiuni noi, dar pot [acorda acces contribuabililor](#allow-contributors-to-use-a-connection-for-exports) pentru a utiliza conexiunile existente. Administratorii controlează unde pot merge datele, contribuitorii definesc sarcina utilă și frecvența potrivită nevoilor lor.

## <a name="enrichment-connections"></a>Conexiuni de îmbogățire

Numai administratorii pot configura conexiuni noi, dar conexiunile create sunt întotdeauna disponibile atât pentru administratori, cât și pentru colaboratori. Administratorii gestionează acreditările și își dau consimțământul transferurilor de date. Conexiunile pot fi apoi utilizate pentru îmbogățiri atât de administratori, cât și de contribuitori.

## <a name="add-a-new-connection"></a>Adăugați o conexiune nouă

### <a name="prerequisites"></a>Cerințe preliminare

- [Permisiuni de administrator](permissions.md)
- Alte servicii Microsoft, dacă există, sunt în aceeași organizație

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți tipul de conexiune pe care doriți să o creați. Sau, du-te la **Descoperi** filă și selectați **Înființat** pe o placă de legătură.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Introduceți detaliile necesare. Câmpurile exacte depind de serviciul la care vă conectați. Pentru detalii despre un anumit tip de conexiune, consultați articolul despre serviciul țintă.

1. Dacă [vă utilizați propria Key Vault](use-azure-key-vault.md) pentru a stoca secrete, activați **Utilizați Kay Vault** și alegeți secretul din listă.

1. Examinați confidențialitatea și conformitatea datelor și selectați **Sunt de acord**.

1. Selectați **Salvați** pentru a crea conexiunea.

### <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către terți sau alte produse Microsoft, permiteți transferul de date în afara limitei de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi Datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil să vă asigurați că terța parte îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Ta Dynamics 365 Customer Insights administratorul poate elimina oricând conexiunea pentru a întrerupe utilizarea funcționalității.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi

Când configurați sau editați o conexiune de export, alegeți ce utilizatori au voie să utilizeze această conexiune specifică pentru a defini [exporturi](export-destinations.md). În mod implicit, o conexiune este disponibilă pentru utilizatorii cu rol de administrator. Schimba **Alegeți cine poate folosi această conexiune** setare pentru a permite utilizatorilor cu rol de colaborator să utilizeze această conexiune.

- Contribuitorii nu vor putea vizualiza sau edita conexiunea. Ei vor vedea numai numele afișat și tipul acestuia atunci când creează un export.
- Prin partajarea unei conexiuni, permiteți colaboratorilor să utilizeze o conexiune. Contribuitorii vor vedea conexiuni partajate atunci când configurează exporturile. Ei pot gestiona fiecare export care utilizează această conexiune specifică.
- Puteți modifica această setare păstrând în același timp exporturile care au fost deja definite de contribuitori.

## <a name="manage-existing-connections"></a>Gestionați conexiunile existente

1. Salt la **Administrator** > **Conexiuni**.

1. Selectează **Îmbogăţire** sau **Exporturi** pentru a vizualiza o listă de conexiuni de îmbogățire sau de export, tipul conexiunii, când a fost creată și cine are acces. Puteți sorta lista de conexiuni după orice coloană.

1. Selectați conexiunea pentru a vedea acțiunile disponibile.

   - **Editați | ×** conexiunea.
   - [**Elimina**](#remove-a-connection) o conexiune.

### <a name="remove-a-connection"></a>Eliminați o conexiune

Dacă conexiunea pe care o eliminați este folosită de îmbogățiri sau exporturi, mai întâi detașați-le sau eliminați-le. Fereastra de eliminare vă ghidează către îmbogățirile sau exporturile relevante.

> [!TIP]
> Îmbogățirile dezactivate și exporturile detașate devin inactive. Le reactivați adăugându-le o altă conexiune pe pagina [Îmbogățiri](enrichment-hub.md) sau [Exporturi](export-destinations.md).

1. Salt la **Administrator** > **Conexiuni**.

1. Selectează **Îmbogăţire** sau **Exporturi** fila.

1. Selectați conexiunea pe care doriți să o eliminați.

1. Selectați **Eliminare** din meniul vertical. Apare un dialog de confirmare.

   1. Dacă există îmbogățiri sau exporturi care utilizează această conexiune, selectați butonul pentru a vedea ce folosește conexiunea.
      - **Exporturi:** Alegeți fie **Elimina** exportul sau **Deconectați conexiunea**. Detașarea conexiunii păstrează configurația de export, dar nu va fi rulată până când nu este adăugată o altă conexiune.
      - **Îmbogățiri:** Alegeți fie **Șterge** sau **Dezactivați** îmbogățirile.
   1. Odată ce conexiunea nu mai are dependențe, reveniți la **Administrator** > **Conexiuni** și încercați să eliminați din nou conexiunea.

1. Pentru a confirma ștergerea selectați **Ștergere**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Configurați conexiuni cu secrete gestionate de propria Key Vault

Unele conexiuni au nevoie de secrete, cum ar fi cheile API sau parolele. Unele conexiuni acceptă secretele stocate în propria Key Vault. Aflați mai multe despre conexiunile acceptate și despre cum să le configurați [propriul tău Key Vault pentru Customer Insights](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
