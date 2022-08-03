---
title: Creați segmente simple cu segmente rapide
description: Creați segmente simple de clienți pentru a le grupa pe baza diferitelor atribute.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171163"
---
# <a name="create-simple-segments-with-quick-segments"></a>Creați segmente simple cu segmente rapide

Segmentele rapide permit crearea de segmente simple cu un singur operator rapid pentru informații mai rapide. Segmentele rapide sunt acceptate numai în medii pentru **clienți individuali**.

## <a name="create-a-new-segment-with-quick-segments"></a>Creați un nou segment cu segmente rapide

1. Mergeți la **Segmente**.

1. Selectați **Nou** > **Creați din**.
   - Selectați opțiunea **Profiluri** pentru a construi un segment care se bazează pe entitatea *Client unificat*.
   - Selectați opțiunea **Măsuri** pentru a construi un segment în jurul măsurilor pe care le-ați creat înainte.
   - Selectați opțiunea **Inteligență** pentru a construi un segment în jurul uneia dintre entitățile de ieșire pe care le-ați generat folosind fie capabilități **Predicții** sau **Modele particularizate**.

1. În caseta de dialog **Segment rapid nou**, selectați un atribut din lista verticală **Câmp**. Pe baza selecției dvs., sistemul oferă valori diferite.
   - Pentru câmpurile categorice, se afișează cei mai buni 10 clienți. Alegeți o **Valoare** și selectați **Revizuire**.
   - Pentru un atribut numeric, sistemul arată ce valoare a atributului se încadrează sub percentila fiecărui client. Alegeți un **Operator** și o **Valoare**, apoi selectați **Revizuire**.

1. Sistemul oferă un **Dimensiunea estimată a segmentului**. Alegeți dacă doriți să generați segmentul pe care l-ați definit sau reveniți pentru a alege un alt câmp.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Numele și estimarea pentru un segment rapid.":::

1. Furnizeaza un **Nume** și **Numele entității de ieșire** pentru segmentul dvs. Opțional, adăugați [Etichete](work-with-tags-columns.md#manage-tags).

1. Selectați **Salvare** pentru a crea segmentul. The **Segmente** afișează pagina.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Pașii următori

[Exportați un segment](export-destinations.md) și explorați [Integrarea Cardului Clientului](customer-card-add-in.md) pentru a utiliza segmente în alte aplicații.

[!INCLUDE [footer-include](includes/footer-banner.md)]
