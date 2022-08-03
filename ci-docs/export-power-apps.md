---
title: Conector Power Apps (previzualizare)
description: Conectarea cu Power Apps și Power Automate.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196915"
---
# <a name="power-apps-connector-preview"></a>Conector Power Apps (previzualizare)

Aduceți profilurile de clienți unificate în aplicațiile dvs. personalizate cu Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Conectare Power Apps și Dynamics 365 Customer Insights

Customer Insights este unul dintre numeroasele [surse de date disponibile în Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Consultați documentația Power Apps pentru a învăța cum să [adăugați o conexiune de date la o aplicație](/powerapps/maker/canvas-apps/add-data-connection). Vă recomandăm să treceți în revistă [Cum Power Apps utilizează delegarea pentru a gestiona seturi de date mari în aplicațiile proiectate pe pânză](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entităţi disponibile

După ce adăugați Customer Insights ca conexiune de date, alegeți următoarele entități în Power Apps:

- **Client**: pentru a utiliza date din [profilul clientului unificat](customer-profiles.md).
- **UnifiedActivity**: pentru a afișa [cronologia activității](activities.md) în aplicație.
- **ContactProfile**: pentru a afișa contactele unui client. Această entitate este disponibilă numai în mediile Customer Insights pentru conturile de afaceri.

## <a name="limitations"></a>Limitări

### <a name="retrievable-entities"></a>Entități recuperabile

Puteți prelua numai entitățile **Client**, **UnifiedActivity**, **Segmente**, și **ContactProfile** prin intermediul conectorului Power Apps. ContactProfile este disponibil numai în mediile Customer Insights pentru conturile de afaceri. Alte entități sunt afișate deoarece conectorul de bază le acceptă prin declanșatoare în Power Automate.

Puteți efectua maximum 100 de apeluri pe 60 de secunde. Puteți apela punctul final API de mai multe ori utilizând parametrul $skip. [Aflați mai multe despre parametrul $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegare

Delegarea funcționează pentru entitatea **Client** și entitatea **UnifiedActivity**.

- Delegatie pentru **Client** entitate: Pentru a utiliza delegarea pentru această entitate, câmpurile trebuie să fie indexate în [index de căutare și filtrare](search-filter-index.md).  
- Delegația pentru **UnifiedActivity**: Delegația pentru această entitate funcționează numai pentru câmpuri **ActivityId** și **CustomerId**.  
- Delegația pentru **ContactProfile**: Delegația pentru această entitate funcționează numai pentru câmpuri **ContactId** și **CustomerId**. ContactProfile este disponibil numai în mediile Customer Insights pentru conturile de afaceri.

Pentru mai multe informații despre delegare, accesați [funcții Power Apps și operații delegabile](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="example-gallery-control"></a>Exemplu de control al galeriei

Opțional, adăugați profiluri de clienți la a [controlul galeriei](/powerapps/maker/canvas-apps/add-gallery).

1. Adăugați un control **galerie** unei aplicații pe care o construiți.
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="Adăugați un element galerie.":::

1. Selectați **Client** ca sursă de date pentru elemente.

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="Selectați o sursă de date.":::

1. Schimbați panoul de date din dreapta pentru a selecta ce câmp pentru entitatea Client pentru a afișa în galerie.

1. Dacă doriți să afișați orice câmp de la clientul selectat în galerie, completați proprietatea **Text** a unei etichete utilizând **{Name_of_the_gallery}.Selectat.{property_name}**  
    - De exemplu: _Gallery1.Selected.address1_city_

1. Pentru a afișa cronologia unificată pentru un client, adăugați un element de galerie și adăugați proprietatea **Elemente** utilizând **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - De exemplu: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]
