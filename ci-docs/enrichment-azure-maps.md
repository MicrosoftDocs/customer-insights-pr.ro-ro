---
title: Îmbogățiți profilurile clienților cu date despre locație din Azure Maps (previzualizare)
description: Informații generale despre îmbogățire de primă parte Azure Maps.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f14b4fc20a9a1d8842f42f9e0e656b3d8dcddcf4
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238057"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Îmbogățiți profilurile clienților cu date despre locație din Azure Maps (previzualizare)

Azure Maps oferă date și servicii centrate pe locație pentru a oferi experiențe bazate pe date geospațiale cu inteligență de locație încorporată. Serviciile de îmbogățire a datelor Azure Maps îmbunătățesc precizia informațiilor despre locație despre clienții dvs. Aduce capabilități precum normalizarea adreselor și extragerea latitudinii și longitudinii la Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Cerințe preliminare

- Un abonament activ Azure Maps. Pentru a obține un abonament, [înscrieți-vă sau obțineți o încercare gratuită](https://azure.microsoft.com/services/azure-maps/).

- Un Azure Maps [conexiune](connections.md) este [configurat](#configure-the-connection-for-azure-maps) de către un administrator.

## <a name="configure-the-connection-for-azure-maps"></a>Configurați conexiunea pentru Azure Maps

Trebuie să fii un [administrator](permissions.md#admin) în Customer Insights și aveți o cheie API Azure Maps activă.

1. Selectați **Adăugați conexiune** când configurați o îmbogățire sau accesați **Administrator** > **Conexiuni** și selectați **Configurare** pe dala Azure Maps.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Pagina de configurare pentru conexiune Azure Maps.":::

1. Introduceți un nume pentru conexiune și o cheie API Azure Maps validă.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Verifica** pentru a valida configurația și apoi selectați **Salvați**.

## <a name="configure-the-enrichment"></a>Configurați îmbogățirea

1. Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**.

1. Selectați **Îmbogățiți-mi datele** pe **Locație** din Microsoft Azure Dală Hărți.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Dală Azure Maps.":::

1. Examinați prezentarea generală și apoi selectați **Următorul**.

1. Selectați conexiunea. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Selectați **Următorul**.

1. Selectează **Set de date despre client** și alegeți profilul sau segmentul pe care doriți să îl îmbogățiți cu date de la Microsoft. The *Client* entitate îmbogățește toate profilurile dvs. de clienți, în timp ce un segment îmbogățește numai profilurile de clienți conținute în acel segment.

1. Definiți ce tip de câmpuri din profilurile dvs. unificate să utilizați pentru potrivire: adresa principală și/sau secundară. Puteți specifica o mapare a câmpului pentru ambele adrese și puteți îmbogăți profilurile pentru ambele adrese separat. De exemplu, pentru o adresă de domiciliu și o adresă de afaceri. Selectați **Următorul**.

1. Hartați câmpurile cu datele de locație din Azure Maps. Câmpurile **Stradă 1** și **Cod poștal** sunt obligatorii pentru adresa primară și/sau secundară selectată. Pentru o mai mare precizie a potrivirii, adăugați mai multe câmpuri.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Maparea atributelor Azure Maps.":::

1. Selectați **Următorul** pentru a completa maparea câmpului.

1. Revizuire **Setari avansate** care oferă flexibilitate maximă pentru a gestiona cazuri de utilizare avansate. Cu toate acestea, următoarele valori implicite de obicei nu trebuie modificate.

   - **Tipuri de adrese** : Cea mai bună potrivire a adresei revine chiar dacă este incompletă. Pentru a obține numai adrese complete&mdash;de exemplu, adrese care includ numărul casei&mdash;debifați toate casetele de selectare, cu excepția **Adrese punct**.
   - **Limba** : Adresele revin în limba în funcție de regiunea adresei. Pentru a aplica o limbă de adresă standardizată, selectați limba din meniul derulant. De exemplu, selectarea **Engleză** se intoarce **Copenhaga, Danemarca** în loc de **København, Danemarca**.
   - **Numărul maxim de rezultate** : Numărul de rezultate pe adresă.

1. Selectați **Următorul**.

1. Furnizeaza un **Nume** pentru îmbogățire și pentru **Numele entității de ieșire**.

1. Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.

1. Selectați **Alerga** pentru a începe procesul de îmbogățire sau aproape pentru a reveni la **Îmbogățiri** pagină.

## <a name="view-enrichment-results"></a>Vedeți rezultatele îmbogățirii

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

The **Număr de clienți îmbogățiți pe domeniu** oferă o detaliere a acoperirii fiecărui câmp îmbogățit.

## <a name="next-steps"></a>Pașii următori

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
