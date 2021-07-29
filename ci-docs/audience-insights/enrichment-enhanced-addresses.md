---
title: Îmbogățirea îmbunătățirii adreselor
description: Îmbogățiți și normalizați informațiile de adresă ale profilurilor clienților cu modelele Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305447"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Îmbogățirea profilurilor clienților cu adrese îmbunătățite

Adresele din datele dvs. pot fi nestructurate, incomplete sau incorecte. Utilizați modelele Microsoft pentru a vă normaliza și îmbogăți adresele în [Formatul Common Data Model](/common-data-model/schema/core/applicationcommon/address) pentru o mai bună acuratețe și informații.

## <a name="how-we-enhance-addresses"></a>Cum îmbunătățim adresele

Modelul nostru trece printr-un proces în doi pași pentru a îmbunătăți o adresă. În primul rând, analizează adresa pentru a identifica componentele sale și le plasează într-un format structurat. Apoi, folosim AI pentru a corecta, completa și standardiza valorile din adresă.

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

Modelul utilizează tehnici bazate pe învățarea automată pentru a îmbunătăți adresele. În timp ce aplicăm un prag ridicat de încredere atunci când modelul modifică o valoare de intrare, la fel ca în cazul oricărui model bazat pe învățarea automată, precizia de 100% nu este garantată.

## <a name="supported-countries-or-regions"></a>Țări sau regiuni sprijinite

În prezent, sprijinim adresele îmbogățitoare din aceste țări sau regiuni: 

- Australia
- Canada
- Regatul Unit
- Statele Unite ale Americii

Adresele trebuie să conțină o valoare a țării/regiunii. Nu procesăm adrese pentru țări sau regiuni care nu sunt acceptate și adrese care nu au furnizat nicio țară sau regiune.

## <a name="configure-the-enrichment"></a>Configurați îmbogățirea

1. Accesați **Date** > **Îmbogățire**.

1. Selectați **Îmbogățire date** pe dala **Adrese îmbunătățite**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Captură de ecran a plăcii Adrese îmbunătățite.":::

1. Selectați **Set de date client** și alegeți entitatea care conține adresele pe care doriți să le îmbogățiți. Puteți selecta entitatea *Client* pentru a îmbogăți adrese în toate profilurile dvs. de clienți sau selectați o entitate de segment pentru a îmbogăți adresele numai în profilurile de clienți din acel segment.

1. Selectați formatatul adreselor în setul de date al dvs. Alegeți **Adresă cu un singur atribut** dacă adresele din datele dvs. utilizează un singur câmp. Alegeți **Adresă cu atribute multiple** dacă adresele din datele dvs. utilizează mai mult de un singur câmp de date.

   > [!NOTE]
   > Țara/regiunea este obligatorie atât în adresele cu un singur atribut, cât și cu mai multe atribute. Adresele care nu conțin valori valabile sau acceptate de țară/regiune nu vor fi îmbogățite.

1.  Mapați câmpurile de adresă de la entitatea client unificată.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Pagina îmbunătățită de mapare a câmpului de adrese.":::

1. Selectați **Următorul** pentru a completa maparea câmpului.

1. Furnizați un nume pentru îmbogățire și entitatea de ieșire.

1. Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.

## <a name="enrichment-results"></a>Rezultate de îmbogățire

Pentru a începe procesul de îmbogățire, selectați **Rulare** din bara de comenzi. De asemenea, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei [reîmprospătări programate](system.md#schedule-tab). Timpul de procesare depinde de dimensiunea datelor clienților dvs.

După finalizarea procesului de îmbogățire, puteți consulta datele din profilurile clienților nou îmbogățite din **Îmbogățirile mele**. În plus, veți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.

Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.

## <a name="next-steps"></a>Pașii următori

Creați în plus față de datele îmbogățite ale clienților. Creați [segmente](segments.md) și [măsuri](measures.md), și chiar [exportați datele](export-destinations.md) pentru a oferi clienților dvs. experiențe particularizate.

[!INCLUDE[footer-include](../includes/footer-banner.md)]