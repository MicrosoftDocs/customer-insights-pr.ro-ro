---
title: Îmbogățiți profilurile clienților cu date de la Microsoft
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
ms.openlocfilehash: 12704ec46832e9463e6115db6c4df64e72bf4f97
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/02/2022
ms.locfileid: "8372704"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Îmbogățiți profilurile clienților cu afinități și cota de voce (previzualizare)

Utilizați datele proprietare Microsoft pentru a vă îmbogăți datele clienților cu afinități de marcă, afinități de interese și cota de voce (SoV). Aceste afinități și SoV se bazează pe date de la persoane cu date demografice similare cu clienții dvs. Aceste informații vă ajută să înțelegeți și să segmentați mai bine clienții în funcție de afinitățile lor sau de SoV pentru mărci și interese specifice.

În detalii despre audiență, accesați **Date** > **Îmbogățire** pentru a [configura și vizualiza îmbogățiri](enrichment-hub.md).

Pentru a configura afinitățile de brand și îmbogățirea SoV, accesați **Descoperi** filă și selectați **Îmbogățiți-mi datele** pe **Mărci** ţiglă.

Pentru a configura afinitățile de interes și îmbogățirea SoV, accesați **Descoperi** filă și selectați **Îmbogățiți-mi datele** pe **Interese** ţiglă.

   > [!div class="mx-imgBorder"]
   > ![Dale de branduri și interese.](media/BrandsInterest-tile-Hub.png "Dale de branduri și dobânzi")

## <a name="how-we-determine-affinities-and-sov"></a>Cum determinăm afinitățile și SoV

Folosim datele de căutare online ale Microsoft pentru a găsi afinități și SoV pentru mărci și interese în diferite segmente demografice (definite de vârstă, sex sau locație). Volumul de căutare online pentru o marcă sau interes formează baza pentru determinarea afinității sau SoV. Cu toate acestea, fiecare oferă o perspectivă diferită pentru a vă înțelege clienții.

- Afinitatea este o comparație între segmente demografice. Puteți utiliza aceste informații pentru a identifica segmentele demografice care au cea mai mare afinitate pentru o anumită marcă sau interes, în comparație cu alte segmente.

- Cota de voce este o comparație între mărcile sau interesele selectate. Puteți utiliza aceste informații pentru a identifica ce marcă sau interes are cea mai mare cotă de voce pentru un anumit segment demografic, în comparație cu alte mărci sau interese pe care le-ați selectat.

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

Pentru a selecta o țară sau o regiune, deschideți **Îmbogățirea mărcilor** sau **Îmbogățirea dobânzii** și selectați **Schimbare** chiar lângă **Țară / Regiune**. În panoul **Setări de țară/regiune**, alegeți o opțiune și selectați **Aplicare**.

### <a name="implications-related-to-country-selection"></a>Implicații legate de selecția țării

- Când [alegeți propriile mărci](#define-your-brands-or-interests), sistemul oferă sugestii pe baza țării sau regiunii selectate.

- Când [alegeți o industrie](#define-your-brands-or-interests), veți obține cele mai relevante mărci sau interese în funcție de țara sau regiunea selectată.

- Când [îmbogățim profilurile](#refresh-enrichment), vom îmbogăți toate profilurile clienților pentru care obținem date pentru mărcile și dobânzile selectate, inclusiv profilurile care nu se află în țara sau regiunea selectată. De exemplu, dacă ați selectat Germania, vom îmbogăți profilurile situate în Statele Unite dacă avem date disponibile pentru mărcile și interesele selectate din SUA.

## <a name="configure-enrichment"></a>Configurarea îmbogățirii

O experiență ghidată vă ajută prin configurarea îmbogățirilor. 

### <a name="define-your-brands-or-interests"></a>Definiți-vă brandurile sau interesele

Alegeți până la cinci mărci sau interese folosind una sau ambele opțiuni:

- **Industrie**: Selectați-vă industria din lista derulantă, apoi alegeți dintre mărcile sau dobânzile de top pentru industria respectivă.
- **Alegeți-vă una proprie**: Introduceți o marcă sau un interes relevant pentru organizația dvs. și apoi alegeți dintre sugestiile potrivite. Dacă nu enumerăm o marcă sau un interes pe care îl căutați, trimiteți-ne feedback folosind legătura **Sugerați**.

### <a name="review-enrichment-preferences"></a>Recenzie preferințe de îmbogățire

Examinați preferințele implicite de îmbogățire și actualizați-le după cum este necesar.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captură de ecran a ferestrei preferințelor de îmbogățire.":::

### <a name="select-entity-to-enrich"></a>Selectați entitatea de îmbogățit

Selectați **Entitate îmbogățită** și alegeți setul de date pe care doriți să îl îmbogățiți cu date de la Microsoft. Puteți selecta entitatea Client pentru a vă îmbogăți toate profilurile de clienți sau selectați o entitate de segment pentru a îmbogăți numai profilurile de clienți din acel segment.

### <a name="map-your-fields"></a>Mapați câmpurile

Hartați câmpurile de la entitatea dvs. client unificată pentru a defini segmentul demografic pe care doriți să îl utilizeze sistemul pentru îmbogățirea datelor despre clienți. Mapați Țară/Regiune și cel puțin Data nașterii sau atributele de gen. În plus, trebuie să mapați cel puțin unul dintre oraș (și stat/provincie) sau cod poștal. Selectați **Editați** pentru a defini maparea câmpurilor și selectați **Aplicare** când ați terminat. Selectați **Salvați** pentru a finaliza maparea câmpului.

Următoarele formate și valori sunt acceptate (valorile nu sunt sensibile la litere mari și mici):

- **Data de naștere**: Recomandăm ca data nașterii să fie transformată în tip DateTime în timpul ingestiei de date. Alternativ, poate fi un șir în formatul [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) „aaaa-LL-zz” sau „aaaa-LL-zzTHTH: mm: ss”.
- **Sex**: Bărbat, Femeie, Necunoscut.
- **Cod poștal**: Coduri poștale din cinci cifre pentru Statele Unite, cod poștal standard peste tot.
- **Oraș**: Numele orașului în engleză.
- **Stat/Provincie**: Abreviere cu două litere pentru SUA și Canada. Abreviere de două sau trei litere pentru Australia. Nu se aplică Franței, Germaniei sau Regatului Unit.
- **Țară/regiune**:

  - SUA: Statele Unite ale Americii, Statele Unite, SUA, SUA, America
  - CA: Canada, CA
  - GB: Regatul Unit, UK, Marea Britanie, GB, Regatul Unit al Marii Britanii și Irlandei de Nord, Regatul Unit al Marii Britanii
  - AU: Australia, UA, Commonwealth of Australia
  - FR: Franța, FR, Republica Franceză
  - DE: Germania, German, Deutschland, Allemagne, DE, Republica Federală Germania, Republica Germania

## <a name="review-and-name-the-enrichment"></a>Examinați și denumiți îmbogățirea

În cele din urmă, trebuie să examinați informațiile și să furnizați un nume pentru îmbogățire.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Revizuirea intereselor și denumirea paginii.":::

## <a name="refresh-enrichment"></a>Reîmprospătare îmbogățire

Rulați îmbogățirea după configurarea mărcilor, a intereselor și a mapării câmpului pentru demografie. Pentru a începe procesul, selectați **Rulare** pe pagina de configurare a mărcii sau a intereselor. În plus, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei actualizări programate.

În funcție de dimensiunea datelor clientului dvs., este posibil să dureze câteva minute pentru a finaliza o îmbogățire.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Rezultate de îmbogățire

După executarea procesului de îmbogățire, accesați **Îmbogățirile mele** pentru a analiza numărul total de clienți îmbogățiți și o defalcare a mărcilor sau a intereselor în profilurile de clienți îmbogățite.

:::image type="content" source="media/my-enrichments.png" alt-text="Previzualizarea rezultatelor după executarea procesului de îmbogățire":::

Veți găsi o diagramă cu numărul de profiluri de clienți îmbogățite de-a lungul timpului și previzualizări ale entităților îmbogățite. Examinați datele îmbogățite selectând **Vezi mai mult** în **Nivel de afinitate** sau **Cota de voce** grafice. Datele îmbogățite pentru mărci merg la **BrandAffinityFromMicrosoft** și **BrandShareOfVoiceFromMicrosoft** entitati. Datele pentru interese se află în **InterestAffinityFromMicrosoft** și **InterestShareOfVoiceFromMicrosoft** entitati. De asemenea, veți găsi aceste entități listate în grupul **Îmbogățire** în **Date** > **Entități**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Consultați datele de îmbogățire de pe cardul clientului

Marca și interesul SoV pot fi vizualizate și pe cardurile individuale ale clienților. Accesați **Clienți** și selectați un profil de client. În cardul clientului, veți găsi diagrame pentru marca sau interesul SoV pe baza persoanelor din profilul demografic al clientului respectiv.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Card de client cu date îmbogățite.":::

## <a name="next-steps"></a>Pașii următori

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
