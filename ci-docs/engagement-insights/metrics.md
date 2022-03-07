---
title: Vizualizați și creați măsurători
description: Cum să creați, să editați și să ștergeți măsurători.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7e8c96f38af74f25080a40fd92e73f05c71320a8
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229831"
---
# <a name="view-and-create-metrics"></a>Vizualizați și creați măsurători

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Măsurătorile vă ajută să înțelegeți comportamentul vizitatorilor dvs. Ele agreghează proprietățile evenimentului și măsoară statisticile și performanța proprietăților dvs. web.  

Să presupunem că derulați o promoție de marketing pe site-ul dvs. web. Puteți utiliza măsurători pentru a urmări numărul de vizitatori unici sau de utilizatori care au venit pe site-ul dvs. în timpul promoției. Analiza măsurătorilor vă ajută să înțelegeți mai bine publicul site-ului dvs. Combinarea măsurătorilor cu [dimensiuni](dimensions.md) pe un [raport personalizat](custom-reports.md) vă permite să măsurați comportamentul pentru a vă înțelege utilizatorii. De exemplu, puteți separa vizitatorii în categorii noi și recurente pentru a identifica diferențele de interes și intenție dintre grupuri.

## <a name="view-metrics"></a>Vizualizați măsurătorile

Detaliile despre angajamentele includ agregări utilizate în mod obișnuit de proprietăți ale evenimentelor ca măsurători ale sistemului: 

- Vizitatori
- Vizite
- Vizualizări de pagini
- Clicuri

Aceste măsurători de sistem se bazează pe proprietățile evenimentelor existente în evenimentele de bază.

1. În panoul de navigare din stânga, accesați **Date**. 
1. Selectați **Măsurători** pentru a vedea o listă cu toate valorile din spațiul de lucru. 
   > [!NOTE]
   > Măsurătorile generate de sistem sunt numai în citire. Nu le puteți edita sau șterge. Puteți crea și edita numai măsurători personalizate.

## <a name="create-a-metric"></a>Creați o măsurătoare

Administratorii de mediu și spațiul de lucru pot crea măsurători. Proprietățile evenimentului trebuie trimise în spațiul de lucru înainte de a crea o măsurătoare. Puteți crea măsurători pe baza proprietăților evenimentelor care sunt trimise de evenimente de bază sau puteți utiliza SDK-ul web pentru a [trimite proprietăți de eveniment personalizate](advanced-SDK-implementation.md).

1. Accesați **Date** > **Măsurători**.
1. Selectați **Măsurătoare nouă** pentru a deschide **Biblioteca de resurse** și caseta de dialog **Nouă măsurătoare fără titlu**.

   :::image type="content" source="media/new-metric.png" alt-text="Adăugați o măsurătoare la un eveniment.":::

1. În caseta de dialog **Nouă măsurătoare fără titlu**, selectați lista derulantă **Format** și alegeți tipul de date **Întreg** sau **Dublu** . Întreg este un număr întreg. Pentru Dublu, puteți alege una și trei zecimale.

   :::image type="content" source="media/create-new-metric.png" alt-text="Creați o măsurătoare nouă.":::
   
5. În panoul **Biblioteca de resurse**, găsiți proprietatea evenimentului pe care se bazează măsurătoarea.
6. Selectați **semnul plus (+)** lângă proprietate pentru a o folosi în formulă. Puteți crea o formulă numai pe baza unei singure proprietăți. 
7. Alegeți una dintre următoarele funcții agregate. 

   - Sumă: totalul aritmetic al tuturor valorilor 
   - Media: valoarea medie a tuturor valorilor
   - Număr: numărul total de valori
   - Număr de valori unice: numărul total de valori unice

   După definirea măsurătorii, vedeți o previzualizare a activității măsurătorii pentru ultima oră.

1. Selectați **Salvare**. 
1. Introduceți un nume pentru măsurătoare și apoi selectați **Salvați**.

Poate dura până la un minut pentru o măsurătoare înainte de a o putea folosi [creați rapoarte personalizate](custom-reports.md).

## <a name="edit-a-metric"></a>Editați o măsurătoare

Puteți edita numai măsurători particularizate.

1. Accesați **Date** > **Măsurători**.
1. Selectați măsurătoarea din listă.
1. Schimbați definiția măsurătoarei
1. Selectați **Salvare**.

## <a name="change-the-name-of-a-metric"></a>Modificați numele unei măsurători

Puteți schimba doar numele măsurătorilor personalizate.

1. Accesați **Date** > **Măsurători**.
1. Selectați **Mai mult [...]** pentru o măsurătoare și alegeți **Editați numele**.
1. Schimbați numele. 
1. Selectați **Redenumiți**.

## <a name="delete-a-metric"></a>Ștergeți o măsurătoare

Puteți doar să ștergeți măsurători particularizate.

1. Accesați **Date** > **Măsurători**.
1. Selectați **Mai mult [...]** pentru o măsurătoare și alegeți **Ștergeți**.

   :::image type="content" source="media/delete-metric.png" alt-text="Ștergeți o măsurătoare la un eveniment.":::

1. Selectați **Ștergere**, apoi confirmați ștergerea.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
