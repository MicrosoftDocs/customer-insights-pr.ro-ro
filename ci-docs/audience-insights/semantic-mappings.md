---
title: Mapări semantice (Versiune preliminară)
description: Prezentare generală a mapărilor semantice și modul de utilizare a acestora.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: f23c622572ff9f967eca07de7898419d1ffc18b0
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/02/2021
ms.locfileid: "7731958"
---
# <a name="semantic-mappings"></a>Mapări semantice

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
