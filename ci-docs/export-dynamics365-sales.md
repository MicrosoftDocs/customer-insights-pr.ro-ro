---
title: Exportați segmente în Dynamics 365 Sales (previzualizare)
description: Aflați cum să configurați conexiunea și să exportați la Dynamics 365 Sales.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195996"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Exportați segmente în Dynamics 365 Sales (previzualizare)

Utilizați datele clienților pentru a crea liste de marketing, a urmări fluxuri de lucru și a trimite promoții cu Dynamics 365 Sales.

## <a name="prerequisites"></a>Cerințe preliminare

Înregistrările de contact trebuie să fie prezente în Dynamics 365 Sales înainte de a putea exporta un segment din Customer Insights în Sales. Citiți mai multe despre cum să ingerați contacte de la [Dynamics 365 Sales folosind Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Exportarea segmentelor din Customer Insights la Sales nu va crea noi înregistrări de contact în instanțele de vânzări. Înregistrările de contact de la vânzări trebuie să fie introduse în Customer Insights și folosite ca sursă de date. De asemenea, trebuie să fie incluse în entitatea Client unificată pentru a identifica ID-urile clienților cu ID-urile de contact înainte ca segmentele să poată fi exportate.

## <a name="known-limitations"></a>Limitări cunoscute

Exporturile către Dynamics 365 Sales sunt limitate la 100.000 pe segment, ceea ce poate dura până la 3 ore.

## <a name="set-up-connection-to-sales"></a>Configurați conexiunea la vânzări

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Dynamics 365 Sales**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți adresa URL de vânzări a organizației dvs. în câmpul **Adresa serverului**.

1. În secțiunea **Cont administrator server**, selectați **Conectare** și alegeți un cont Dynamics 365 Sales.

1. Mapați un câmp ID client la ID-ul de contact Dynamics 365.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Dynamics 365 Sales. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. Selectați câmpul Contact ID din entitatea Client care se potrivește cu Dynamics 365 Contact ID.

1. Selectați segmentele pe care doriți să le exportați.

1. Selectați **Salvare**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
