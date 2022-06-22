---
title: Îmbunătățirea datelor companiei
description: Îmbogățiți și normalizați datele companiei cu modelele Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4247d59806468907d93fc7848231ec5a2985580e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953964"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Îmbogățirea profilurilor companiei cu date îmbunătățite ale companiei

Utilizați modelele Microsoft și datele compilate ale companiei pentru a corecta, completa și standardiza profilurile companiei. Vom folosi [Formatul Common Data Model](/common-data-model/schema/core/applicationcommon/account) pentru o mai bună acuratețe și perspectivă.

Poti de asemenea [îmbunătățirea datelor companiei despre sursele de date](data-sources-enrichment.md) pentru a îmbunătăți acuratețea potrivirii în procesul de unificare a datelor.

Pentru companiile publice din Statele Unite ale Americii, sunt disponibile informații precum venitul, simbolul acțiunilor, industria și multe altele.  

## <a name="how-we-enhance-company-data"></a>Cum îmbunătățim datele companiei

Modelul nostru trece printr-un proces în doi pași pentru a îmbunătăți profilul companiei. În primul rând, normalizează numele companiei. De exemplu, *Microsoft Corp* vor fi corectate și standardizate la *Microsoft Corporation*. Încearcă să găsească o potrivire în datele companiei compilate de Microsoft. Dacă se găsește o potrivire, îmbogățim profilul companiei cu informații din datele companiei compilate, inclusiv numele companiei.

### <a name="example"></a>Exemplu

Este posibil ca informațiile despre companie să nu urmeze un format standard și să conțină greșeli de ortografie. Modelul încearcă să rezolve aceste probleme și să creeze informații consistente.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Limitări

Modelul nu:

- Confirmați identitatea companiei. Nu verificăm dacă intrarea este o organizație existentă sau dacă o companie folosește rezultatul ca nume standard.
- Acoperiți cuprinzător companii la nivel global. Datele companiei compilate de Microsoft au acoperire globală, dar oferă cea mai mare acoperire în Australia, Canada, Regatul Unit și Statele Unite.
- Standardizați adresele companiei la nivel global. În prezent, acceptăm standardizarea adreselor în aceste țări sau regiuni: Australia, Canada, Franța, Germania, Italia, Japonia, Regatul Unit și Statele Unite.
- Garantați acuratețea sau prospețimea datelor. Deoarece informațiile comerciale se schimbă adesea, nu putem garanta că datele îmbunătățite ale companiei furnizate sunt întotdeauna exacte sau actualizate.

## <a name="configure-the-enrichment"></a>Configurați îmbogățirea

1. Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**.

1. Selectați **Îmbogățiți-mi datele** pe **Date îmbunătățite ale companiei** ţiglă.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Dală de îmbogățire în hub-ul de îmbogățire pentru datele companiei.":::

1. Examinați prezentarea generală și apoi selectați **Următorul**.

1. Selectează **Set de date despre client** și alegeți profilul sau segmentul pe care doriți să îl îmbogățiți. The *Client* entitate îmbogățește toate profilurile dvs. de clienți, în timp ce un segment îmbogățește numai profilurile de clienți conținute în acel segment.

1. Selectați ce tip de câmpuri din profilurile companiei dvs. să utilizați pentru potrivirea cu datele companiei compilate de Microsoft. Această selecție va afecta câmpurile de mapare la care aveți acces în pasul următor.

1. Selectați **Următorul**.

1. Hartați câmpurile companiei dvs. la datele companiei de la Microsoft. Pentru o mai mare precizie a potrivirii, adăugați mai multe câmpuri.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Etapa de cartografiere a datelor la configurarea îmbogățirii unei companii.":::

1. Selectați **Următorul** pentru a completa maparea câmpului.

1. Furnizeaza un **Nume** pentru îmbogățire și pentru **Entitate de ieșire**.

1. Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.

1. Selectați **Alerga** pentru a începe procesul de îmbogățire sau aproape pentru a reveni la **Îmbogățiri** pagină.

## <a name="enrichment-results"></a>Rezultate de îmbogățire

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Card de prezentare generală

The **Clienții modifică imaginea de ansamblu** țigla arată detalii despre acoperirea îmbogățirii

- **Companiile procesate și schimbate** : Numărul de profiluri de companie client care au fost îmbogățite cu succes.
- **Companii procesate și neschimbate** : Numărul de profiluri ale companiei clienți care au fost recunoscute, dar nu au fost modificate. Acest lucru se întâmplă de obicei atunci când datele de intrare sunt valide și nu pot fi îmbunătățite prin îmbogățire.
- **Companiile nu sunt procesate și neschimbate** : numărul de profiluri ale companiei clienți care nu au fost recunoscute. Acest lucru se întâmplă de obicei pentru datele de intrare care nu sunt valide sau nu sunt acceptate de îmbogățire.

## <a name="next-steps"></a>Pașii următori

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
