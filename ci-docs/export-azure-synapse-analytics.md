---
title: Exportați datele Customer Insights către Azure Synapse Analytics
description: Aflați cum să configurați conexiunea la Azure Synapse Analytics.
ms.date: 04/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 772fe0978362ccd829077a8133e2a3e74043f3f8
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741518"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exportați datele în Azure Synapse Analytics (Previzualizare)

Azure Synapse este un serviciu de analize ce accelerează timpul de detaliere a depozitelor de date și a sistemelor de date mari. Puteți ingera și utiliza datele Customer Insights în [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Cerințe preliminare

Următoarele condiții preliminare trebuie îndeplinite pentru a configura conexiunea de la Customer Insights la Azure Synapse.

> [!NOTE]
> Asigurați-vă să setați toate **atribuirile de roluri** după cum este descris.  

## <a name="prerequisites-in-customer-insights"></a>Cerințe preliminare în Customer Insights

* Ta Azure Active Directory Contul de utilizator (AD) are un **Administrator** rol în Customer Insights. Află mai multe despre [stabilirea permisiunilor utilizatorului](permissions.md#assign-roles-and-permissions).

În Azure: 

- Un abonament Azure activ.

- Dacă utilizați un nou Azure Data Lake Storage Contul Gen2, the *principal de serviciu pentru Customer Insights* are nevoie **Colaborator de date Blob de stocare** permisiuni. Aflați mai multe pe [conectarea la o Azure Data Lake Storage Cont Gen2 cu principalul serviciului Azure pentru Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **trebuie să aibă** [spațiul de nume ierarhic](/azure/storage/blobs/data-lake-storage-namespace) activat.

- Pe grupul de resurse unde Azure Synapse spațiul de lucru este situat, the *principalul serviciului* si *Azure AD utilizator cu permisiuni de administrator în Customer Insights* trebuie să fie atribuit cel puțin **Cititor** permisiuni. Pentru mai multe informații, consultați [Atribuirea de roluri Azure utilizând portalul Azure](/azure/role-based-access-control/role-assignments-portal).

- The *Azure AD utilizator cu permisiuni de administrator în Customer Insights* are nevoie **Colaborator de date Blob de stocare** permisiuni pe Azure Data Lake Storage Contul Gen2 în care se află datele și sunt legate la Azure Synapse spațiu de lucru. Aflați mai multe despre [utilizarea portalului Azure pentru a atribui un rol Azure pentru accesul la datele de blob și la coadă](/azure/storage/common/storage-auth-aad-rbac-portal) și [permisiuni de stocare pentru contribuitor date blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Pentru utilizator *[identitatea gestionată de spațiu de lucru Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* este nevoie de permisiuni **Contribuitor stocare date blob** pentru contul Azure Data Lake Storage Gen2 unde sunt amplasate datele și conectate la spațiul de lucru Azure Synapse. Aflați mai multe despre [utilizarea portalului Azure pentru a atribui un rol Azure pentru accesul la datele de blob și la coadă](/azure/storage/common/storage-auth-aad-rbac-portal) și [permisiuni de stocare pentru contribuitor date blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Pe Azure Synapse spaţiul de lucru, *principal de serviciu pentru Customer Insights* are nevoie **Administrator Synapse** rolul atribuit. Pentru mai multe informații, consultați [Cum să configurați controlul accesului pentru spațiul de lucru Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Configurați conexiunea și exportul la Azure Synapse

### <a name="configure-a-connection"></a>Configurați o conexiune

Pentru a crea o conexiune, este nevoie de principalul serviciu și contul de utilizator din Customer Insights **Cititor** permisiuni pe *grup de resurse* unde se află spațiul de lucru Synapse Analytics. În plus, principalul serviciu și utilizatorul din spațiul de lucru Synapse Analytics au nevoie **Administrator Synapse** permisiuni. 

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Azure Synapse Analytics** sau selectați **Înființat** pe **Azure Synapse Analytics** țiglă pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul Nume afișat. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selectați sau căutați abonamentul în care doriți să utilizați datele Customer Insights. De îndată ce este selectat un abonament, puteți selecta și **Spațiul de lucru**, **Contul de stocare** și **containerul**.

1. Selectați **Salvare** pentru a salva conexiunea.

### <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru a configura exportul cu o conexiune partajată, aveți nevoie de cel puțin **Colaborator** permisiunile din Customer Insights. Pentru mai multe informații, consultați [permisiunile necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare export**.

1. În **Conexiune pentru export** câmp, alegeți o conexiune din **Azure Synapse Analytics** secțiune. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile [conexiuni](connections.md) de acest tip.

1. Dați un **Nume afișat** pentru exportul dvs. și un **Nume al bazei de date**.

1. Selectați la ce entități doriți să exportați Azure Synapse Analytics.
   > [!NOTE]
   > Surse de date bazate pe un [Dosar Common Data Model](connect-common-data-model.md) nu sunt acceptate.

2. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).

Pentru a interoga datele care au fost exportate în Synapse Analytics, aveți nevoie **Cititor de date Blob de stocare** acces la stocarea de destinație pe spațiul de lucru al exporturilor. 

### <a name="update-an-export"></a>Actualizați un export

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Editare** pe exportul pe care doriți să îl actualizați.

   - **Adăugați** sau **Eliminați** entități din selecție. Dacă entitățile sunt eliminate din selecție, ele nu sunt șterse și din baza de date Synapse Analytics. Cu toate acestea, reîmprospătările de date viitoare nu vor actualiza entitățile eliminate din baza de date respectivă.

   - **Modificarea numelui bazei de date** creează o nouă bază de date Synapse Analytics. Baza de date cu numele ce a fost configurat înainte nu va primi actualizări în reîmprospătări viitoare.
