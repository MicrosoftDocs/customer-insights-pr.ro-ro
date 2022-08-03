---
title: Găsiți clienți similari cu AI (previzualizare) (conține videoclip)
description: Găsiți segmente de clienți similare cu inteligență artificială.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170742"
---
# <a name="find-similar-customers-with-ai-preview"></a>Găsiți clienți similari cu AI (previzualizare)

Găsiți clienți similari în baza de clienți utilizând informații artificiale. Aveți nevoie de cel puțin un segment creat pentru a utiliza această funcție. Extinderea criteriilor unui segment existent ajută la găsirea de clienți care sunt similari cu acel segment.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Găsiți clienți similari* folosește mijloace automate pentru a evalua datele și a face predicții pe baza acestor date. Prin urmare, are capacitatea de a fi utilizat ca metodă de profilare, așa cum termenul respectiv este definit de Regulamentul general privind protecția datelor („GDPR”). Utilizarea acestei funcții de către client pentru prelucrarea datelor poate fi supusă RGPD sau altor legi sau reglementări. Sunteți responsabil pentru a vă asigura că utilizarea de către dvs. a Dynamics 365 Customer Insights, inclusiv predicțiile, respectă toate legile și reglementările aplicabile, inclusiv legile legate de confidențialitate, date cu caracter personal, date biometrice, protecția datelor și confidențialitatea comunicărilor.

## <a name="find-similar-customers"></a>Găsiți clienți similari

1. Mergi la **Segmente** și selectați segmentul pe care doriți să vă bazați noul segment. Acesta este *segmentul sursă* al dvs.

1. Selectați **Găsiți clienți similari**.

1. Examinați numele sugerat pentru noul segment și schimbați-l dacă este necesar.

1. Opțional, adăugați [Etichete](work-with-tags-columns.md#manage-tags) la noul segment.

1. Examinați câmpurile care definesc noul dvs. segment. Aceste câmpuri definesc baza pe care sistemul va încerca să găsească clienți similari cu segmentul dvs. sursă. Sistemul selectează în mod implicit câmpurile recomandate. Dacă este necesar, adăugați mai multe câmpuri.
  Câmpurile care pot reduce semnificativ performanța modelului sunt excluse automat:
  
   - Câmpuri cu următoarele tipuri de date: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Câmpuri cu o cardinalitate (numărul de elemente dintr-un câmp) mai mică de 2 sau mai mare de 30

1. Alegeți dacă doriți să includeți **Toți clienții** cu excepția segmentului sursă sau numai clienții din a **segment diferit** în noul tău segment.

1. În mod implicit, sistemul sugerează să includeți doar 20% din mărimea publicului țintă în rezultatul dvs. Editați acest prag în funcție de necesități. Creșterea pragului va reduce precizia.

1. Includeți clienții în segmentul sursă selectând **Includeți membri din segmentul sursă pe lângă clienții cu atribute similare** Caseta de bifat.

1. Selectați **Alerga** în partea de jos a paginii pentru a începe a [sarcină de clasificare binară](#about-similarity-scores) (o metodă de învățare programată) care analizează setul de date.

## <a name="view-the-similar-segment"></a>Vizualizați segmentul similar

După procesarea segmentului similar, veți găsi noul segment listat pe **Segmente** pagina cu tipul **Expansiune**.

Selectați **Vedere** pentru a vedea distribuția rezultatelor [scoruri de similaritate](#about-similarity-scores) și valorile scorului de similaritate sub **Previzualizarea membrilor segmentului**.

:::image type="content" source="media/expanded-segment.png" alt-text="Segment de clienți similar.":::

## <a name="manage-a-similar-segment"></a>Gestionați un segment similar

[Lucrați și gestionați un segment similar](segments.md#manage-existing-segments) asa cum faci cu alte segmente. De exemplu, exportați segmentul sau construiți o măsură.

Editați, reîmprospătați, redenumiți, descărcați și ștergeți un segment similar. Editarea unui segment similar vă reprocesează datele. Segmentul creat anterior este actualizat cu datele reîmprospătate.

## <a name="about-similarity-scores"></a>Despre scoruri de similaritate

Modelul învățare programată a clasificării binare atribuie un scor clienților din segmentul similar. Scorul se bazează pe similaritatea cu clienții din segmentul sursă.

- Scorurile de similaritate sub 0,55 cuprinde clienții din sistemul clasificat ca *nesimilar* al clienților din segmentul sursă
- Scorurile de similaritate între 0,55 - 0,7 sunt clasificate ca fiind *oarecum similar*
- Scorurile de similaritate între 0,7 - 0,85 sunt clasificate ca fiind *similar*
- Scorurile de similaritate între 0,85 - 1 sunt clienții pe care sistemul îi clasifică drept *foarte similari*

Clienții cu scoruri de similaritate sub 0,4 nu sunt incluși în rezultatul modelului. Sistemul nu îi consideră suficient de similari cu segmentul sursă.

[!INCLUDE [footer-include](includes/footer-banner.md)]
