---
title: Mapări semantice (versiune preliminară)
description: Prezentare generală a mapărilor semantice și modul de utilizare a acestora.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 8780c11c8b091717349f0fd75a36b99c3a63ab49
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303891"
---
# <a name="semantic-mappings-preview"></a>Mapări semantice (versiune preliminară)

> [!NOTE]
> The **Mapări semantice** pagina este disponibilă numai pentru mediile de afaceri (B-to-B) în care profilurile de contact au fost deja create folosind această pagină. Puteți continua să creați și să gestionați profilurile individuale de contact utilizând **Mapări semantice** pagină. Sau, [unificați datele dvs. de contact](data-unification-contacts.md) pentru a elimina duplicatele, a identifica potrivirile între entități și a crea un profil de contact unificat. Puteți utiliza apoi profilul de contact unificat pentru a crea activități la nivel de contact.

Asocierile semantice vă permit să vă mapați datele de non-activitate în scheme predefinite. Aceste scheme ajută Customer Insights să vă înțeleagă mai bine atributele datelor. Maparea semantică și datele furnizate permit noi perspective și funcții în Customer Insights. Pentru a vă mapa datele de activitate cu schemele, consultați documentația [activități](activities.md).

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definiți o mapare a entității semantice ContactProfile

1. Mergi la **Date** > **Mapări semantice (previzualizare)**.

1. Selectați **Adăugați mapare semantică** pentru a începe experiența ghidată.

1. În pasul **Date entitate**, setați valorile pentru următoarele câmpuri:

   - **Numele maparii entității semantice** : Nume pentru maparea entității semantice.
   - **Entitatea sursă** : Entitate care include datele de contact.
   - **Cheia principala** : Câmp care identifică în mod unic o înregistrare de contact. Nu ar trebui să conțină valori duplicate, valori goale sau valori lipsă.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Configurați maparea entității semantice cu numele, entitatea sursă și cheia primară.":::

1. Selectați **Următorul**.

1. În pasul **Relații**, configurați detaliile pentru a vă conecta datele de contact la datele de cont corespunzătoare. Acest pas vizualizează conexiunea dintre entități.  

   Există două tipuri de căi de relații care pot fi implementate: **Relații directe** și **Relații indirecte**. Pentru mai multe informații, accesați [căi de relații directe și indirecte](relationships.md#relationship-paths).

   1. Selectați **Adăugați o relație** pentru a configura relația.
   1. Alegeți atributul din entitatea sursă care vă conectează entitatea de contact la o altă entitate.
   1. Alegeți entitatea la care să vă conectați entitatea de contact. Alegeți o entitate din **Entități de cont** sau **Entitate intermediară** secțiune. Dacă selectați o entitate intermediară, definiți o a doua relație pentru a vă conecta la entitatea de cont țintă.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Selectați fie o entitate de cont, fie o entitate intermediară.":::

   1. Furnizați un **Nume de relație**. Dacă există deja o relație între entitățile dvs., numele relației este numai în citire. Dacă nu există nicio relație, va fi creată o nouă relație cu numele pe care îl furnizați.
   1. Selectați **Aplicare** pentru a finaliza configurația relației.

   > [!NOTE]
   > Puteți configura mai multe relații între entitatea de contact și alte entități de cont cu entități intermediare.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Vizualizarea diferitelor relații conectează entitățile de contact cu entitățile de cont.":::

1. Selectați **Următorul**.

1. În pasul **Setați tipul semantic**, alegeți un **Tip semantic**. În prezent, există un **Tip semantic** numit *ContactProfile*.

1. Mapați ID-ul dvs. de contact la *Profil de contact* tip semantic **ID de contact**. Opțional, mapați alte câmpuri, cum ar fi prenume, nume de familie, sex sau e-mail.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Asociați atributele datelor dvs. de contact la câmpurile obligatorii și opționale furnizate.":::

1. Selectați **Următorul**.

1. În **Revizuire** pas, revizuiți configurația mapării semantice. Pentru a face modificări, selectați **Editați | ×** pentru secțiunea corespunzătoare.

1. Selectați **Salvare**.

1. Pentru a procesa maparea semantică, selectați **Alerga**. Sau selectați **Închide** pentru a salva maparea semantică fără a o procesa. Pentru a o rula mai târziu, selectați maparea semantică și selectați **Reîmprospăta**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Gestionați mapările semantice existente

Mergi la **Date** > **Mapări semantice (previzualizare)** pentru a vizualiza mapările semantice salvate, entitatea sursă, tipul semantic, tipul de mapare și starea acestora.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opțiuni pentru gestionarea mapărilor semantice.":::

Selectați maparea semantică pentru a vedea acțiunile disponibile.
- **Editați | ×** configurația curentă. Selectați **Salvare** și **Rulare** pentru a procesa modificările.
- **Reîmprospăta** maparea semantică pentru a include cele mai recente date. Reîmprospătarea oricărei mapări semantice va actualiza toate mapările semantice de același tip.
- **Redenumiți** maparea semantică. Selectați **Salvare**.
- **Șterge** maparea semantică. Pentru a șterge mai multe mapări semantice simultan, selectați mapările semantice și pictograma de ștergere. Selectați **Ștergere**, apoi confirmați ștergerea.

[!INCLUDE [footer-include](includes/footer-banner.md)]
