---
title: Îmbogățirea datelor de identitate LiveRamp
description: Îmbogățiți profilurile clienților cu date LiveRamp.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0727818f6df565d9a031966a68d521ae7167e484
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643190"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Îmbogățiți profilurile clienților cu date de identitate din LiveRamp (Previzualizare) 

LiveRamp oferă rezoluție deterministă a identității offline și consolidarea datelor clienților. Puteți mapa identificatorii personali din datele clienților dvs. la graficul de identitate AbiliTec și puteți primi ID-uri AbiliTec. Apoi puteți utiliza aceste ID-uri pentru o mai bună unificare a datelor clienților dvs. 

## <a name="prerequisites"></a>Cerințe preliminare 

Pentru a configura îmbogățirea, trebuie îndeplinite următoarele cerințe preliminare: 

- Aveți un abonament activ LiveRamp. Pentru a obține un abonament, contactați echipa de cont LiveRamp sau la [dynamics@liveramp.com](mailto:dynamics@liveramp.com) pentru mai multe informatii.   

- Un abonament AbiliTec activ cu un ID de client și un secret pentru a accesa API-ul. Pentru mai multe informații, vezi [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Țări / regiuni acceptate 

În prezent, acceptăm îmbogățirea profilurilor clienților cu date LiveRamp numai în Statele Unite. 

## <a name="configure-the-enrichment"></a>Configurați îmbogățirea 

1. Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**. 

1. Selectați **Îmbogățiți-mi datele** pe **Identitate** ţiglă. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Dală identitate în pagina de prezentare generală a îmbogățirii.":::

1. Selectați o [conexiune](connections.md) din lista derulantă. Contactați un administrator dacă nu este disponibilă nicio conexiune. Dacă sunteți administrator, puteți crea o conexiune selectând **Adăugați conexiune**. Alege **LiveRamp** din lista derulantă. 

1. Selectați **Următorul** și alegeți **Set de date despre client** doriți să vă îmbogățiți cu datele de identitate de la LiveRamp. Puteți selecta *Client* entitate pentru a vă îmbogăți toate profilurile de clienți sau selectați a *segment* entitate să îmbogățească numai profilurile clienților conținute în acel segment. 

1. Selectați **Următorul** și definiți ce tip de câmpuri din profilurile dvs. unificate ar trebui utilizate pentru a căuta datele de identitate care se potrivesc din LiveRamp. Cel puțin unul dintre câmpuri **Nume si adresa**, **·**, sau **E-mail** este necesară. 

   > [!TIP]
   > Cu cât mapați mai mulți identificatori cheie și câmpuri, cu atât este mai probabilă o rată de potrivire mai mare 

1. Hartați câmpurile din unitatea dvs *Client* entitate care va fi utilizată pentru potrivirea cu graficul AbiliTec ID LiveRamp. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opțiuni de mapare a datelor pentru îmbogățirea LiveRamp.":::

1. Selectați **Următorul** pentru a completa maparea câmpului. 

1. Furnizeaza un **Nume** pentru îmbogățire și pentru **Entitate de ieșire**. 

1. Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile. 

## <a name="configure-the-connection-for-liveramp"></a>Configurați conexiunea pentru LiveRamp 

Trebuie să fii administrator [configurați conexiunile](connections.md). Selectați **Adăugați conexiune** la configurarea îmbogățirii sau accesați **Admin** > **Conexiuni** și selectați **Înființat** pe **LiveRamp** ţiglă. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Panoul de configurare pentru a configura conexiunea la serviciul LiveRamp AbiliTec.":::

1. Pentru **Numele afisat**, introduceți numele conexiunii. 

1. Furnizați un ID de client LiveRamp valid și un secret. 

1. Analizați și acordați-vă consimțământul pentru **Confidențialitatea și conformitatea datelor** prin selectarea casetei de selectare **Sunt de acord**. 

1. Selectați **Verificare** pentru a valida configurația. 

1. Pentru a finaliza conexiunea, selectați **salva**. 

## <a name="enrichment-results"></a>Rezultate de îmbogățire 

Pentru a începe procesul de îmbogățire, selectați Executare din bara de comandă. De asemenea, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unui [reîmprospătare programată](system.md#schedule-tab). Timpul de procesare depinde de dimensiunea datelor clienților dvs. 

După finalizarea procesului de îmbogățire, puteți examina datele profilurilor clienților nou îmbogățite în **Îmbogățirile mele**. În plus, veți găsi ora ultimei actualizări și numărul de profiluri îmbogățite. 

Puteți accesa o vizualizare detaliată a fiecărui profil îmbogățit selectând **Vizualizare îmbogățită** date. 

## <a name="next-steps"></a>Pașii următori

Creați în plus față de datele îmbogățite ale clienților. Utilizați ID-urile AbiliTec pentru a consolida profilurile clienților într-o vizualizare bazată pe persoană. 
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor 

Când activați Dynamics 365 Customer Insights pentru a transmite date către LiveRamp, permiteți transferul de date în afara limitei de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele personale. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru a vă asigura că LiveRamp îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru mai multe informații, consultați [Declarație de confidențialitate Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Administratorul Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități. 


[!INCLUDE [footer-include](includes/footer-banner.md)]
