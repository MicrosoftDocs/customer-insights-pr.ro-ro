---
title: Conectați un Azure Synapse sursă de date (previzualizare)
description: Utilizați o bază de date în Azure Synapse ca un sursă de date în Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 54247fbcdc27f6ed8314e0755164083eb461aa64
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206922"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Conectați un Azure Synapse Analytics sursă de date (previzualizare)

Azure Synapse Analytics este un serviciu de analiză a întreprinderii care accelerează timpul de a obține informații în depozitele de date și sistemele de date mari. Azure Synapse Analytics reunește cele mai bune tehnologii SQL utilizate în depozitarea datelor de întreprindere, tehnologiile Spark utilizate pentru big data, Data Explorer pentru analize de jurnal și serii de timp, Pipelines pentru integrarea datelor și ETL/ELT și integrare profundă cu alte servicii Azure, cum ar fi Power BI,Cosmos DB și AzureML.

Pentru mai multe informații, vezi [Azure Synapse Prezentare generală](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Cerințe preliminare

> [!IMPORTANT]
> Asigurați-vă să setați toate **atribuirile de roluri** după cum este descris.  

**În Customer Insights**:

* Ai un **Administrator** rol în Customer Insights. Află mai multe despre [permisiunile utilizatorului în Customer Insights](permissions.md#assign-roles-and-permissions).

**În Azure**:

- Un abonament Azure activ.

- Dacă utilizați un nou Azure Data Lake Storage Contul Gen2, the *principal de serviciu pentru Customer Insights* are nevoie **Colaborator de date Blob de stocare** permisiuni. Află mai multe despre [conectarea la o Azure Data Lake Storage cu un principal de servicii pentru Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **trebuie să aibă** [spațiul de nume ierarhic](/azure/storage/blobs/data-lake-storage-namespace) activat.

- Pe grupul de resurse Azure Synapse spațiul de lucru este situat, the *principalul serviciului* si *utilizator pentru Customer Insights* trebuie să fie atribuit cel puțin **Cititor** permisiuni. Pentru mai multe informații, consultați [Atribuirea de roluri Azure utilizând portalul Azure](/azure/role-based-access-control/role-assignments-portal).

- Pentru *utilizator* este nevoie de permisiuni **Contribuitor stocare date blob** pentru contul Azure Data Lake Storage Gen2 unde sunt amplasate datele și conectate la spațiul de lucru Azure Synapse. Aflați mai multe despre [utilizarea portalului Azure pentru a atribui un rol Azure pentru accesul la datele de blob și la coadă](/azure/storage/common/storage-auth-aad-rbac-portal) și [permisiuni de stocare pentru contribuitor date blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Pentru utilizator *[identitatea gestionată de spațiu de lucru Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* este nevoie de permisiuni **Contribuitor stocare date blob** pentru contul Azure Data Lake Storage Gen2 unde sunt amplasate datele și conectate la spațiul de lucru Azure Synapse. Aflați mai multe despre [utilizarea portalului Azure pentru a atribui un rol Azure pentru accesul la datele de blob și la coadă](/azure/storage/common/storage-auth-aad-rbac-portal) și [permisiuni de stocare pentru contribuitor date blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Pe Azure Synapse spaţiul de lucru, *principal de serviciu pentru Customer Insights* are nevoie **Administrator Synapse** rolul atribuit. Pentru mai multe informații, consultați [Cum să configurați controlul accesului pentru spațiul de lucru Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Conectați-vă la baza de date a lacului de date în Azure Synapse Analytics

1. Accesați **Date** > **Surse de date**.

1. Selectați **Adăugați sursa de date**.

1. Alege **Azure Synapse Analytics (Previzualizare)** metodă.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Casetă de dialog pentru a vă conecta la datele Synapse Analytics":::
  
1. Introduceți a **Nume** pentru sursă de date și opțional **Descriere**.

1. Alegeți un [conexiune disponibilă](connections.md) la Azure Synapse Analytics sau creați unul nou.

1. Alege un **Bază de date** din spațiul de lucru conectat în cel selectat Azure Synapse Analytics conexiune și selectați **Următorul**. În prezent, acceptăm doar tipul de bază de date *Baza de date lac*.

1. Selectați entitățile de asimilat din baza de date conectată și selectați **Următorul**.

1. Opțional, alegeți entitățile de date pentru a permite profilarea datelor.

1. Selectați **Salvați** pentru a aplica selecția dvs. și pentru a începe asimilarea datelor din sursă de date nou creat, legat de tabelele bazei de date Lake în Azure Synapse Analytics. The **Surse de date** se deschide pagina afișând noul sursă de date în **Înviorător** stare.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Încărcarea datelor poate dura timp. După o reîmprospătare cu succes, datele ingerate pot fi revizuite din [**Entități**](entities.md) pagină.

[!INCLUDE [footer-include](includes/footer-banner.md)]
