---
title: Îmbogățirea profilurilor companiei cu Dun & Bradstreet
description: Informații generale despre îmbogățirea de la terți Dun & Bradstreet.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ecbbf2c94020bf395f4eb70a99a63cea335af2dd
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653800"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Îmbogățirea profilurilor companiei cu Dun & Bradstreet (previzualizare)

Dun & Bradstreet oferă date comerciale, analize și perspective pentru companii. Aceasta permite clienților cu profiluri de clienți unificate pentru companii să-și îmbogățească datele. Îmbogățirile includ atribute precum numărul DUNS, dimensiunea companiei, locația, industria și multe altele.

## <a name="prerequisites"></a>Cerințe preliminare

Pentru a configura o îmbogățire Dun & Bradstreet, trebuie îndeplinite următoarele cerințe preliminare:

- Ai un activ [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) licență.
- Aveți [profiluri de clienți unificate](customer-profiles.md) pentru companii.
- Un Dun & Bradstreet [conexiune](connections.md) este configurat de un administrator. Îl poți crea dacă ai [administrator](permissions.md#admin) permisiunile și acreditările de la Dun & Bradstreet Connect. 

## <a name="setting-up-your-dun--bradstreet-project"></a>Configurarea proiectului Dun & Bradstreet

În calitate de utilizator licențiat al Dun & Bradstreet, puteți configura un proiect în [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). 


1. Conectați la [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Pentru a recupera acreditările, [restaurați-vă parola](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Descarca [fișierul nostru șablon csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) care vor fi folosite pentru a mapa câmpurile de informații despre audiență la câmpurile Dun & Bradstreet corespunzătoare. 

1. Încărcați fișierul în **Încărcați date** pasul experienței de creare a proiectelor Dun & Bradstreet. 

1. Selectați punctele orizontale sub cele relevante **sursă** în proiectul Dun & Bradstreet nou creat pentru a vedea opțiunile disponibile.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Captură de ecran cu puncte într-un proiect Dun & Bradstreet.":::

1. Alege **Obțineți detalii S3**. Păstrați aceste informații într-un loc sigur. Veți avea nevoie de el [stabiliți legătura pentru îmbogățire](#configure-a-connection-for-dun--bradstreet) în perspectivele audienței. 

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Captură de ecran cu selecția informațiilor s3 într-un proiect Dun & Bradstreet.":::



## <a name="configure-the-enrichment"></a>Configurați îmbogățirea

1. În Detalii despre audiență, accesați **Date** > **Îmbogățire**.

1. Selectați **Îmbogățiți-mi datele** pe tigla Dun & Bradstreet și selectați **Incepe**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Captură de ecran a plăcilor Dun & Bradstreet.":::

1. Selectați o [conexiune](connections.md) din lista derulantă. Contactați un administrator dacă nu este disponibilă nicio conexiune. Dacă sunteți administrator, puteți crea o conexiune. Selectați **Adăugați conexiune** și alegeți **Dun & Bradstreet**. 

1. Selectați **Conectați-vă la Dun & Bradstreet** pentru a confirma conexiunea.

1. Selectați **Următorul** și alegeți **Set de date despre client** doriți să vă îmbogățiți cu datele companiei de la Dun & Bradstreet. Puteți selecta **Client** entitate pentru a vă îmbogăți toate profilurile de clienți sau selectați o entitate de segment pentru a îmbogăți numai profilurile de clienți unificate conținute în acel segment.

1. Selectați **Următorul** și definiți ce câmpuri din profilurile dvs. unificate sunt folosite pentru a căuta datele companiei care se potrivesc de la Dun & Bradstreet. Fie **Numărul DUNS** sau **Numele companiei** și **Țară** câmpurile sunt obligatorii. Domeniul de țară susține [coduri de țară din două sau trei litere](https://www.iso.org/iso-3166-country-codes.html), numele țării în engleză, numele țării în limba maternă și prefixul de telefon. Unele variante comune de țară includ:

   * SUA: Statele Unite ale Americii, Statele Unite ale Americii, SUA, America.
   * CA: Canada.
   * GB: Regatul Unit, Regatul Unit, Marea Britanie, GB, Regatul Unit al Marii Britanii și Irlandei de Nord, Regatul Unit al Marii Britanii.
   * AU: Australia, Commonwealth of Australia.
   * FR: Franța, Republica Franceză.
   * DE: Germania, Germană, Deutschland, Allemagne, Republica Federală Germania, Republica Germania.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Panoul de cartografiere a câmpurilor Dun & Bradstreet.":::

1. Selectați **Următorul** pentru a completa maparea câmpului.

1. Furnizați un nume pentru îmbogățire și selectați **Salvați îmbogățirea** după ce v-ați analizat alegerile.


## <a name="configure-a-connection-for-dun--bradstreet"></a>Configurați o conexiune pentru Dun & Bradstreet 

Trebuie să fiți administrator pentru a configura conexiunile. Selectați **Adăugați conexiune** la configurarea unei îmbogățiri *sau* mergi la **Admin** > **Conexiuni** și selectați **Înființat** pe tigla Dun & Bradstreet.

1. Selectați **Începeți lucrul**. 

1. Introduceți un nume pentru conexiune în caseta **Nume afișat**.

1. Furnizați acreditările Dun & Bradstreet valide și detaliile proiectului Dun & Bradstreet *Regiunea, Calea folderului Drop și Drop folder name*. Tu [obține aceste informații](#setting-up-your-dun--bradstreet-project) din proiectul Dun & Bradstreet.

1. Examinați și furnizați consimțământul pentru **Confidențialitatea și respectarea datelor** prin selectarea **Sunt de acord**.

1. Selectați **Verificare** pentru a valida configurația.

1. După finalizarea verificării, selectați **Salvare**.
   
   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Pagina de configurare a conexiunii Dun & Bradstreet.":::

## <a name="enrichment-results"></a>Rezultate de îmbogățire

După reîmprospătarea îmbogățirii, puteți examina datele companiei nou îmbogățite sub [Îmbogățirile mele](enrichment-hub.md). Puteți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.

Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.

## <a name="next-steps"></a>Pașii următori

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Dun & Bradstreet, permiteți transferul de date în afara limitei de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele personale. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru a vă asigura că Dun & Bradstreet îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul dvs. Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.


[!INCLUDE[footer-include](includes/footer-banner.md)]
