---
title: Detalii de segment pentru segmentele existente
description: Obțineți detalii despre segmentele existente pentru a vedea diferențele și punctele comune.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: d731d21462b5a31aba0653f87e299d98373bbf49
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270035"
---
# <a name="segment-insights-preview"></a>Detalii despre segment (previzualizare)

Descoperiți informații suplimentare și detalii despre segmentele dvs. existente. Aflați ce diferențiază două segmente sau ce au în comun.

## <a name="segment-overlap"></a>Suprapunere de segment

Analiza de suprapunere a segmentelor arată câți și care clienți sunt comuni pentru două sau mai multe segmente. De exemplu, modul în care un segment de clienți frecvenți se suprapune cu un segment care conține clienți mulțumiți de serviciul sau produsul dvs.
De asemenea, puteți analiza modul în care se suprapun modificările pentru atribute specifice.

### <a name="run-an-overlap-analysis"></a>Executați o analiză de suprapunere

1. Accesați **Segmente** și selectați fila **Detalii (previzualizare)**.

1. Selectați **Nou** și alegeți opțiunea **Suprapune** în panoul **Alegeți tipul de Detaliu**.

1. Alegeți segmentele de interes și selectați **Următorul**.

1. Opțional, alegeți unul sau mai multe câmpuri de interes pentru a analiza suprapunerile pentru fiecare valoare posibilă a câmpului și selectați **Următorul**.

1. Furnizați un nume pentru analiza de suprapunere, un nume de afișare opțional și o descriere.

1. Selectați **Salvare** pentru a începe analiza. Analiza de suprapunere este gata atunci când starea se schimbă de la Actualizare la Succes.

### <a name="view-and-optimize-an-overlap-analysis"></a>Vizualizați și optimizați o analiză de suprapunere

După finalizarea analizei, găsiți detalii despre acest detaliu despre **Segmente** > **Detalii (previzualizare)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Detalii despre suprapunere pe segment":::

Selectați un detaliu pentru a vedea rezultatele analizei:

- Numărul de membri care se suprapun segmentelor selectate pentru analiză.
- Numărul de membri incluși într-unul dintre segmente, dar nu și în restul segmentelor.
- Dacă ați selectat câmpuri în timp ce configurați analiza de suprapunere, le veți găsi în filele corespunzătoare. Puteți utiliza funcția verticală a filtrului pentru a selecta orice nivel de interes al atributului, iar tabelul din partea de jos va afișa datele corespunzătoare.

## <a name="segment-differentiators"></a>Diferențiatori de segmente

Diferențiatori de segmente vă ajută să aflați ce diferențiază un segment de restul clienților dvs. sau de un alt segment. Trebuie doar să selectați un segment, iar sistemul va identifica atributele de profil și măsurile care disting segmentul selectat.

### <a name="run-a-differentiator-analysis"></a>Efectuați o analiză de diferențiator

1. Accesați **Segmente** și selectați fila **Detalii (previzualizare)**.

1. Selectați **Nou** și alegeți opțiunea **Suprapune** în panoul **Alegeți tipul de Detaliu**.

1. Alegeți segmentul pe care doriți să îl analizați **Segmentul primar** și selectați **Următorul**.

1. Alegeți **Toți clienții** sau un **Segment secundar** pentru a compara segmentul principal cu și selecta **Următorul**.

1. Opțional, alege unul sau mai multe câmpuri de interes pentru a concentra analiza pe atribute specifice și selectează **Următorul**.

1. Furnizați un nume pentru analiza de suprapunere, un nume de afișare opțional și o descriere.

1. Selectați **Salvare** pentru a începe analiza. Analiza de suprapunere este gata atunci când starea se schimbă de la Actualizare la Succes.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Vizualizați și optimizați o analiză a diferențiatorilor

După finalizarea analizei, găsiți detalii despre acest detaliu despre **Segmente** > **Detalii (previzualizare)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Detalii despre diferențiator pe segment":::

Selectați un detaliu pentru a vedea rezultatele analizei. O analiză a diferențiatorului include două file. Fila **Atribute** listează atributele profilului considerate ca diferențiatori. Fila **Măsuri** listează diferențiatori. Fiecare filă include următoarele detalii:

- Lista clasificată a diferențiatorilor, ordonată după scorul diferenței.
- **Scorul de diferență** pentru fiecare diferențiator. Scorul de diferență reprezintă gradul de diferență a unui atribut între două segmente. Cu cât scorul de diferență este mai mare, cu atât atributele diferă între cele două segmente. Selectați un scor pentru a deschide panoul **Scorul de diferență** cu distribuțiile de valori pentru acel atribut.

## <a name="manage-segment-insights"></a>Gestionați detaliile de segment

Puteți utiliza următoarele opțiuni pentru detaliile dvs. din bara de comenzi:

- **Înapoi** pentru a returna lista de detalii
- **Reîmprospăta** pentru a rula din nou analiza
- **Ștergere** pentru a elimina acest detaliu


[!INCLUDE[footer-include](../includes/footer-banner.md)]