---
title: Îmbogățiți profilurile clienților cu Microsoft Graph
description: Utilizați datele de proprietate din Microsoft Graph pentru a îmbogăți datele clienților dvs. cu afinități de marcă și interes.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406674"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Îmbogățiți profilurile clienților cu afinități de brand și interes (previzualizare)

Utilizați datele de proprietate din Microsoft Graph pentru a îmbogăți datele clienților dvs. cu afinități de marcă și interes. Aceste afinități sunt determinate pe baza datelor de la persoane cu o demografie similară pentru clienții dvs. Aceste informații vă ajută să vă înțelegeți și să vă segmentați mai bine clienții în funcție de afinitățile lor către anumite mărci și interese.

În Detalii despre audiență, accesați **Date** > **Îmbogățire** pentru a [configura și vizualiza îmbogățiri](enrichment-hub.md).

Pentru a configura îmbogățirea afinităților de marcă, accesați fila **Descoperire** și selectați **Îmbogățiți-mi datele** pe dala **Mărci**.

Pentru a configura îmbogățirea afinităților de interes, accesați fila **Descoperire** și selectați **Îmbogățiți-mi datele** pe dala **Interese**.

   > [!div class="mx-imgBorder"]
   > ![Dale Branduri și interese](media/BrandsInterest-tile-Hub.png "Dale Branduri și interese")

## <a name="about-microsoft-graph"></a>Despre Microsoft Graph

Folosim datele de căutare online din Microsoft Graph pentru a găsi afinități pentru mărci și interese pe diverse segmente demografice (definite în funcție de vârstă, sex sau locație). Volumul de căutare online pentru o marcă sau interes determină cât de multă afinitate are un segment demografic, comparativ cu alte segmente, față de acea marcă sau interes.

[Aflați mai multe despre Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Scorul de afinitate și încrederea

**Scorul de afinitate** este calculat pe o scară de 100 de puncte, 100 reprezentând segmentul care are cea mai mare afinitate pentru o marcă sau interes.

**Încredere în afinitate** se calculează, de asemenea, pe o scară de 100 de puncte. Indică nivelul de încredere al sistemului că un segment are afinitate pentru brand sau interes. Nivelul de încredere se bazează pe mărimea segmentului și pe granularitatea segmentului. Mărimea segmentului este determinată de cantitatea de date pe care o avem pentru un segment dat. Granularitatea segmentului este determinată de câte atribute (vârstă, sex, locație) sunt disponibile într-un profil.

Nu normalizăm scorurile pentru setul dvs. de date. În consecință, este posibil să nu vedeți toate valorile posibile ale scorului de afinitate pentru setul dvs. de date. De exemplu, este posibil să nu existe un profil de clienți îmbogățit cu scorul de afinitate 100 în datele dvs. Acest lucru este posibil dacă nu există clienți în segmentul demografic care a înregistrat un scor de 100 pentru o anumită marcă sau interes.

> [!TIP]
> Când [creați segmente](segments.md) utilizând scoruri de afinitate, consultați distribuția scorurilor de afinitate pentru setul de date înainte de a decide cu privire la pragurile de scor corespunzătoare. De exemplu, un scor de afinitate de 10 poate fi considerat semnificativ într-un set de date care are un scor de afinitate cel mai mare de doar 25 pentru o anumită marcă sau interes.

## <a name="supported-countriesregions"></a>Țări / regiuni acceptate

În prezent, acceptăm următoarele opțiuni de țară/regiune: Australia, Canada (engleză), Franța, Germania, Regatul Unit sau Statele Unite (engleză).

Pentru a selecta o țară, deschideți **Îmbogățirea mărcilor** sau **Îmbogățirea intereselor** și selectați **Schimbare** lângă **Țară/Regiune**. În panoul **Setări de țară/regiune**, alegeți o opțiune și selectați **Aplicare**.

### <a name="implications-related-to-country-selection"></a>Implicații legate de selecția țării

- La [alegerea propriilor mărci](#define-your-brands-or-interests), vom oferi sugestii în funcție de țara/regiunea selectată.

- Când [alegeți o industrie](#define-your-brands-or-interests), vom identifica cele mai relevante mărci sau interese pe baza țării/regiunii selectate.

- La [maparea câmpurilor dvs.](#map-your-fields), când câmpul Țară/Regiune nu este mapat, vom folosi datele Microsoft Graph din țara/regiunea selectată pentru a vă îmbogăți profilurile de clienți. De asemenea, vom folosi respectiva selecție pentru a vă îmbogăți profilurile de clienți care nu au date de țară/regiune disponibile.

- La [îmbogățirea profilurilor](#refresh-enrichment), vom îmbogăți toate profilurile clienților pentru care avem date Microsoft Graph disponibile pentru mărcile și interesele selectate, inclusiv profilurile care nu sunt în țara/regiunea selectată. De exemplu, dacă ați selectat Germania, vom îmbogăți profilurile situate în Statele Unite dacă avem date Microsoft Graph disponibile pentru mărcile și interesele selectate din SUA.

## <a name="configure-enrichment"></a>Configurați îmbogățirea

Configurarea îmbogățirii mărcilor sau intereselor constă în doi pași:

### <a name="define-your-brands-or-interests"></a>Definiți-vă brandurile sau interesele

Selectaţi una dintre următoarele opţiuni:

- **Industrie**: Sistemul identifică cele mai importante mărci sau interese relevante pentru industria dvs. și îmbogățește datele clientului cu acestea.
- **Alegeți-vă una proprie**: Selectați până la cinci articole din lista mărcilor sau a intereselor care sunt cele mai relevante pentru organizația dvs.

Pentru a adăuga o marcă sau interes, introduceți-o în zona de intrare pentru a primi sugestii bazate pe termeni potriviți. Dacă nu enumerăm o marcă sau un interes pe care îl căutați, trimiteți-ne feedback folosind legătura **Sugerați**.

### <a name="map-your-fields"></a>Mapați câmpurile

Mapați câmpurile de la entitatea dvs. de client unificată la cel puțin două atribute pentru a defini segmentul demografic pe care doriți să îl utilizați pentru îmbogățirea datelor clientului dvs. Selectați **Editați** pentru a defini maparea câmpurilor și selectați **Aplicare** când ați terminat. Selectați **Salvați** pentru a finaliza maparea câmpului.

Următoarele formate și valori sunt acceptate, valorile nu sunt sensibile la litere mari și mici:

- **Data de naștere**: Recomandăm ca data nașterii să fie transformată în tip DateTime în timpul ingestiei de date. Alternativ, poate fi un șir în format [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format „aaaa-LL-zz” sau „aaaa-LL-zzTOO:mm:ssZ”.
- **Sex**: Bărbat, Femeie, Necunoscut
- **Cod poștal**: Coduri poștale de cinci cifre pentru SUA, cod poștal standard în restul locațiilor
- **Oraș**: Numele orașului în engleză
- **Stat/Provincie**: Abreviere cu două litere pentru SUA și Canada. Abreviere cu două sau trei litere pentru Australia. Nu se aplică Franței, Germaniei sau Regatului Unit.
- **Țară/regiune**:

  - SUA: Statele Unite ale Americii, Statele Unite, SUA, SUA, America
  - CA: Canada, CA
  - GB: Regatul Unit, UK, Marea Britanie, GB, Regatul Unit al Marii Britanii și Irlandei de Nord, Regatul Unit al Marii Britanii
  - AU: Australia, AU, Commonwealth-ul Australiei
  - FR: Franța, FR, Republica Franceză
  - DE: Germania, German, Deutschland, Allemagne, DE, Republica Federală Germania, Republica Germania

## <a name="refresh-enrichment"></a>Reîmprospătare îmbogățire

Rulați îmbogățirea după configurarea mărcilor, a intereselor și a mapării câmpului pentru demografie. Pentru a începe procesul, selectați **Rulare** pe pagina de configurare a mărcii sau a intereselor. În plus, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei actualizări programate.
În funcție de dimensiunea datelor clientului dvs., este posibil să dureze câteva minute pentru a finaliza o îmbogățire.

> [!TIP]
> Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese. În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies). Puteți selecta starea unui proces pentru a vedea detalii despre evoluția întregii lucrări. După selectarea **Vizualizare detalii** pentru una dintre sarcinile jobului, găsiți informații suplimentare: timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate sarcinii.

## <a name="enrichment-results"></a>Rezultate de îmbogățire

După executarea procesului de îmbogățire, accesați **Îmbogățirile mele** pentru a analiza numărul total de clienți îmbogățiți și o defalcare a mărcilor sau a intereselor în profilurile de clienți îmbogățite.

:::image type="content" source="media/my-enrichments.png" alt-text="Previzualizarea rezultatelor după executarea procesului de îmbogățire":::

Verificați datele îmbogățite selectând **Vizualizați date îmbogățite** în grafic. Datele îmbogățite pentru mărci se includ în entitatea **BrandAffinityFromMicrosoft**. Datele pentru interese sunt în entitatea **InterestAffinityFromMicrosoft**. De asemenea, veți găsi aceste entități listate în grupul **Îmbogățire** în **Date** > **Entități**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Consultați datele de îmbogățire de pe cardul clientului

Afinitățile de marcă și interes pot fi, de asemenea, vizualizate pe carduri individuale ale clienților. Accesați **Clienți** și selectați un profil de client. În cardul de client, veți găsi diagrame pentru mărcile sau interesele pentru care persoanele din profilul demografic al clientului au afinitate.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Card de client cu date îmbogățite":::

## <a name="next-steps"></a>Următorii pași

Creați în plus față de datele îmbogățite ale clienților. Creați [Segmente](segments.md), [Măsuri](measures.md) și chiar [exportați datele](export-destinations.md) pentru a oferi experiențe personalizate clienților.
