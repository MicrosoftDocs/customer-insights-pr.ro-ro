---
title: Îmbogățire cu îmbogățiri terță parte HERE Technologies
description: Informații generale despre îmbogățirea terță parte HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668693"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Îmbogățirea profilurilor clienților cu HERE Technologies (previzualizare)

HERE Technologies este o companie de platformă de localizare care oferă date și servicii centrate pe locație. Cu serviciile de îmbogățire a datelor de la HERE Technologies, puteți construi o înțelegere mai precisă a locației clienților dvs. cu normalizarea adreselor, extragerea latitudinii și longitudinii și multe altele.

## <a name="prerequisites"></a>Cerințe preliminare

Pentru a configura îmbogățirile HERE Technologies, trebuie îndeplinite următoarele condiții prealabile:

- Aveți un abonament activ HERE Technologies. Pentru a obține un abonament, puteți să vă [înscrieți aici](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) sau [contactați HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direct. [Aflați mai multe despre îmbogățirea locației HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Aveți cheia API HERE Technologies.

- Aveți permisiuni de [Administrator](permissions.md#administrator).

## <a name="configuration"></a>Configurație

1. Accesați **Date** > **Îmbogățire**.

1. Pe dala HERE Technologies, selectați **Doresc îmbogățirea datelor**.

   > [!div class="mx-imgBorder"]
   > ![Dală HERE Technologies](media/HERE-tile.png "Dală HERE Technologies")

1. Introduceți o **cheie API HERE Technologies** activă. Analizați și acordați-vă consimțământul pentru **Confidențialitatea și conformitatea datelor** prin selectarea casetei de selectare **Sunt de acord**. 

1. Confirmați ambele intrări selectând **Conectați-vă la HERE**.

1. Selectați **Adăugare date** și alegeți dacă doriți să mapați câmpurile la adresa primară și/sau secundară. Puteți specifica o mapare a câmpului pentru ambele adrese (de exemplu, o adresă de domiciliu și una pentru companie) și puteți îmbogăți profilurile pentru ambele adrese separat. Selectați **Următorul**.

1. Definiți ce câmpuri din profilurile dvs. unificate ar trebui utilizate pentru a căuta date de locație potrivite de la HERE Technologies. Câmpurile **Stradă 1** și **Cod poștal** sunt obligatorii pentru adresa primară și/sau secundară selectată. Pentru o precizie mai mare a potrivirii, pot fi adăugate mai multe câmpuri.

   > [!div class="mx-imgBorder"]
   > ![Pagina de configurare pentru îmbogățirii HERE Technologies](media/enrichment-HERE-configuration.png "Pagina de configurare pentru îmbogățirii HERE Technologies")

1. Selectați **Aplicare** pentru a finaliza maparea câmpului.

## <a name="enrichment-results"></a>Rezultate de îmbogățire

Pentru a începe procesul de îmbogățire, selectați **Rulare** din bara de comenzi. De asemenea, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei [reîmprospătări programate](system.md#schedule-tab). Timpul de procesare va depinde de mărimea datelor clienților dvs. și de timpii de răspuns API de la HERE Technologies.

După finalizarea procesului de îmbogățire, puteți consulta datele din profilurile clienților nou îmbogățite din **Îmbogățirile mele**. În plus, veți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.

Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.

## <a name="next-steps"></a>Pașii următori

Creați în plus față de datele îmbogățite ale clienților. Creați [segmente](segments.md), [măsuri](measures.md) și chiar [exportați datele](export-destinations.md) pentru a oferi experiențe personalizate clienților.

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către HERE Technologies, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că HERE Technologies îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.
