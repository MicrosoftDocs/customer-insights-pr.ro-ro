---
title: Îmbogățirea profilurilor companiei cu îmbogățirea terță parte Leadspace
description: Informații generale despre îmbogățirea terță parte Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668738"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Îmbogățirea profilurilor companiei cu Leadspace (previzualizare)

Leadspace este o companie de știință a datelor care oferă o platformă de date pentru clienți B2B. Aceasta permite clienților cu profiluri de clienți unificate pentru companii să-și îmbogățească datele. Îmbogățirile includ atribute suplimentare cum ar fi dimensiunea firmei, locația, domeniul de activitate și multe altele.

## <a name="prerequisites"></a>Cerințe preliminare

Pentru a configura Leadspace, trebuie îndeplinite următoarele cerințe preliminare:

- Aveți o licență Leadspace activă și „cheia perpetuă” (denumită **Token Leadspace**). Contactați direct [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) pentru detalii despre produsul lor.
- Aveți permisiuni de [Administrator](permissions.md#administrator).
- Aveți [profiluri de clienți unificate](customer-profiles.md) pentru companii.

## <a name="configuration"></a>Configurație

1. În Detalii despre audiență, accesați **Date** > **Îmbogățire**.

1. Selectați **Doresc îmbogățirea datelor** pe dala Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captură de ecran a dalei Leadspace.":::

1. Selectați **Începeți** și apoi introduceți un **token Leadspace** activ (cheie perpetuă). Analizați și acordați-vă consimțământul pentru **Confidențialitatea și conformitatea datelor** prin selectarea casetei de selectare **Sunt de acord**. Confirmați ambele intrări selectând **Conectați-vă la Leadspace**.

1. Selectați **Date cartografice** și definiți ce câmpuri din profilurile dvs. unificate ar trebui utilizate pentru a căuta datele companiei potrivite din Leadspace. Câmpul **Numele companiei** este obligatoriu. Pentru o precizie mai mare a potrivirii, până la două alte câmpuri, **Site-ul companiei** și **Locația companiei**, pot fi adăugate.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panoul de mapare a câmpului Leadspace.":::
   
1. Selectați **Aplicare** pentru a finaliza maparea câmpului.

1. Selectați **Rulare** pentru a îmbogăți profilurile companiei. Cât durează o îmbogățire depinde de numărul de profiluri unificate ale clienților.

## <a name="enrichment-results"></a>Rezultate de îmbogățire

După reîmprospătarea îmbogățirii, puteți examina datele companiei nou îmbogățite sub [Îmbogățirile mele](enrichment-hub.md). Puteți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.

Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.

Pentru informații suplimentare, consultați [API-uri Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Pașii următori

Creați în plus față de datele îmbogățite ale clienților. Creați [segmente](segments.md), [măsuri](measures.md) și chiar [exportați datele](export-destinations.md) pentru a oferi experiențe personalizate clienților.

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Leadspace, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Leadspace îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.