---
title: Îmbogățiți profilurile clienților cu tehnologiile HERE (previzualizare)
description: Informații generale despre îmbogățirea terță parte HERE Technologies.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237873"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Îmbogățiți profilurile clienților cu tehnologiile HERE (previzualizare)

HERE Technologies este o companie de platformă de localizare care oferă date și servicii centrate pe locație. Serviciile de îmbogățire a datelor HERE Technologies îmbunătățesc precizia informațiilor despre locație despre clienții dvs. Oferă normalizarea adreselor, extragerea latitudinii și longitudinii și multe altele.

## <a name="prerequisites"></a>Cerințe preliminare

- Un abonament activ HERE Technologies. Pentru a obține un abonament, [înscrie-te aici](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) sau [contactați AICI Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direct. [Aflați mai multe despre îmbogățirea locației HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- A AICI [conexiune](connections.md) este [configurat](#configure-the-connection-for-here-technologies) de către un administrator.

## <a name="configure-the-connection-for-here-technologies"></a>Configurați conexiunea pentru HERE Technologies

Trebuie să fii un [administrator](permissions.md#admin) în Customer Insights și aveți o cheie activă HERE Technologies API.

1. Selectați **Adăugați conexiune** atunci când configurați o îmbogățire sau accesați **Admin** > **Conexiuni** și selectați **Înființat** pe tigla HERE Technologies.

1. Introduceți un nume pentru conexiune și o cheie validă HERE Technologies API.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Verifica** pentru a valida configurația și apoi selectați **Salvați**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Pagina de configurare a conexiunii HERE Technologies.":::

## <a name="configure-the-enrichment"></a>Configurați îmbogățirea

1. Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**.

1. Selectați **Îmbogățiți-mi datele** pe **Locație** de AICI țiglă Tehnologii.

   :::image type="content" source="media/HERE-tile.png" alt-text="Dală HERE Technologies.":::

1. Examinați prezentarea generală și apoi selectați **Următorul**.

1. Selectați conexiunea. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Selectați **Următorul**.

1. Selectează **Set de date despre client** și alegeți profilul sau segmentul pe care doriți să îl îmbogățiți cu date de la HERE Technologies. The *Client* entitate îmbogățește toate profilurile dvs. de clienți, în timp ce un segment îmbogățește numai profilurile de clienți conținute în acel segment.

1. Definiți ce tip de câmpuri din profilurile dvs. unificate să utilizați pentru potrivire: adresa principală și/sau secundară. Puteți specifica o mapare a câmpului pentru ambele adrese și puteți îmbogăți profilurile pentru ambele adrese separat. De exemplu, pentru o adresă de domiciliu și o adresă de afaceri. Selectați **Următorul**.

1. Hartați câmpurile dvs. la datele de la HERE Technologies. Câmpurile **Stradă 1** și **Cod poștal** sunt obligatorii pentru adresa primară și/sau secundară selectată. Pentru o precizie mai mare a potrivirii, adăugați mai multe câmpuri.

1. Selectați **Următorul** pentru a completa maparea câmpului.

1. Furnizeaza un **Nume** pentru îmbogățire și pentru **Numele entității de ieșire**.

1. Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.

1. Selectați **Alerga** pentru a începe procesul de îmbogățire sau aproape pentru a reveni la **Îmbogățiri** pagină.

## <a name="view-enrichment-results"></a>Vedeți rezultatele îmbogățirii

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

The **Număr de clienți îmbogățiți pe domeniu** oferă o detaliere a acoperirii fiecărui câmp îmbogățit.

## <a name="next-steps"></a>Pașii următori

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
