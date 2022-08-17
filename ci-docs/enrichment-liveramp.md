---
title: Îmbogățiți profilurile clienților cu date de identitate din LiveRamp (previzualizare)
description: Îmbogățiți profilurile clienților cu date LiveRamp.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0aa6dc144602741b87843a5373779855ee3e334c
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237828"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Îmbogățiți profilurile clienților cu date de identitate din LiveRamp (previzualizare)

LiveRamp oferă rezoluție deterministă a identității offline și consolidarea datelor clienților. Puteți mapa identificatorii personali din datele clienților dvs. la graficul de identitate AbiliTec și puteți primi ID-uri AbiliTec. Puteți utiliza apoi aceste ID-uri pentru o mai bună unificare a datelor clienților dvs.

## <a name="supported-countriesregions"></a>Țări / regiuni acceptate

În prezent, acceptăm îmbogățirea profilurilor clienților cu date LiveRamp numai în Statele Unite.

## <a name="prerequisites"></a>Cerințe preliminare

- Un abonament activ LiveRamp. Pentru a obține un abonament, contactați echipa de cont LiveRamp sau la [dynamics@liveramp.com](mailto:dynamics@liveramp.com) pentru mai multe informatii.

- Un abonament AbiliTec activ cu un ID de client și un secret pentru a accesa API-ul. Pentru mai multe informații, vezi [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/).

- Un LiveRamp [conexiune](connections.md) este [configurat](#configure-the-connection-for-liveramp) de către un administrator.

## <a name="configure-the-connection-for-liveramp"></a>Configurați conexiunea pentru LiveRamp

Trebuie să fii un [administrator](permissions.md#admin) în Customer Insights și au un ID de client și un secret LiveRamp activ.

1. Selectați **Adăugați conexiune** când configurați o îmbogățire sau accesați **Admin** > **Conexiuni** și selectați **Înființat** pe țigla LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Panoul de configurare pentru a configura conexiunea la serviciul LiveRamp AbiliTec.":::

1. Introduceți un nume pentru conexiune și un ID de client LiveRamp valid și un secret.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Verifica** pentru a valida configurația și apoi selectați **Salvați**.

## <a name="configure-the-enrichment"></a>Configurați îmbogățirea

1. Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**.

1. Selectați **Îmbogățiți-mi datele** pe **Identitate** din țiglă LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Dală de identitate în pagina de prezentare generală a îmbogățirii.":::

1. Examinați prezentarea generală și apoi selectați **Următorul**.

1. Selectați conexiunea. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Selectați **Următorul**.

1. Selectează **Set de date despre client** și alegeți profilul sau segmentul pe care doriți să îl îmbogățiți cu date de identitate din LiveRamp. The *Client* entitate îmbogățește toate profilurile dvs. de clienți, în timp ce un segment îmbogățește numai profilurile de clienți conținute în acel segment.

1. Definiți ce tip de câmpuri din profilurile dvs. unificate să utilizați pentru potrivirea datelor de identitate din LiveRamp. Cel puțin unul dintre câmpuri **Nume și adresa**, **-mail**, sau **Telefon** este necesară. Pentru o precizie mai mare a potrivirii, adăugați alte câmpuri. Selectați **Următorul**.

1. Hartați câmpurile cu datele de identificare din LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opțiuni de mapare a datelor pentru îmbogățirea LiveRamp.":::

1. Selectați **Următorul** pentru a completa maparea câmpului.

1. Furnizeaza un **Nume** pentru îmbogățire și pentru **Numele entității de ieșire**.

1. Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.

1. Selectați **Alerga** pentru a începe procesul de îmbogățire sau aproape pentru a reveni la **Îmbogățiri** pagină.

## <a name="view-enrichment-results"></a>Vedeți rezultatele îmbogățirii

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

The **Număr de clienți îmbogățiți pe domeniu** oferă o detaliere a acoperirii fiecărui câmp îmbogățit.

## <a name="next-steps"></a>Pașii următori

Creați în plus față de datele îmbogățite ale clienților. Utilizați ID-urile AbiliTec pentru a consolida profilurile clienților într-o vizualizare bazată pe persoană.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
