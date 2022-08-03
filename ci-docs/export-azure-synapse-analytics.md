---
title: Exportați datele în Azure Synapse Analytics (previzualizare)
description: Aflați cum să configurați conexiunea la Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196409"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exportați datele în Azure Synapse Analytics (previzualizare)

Azure Synapse este un serviciu de analize ce accelerează timpul de detaliere a depozitelor de date și a sistemelor de date mari. Puteți ingera și utiliza datele Customer Insights în [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Cerințe preliminare

> [!NOTE]
> Asigurați-vă să setați toate **atribuirile de roluri** după cum este descris.

- În Customer Insights, dvs Azure Active Directory Contul de utilizator (AD) trebuie să aibă un [Rolul de administrator](permissions.md#assign-roles-and-permissions).

În Azure:

- Un abonament Azure activ.

- Dacă utilizați un nou Azure Data Lake Storage Contul Gen2, the [principal de serviciu pentru Customer Insights](connect-service-principal.md) are **Colaborator de date Blob de stocare** permisiuni. Data Lake Storage Gen2 **trebuie să aibă** [spațiul de nume ierarhic](/azure/storage/blobs/data-lake-storage-namespace) activat.

- Pe grupul de resurse unde Azure Synapse spațiul de lucru este situat, the *principalul serviciului* si *Azure AD utilizator cu permisiuni de administrator în Customer Insights* trebuie să fie atribuit cel puțin **Cititor**[permisiuni](/azure/role-based-access-control/role-assignments-portal).

- The *Azure AD utilizator cu permisiuni de administrator în Customer Insights* are **Colaborator de date Blob de stocare** permisiuni pe Azure Data Lake Storage Contul Gen2 în care se află datele și sunt legate la Azure Synapse spațiu de lucru. Aflați mai multe despre [utilizarea portalului Azure pentru a atribui un rol Azure pentru accesul la datele de blob și la coadă](/azure/storage/common/storage-auth-aad-rbac-portal) și [permisiuni de stocare pentru contribuitor date blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- The *[Azure Synapse identitatea administrată de spațiul de lucru](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* are **Colaborator de date Blob de stocare** permisiuni pe Azure Data Lake Storage Contul Gen2 în care se află datele și sunt legate la Azure Synapse spațiu de lucru. Aflați mai multe despre [utilizarea portalului Azure pentru a atribui un rol Azure pentru accesul la datele de blob și la coadă](/azure/storage/common/storage-auth-aad-rbac-portal) și [permisiuni de stocare pentru contribuitor date blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Pe Azure Synapse spaţiul de lucru, *principal de serviciu pentru Customer Insights* are **Administrator Synapse**[rolul atribuit](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-connection-to-azure-synapse"></a>Configurați conexiunea la Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Azure Synapse Analytics**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selectați sau căutați abonamentul în care doriți să utilizați datele Customer Insights. De îndată ce este selectat un abonament, puteți selecta și **Spațiul de lucru**, **Contul de stocare** și **containerul**.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)] Pentru a configura exportul cu o conexiune partajată, aveți nevoie de cel puțin **Colaborator** permisiunile din Customer Insights.

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În **Conexiune pentru export** câmp, alegeți o conexiune din Azure Synapse Analytics secțiune. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Dați un **Nume afișat** pentru exportul dvs. și un **Nume al bazei de date**. Exportul va crea un nou [Azure Synapse baza de date a lacului](/azure/synapse-analytics/database-designer/concepts-lake-database) în spațiul de lucru definit în conexiune.

1. Selectați la ce entități doriți să exportați Azure Synapse Analytics.
   > [!NOTE]
   > Surse de date bazate pe un [Dosar Common Data Model](connect-common-data-model.md) nu sunt acceptate.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Pentru a interoga datele care au fost exportate în Synapse Analytics, aveți nevoie **Cititor de date Blob de stocare** acces la stocarea de destinație pe spațiul de lucru al exporturilor.

## <a name="update-an-export"></a>Actualizați un export

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Editare** pe exportul pe care doriți să îl actualizați.

   - **Adăugați** sau **Eliminați** entități din selecție. Dacă entitățile sunt eliminate din selecție, ele nu sunt șterse și din baza de date Synapse Analytics. Cu toate acestea, reîmprospătările de date viitoare nu vor actualiza entitățile eliminate din baza de date respectivă.

   - **Modificarea numelui bazei de date** creează o nouă bază de date Synapse Analytics. Baza de date cu numele ce a fost configurat înainte nu va primi actualizări în reîmprospătări viitoare.

[!INCLUDE [footer-include](includes/footer-banner.md)]
