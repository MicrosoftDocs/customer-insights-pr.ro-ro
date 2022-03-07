---
title: Ingerați date de la Azure Synapse Analytics
description: Utilizați o bază de date în Azure Synapse ca sursă de date în Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356052"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Conectați un Azure Synapse sursă de date (previzualizare)

Azure Synapse Analytics este un serviciu de analiză a întreprinderii care accelerează timpul de a obține informații în depozitele de date și sistemele de date mari. Azure Synapse Analytics reunește cele mai bune tehnologii SQL utilizate în depozitarea datelor de întreprindere, tehnologiile Spark utilizate pentru big data, Data Explorer pentru analize de jurnal și serii de timp, Pipelines pentru integrarea datelor și ETL/ELT și integrare profundă cu alte servicii Azure, cum ar fi Power BI,Cosmos DB și AzureML.

Pentru mai multe informații, vezi [Azure Synapse Prezentare generală](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Cerințe preliminare

Următoarele condiții preliminare trebuie îndeplinite pentru a configura conexiunea de la Customer Insights la Azure Synapse.

> [!IMPORTANT]
> Asigurați-vă să setați toate **atribuirile de roluri** după cum este descris.  

## <a name="prerequisites-in-customer-insights"></a>Cerințe preliminare în Customer Insights

* Ai un **Administrator** rol în Customer Insights. Aflați mai multe despre [permisiunile utilizatorilor în statistici privind publicul](permissions.md#assign-roles-and-permissions).

În Azure: 

- Un abonament Azure activ.

- Dacă utilizați un nou cont Azure Data Lake Storage Gen2, *director principal de serviciu pentru detalii despre public* are nevoie de permisiune de **Contributor stocare data blob**. Află mai multe despre [conectarea la o Azure Data Lake Storage cu un principal de servicii pentru informații despre public](connect-service-principal.md). Data Lake Storage Gen2 **trebuie să aibă** [spațiul de nume ierarhic](/azure/storage/blobs/data-lake-storage-namespace) activat.

- Pe grupul de resurse, unde se află spațiul de lucru Azure Synapse, *director principal de serviciu* și *utilizator pentru detalii despre public* trebuie să le fie atribuite cel puțin permisiuni **Cititor**. Pentru mai multe informații, consultați [Atribuirea de roluri Azure utilizând portalul Azure](/azure/role-based-access-control/role-assignments-portal).

- Pentru *utilizator* este nevoie de permisiuni **Contribuitor stocare date blob** pentru contul Azure Data Lake Storage Gen2 unde sunt amplasate datele și conectate la spațiul de lucru Azure Synapse. Aflați mai multe despre [utilizarea portalului Azure pentru a atribui un rol Azure pentru accesul la datele de blob și la coadă](/azure/storage/common/storage-auth-aad-rbac-portal) și [permisiuni de stocare pentru contribuitor date blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Pentru utilizator *[identitatea gestionată de spațiu de lucru Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* este nevoie de permisiuni **Contribuitor stocare date blob** pentru contul Azure Data Lake Storage Gen2 unde sunt amplasate datele și conectate la spațiul de lucru Azure Synapse. Aflați mai multe despre [utilizarea portalului Azure pentru a atribui un rol Azure pentru accesul la datele de blob și la coadă](/azure/storage/common/storage-auth-aad-rbac-portal) și [permisiuni de stocare pentru contribuitor date blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Pentru spațiul de lucru Azure Synapse,*directorul principal de serviciu pentru detalii despre public* este nevoie să aibă atribuit rolul **Administrator Synapse**. Pentru mai multe informații, consultați [Cum să configurați controlul accesului pentru spațiul de lucru Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Conectați-vă la bazele de date ale lacului de date în Azure Synapse Analytics

1. Accesați **Date** > **Surse de date**.

1. Selectați **Adăugați sursa de date**.

1. Alege **Azure Synapse Analytics (Previzualizare)** metodă.

1. Furnizați un **Nume** pentru sursa de date și selectați **Următorul** pentru a crea sursă de date. 

1. Alegeți un [conexiune disponibilă](connections.md) la Azure Synapse Analytics sau creați unul nou.

1. Alege un **Baza de date Lake** din spațiul de lucru conectat în cel selectat Azure Synapse Analytics conexiune și selectați **Următorul**.

1. Selectați entitățile de asimilat din baza de date conectată. 

1. Opțional, alegeți entitățile de date pentru a permite profilarea datelor. 

1. Selectați **salva** pentru a aplica selecția dvs. și pentru a începe asimilarea datelor din sursă de date nou creat, legat de tabelele bazei de date Lake în Azure Synapse Analytics.
