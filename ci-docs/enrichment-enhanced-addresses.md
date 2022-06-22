---
title: Îmbogățirea adresei (conține videoclip)
description: Îmbogățiți și normalizați informațiile de adresă ale profilurilor clienților cu modelele Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: f6279b9bb721d99d66f73e8dc839a92f1ad90140
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953826"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Îmbogățirea profilurilor clienților cu adrese îmbunătățite

Adresele din datele dvs. pot fi nestructurate, incomplete sau incorecte. Utilizați modelele Microsoft pentru a vă normaliza și îmbogăți adresele în [Formatul Common Data Model](/common-data-model/schema/core/applicationcommon/address) pentru o mai bună acuratețe și informații.

Poti de asemenea [îmbogăți adresele pe surse de date](data-sources-enrichment.md) pentru a îmbunătăți acuratețea potrivirii în procesul de unificare a datelor. 

## <a name="how-we-enhance-addresses"></a>Cum îmbunătățim adresele

Modelul nostru trece printr-un proces în doi pași pentru a îmbunătăți o adresă. În primul rând, analizează adresa pentru a identifica componentele sale și le plasează într-un format structurat. Apoi, folosim AI pentru a corecta, completa și standardiza valorile din adresă.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Exemplu

Informațiile despre adresă pot fi într-un format non-standard și să conțină erori de ortografie. Modelul poate rezolva aceste probleme și poate crea adrese consistente în profilurile unificate ale clienților.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Limitări

Adresele îmbunătățite funcționează numai cu valorile care există deja în datele de adresă ingerate. Modelul nu:

1. Verificî dacă adresa este o adresă validă.
2. Verifică dacă oricare dintre valori, cum ar fi codurile poștale sau numele străzilor, sunt valide.
3. Schimbă valorile pe care nu le recunoaște.

Modelul utilizează tehnici bazate pe învățarea automată pentru a îmbunătăți adresele. Ca și în cazul oricărui model bazat pe învățarea automată, acuratețea de 100% nu este garantată.

## <a name="supported-countries-or-regions"></a>Țări sau regiuni sprijinite

În prezent, sprijinim adresele îmbogățitoare din aceste țări sau regiuni:

- Australia
- Canada
- Franța
- Germania
- Italia
- Japonia
- Regatul Unit
- Statele Unite ale Americii

## <a name="configure-the-enrichment"></a>Configurați îmbogățirea

1. Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**.

1. Selectați **Îmbogățire date** pe dala **Adrese îmbunătățite**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Captură de ecran a plăcii Adrese îmbunătățite.":::

1. Examinați prezentarea generală și apoi selectați **Următorul**.

1. Selectează **Set de date despre client** și alegeți profilul sau segmentul pe care doriți să îl îmbogățiți. The *Client* entitate îmbogățește toate profilurile dvs. de clienți, în timp ce un segment îmbogățește numai profilurile de clienți conținute în acel segment.

1. Selectați formatatul adreselor în setul de date al dvs. Alegeți **Adresă cu un singur atribut** dacă adresele din datele dvs. utilizează un singur câmp. Alegeți **Adresă cu atribute multiple** dacă adresele din datele dvs. utilizează mai mult de un singur câmp de date.

1. Selectați **Următorul** și mapați câmpurile de adresă de la entitatea dvs. unificată client.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Pagina îmbunătățită de mapare a câmpului de adrese.":::

   > [!NOTE]
   > Țara/regiunea este obligatorie atât în adresele cu un singur atribut, cât și cu mai multe atribute. Adresele care nu conțin valori valabile sau acceptate de țară/regiune nu vor fi îmbogățite.

1. Selectați **Următorul** pentru a completa maparea câmpului.

1. Furnizeaza un **Nume** pentru îmbogățire și pentru **Entitate de ieșire**.

1. Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.

## <a name="enrichment-results"></a>Rezultate de îmbogățire

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

The **Număr de clienți îmbogățiți pe domeniu** oferă o detaliere a acoperirii fiecărui câmp îmbogățit.

### <a name="overview-card"></a>Card de prezentare generală

The **Clienții modifică imaginea de ansamblu** cardul prezintă detalii despre acoperirea îmbogățirii:

- **Adresele procesate și schimbate** : Numărul de profiluri de clienți cu adrese care au fost îmbogățite cu succes.
- **Adresele procesate și neschimbate** : numărul de profiluri de clienți cu adrese care au fost recunoscute, dar care nu au fost modificate. Se întâmplă de obicei atunci când datele de intrare sunt valide și nu pot fi îmbunătățite prin îmbogățire.
- **Adresele nu au fost procesate și nu au fost modificate** : numărul de profiluri cu adrese care nu au fost recunoscute. De obicei, pentru date de intrare care nu sunt valide sau nu sunt acceptate de îmbogățire.

## <a name="next-steps"></a>Pașii următori

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]