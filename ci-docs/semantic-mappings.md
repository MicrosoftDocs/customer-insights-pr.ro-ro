---
title: Mapări semantice (versiune preliminară)
description: Prezentare generală a mapărilor semantice și modul de utilizare a acestora.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183646"
---
# <a name="semantic-mappings-preview"></a>Mapări semantice (versiune preliminară)

Asocierile semantice vă permit să vă mapați datele de non-activitate în scheme predefinite. Aceste scheme ajută Customer Insights să vă înțeleagă mai bine atributele datelor. Maparea semantică și datele furnizate permit noi perspective și funcții în Customer Insights. Pentru a vă mapa datele de activitate cu schemele, consultați documentația [activități](activities.md).

**Mapările semantice sunt în prezent activate pentru medii bazate pe conturi de business**. *Profil de contact* este singurul tip de mapare semantică disponibilă în prezent în Customer Insights.

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

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Utilizați o mapare a entităților semantice ContactProfile pentru a crea activități la nivel de contact

După crearea unui *Profil de contact* cartografierea entităților semantice, puteți captura activitățile contactelor. Vă permite să vedeți în cronologia activității pentru un cont care persoană de contact a fost responsabilă pentru fiecare activitate. Majoritatea pașilor urmează configurația tipică de mapare a activității.

   > [!NOTE]
   > Pentru ca activitățile la nivel de contact să funcționeze, trebuie să aveți ambele **Cont ID** și **ContactID** atribute pentru fiecare înregistrare din datele dvs. de activitate.

1. [Definiți a *Profil de contact* maparea entităților semantice](#define-a-contactprofile-semantic-entity-mapping) și rulați maparea semantică.

1. Mergi la **Date** > **Activități**.

1. Selectați **Adăugați o activitate** pentru a crea o activitate nouă.

1. Denumiți activitatea, selectați entitatea de activitate sursă și selectați cheia primară a entității de activitate.

1. În **Relații** pas, creați o relație indirectă între datele dvs. sursă de activitate și conturi, folosind datele dvs. de contact ca entitate intermediară. Pentru mai multe informații, vezi [căi de relație directe și indirecte](relationships.md#relationship-paths).
   - Exemplu de relație pentru o activitate numită *Achiziții*:
      - **Date privind activitatea sursă de achiziții** > **Datele de contact** asupra atributului **ContactID**
      - **Datele de contact** > **Datele contului** asupra atributului **Cont ID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Exemplu de configurare a relației.":::

1. După configurarea relațiilor, selectați **Următorul** și finalizați configurația de cartografiere a activității. Pentru pașii detaliați despre crearea activității, consultați [defini o activitate](activities.md).

1. Rulați mapările activității dvs.

1. După ce se rulează o mapare a activității la nivel de contact, selectați **Clienți**. Activitățile la nivel de contact sunt afișate pe cronologia clientului.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Rezultatul final după configurarea activităților de contact":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtrarea cronologiei activității la nivel de contact

Cronologia activității pentru clienții dvs. include ID-urile sau numele acestora, în funcție de dvs *Profil de contact* configuratie, pentru activitatile asupra carora au actionat. Filtrați activitățile după persoane de contact din cronologie pentru a vedea anumite persoane de contact care vă interesează. Pentru a vizualiza toate activitățile care nu sunt alocate unui anumit contact, selectați **Activități care nu sunt mapate la o persoană de contact**.

:::image type="content" source="media/Contact_Activities3.png" alt-text="Opțiuni de filtrare disponibile pentru activitățile la nivel de contact.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
