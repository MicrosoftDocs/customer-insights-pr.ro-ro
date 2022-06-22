---
title: Îmbogățiți profilurile clienților cu date despre mărci și interese de la Microsoft
description: Utilizați datele proprietare de la Microsoft pentru a vă îmbogăți datele clienților cu afinități și partajarea vocii.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 61262980cafdcd130430e200e466ce7da6cc4d07
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953780"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Îmbogățiți profilurile clienților cu afinități și cota de voce (previzualizare)

Utilizați datele proprietare Microsoft pentru a vă îmbogăți datele clienților cu afinități de marcă, afinități de interese și cota de voce (SoV). Aceste afinități și SoV se bazează pe date de la persoane cu date demografice similare cu clienții dvs. Aceste informații vă ajută să înțelegeți și să segmentați mai bine clienții în funcție de afinitățile lor sau de SoV pentru mărci și interese specifice.

## <a name="how-we-determine-affinities-and-sov"></a>Cum determinăm afinitățile și SoV

Folosim datele de căutare online ale Microsoft pentru a găsi afinități și SoV pentru mărci și interese în diferite segmente demografice (definite de vârstă, sex sau locație). Volumul de căutare online pentru o marcă sau interes formează baza pentru determinarea afinității sau SoV. Cu toate acestea, fiecare oferă o perspectivă diferită pentru a vă înțelege clienții.

- Afinitatea este o comparație între segmente demografice. Puteți utiliza aceste informații pentru a identifica segmentele demografice care au cea mai mare afinitate pentru o anumită marcă sau interes, în comparație cu alte segmente.

- Cota de voce este o comparație între mărcile sau interesele selectate. Puteți utiliza aceste informații pentru a identifica care marcă sau interes are cea mai mare cotă de voce pentru un anumit segment demografic, în comparație cu alte mărci sau interese pe care le-ați selectat.

## <a name="affinity-level-and-score"></a>Nivelul și scorul de afinitate

Pe fiecare profil de client îmbogățit, oferim două valori conexe - nivelul de afinitate și scorul de afinitate. Aceste valori vă ajută să determinați cât de puternică este afinitatea pentru segmentul demografic al profilului respectiv, pentru un brand sau interes, în comparație cu alte segmente demografice.

*Nivelul de afinitate* este format din patru niveluri și *scor de afinitate* este calculat pe o scară de 100 de puncte care se mapează la nivelurile de afinitate.

|Nivelul de afinitate |Scor de afinitate  |
|---------|---------|
|Foarte mare     | 85-100       |
|Înalt     | 70-84        |
|Mediu     | 35-69        |
|Redusă     | 1-34        |

În funcție de granularitatea pe care doriți să o măsurați afinitatea, puteți utiliza fie nivelul de afinitate, fie punctajul. Scorul de afinitate vă oferă un control mai precis.

## <a name="share-of-voice-sov"></a>Cota de voce (SoV)

Calculăm SoV pe o scară de 100 de puncte. SoV total pentru toate mărcile sau interesele pentru fiecare profil de client îmbogățit se ridică la 100. Spre deosebire de afinități, SoV este relativ la mărcile și interesele pe care le selectați. De exemplu, valorile SoV pentru „Microsoft” pot fi diferite dacă mărcile selectate sunt („Microsoft”, „GitHub”) față de („Microsoft”, „LinkedIn”).

## <a name="supported-countriesregions"></a>Țări / regiuni acceptate

În prezent, acceptăm următoarele opțiuni de țară/regiune: Australia, Canada (engleză), Franța, Germania, Regatul Unit sau Statele Unite (engleză).

## <a name="configure-the-enrichment"></a>Configurați îmbogățirea

1. Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**.

   - Pentru a configura afinitățile de marcă și îmbogățirea SoV, selectați **Îmbogățiți-mi datele** pe **Mărci** ţiglă.

   - Pentru a configura afinitățile de interes și îmbogățirea SoV, selectați **Îmbogățiți-mi datele** pe **Interese** ţiglă.

   > [!div class="mx-imgBorder"]
   > ![Dale de branduri și interese.](media/BrandsInterest-tile-Hub.png "Dale de branduri și dobânzi")

1. Examinați prezentarea generală și apoi selectați **Următorul**.

1. Pentru a vă schimba țara sau regiunea, selectați **Schimbare** lângă **Țara/Regiune**. În **Setări de țară/regiune** panou, alegeți a [țara/regiunea acceptată](#supported-countriesregions) și selectați **aplica**.

   > [!NOTE]
   > Când alegeți propriile mărci, sistemul oferă sugestii pe baza țării sau regiunii selectate. Când alegeți o industrie, veți obține cele mai relevante mărci sau interese în funcție de țara sau regiunea selectată.

1. Alegeți până la cinci mărci sau interese folosind una sau ambele opțiuni:

   - **Industrie**: Selectați-vă industria din lista derulantă, apoi alegeți dintre mărcile sau dobânzile de top pentru industria respectivă.
   - **Alegeți-vă una proprie**: Introduceți o marcă sau un interes relevant pentru organizația dvs. și apoi alegeți dintre sugestiile potrivite. Dacă nu enumerăm o marcă sau un interes pe care îl căutați, trimiteți-ne feedback folosind legătura **Sugerați**.

1. Selectați **Următorul** și revizuiți preferințele implicite de îmbogățire și actualizați-le după cum este necesar.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captură de ecran a ferestrei preferințelor de îmbogățire.":::

1. Selectați **Următorul**.

1. Selectează **Set de date despre client** și alegeți profilul sau segmentul pe care doriți să îl îmbogățiți cu date de la Microsoft. The *Client* entitate îmbogățește toate profilurile dvs. de clienți, în timp ce un segment îmbogățește numai profilurile de clienți conținute în acel segment.

1. Selectați **Următorul**.

1. Hartați câmpurile de la entitatea client unificată la datele Microsoft.

   > [!NOTE]
   > Sunt necesare cel puțin atributele Data nașterii sau Gen. Sunt necesare țara/regiunea și cel puțin orașul (și statul/provinția) sau codul poștal. Vă recomandăm ca data nașterii să fie convertită în tipul DateTime în timpul ingerării datelor. Alternativ, poate fi un șir în formatul [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) „aaaa-LL-zz” sau „aaaa-LL-zzTHTH: mm: ss”.

1. Selectați **Următorul** pentru a completa maparea câmpului.

1. Oferiți un nume pentru îmbogățire. The **Numele entității de ieșire** este selectat automat.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Revizuirea intereselor și denumirea paginii.":::

1. Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.

1. Selectați **Alerga** pentru a începe procesul de îmbogățire sau aproape pentru a reveni la **Îmbogățiri** pagină.

   Când îmbogățim profilurile, vom îmbogăți toate profilurile clienților pentru care obținem date pentru mărcile și dobânzile selectate, inclusiv profilurile care nu se află în țara sau regiunea selectată. De exemplu, dacă ați selectat Germania, vom îmbogăți profilurile situate în Statele Unite dacă avem date disponibile pentru mărcile și interesele selectate din SUA.

## <a name="enrichment-results"></a>Rezultate de îmbogățire

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Previzualizarea rezultatelor după executarea procesului de îmbogățire":::

Rezultatele includ **Nivel de afinitate** sau **Cota de voce** grafice.

Entitățile create din îmbogățiri sunt enumerate sub **Îmbogăţire** grup in **Date** > **Entități**. Datele îmbogățite pentru mărci merg la **BrandAffinityFromMicrosoft** și **BrandShareOfVoiceFromMicrosoft** entitati. Datele pentru interese sunt în **InterestAffinityFromMicrosoft** și **InterestShareOfVoiceFromMicrosoft** entitati.

## <a name="see-enrichment-data-on-the-customer-card"></a>Consultați datele de îmbogățire de pe cardul clientului

Marca și interesul SoV pot fi vizualizate și pe cardurile individuale ale clienților. Accesați **Clienți** și selectați un profil de client. În cardul clientului, veți găsi diagrame pentru marca sau interesul SoV pe baza persoanelor din profilul demografic al clientului respectiv.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Card de client cu date îmbogățite.":::

## <a name="next-steps"></a>Pașii următori

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
