---
title: Creați și modificați evenimente selectate
description: Cum să creați și modificați evenimente selectate.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034789"
---
# <a name="create-and-modify-refined-events"></a>Creați și modificați evenimente selectate

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Un eveniment reprezintă date care reprezintă comportamentul utilizatorilor, cum ar fi activitatea pe un site web.

- O înregistrare de eveniment de *bază* atunci când un utilizator vizualizează o pagină (vizualizare eveniment) sau interacționează cu conținutul (eveniment de acțiune).
- Un eveniment *rafinat* este o vizualizare virtuală a unui eveniment de bază. Definiți evenimente rafinate prin eliminarea și adăugarea de proprietăți sau prin filtrarea evenimentelor pe baza valorilor proprietăților.

Utilizați evenimente rafinate pentru a reduce scopul unui eveniment de bază pentru [export](export-events.md) sau pentru a elimina proprietățile care nu sunt necesare expunerii.

## <a name="create-refined-events"></a>Creați evenimente rafinate

Există trei moduri de a crea un eveniment rafinat dintr-un eveniment de bază. 

1. Accesați **Date**> **Evenimente** și alegeți una dintre următoarele opțiuni:
    - Selectați **Evenimente noi** și apoi selectați **Creați evenimente rafinate**.
    - Selectați un eveniment de bază pentru a deschide o vizualizare detaliată și selectați **Creați evenimente rafinate** din meniul de sus.
    - Selectați **Mai mult [...]** pentru a deschide meniul de comenzi rapide pentru un eveniment de bază. Apoi selectați **Creați evenimente rafinate**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Opțiuni pentru a crea evenimente rafinate.":::

1. În caseta de dialog **Creați evenimente rafinate**, introduceți următoarele informații:

- Selectați un eveniment din lista verticală **Evenimente de bază** dacă creați un eveniment nou.
- Introduceți un nume în caseta **Numele afișat al evenimentelor rafinate**.
- Opțional, actualizați sugestia **Numele real** fără a folosi spații.

3. Selectați **Creați** pentru a aplica setările.

1. În vizualizarea detaliată a evenimentului dvs. rafinat, selectați **Adăugați și eliminați proprietăți** pentru a deschide panoul **Editați proprietățile**. 

1. Utilizați casetele de selectare pentru a selecta proprietățile pe care doriți să le afișați și cele pe care doriți să le ascundeți. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Editați proprietățile pentru evenimente rafinate.":::

1. Selectați **Confirmare** pentru a aplica selecția dvs.

1. Selectați **Salvare** pentru a salva configurația.

## <a name="edit-refined-events"></a>Editați evenimente rafinate

Puteți schimba numele și proprietățile unui eveniment rafinat.

### <a name="edit-event-name"></a>Editați numele evenimentului

1. Accesați **Date** > **Evenimente**. 
1. Selectați **Mai mult [...]** pentru un eveniment și selectați **Editați numele**.
1. Actualizați numele evenimentului și selectați **Redenumiți**.

### <a name="edit-selected-properties"></a>Editați proprietățile selectate

1. Accesați **Date** > **Evenimente** și selectați evenimentele rafinate pentru a deschide vizualizarea detaliată.
1. Selectați **Adăugați și eliminați proprietăți**. 
1. Editați selecția casetelor de selectare.
1. Selectați **Confirmați** și apoi **Salvați** pentru a aplica modificările.

Pentru informații despre exportul evenimentelor, consultați [Exportați evenimente](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
