---
title: Creați și modificați evenimente
description: Cum să creați și să modificați evenimente.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 935dc4cd41218842e8406b747daef47de04e337a
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606256"
---
# <a name="create-and-modify-events"></a>Creați și modificați evenimente

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un eveniment reprezintă date care reprezintă comportamentul utilizatorilor, cum ar fi activitatea pe un site web.

- O înregistrare de eveniment de *bază* atunci când un utilizator vizualizează o pagină (vizualizare eveniment) sau interacționează cu conținutul (eveniment de acțiune).
- Un eveniment *rafinat* este o vizualizare virtuală a unui eveniment de bază. Definiți evenimente rafinate prin eliminarea și adăugarea de proprietăți sau prin filtrarea evenimentelor pe baza valorilor proprietăților.

## <a name="prerequisites"></a>Cerințe preliminare

Pentru a obține evenimentele, datele site-ului dvs. web trebuie să fie conectate mai întâi la detaliile de angajament cu ajutorul unui fragment de cod. Pentru mai multe informații, consultați [Instalați SDK-ul web pe un site web](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Conectați-vă datele mai întâi.":::

## <a name="create-refined-events"></a>Creați evenimente rafinate

Utilizați evenimente rafinate pentru a reduce scopul unui eveniment de bază pentru [export](export-events.md) sau pentru a elimina proprietățile care nu sunt necesare expunerii.

> [!NOTE]
> După ce adăugați kitul SDK web pe site-ul dvs. web, puteți vizualiza evenimentele de bază și puteți crea evenimente rafinate. 

Pentru a vizualiza evenimentele de bază:

1. În panoul de navigare din stânga, accesați **Date**.

1. Selectați **Evenimente** pentru a vedea o listă a tuturor evenimentelor din spațiul de lucru.

    :::image type="content" source="media/data-events.png" alt-text="Vizualizați evenimente.":::

Pentru a crea un eveniment rafinat dintr-un eveniment de bază: 

1. Accesați **Dată** > **Evenimente** și selectați **+ Evenimente noi** în partea de sus a ecranului.

1. În caseta de dialog **Evenimente noi**, selectați **Creați evenimente rafinate** și apoi selectați **Următorul**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Expert evenimente noi.":::
     
1. În caseta de dialog **Evenimente noi**, introduceți următoarele informații:

   - Selectați un eveniment din lista derulantă **Evenimente de bază**.
   - Introduceți un nume în caseta **Numele afișat al evenimentelor rafinate**.
   - Opțional, actualizați sugestia **Numele real** fără a folosi spații.

1. Selectați **Creați** pentru a aplica setările.

Evenimentul rafinat apare acum în lista **Evenimente**.

### <a name="edit-event-name"></a>Editați numele evenimentului

Puteți modifica numele și proprietățile unui eveniment de bază sau rafinat.

1. Accesați **Date** > **Evenimente**. 

1. Selectați **Mai mult [...]** pentru un eveniment și selectați **Editați numele**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Opțiuni pentru a crea evenimente rafinate.":::

3. Actualizați numele evenimentului și selectați **Redenumiți**.

### <a name="view-the-details-of-a-refined-event"></a>Vizualizați detaliile unui eveniment rafinat:

1. În lista **Eveniment**, selectați-vă evenimentul de bază sau rafinat. 

1. Selectați **Adăugați și eliminați proprietăți** în partea de sus a ecranului pentru a deschide panoul **Editați proprietățile**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Adăugați și eliminați proprietăți.":::

1. Utilizați casetele de selectare pentru a selecta proprietățile pe care doriți să le afișați și cele pe care doriți să le ascundeți. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Editați proprietățile pentru evenimente rafinate.":::

1. Selectați **Confirmați** pentru a aplica selecția, apoi selectați **Salvați**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Editați proprietățile selectate pentru un eveniment rafinat

1. Accesați **Date** > **Evenimente** și selectați evenimentele rafinate pentru a deschide vizualizarea detaliată.
1. Selectați **Adăugați și eliminați proprietăți**. 
1. Editați selecția casetelor de selectare.
1. Selectați **Confirmați** și apoi **Salvați** pentru a aplica modificările.

Pentru informații despre exportul evenimentelor, consultați [Exportați evenimente](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
