---
title: Exportați datele Customer Insights către Dynamics 365 Sales
description: Aflați cum să configurați conexiunea și să exportați la Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 4c1b5eaa3568b5c73013024d2da7e65276142f72
ms.sourcegitcommit: d168a738a08adb8b4b2e410bdaa3716d7b63cc9b
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/17/2022
ms.locfileid: "8455877"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Utilizarea segmentelor în Dynamics 365 Sales (previzualizare)



Utilizați datele clienților pentru a crea liste de marketing, a urmări fluxuri de lucru și a trimite promoții cu Dynamics 365 Sales.

## <a name="known-limitations"></a>Limitări cunoscute

- Exporturile către Dynamics 365 Sales sunt limitate la 100.000 de membri pe segment.
- Exporturile de segmente către Dynamics 365 Sales pot dura până la 3 ore. 

## <a name="prerequisite-for-connection"></a>Cerință preliminară pentru conexiune

1. Înregistrările de contact trebuie să fie prezente în Dynamics 365 Sales înainte de a putea exporta un segment din Customer Insights în Sales. Citiți mai multe despre cum să ingerați contacte de la [Dynamics 365 Sales folosind Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Exportul de segmente din perspectivele publicului către Sales nu va crea noi înregistrări de contact în instanțele de Sales. Înregistrările de contact din Sales trebuie să fie ingerate în statistici ale publicului și utilizate ca sursă de date. De asemenea, trebuie să fie incluse în entitatea Client unificată pentru a identifica ID-urile clienților cu ID-urile de contact înainte ca segmentele să poată fi exportate.

## <a name="set-up-the-connection-to-sales"></a>Configurarea conexiunii la Sales

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Dynamics 365 Sales** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți adresa URL de vânzări a organizației dvs. în câmpul **Adresa serverului**.

1. În secțiunea **Cont administrator server**, selectați **Conectare** și alegeți un cont Dynamics 365 Sales.

1. Mapați un câmp ID client la ID-ul de contact Dynamics 365.

1. Selectați **Salvare** pentru a finaliza conexiunea. 

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Dynamics 365 Sales. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

1. Alegeți unul sau mai multe segmente.

1. Selectați **Salvare**

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
