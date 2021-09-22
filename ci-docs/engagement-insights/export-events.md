---
title: Exportați evenimente rafinate
description: Cum se pot exporta evenimente rafinate și evenimente de bază.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032400"
---
# <a name="export-events"></a>Exportați evenimente

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un eveniment reprezintă comportamentul utilizatorului. Înregistrează atunci când un utilizator vizualizează o pagină (vizualizare eveniment) sau interacționează cu conținutul (eveniment de acțiune). Când puteți decide ce proprietăți ale datelor pe care doriți să le afișați într-un raport, această vizualizare virtuală a datelor se numește un *eveniment rafinat*. 

- Puteți exporta evenimente și evenimente rafinate într-un spațiu de stocare extern. 
- Exporturile sunt un flux de date înainte. Nu puteți recompleta fluxul. 
- Exporturile au scheme fixe. Dacă adăugați proprietăți particularizate la un eveniment, acestea nu vor fi incluse. Va trebui să creați un nou export.

## <a name="prerequisites"></a>Cerințe preliminare

Înainte de a configura un export, trebuie să aveți acces și un abonament activ la portalul Azure. Veți avea nevoie de informațiile despre contul de stocare în timpul procesului de export. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Creați conturi Azure Data Lake Storage Gen 2

1. Conectați-vă la portalul Azure și [creați un cont de stocare nou](/azure/storage/common/storage-account-create). 

1. Asigurați-vă că activați **Spațiu de nume ierarhic** pe fila **Avansat**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Activați Spațiu de nume ierarhic pe fila Avansat.":::

1. Odată ce a fost implementat, accesați contul de stocare nou creat. În panoul de navigare, selectați **Setări** > **Cheie de acces**. 

1. Copiați **Nume de cont** și **Cheie** pentru a le utiliza la crearea unui nou export.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Accesați cheile dintr-un cont de stocare.":::

## <a name="export-events"></a>Export evenimente

Există două moduri de a exporta evenimente. 
- Accesați **Date** > **Exporturi** și selectați **Export nou**.
- Accesați **Date** > **Evenimente**, selectați **Mai mult [...]** lângă evenimentul pe care doriți să-l exportați și selectați **Export** din meniul derulant. 

Sunteți ghidat prin pașii pentru a crea un export:

1. Furnizați un **Nume de export**.

1. În lista verticală **Selectarea evenimentelor**, alegeți evenimentele de bază și evenimentele rafinate pe care să le includeți în export. 

1. Sub **Structura fișierului**, selectați cadența pentru a crea fișiere noi în memoria de destinație. Evenimentele sunt exportate continuu pe măsură ce sosesc.

1. Selectați formatul pentru exportul dvs. Puteți alege între format **Common Data Model**, **CSV** și **JSON**. Pentru a utiliza exportul cu alte aplicații Dynamics 365, vă recomandăm să utilizați formatul Common Data Model.

1. La pasul **Alegeți destinația**, specificați locație Azure Data Lake Storage Gen 2.
    1. **Numele contului ADLS Gen 2** este numele contului de stocare în care doriți să salvați exportul. 
    1. **Calea folderului** definește unde trebuie stocat exportul în sistemul de fișiere și structura directorului contului de stocare.
    1. **Cheie partajată** este disponibil de pe portalul Azure pentru contul de stocare.

1. Revizuiți și confirmați selecțiile.

## <a name="view-and-manage-exports"></a>Vizualizați și gestionați exporturi

După ce ați configurat un export, accesați **Date** > **Exporturi** pentru a-l vizualiza. Selectați **Mai mult [...]** pentru orice export existent pentru a-l edita și șterge.


[!INCLUDE[footer-include](../includes/footer-banner.md)]