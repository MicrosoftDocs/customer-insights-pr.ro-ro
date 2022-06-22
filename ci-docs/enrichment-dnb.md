---
title: Îmbogățirea profilurilor companiei cu Dun & Bradstreet
description: Informații generale despre îmbogățirea de la terți Dun & Bradstreet.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b1038970b6aee3bbdd7f79cc457f79aaf1c38222
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953906"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Îmbogățirea profilurilor companiei cu Dun & Bradstreet (Previzualizare)

Dun & Bradstreet oferă date comerciale, analize și perspective pentru companii. Aceasta permite clienților cu profiluri de clienți unificate pentru companii să-și îmbogățească datele. Îmbogățirile includ atribute precum numărul DUNS, dimensiunea companiei, locația, industria și multe altele.

## <a name="prerequisites"></a>Cerințe preliminare

- Un activ [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) licență.
- [Profiluri de clienți unificate](customer-profiles.md) pentru companii.
- Un Dun & Bradstreet [proiect](#set-up-your-dun--bradstreet-project) este pus la punct.
- Un Dun & Bradstreet [conexiune](connections.md) este [configurat](#configure-a-connection-for-dun--bradstreet) de către un administrator.

## <a name="set-up-your-dun--bradstreet-project"></a>Configurați-vă proiectul Dun & Bradstreet

În calitate de utilizator licențiat al Dun & Bradstreet, puteți configura un proiect în [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Conectați la [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Pentru a recupera acreditările, [restaurați-vă parola](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Descarca [fișierul nostru șablon csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) care vor fi folosite pentru a mapa câmpurile Customer Insights la câmpurile Dun & Bradstreet corespunzătoare.

1. Încărcați fișierul în **Încărcați date** pasul experienței de creare a proiectelor Dun & Bradstreet.

1. Selectați punctele orizontale sub cele relevante **sursă** în proiectul Dun & Bradstreet nou creat pentru a vedea opțiunile disponibile.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Captură de ecran cu puncte într-un proiect Dun & Bradstreet.":::

1. Alege **Obțineți detalii S3**. Păstrați aceste informații într-un loc sigur. Veți avea nevoie de el [stabiliți legătura pentru îmbogățire](#configure-a-connection-for-dun--bradstreet) în Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Captură de ecran cu selecția informațiilor s3 într-un proiect Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Configurați o conexiune pentru Dun & Bradstreet

Trebuie să fii un [administrator](permissions.md#admin) în Customer Insights și aveți acreditările de la Dun & Bradstreet Connect.

1. Selectați **Adăugați conexiune** atunci când configurați o îmbogățire sau mergeți la **Admin** > **Conexiuni** și selectați **Înființat** pe tigla Dun & Bradstreet.

1. Introduceți un nume pentru conexiune.

1. Furnizați acreditările Dun & Bradstreet valide și detaliile proiectului Dun & Bradstreet *Regiunea, Calea folderului Drop și Drop folder name*. Tu [obține aceste informații](#set-up-your-dun--bradstreet-project) din proiectul Dun & Bradstreet.

1. Examinați și furnizați consimțământul pentru [Confidențialitatea și respectarea datelor](#data-privacy-and-compliance) prin selectarea **Sunt de acord**.

1. Selectați **Verifica** pentru a valida configurația și apoi selectați **Salvați**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Pagina de configurare a conexiunii Dun & Bradstreet.":::

### <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Dun & Bradstreet, permiteți transferul de date în afara limitei de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele personale. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru a vă asigura că Dun & Bradstreet îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul dvs. Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.

## <a name="supported-countries-or-regions"></a>Țări sau regiuni sprijinite

În prezent, acceptăm următoarele opțiuni de țară/regiune: Canada (engleză) sau Statele Unite ale Americii (engleză).

## <a name="configure-the-enrichment"></a>Configurați îmbogățirea

1. Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**.

1. Selectați **Îmbogățiți-mi datele** pe **Datele companiei** pentru faianta Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Captură de ecran a plăcilor Dun & Bradstreet.":::

1. Examinați prezentarea generală și apoi selectați **Următorul**.

1. Selectați conexiunea și confirmați. Contactați un administrator dacă unul nu este disponibil.

1. Selectați **Următorul**.

1. Selectează **Set de date despre client** și alegeți profilul sau segmentul pe care doriți să îl îmbogățiți cu datele companiei de la Dun & Bradstreet. The *Client* entitate îmbogățește toate profilurile dvs. de clienți, în timp ce un segment îmbogățește numai profilurile de clienți conținute în acel segment.

1. Definiți ce tip de câmpuri din profilurile dvs. unificate să utilizați pentru potrivirea datelor companiei de la Dun & Bradstreet. Cel puțin unul dintre câmpurile **Numele și adresa**, **Telefon** sau **E-mail** este necesar.

1. Selectați **Următorul**

1. Hartați câmpurile cu datele companiei de la Dun & Bradstreet. Fie **Numărul DUNS** sau **Numele companiei** și **Țară** câmpurile sunt obligatorii.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Panoul de cartografiere a câmpurilor Dun & Bradstreet.":::

1. Selectați **Următorul** pentru a completa maparea câmpului.

1. Furnizeaza un **Nume** pentru îmbogățire și pentru **Numele entității de ieșire**.

1. Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.

1. Selectați **Alerga** pentru a începe procesul de îmbogățire sau aproape pentru a reveni la **Îmbogățiri** pagină.

## <a name="enrichment-results"></a>Rezultate de îmbogățire

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Pașii următori

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
