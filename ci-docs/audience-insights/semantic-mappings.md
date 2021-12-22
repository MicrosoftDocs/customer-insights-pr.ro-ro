---
title: Mapări semantice (Versiune preliminară)
description: Prezentare generală a mapărilor semantice și modul de utilizare a acestora.
ms.date: 12/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: 08b257b97704b219bb3277042516e00deb886a49
ms.sourcegitcommit: 58651d33e0a7d438a2587c9ceeaf7ff58ae3b648
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 12/02/2021
ms.locfileid: "7881845"
---
# <a name="semantic-mappings-preview"></a>Mapări semantice (Versiune preliminară)

Asocierile semantice vă permit să vă mapați datele de non-activitate în scheme predefinite. Aceste scheme ajută statisticile publicului să vă înțeleagă mai bine atributele de date. Maparea semantică și datele furnizate permit noi informații și caracteristici în detaliile despre public. Pentru a vă mapa datele de activitate cu schemele, consultați documentația [activități](activities.md).

**Mapările semantice sunt în prezent activate pentru medii bazate pe conturi de business**. *ContactProfile* este singurul tip de mapare semantică disponibil în prezent în statisticile publicului.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definiți o mapare a entității semantice ContactProfile

1. În statisticile publicului, accesați **Date** > **Mapări semantice (versiune preliminară)**.

1. Selectați **Adăugați mapare semantică** pentru a începe experiența ghidată.

1. În pasul **Date entitate**, setați valorile pentru următoarele câmpuri:

   - **Numele mapării entității semantice**: Furnizați un nume pentru maparea entității semantice.
   - **Entitate sursă**: Selectați o entitate care include date de contact.
   - **Cheie primară**: Selectați câmpul care identifică în mod unic o înregistrare de contact. Nu ar trebui să conțină valori duplicate, valori goale sau valori lipsă.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Configurați maparea entității semantice cu numele, entitatea sursă și cheia primară.":::

1. Selectați **Următorul** pentru a continua.

1. În pasul **Relații**, configurați detaliile pentru a vă conecta datele de contact la datele de cont corespunzătoare. Acest pas vizualizează conexiunea dintre entități.  

   Există două tipuri de căi de relații care pot fi implementate: **Relații directe** și **Relații indirecte**. Pentru mai multe informații, accesați [căi de relații directe și indirecte](relationships.md#relationship-paths).

   1. Selectați **Adăugați o relație** configurați relația.
   1. Alegeți atributul din entitatea sursă care vă conectează entitatea de contact la o altă entitate.
   1. Alegeți entitatea la care să vă conectați entitatea de contact. Puteți alege o entitate din secțiunea **Entități de cont** sau **Entitate intermediară**. Dacă selectați o entitate intermediară, trebuie să definiți o a doua relație pentru a vă conecta la entitatea contului dvs. țintă.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Selectați fie o entitate de cont, fie o entitate intermediară.":::

   1. Furnizați un **Nume de relație**. Dacă există deja o relație între entitățile dvs., numele relației este numai în citire. Dacă nu există nicio relație, va fi creată o nouă relație cu numele pe care îl furnizați.
   1. Selectați **Aplicare** pentru a finaliza configurația relației.

   > [!NOTE]
   > Puteți configura mai multe relații între entitatea de contact și alte entități de cont cu entități intermediare.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Vizualizarea diferitelor relații conectează entitățile de contact cu entitățile de cont.":::

1. Selectați **Următorul** când ați terminat configurația relației.

1. În pasul **Setați tipul semantic**, alegeți un **Tip semantic**. În prezent, există un **Tip semantic** numit *ContactProfile*.

1. Mapați-vă datele la *ContactProfile* **Tip semantic** pentru câmpurile afișate.
   - Câmp obligatoriu: ID Contact
   - Câmpuri opționale: prenume, nume de familie, Data nașterii, sexul, adresa de e-mail principală și telefonul principal

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Asociați atributele datelor dvs. de contact la câmpurile obligatorii și opționale furnizate.":::

1. Selectați **Următorul** pentru a continua.

1. În pasul **Revizuire**, aruncați o privire la configurația mapării semantice. Selectați **Editați** pentru ca secțiunea corespunzătoare să facă modificări.

1. Selectați **Salvați** pentru a vă salva noua **Mapare semantică**.

1. După salvare, puteți selecta **Rulați** procesul mapării semantice sau puteți selecta **Închideți** pentru a vă salva maparea semantică fără a o procesa.

1. Pentru a rula o mapare semantică într-un punct ulterior, selectați maparea semantică și selectați **Reîmprospătare**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Gestionați mapările semantice existente

Pe **Date** > **Mapări semantice (previzualizare)**, puteți vizualiza toate mapările semantice salvate și le puteți gestiona. Fiecare mapare semantică este reprezentată de un rând separat. Veți găsi detalii despre entitatea sursă, tipul semantic, tipul de mapare și starea acesteia.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opțiuni pentru gestionarea mapărilor semantice.":::

- **Editare**: Deschide configurarea instalării mapării semantice în pasul de recenzie. Puteți modifica configurația curentă. Selectați **Salvare** și **Rulare** pentru a procesa modificările.

- **Reîmprospătare**: Reîmprospătează maparea semantică selectată cu cele mai actualizate date de la entitățile care fac parte din configurația sa. Reîmprospătarea oricărei mapări semantice va actualiza toate mapările semantice de același tip.

- **Redenumiți**: Deschide un dialog în care puteți introduce un nume diferit pentru maparea semantică selectată. Selectați **Salvare** pentru a vă aplica modificările.

- **Șterge**: Deschide un dialog pentru a confirma ștergerea mapării semantice selectate. De asemenea, puteți șterge mai multe mapări semantice simultan selectând mapările semantice și pictograma de ștergere. Selectați **Ștergere**, apoi confirmați ștergerea.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Utilizați o mapare a entităților semantice ContactProfile pentru a crea activități la nivel de contact

După crearea unui *Profil de contact* cartografierea entităților semantice, puteți captura activitățile contactelor. Vă permite să vedeți în cronologia activității pentru un cont care persoană de contact a fost responsabilă pentru fiecare activitate. Majoritatea pașilor urmează configurația tipică de mapare a activității.

   > [!NOTE]
   > Pentru ca activitățile la nivel de contact să funcționeze, trebuie să aveți ambele **Cont ID** și **ContactID** atribute pentru fiecare înregistrare din datele dvs. de activitate.

1. [Definiți a *Profil de contact* maparea entităților semantice.](#define-a-contactprofile-semantic-entity-mapping) și rulați maparea semantică.

1. În Detalii despre audiență, accesați **Date** > **Activități**.

1. Selectați **Adăugați o activitate** pentru a crea o activitate nouă.

1. Denumiți activitatea, selectați entitatea de activitate sursă și selectați cheia primară a entității de activitate.

1. În **Relații** pas, creați o relație indirectă între datele dvs. sursă de activitate și conturi, folosind datele dvs. de contact ca entitate intermediară. Pentru mai multe informații, vezi [căi de relație directe și indirecte](relationships.md#relationship-paths).
   - Relație de exemplu pentru o activitate numită *Achiziții*:
      - **Date privind activitatea sursă de achiziții** > **Datele de contact** asupra atributului **ContactID**
      - **Datele de contact** > **Datele contului** asupra atributului **Cont ID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Exemplu de configurare a relației.":::

1. După configurarea relațiilor, selectați **Următorul** și finalizați configurația de cartografiere a activității. Pentru pașii detaliați despre crearea activității, consultați [defini o activitate](activities.md).

1. Rulați mapările activității dvs.

1. Activitățile tale la nivel de contact vor fi acum vizibile pe cronologia clientului.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Rezultatul final după configurarea activităților de contact":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtrarea cronologiei activității la nivel de contact

După ce configurați o mapare a activității la nivel de contact și o rulați, cronologia activității pentru clienții dvs. va fi actualizată. Include ID-urile sau numele lor, în funcție de dvs *Profil de contact* configuratie, pentru activitatile asupra carora au actionat. Puteți filtra activitățile după persoane de contact din cronologie pentru a vedea anumite persoane de contact care vă interesează. În plus, puteți vedea toate activitățile care nu sunt alocate unui anumit contact selectând **Activități care nu sunt mapate la o persoană de contact**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Opțiuni de filtrare disponibile pentru activitățile la nivel de contact.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
