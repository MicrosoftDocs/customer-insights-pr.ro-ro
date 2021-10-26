---
title: Îmbogățire cu importul particularizat SFTP
description: Informații generale despre îmbogățirea particularizată a importului SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: fa1d4ffd9f77e128b5d804e4562e964561f4684f
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618720"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Îmbogățiți profilurile clienților cu date particularizate (previzualizare)

Importul particularizat Secure File Transfer Protocol (SFTP) vă permite să importați date care nu trebuie să treacă prin procesul de unificare a datelor. Este un mod flexibil, sigur și ușor de a vă obține datele. Importul particularizat SFTP poate fi utilizat în combinație cu [exportul SFTP](export-sftp.md) care vă permite să exportați datele de profil ale clienților necesare pentru îmbogățire. Datele pot fi apoi procesate și îmbogățite, iar importul personalizat SFTP poate fi utilizat pentru a readuce datele îmbogățite înapoi la capacitatea de detalii despre public a Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Cerințe preliminare

Pentru a configura importul particularizat SFTP, trebuie îndeplinite următoarele condiții prealabile:

- Aveți numele fișierului și locația (calea) fișierului de importat pe gazda SFTP.
- Există un fișier *model.json* care specifică [schema Common Data Model](/common-data-model/) pentru ca datele să fie importate. Acest fișier trebuie să fie în același director cu fișierul de importat.
- O conexiune SFTP a fost deja configurată de un administrator *sau* aveți permisiuni de [administrator](permissions.md#administrator). Veți avea nevoie de acreditările utilizatorului, adresa URL și numărul de port pentru locația SFTP de unde doriți să importați date.


## <a name="configure-the-import"></a>Configurați importul

1. Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**.

1. În **dala de import particularizat SFTP**, selectați **Îmbogățiți datele mele** și apoi selectați **Începeți**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Dala import particularizat SFTP":::

1. Selectați o [conexiune](connections.md) din lista derulantă. Contactați un administrator dacă nu este disponibilă nicio conexiune. Dacă sunteți administrator, puteți crea o conexiune selectând **Adăugare conexiune** și alegând **Importul particularizat SFTP** din lista verticală.

1. Selectați **Conectați-vă la import particularizat** pentru a selecta conexiunea.

1.  Selectați **Următorul** și introduceți **Cale** și **Nume de fișier** din fișierul de date pe care doriți să îl importați.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Captură de ecran la introducerea locației datelor.":::

1. Selectați **Următorul** și alegeți setul de date pentru clienți. Acesta poate fi fie toate profilurile clienților, fie un segment.

1. Selectați **Următorul** și furnizați un nume pentru îmbogățire și un nume pentru entitatea de ieșire. 

1. Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Configurați conexiunea pentru importul particularizat SFTP 

Trebuie să fiți administrator pentru a configura conexiunile. Selectați **Adăugați conexiune** la configurarea unei îmbogățiri *sau* mergeți la **Administrator** > **Conexiuni** și selectați **Configurare** pe dala Import particularizat.

1. Introduceți un nume pentru conexiune în caseta **Nume afișat**.

1. Introduceți un nume de utilizator, o parolă și o adresă URL gazdă valide pentru serverul SFTP pe care se află datele de importat.

1. Analizați și acordați-vă consimțământul pentru **Confidențialitatea și conformitatea datelor** prin selectarea casetei de selectare **Sunt de acord**.

1. Selectați **Verificare** pentru a valida configurația.

1. După finalizarea verificării, conexiunea poate fi salvată selectând **Salvați**.

   > [!div class="mx-imgBorder"]
   > ![Experian pagină de configurare a conexiunii.](media/enrichment-SFTP-connection.png "Experian pagină de configurare a conexiunii")


## <a name="defining-field-mappings"></a>Se definesc mapările de câmp 

Directorul care conține fișierul de importat pe serverul SFTP trebuie să conțină și un fișier *model.json*. Acest fișier definește schema de utilizat pentru importul datelor. Schema trebuie utilizată [Common Data Model](/common-data-model/) pentru a specifica maparea câmpului. Un exemplu simplu de fișier model.json arată astfel:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a>Rezultate de îmbogățire

Pentru a începe procesul de îmbogățire, selectați **Rulare** din bara de comenzi. De asemenea, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei [reîmprospătări programate](system.md#schedule-tab). Timpul de procesare va depinde de mărimea datelor de importat și de conexiunea la serverul SFTP.

După finalizarea procesului de îmbogățire, puteți examina datele de îmbogățire particularizate nou importate în secțiunea **Îmbogățirile mele**. În plus, veți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.

Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.

## <a name="next-steps"></a>Pașii următori

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
