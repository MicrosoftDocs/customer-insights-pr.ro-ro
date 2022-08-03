---
title: Exportați segmente în Dynamics 365 Marketing (previzualizare)
description: Aflați cum să configurați conexiunea și să exportați la Dynamics 365 Marketing.
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
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196639"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Exportați segmente în Dynamics 365 Marketing (previzualizare)

Utilizare [segmente](segments.md) pentru a genera campanii și a contacta anumite grupuri de clienți cu care [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Dacă utilizați noile capabilități ale Dynamics 365 Marketing pentru orchestrarea călătoria clientului în timp real într-o organizație Dataverse, nu este nevoie să creați un export standard către Dynamics 365 Marketing. Persoanele de contact și segmentele din Customer Insights sunt disponibile direct în Dynamics 365 Marketing după conectarea Marketing și Customer Insights. Înainte de a șterge exporturile existente, consultați documentația pe [cum să conectați Customer Insights și Dynamics 365 Marketing călătoria clientului orchestrație](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Cerințe preliminare

Înregistrările de contact trebuie să fie prezente în Dynamics 365 Marketing înainte de a putea exporta un segment din Customer Insights în Marketing. Citiți mai multe despre cum să efectuați ingestia persoanelor de contact în [Dynamics 365 Marketing folosind Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> Exportarea segmentelor din Customer Insights în Marketing nu va crea noi înregistrări de contact în instanțele de Marketing. Înregistrările de contact de la Marketing trebuie să fie ingerate în Customer Insights și utilizate ca sursă de date. De asemenea, trebuie să fie incluse în entitatea Client unificată pentru a identifica ID-urile clienților cu ID-urile de contact înainte ca segmentele să poată fi exportate.

## <a name="set-up-connection-to-marketing"></a>Configurarea conexiunii la Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Dynamics 365 Marketing**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți adresa URL de marketing a organizației dvs. în câmpul **Adresa serverului**.

1. În secțiunea **Cont administrator server**, selectați **Conectare** și alegeți un cont Dynamics 365 Marketing.

1. Mapați câmpul Contact ID din entitatea Client la ID-ul de contact Dynamics 365.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Dynamics 365 Marketing. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. Selectați câmpul Contact ID din entitatea Client care se potrivește cu Dynamics 365 Contact ID.

1. Selectați segmentele pe care doriți să le exportați.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
