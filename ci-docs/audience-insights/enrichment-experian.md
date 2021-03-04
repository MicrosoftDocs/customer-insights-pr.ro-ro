---
title: Îmbogățire cu îmbogățiri terță parte Experian
description: Informații generale despre îmbogățirea terță parte Experian.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269575"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Îmbogățirea profilurilor clienților cu date demografice de la Experian (previzualizare)

Experian este lider global în raportarea creditelor pentru consumatori și afaceri și servicii de marketing. Cu Serviciile de îmbogățire a datelor Experian, puteți construi o înțelegere mai profundă a clienților dvs. îmbogățind profilurile clienților cu date demografice, cum ar fi dimensiunea gospodăriei, veniturile și multe altele.

## <a name="prerequisites"></a>Cerințe preliminare

Pentru a configura Experian, trebuie îndeplinite următoarele condiții prealabile:

- Aveți un abonament Experian activ. Pentru a obține un abonament, [contactați Experian](https://www.experian.com/marketing-services/contact) direct. [Aflați mai multe despre îmbogățirea datelor Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Aveți ID-ul de utilizator, ID-ul de parte și numărul de model pentru contul dvs. cu SSH activat Secure Transport (ST) creat de Experian pentru dvs.
- Aveți permisiuni de [Administrator](permissions.md#administrator) în Detalii despre audiență.

## <a name="configuration"></a>Configurație

1. Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**.

1. Selectați **Doresc îmbogățirea datelor** din dala Experian.

   > [!div class="mx-imgBorder"]
   > ![Dală Experian](media/experian-tile.png "Dală Experian")

1. Selectați **Începere** și introduceți ID-ul de utilizator, ID-ul de parte și numărul de model pentru contul dvs. Experian Secure Transport. Analizați și acordați-vă consimțământul pentru **Confidențialitatea și conformitatea datelor** prin selectarea casetei de selectare **Sunt de acord**. Confirmați toate intrările selectând **Aplicare**.

## <a name="map-your-fields"></a>Mapați câmpurile

1.  Selectați **Adăugați date** și alegeți **Set de date client** pe care doriți să îl îmbogățiți cu date demografice din Experian. Puteți selecta entitatea **Client** pentru a vă îmbogăți toate profilurile de clienți sau selectați o entitate de segment pentru a îmbogăți numai profilurile de clienți din acel segment.

1. Selectați identificatorii cheie din **Numele și adresa**, **E-mail**, sau **Telefon** pentru a trimite la Experian pentru rezolvarea identității.

   > [!TIP]
   > Mai multe atribute de identificare cheie trimise către Experian generează probabil o rată de potrivire mai mare.

1. Selectați **Următorul** și mapați atributele corespunzătoare de la entitatea dvs. client unificată pentru câmpurile de identificare cheie selectate.

1. Selectați **Adăugare atribut** pentru a mapa orice atribute suplimentare pe care doriți să le trimiteți către Experian.

1.  Selectați **Salvați** pentru a finaliza maparea câmpului.

    > [!div class="mx-imgBorder"]
    > ![Mapare câmp Experian](media/experian-field-mapping.png "Mapare câmp Experian")

## <a name="enrichment-results"></a>Rezultate de îmbogățire

Pentru a începe procesul de îmbogățire, selectați **Rulare** din bara de comenzi. De asemenea, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei [reîmprospătări programate](system.md#schedule-tab). Timpul de procesare va depinde de mărimea datelor clienților dvs. și de procesele de îmbogățire stabilite pentru contul dvs. de Experian.

După finalizarea procesului de îmbogățire, puteți consulta datele din profilurile clienților nou îmbogățite din **Îmbogățirile mele**. În plus, veți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.

Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.

## <a name="next-steps"></a>Pașii următori

Creați în plus față de datele îmbogățite ale clienților. Creați [segmente](segments.md), [măsuri](measures.md) și chiar [exportați datele](export-destinations.md) pentru a oferi experiențe personalizate clienților.

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Experian, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Experian îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.


[!INCLUDE[footer-include](../includes/footer-banner.md)]