---
title: Găsiți clienți similari cu AI
description: Găsiți segmente de clienți similare cu inteligență artificială.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: b9b2e7fa862b595c6a364a7208e42295b4f9df83
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268885"
---
# <a name="similar-customers-preview"></a>Clienți similari (previzualizare)

Această caracteristică vă permite să găsiți clienți similari în baza de clienți utilizând inteligența artificială. Trebuie să aveți cel puțin un segment creat pentru a utiliza această caracteristică. Extinderea criteriilor unui segment existent vă ajută să găsiți clienți similari cu acel segment.

> [!NOTE]
> *Găsiți clienți similari* utilizează mijloace automate pentru a evalua datele și a face predicții pe baza acestor date și, prin urmare, are capacitatea de a fi utilizat ca metodă de profilare, deoarece acest termen este definit prin Regulamentul general privind protecția datelor („GDPR”). Utilizarea acestei funcții de către client pentru prelucrarea datelor poate fi supusă RGPD sau altor legi sau reglementări. Sunteți responsabil pentru a vă asigura că utilizarea de către dvs. a Dynamics 365 Customer Insights, inclusiv predicțiile, respectă toate legile și reglementările aplicabile, inclusiv legile legate de confidențialitate, date cu caracter personal, date biometrice, protecția datelor și confidențialitatea comunicărilor.

## <a name="finding-similar-customers"></a>Găsirea unor clienți similari

1. În Detalii despre audiență, accesați **Segmente** și selectați segmentul pe care doriți să vă bazați noul segment. Acesta este *segmentul sursă* al dvs.

1. În bara de acțiuni, selectați **Găsiți clienți similari**.

1. Examinați numele sugerat pentru noul segment și schimbați-l dacă este necesar.

1. Examinați câmpurile care definesc noul dvs. segment. Aceste câmpuri definesc baza pe care sistemul va încerca să găsească clienți similari cu segmentul dvs. sursă. În mod implicit, sistemul va selecta câmpurile recomandate.
  Câmpurile care pot reduce semnificativ performanța modelului sunt excluse automat:
  
   - Câmpuri cu următoarele tipuri de date: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Câmpuri cu o cardinalitate (numărul de elemente dintr-un câmp) mai mică de 2 sau mai mare de 30

1. Alegeți dacă doriți să includeți **Toți clienții** sau numai clienții dintr-un **Segment specific existent** în noul dvs. segment.

1. Excludeți clienții din segmentul sursă selectând caseta de selectare **Excludeți pe toți din segmentul sursă**.

1. În mod implicit, sistemul sugerează să includeți doar 20% din mărimea publicului țintă în rezultatul dvs. Editați acest prag în funcție de necesități. Creșterea pragului va reduce precizia.

1. Selectați **Rulează** în partea de jos a paginii pentru a începe o sarcină de clasificare binară (o metodă a învățare programată) care analizează setul de date.

## <a name="view-the-similar-segment"></a>Vizualizați segmentul similar

După procesarea segmentului similar, veți găsi noul segment listat pe pagina **Segmente**.

> [!div class="mx-imgBorder"]
> ![Segment de clienți similar](media/expanded-segment.png "Segment de clienți similar")

Selectați **Vizualizare** în bara de acțiuni pentru a deschide detaliile segmentului. Această vizualizare conține informații despre distribuția rezultatelor în cadrul [scorurilor de similaritate](#about-similarity-scores). De asemenea, veți găsi valorile scorului de similaritate în **Previzualizarea membrilor segmentului**.

## <a name="use-the-output-of-a-similar-segment"></a>Utilizați rezultatul unui segment similar

Puteți [lucra cu rezultatul unui segment similar](segments.md) așa cum faceți cu alte segmente. De exemplu, exportați segmentul sau construiți o măsură.

## <a name="refresh-and-edit-a-similar-segment"></a>Reîmprospătați și editați un segment similar

Pentru a reîmprospăta un segment similar, selectați-l pe pagina **Segmente** și selectați **Reîmprospătare** în bara de acțiune.

Editarea unui segment similar va reprocesa datele dumneavoastră. Segmentul creat anterior este actualizat cu datele reîmprospătate.    
Pentru a edita un segment similar, selectați-l pe pagina **Segmente** și selectați **Editare** în bara de acțiune. Aplicați modificările și selectați **Rulează** pentru a începe procesarea.

## <a name="delete-a-similar-segment"></a>Ștergeți un segment similar

Selectați segmentul de pe pagina **Segmente** și selectați **Ștergeți** în bara de acțiune. Apoi, confirmați ștergerea.

## <a name="about-similarity-scores"></a>Despre scoruri de similaritate

Modelul învățare programată a clasificării binare atribuie un scor clienților din segmentul similar. Scorul se bazează pe similaritatea cu clienții din segmentul sursă.

- Scorurile de similaritate sub 0,55 cuprinde clienții din sistemul clasificat ca *nesimilar* al clienților din segmentul sursă
- Scorurile de similaritate între 0,55 - 0,7 sunt clasificate ca fiind *oarecum similar*
- Scorurile de similaritate între 0,7 - 0,85 sunt clasificate ca fiind *similar*
- Scorurile de similaritate între 0,85 - 1 sunt clienții pe care sistemul îi clasifică drept *foarte similari*

Clienții cu scoruri de similaritate sub 0,4 nu sunt incluși în rezultatul modelului. Sistemul nu îi consideră suficient de similari cu segmentul sursă.


[!INCLUDE[footer-include](../includes/footer-banner.md)]