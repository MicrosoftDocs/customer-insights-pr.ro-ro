---
title: Îmbunătățirea datelor companiei
description: Îmbogățiți și normalizați datele companiei cu modelele Microsoft.
ms.date: 11/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9bfb96d47de4ec98325e644c60752fc7cab2706c
ms.sourcegitcommit: 6efcba688d1db1a5d6343c229f292a26c48fc007
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/05/2021
ms.locfileid: "7770185"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Îmbogățirea profilurilor companiei cu date îmbunătățite ale companiei

Utilizați modelele Microsoft și datele compilate ale companiei pentru a corecta, completa și standardiza profilurile companiei dvs. Vom folosi [Formatul Common Data Model](/common-data-model/schema/core/applicationcommon/account) pentru o mai bună acuratețe și perspectivă.

## <a name="how-we-enhance-company-data"></a>Cum îmbunătățim datele companiei

Modelul nostru trece printr-un proces în doi pași pentru a îmbunătăți profilul companiei. În primul rând, normalizează numele companiei. De exemplu, *Microsoft Corp* vor fi corectate și standardizate la *Microsoft Corporation*. Încearcă să găsească o potrivire în datele companiei compilate de Microsoft. Dacă se găsește o potrivire, îmbogățim profilul companiei cu informații din datele companiei compilate, inclusiv numele companiei.


### <a name="example"></a>Exemplu

Este posibil ca informațiile despre companie să nu urmeze un format standard și să conțină greșeli de ortografie. Modelul încearcă să remedieze aceste probleme și să creeze informații consistente.

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

Există câteva limitări cu datele îmbunătățite. Elementele din lista de mai jos nu sunt acceptate de model.

1.  Confirmați identitatea companiei. Nu verificăm dacă intrarea este o organizație existentă sau dacă o companie folosește rezultatul ca nume standard.
2.  Acoperiți cuprinzător companiile la nivel global. Datele companiei compilate de Microsoft au acoperire globală, dar oferă cea mai mare acoperire în Australia, Canada, Regatul Unit și Statele Unite.
3.  Garantați acuratețea sau prospețimea datelor. Deoarece informațiile comerciale se schimbă adesea, nu putem garanta că datele îmbunătățite ale companiei furnizate sunt întotdeauna exacte sau actualizate.

## <a name="configure-the-enrichment"></a>Configurați îmbogățirea

1. Accesați **Date** > **Îmbogățire**.

1. Selectați **Îmbogățiți-mi datele** pe **Date îmbunătățite ale companiei** ţiglă.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Dală de îmbogățire în hub-ul de îmbogățire pentru datele companiei.":::

1. Selectați **Set de date client** și alegeți entitatea care conține adresele pe care doriți să le îmbogățiți. Puteți selecta entitatea *Client* pentru a îmbogăți adrese în toate profilurile dvs. de clienți sau selectați o entitate de segment pentru a îmbogăți adresele numai în profilurile de clienți din acel segment.

1. Selectați ce tip de câmpuri din profilurile companiei dvs. ar trebui să fie utilizate pentru potrivirea cu datele companiei compilate de Microsoft. Această selecție va afecta câmpurile de mapare la care aveți acces în pasul următor.

1.  Hartați câmpurile companiei de la entitatea dvs. unificată client. Cu cât mapați mai mulți identificatori cheie și câmpuri, cu atât este mai probabilă o rată de potrivire mai mare.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Etapa de cartografiere a datelor la configurarea îmbogățirii unei companii.":::

1. Selectați **Următorul** pentru a completa maparea câmpului.

1. Furnizați un nume pentru îmbogățire și entitatea de ieșire.

1. Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.

## <a name="enrichment-results"></a>Rezultate de îmbogățire

Pentru a începe procesul de îmbogățire, selectați **Rulare** din bara de comenzi. De asemenea, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei [reîmprospătări programate](system.md#schedule-tab). Timpul de procesare depinde de dimensiunea datelor clienților dvs.

După finalizarea procesului de îmbogățire, puteți consulta datele din profilurile clienților nou îmbogățite din **Îmbogățirile mele**. În plus, veți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.

Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.

## <a name="next-steps"></a>Pașii următori

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
