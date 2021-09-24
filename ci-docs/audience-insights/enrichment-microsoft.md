---
title: Îmbogățiți profilurile clienților cu date de la Microsoft
description: Folosiți date cu caracter proprietar de la Microsoft pentru a vă îmbogăți datele clienților cu afinități de marcă și de interes.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 45c81a037258e42d8975e0372c104865a9d4cbfe
ms.sourcegitcommit: 2acda3c5adf40bc3f5bbb4b2b4b6c22f84371da7
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466639"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Îmbogățiți profilurile clienților cu afinități de brand și interes (previzualizare)

Folosiți datele cu caracter proprietar ale Microsoft pentru a vă îmbogăți datele clienților cu afinități de marcă și de interes. Aceste afinități se bazează pe date de la persoane dntr-o categorie demografică similară cu cea a clienților dvs. Aceste informații vă ajută să vă înțelegeți și să vă segmentați mai bine clienții în funcție de afinitățile lor către anumite mărci și interese.

În detalii despre audiență, accesați **Date** > **Îmbogățire** pentru a [configura și vizualiza îmbogățiri](enrichment-hub.md).

Pentru a configura îmbogățirea afinităților de marcă, accesați fila **Descoperire** și selectați **Îmbogățiți-mi datele** pe dala **Mărci**.

Pentru a configura îmbogățirea afinităților de interes, accesați fila **Descoperire** și selectați **Îmbogățiți-mi datele** pe dala **Interese**.

   > [!div class="mx-imgBorder"]
   > ![Dale de branduri și interese.](media/BrandsInterest-tile-Hub.png "Dale de branduri și dobânzi")

## <a name="how-we-determine-affinities"></a>Cum determinăm afinitățile

Folosim datele de căutare online ale Microsoft pentru a găsi afinități pentru mărci și interese în diferite segmente demografice (definite în funcție de vârstă, sex sau locație). Volumul de căutare online pentru o marcă sau interes determină cât de multă afinitate are un segment demografic, comparativ cu alte segmente, față de acea marcă sau interes.

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

Selectați **Entitate îmbogățită** și alegeți setul de date pe care doriți să îl îmbogățiți cu datele companiei de la Microsoft. Puteți selecta entitatea Client pentru a vă îmbogăți toate profilurile de clienți sau selectați o entitate de segment pentru a îmbogăți numai profilurile de clienți din acel segment.

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

> [!TIP]
> Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese. În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies). Puteți selecta starea unui proces pentru a vedea detalii despre evoluția întregii lucrări. După selectare **Vezi detalii** pentru una dintre activitățile operațiunii, veți găsi informații suplimentare: timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate activității.

## <a name="enrichment-results"></a>Rezultate de îmbogățire

După executarea procesului de îmbogățire, accesați **Îmbogățirile mele** pentru a analiza numărul total de clienți îmbogățiți și o defalcare a mărcilor sau a intereselor în profilurile de clienți îmbogățite.

:::image type="content" source="media/my-enrichments.png" alt-text="Previzualizarea rezultatelor după executarea procesului de îmbogățire":::

Verificați datele îmbogățite selectând **Vizualizați date îmbogățite** în grafic. Datele îmbogățite pentru mărci se includ în entitatea **BrandAffinityFromMicrosoft**. Datele pentru interese sunt în entitatea **InterestAffinityFromMicrosoft**. De asemenea, veți găsi aceste entități listate în grupul **Îmbogățire** în **Date** > **Entități**.

Veți vedea o diagramă cu numărul de profiluri de clienți îmbogățiți în timp și o previzualizare a entității îmbogățite. Selectați **Afișați mai multe** în dala de previzualizare pentru a deschide entitatea îmbogățită.

## <a name="see-enrichment-data-on-the-customer-card"></a>Consultați datele de îmbogățire de pe cardul clientului

Afinitățile de marcă și interes pot fi, de asemenea, vizualizate pe carduri individuale ale clienților. Accesați **Clienți** și selectați un profil de client. În cardul de client, veți găsi diagrame pentru mărcile sau interesele pentru care persoanele din profilul demografic al clientului au afinitate.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Card de client cu date îmbogățite.":::

## <a name="next-steps"></a>Pașii următori

Creați în plus față de datele îmbogățite ale clienților. Creați [Segmente](segments.md) și [Măsuri](measures.md), și chiar [exportați datele](export-destinations.md) pentru a oferi clienților dvs. experiențe particularizate.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
