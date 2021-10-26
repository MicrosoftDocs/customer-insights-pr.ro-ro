---
title: Vizualizați și creați dimensiuni
description: Cum se creează, se editează și se șterg dimensiunile.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 136da1e1265c7087d861712d34d011b09cb60ad5
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623647"
---
# <a name="view-and-create-dimensions"></a>Vizualizați și creați dimensiuni

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

O dimensiune este un atribute pentru un eveniment care poate descrie, filtra sau grupa date. Dacă desfășurați o promoție de marketing pe site-ul dvs. web, puteți utiliza dimensiunile pentru a sorta vizitatorii după utilizatorii noi și recenți.  

Detaliile despre angajamente includ dimensiuni predefinite (OOB) pentru proprietățile evenimentului. Exemplele includ:

- Nume de browser
- Nume de pagină
- Model dispozitiv
- Sistem de operare
- Țara

## <a name="view-dimensions"></a>Vizualizați dimensiunile

Dimensiunile se bazează pe proprietățile evenimentelor existente. Când utilizați codul de urmărire pentru detaliile despre angajamente, dimensiunile sistemului sunt create automat.

1. În panoul de navigare din stânga, accesați **Date**. 
1. Selectați **Dimensiuni** pentru a vedea o listă cu toate dimensiunile din spațiul de lucru. 
   > [!NOTE]
   > Dimensiunile generate de sistem sunt numai în citire. Nu le puteți edita. Puteți crea și edita doar dimensiuni personalizate.

## <a name="create-a-dimension"></a>Crearea unei dimensiuni

Pe lângă dimensiunile generate de sistem, administratorii de mediu și de spațiu de lucru pot crea dimensiuni personalizate. Dimensiunile particularizate se bazează pe proprietățile implicite ale evenimentelor de bază sau pot fi utilizate [proprietățile personalizate ale unui eveniment](advanced-SDK-implementation.md).

1. Accesați **Date** > **Dimensiuni**.
1. Selectați **Dimensiune nouă**.

   :::image type="content" source="media/add-dimension.png" alt-text="Adăugați o dimensiune unui eveniment.":::

1. În **Creați o dimensiune**, selectați o proprietate pentru a o utiliza ca bază a dimensiunii. Lista de proprietăți va afișa toate proprietățile din spațiul de lucru neatribuite unei dimensiuni.
   
   :::image type="content" source="media/create-new-dimension.png" alt-text="Crearea unei noi dimensiuni.":::
      
3. Introduceți un nume în caseta **Nume afișat**. Opțional, puteți adăuga o **Descriere**.
4. Selectați **Creați** pentru a salva dimensiunea. Poate dura până la un minut înainte de a putea utiliza dimensiunea într-un [raport particularizat](custom-reports.md) sau [segment](segments.md). 

## <a name="edit-a-dimension"></a>Editați o dimensiune

Puteți schimba numele și descrierea unei dimensiuni. Puteți edita numai dimensiunile create de utilizator, dar nu puteți edita dimensiunile sistemului.


1. Accesați **Date** > **Dimensiuni**.
1. Selectați dimensiunea pe care doriți să îl ștergeți.
1. În **Editați dimensiunea**, actualizați dimensiunea.
1. Selectați **Aplicați** pentru a vă salva modificările.

## <a name="delete-a-dimension"></a>Ștergeți o dimensiune

Puteți șterge doar dimensiunile create de utilizator, dar nu puteți elimina dimensiunile sistemului.

Ștergerea unei dimensiuni este permanentă. Rapoartele și segmentele care utilizează un parametru șters nu vor mai funcționa. 

1. Accesați **Date** > **Dimensiuni**.
1. Selectați dimensiunea pe care doriți să îl ștergeți.
1. În **Editați dimensiunea**, selectați **Ștergeți dimensiunea**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Ștergeți o dimensiune unui eveniment.":::

1. Introduceți **CONFIRMARE ȘTERGERE** (în majuscule) pentru a confirma ștergerea. 
1. Selectați **Ștergere**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
