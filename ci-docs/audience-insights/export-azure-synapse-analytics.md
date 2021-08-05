---
title: Exportați datele Customer Insights către Azure Synapse Analytics
description: Aflați cum să configurați conexiunea și să exportați la Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7ee57aa9e86ebf9bd1989d88750642f0b01bd4bf
ms.sourcegitcommit: f18635c29bb25d9e424a3f5825dc2696278450cf
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/30/2021
ms.locfileid: "6327379"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exportați datele la Azure Synapse Analytics (versiune preliminară)

Azure Synapse este un serviciu de analize ce accelerează timpul de detaliere a depozitelor de date și a sistemelor de date mari. Puteți ingera și utiliza datele Customer Insights în [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Cerințe preliminare

Următoarele condiții preliminare trebuie îndeplinite pentru a configura conexiunea de la Customer Insights la Azure Synapse.

> [!NOTE]
> Asigurați-vă să setați toate **atribuirile de roluri** după cum este descris.  

## <a name="prerequisites-in-customer-insights"></a>Cerințe preliminare în Customer Insights

* Aveți un rol **Administrator** în Detalii despre public. Aflați mai multe despre [setarea permisiunilor utilizatorilor în Detalii privind publicul](permissions.md#assign-roles-and-permissions)

În Azure: 

- Un abonament Azure activ.

- Dacă utilizați un nou cont Azure Data Lake Storage Gen2, *director principal de serviciu pentru detalii despre public* are nevoie de permisiune de **Contributor stocare data blob**. Aflați mai multe despre [conectarea la un cont Azure Data Lake Storage Gen2 cu contul principal de serviciu Azure pentru detalii despre public](connect-service-principal.md). Data Lake Storage Gen2 **trebuie să aibă** [spațiul de nume ierarhic](/azure/storage/blobs/data-lake-storage-namespace) activat.

- Pe grupul de resurse, unde se află spațiul de lucru Azure Synapse, *director principal de serviciu* și *utilizator pentru detalii despre public* trebuie să le fie atribuite cel puțin permisiuni **Cititor**. Pentru mai multe informații, consultați [Atribuirea de roluri Azure utilizând portalul Azure](/azure/role-based-access-control/role-assignments-portal).

- Pentru *utilizator* este nevoie de permisiuni **Contribuitor stocare date blob** pentru contul Azure Data Lake Storage Gen2 unde sunt amplasate datele și conectate la spațiul de lucru Azure Synapse. Aflați mai multe despre [utilizarea portalului Azure pentru a atribui un rol Azure pentru accesul la datele de blob și la coadă](/azure/storage/common/storage-auth-aad-rbac-portal) și [permisiuni de stocare pentru contribuitor date blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Pentru utilizator *[identitatea gestionată de spațiu de lucru Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* este nevoie de permisiuni **Contribuitor stocare date blob** pentru contul Azure Data Lake Storage Gen2 unde sunt amplasate datele și conectate la spațiul de lucru Azure Synapse. Aflați mai multe despre [utilizarea portalului Azure pentru a atribui un rol Azure pentru accesul la datele de blob și la coadă](/azure/storage/common/storage-auth-aad-rbac-portal) și [permisiuni de stocare pentru contribuitor date blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Pentru spațiul de lucru Azure Synapse,*directorul principal de serviciu pentru detalii despre public* este nevoie să aibă atribuit rolul **Administrator Synapse**. Pentru mai multe informații, consultați [Cum să configurați controlul accesului pentru spațiul de lucru Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Configurați conexiunea și exportul la Azure Synapse

### <a name="configure-a-connection"></a>Configurați o conexiune

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugare conexiune** și alegeți **Azure Synapse Analytics** sau selectați **Configurare** pe dala **Azure Synapse Analytics** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul Nume afișat. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selectați sau căutați abonamentul în care doriți să utilizați datele Customer Insights. De îndată ce este selectat un abonament, puteți selecta și **Spațiul de lucru**, **Contul de stocare** și **containerul**.

1. Selectați **Salvare** pentru a salva conexiunea.

### <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [permisiunile necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea **Azure Synapse Analytics**. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile [conexiuni](connections.md) de acest tip.

1. Dați un **Nume afișat** pentru exportul dvs. și un **Nume al bazei de date**.

1. Selectați ce entități doriți să exportați la Azure Synapse Analytics.
   > [!NOTE]
   > Surse de date bazate pe un [Dosar Common Data Model](connect-common-data-model.md) nu sunt acceptate.

2. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).

### <a name="update-an-export"></a>Actualizați un export

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Editare** pe exportul pe care doriți să îl actualizați.

   - **Adăugați** sau **Eliminați** entități din selecție. Dacă entitățile sunt eliminate din selecție, ele nu sunt șterse și din baza de date Synapse Analytics. Cu toate acestea, reîmprospătările de date viitoare nu vor actualiza entitățile eliminate din baza de date respectivă.

   - **Modificarea numelui bazei de date** creează o nouă bază de date Synapse Analytics. Baza de date cu numele ce a fost configurat înainte nu va primi actualizări în reîmprospătări viitoare.
