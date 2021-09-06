---
title: Conector Power Apps
description: Conectarea cu Power Apps și Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: fc0af656cd5b436d9efd65b2a2c75dde9c9deb9dbcdd56ffc6a960f5878a631f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031810"
---
# <a name="microsoft-power-apps-connector-preview"></a>Conector Microsoft Power Apps (previzualizare)

Aduceți profilurile de clienți unificate în aplicațiile dvs. personalizate cu Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Conectare Power Apps și Dynamics 365 Customer Insights

Customer Insights este unul dintre numeroasele [surse de date disponibile în Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Consultați documentația Power Apps pentru a învăța cum să [adăugați o conexiune de date la o aplicație](/powerapps/maker/canvas-apps/add-data-connection). Vă recomandăm să treceți în revistă [Cum Power Apps utilizează delegarea pentru a gestiona seturi de date mari în aplicațiile proiectate pe pânză](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entităţi disponibile

După adăugarea Customer Insights ca o conexiune de date, puteți alege următoarele entități în Power Apps:

- Client: să utilizeze date din [profilul clientului unificat](customer-profiles.md).
- UnifiedActivity: pentru a afișa [cronologia de activitate](activities.md) pe aplicație.

## <a name="limitations"></a>Limitări

### <a name="retrievable-entities"></a>Entități recuperabile

Puteți regăsi numai entitățile **Client**, **UnifiedActivity** și **Segmente** i prin intermediul conectorului Power Apps. Alte entități sunt afișate deoarece conectorul de bază le acceptă prin declanșatoare în Power Automate.  

### <a name="delegation"></a>Delegare

Delegarea funcționează pentru entitatea Client și entitatea UnifiedActivity. 

- Delegare pentru entitatea **Client**: pentru a utiliza delegarea pentru această entitate, câmpurile trebuie să fie indexate în [Index de căutare și filtrare](search-filter-index.md).  

- Delegația pentru **UnifiedActivity**: Delegația pentru această entitate funcționează numai pentru câmpuri **ActivityId** și **CustomerId**.  

- Pentru mai multe informații despre delegare, consultați [Funcții și operațiuni Power Apps delegabile](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Exemplu de control al galeriei

De exemplu, adăugați profiluri de clienți la un [control al galeriei](/powerapps/maker/canvas-apps/add-gallery).

1. Adăugați un control **Galerie** unei aplicații pe care o construiți.

> [!div class="mx-imgBorder"]
> ![Adăugați un element galerie.](media/connector-powerapps9.png "Adăugați un element galerie")

1. Selectați **Client** ca sursă de date pentru elemente.

    > [!div class="mx-imgBorder"]
    > ![Selectați o sursă de date.](media/choose-datasource-powerapps.png "Selectați o sursă de date")

1. Puteți schimba panoul de date din dreapta pentru a selecta ce câmp pentru entitatea Client să se afișeze în galerie.

1. Dacă doriți să afișați orice câmp de la clientul selectat în galerie, completați proprietatea Text a unei etichete: **{Name_of_the_gallery}.Selectate.{property_name}**

    Exemplu: Gallery1.Selected.address1_city

1. Pentru a afișa cronologia unificată pentru un client, adăugați un element de galerie și adăugați proprietatea Elemente: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Exemplu: Filtru ('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]