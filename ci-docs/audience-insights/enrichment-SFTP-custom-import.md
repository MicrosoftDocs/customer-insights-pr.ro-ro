---
title: Îmbogățire cu importul particularizat SFTP
description: Informații generale despre îmbogățirea particularizată a importului SFTP.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595870"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Îmbogățiți profilurile clienților cu date particularizate (previzualizare)

Importul particularizat Secure File Transfer Protocol (SFTP) vă permite să importați date care nu trebuie să treacă prin procesul de unificare a datelor. Este un mod flexibil, sigur și ușor de a vă obține datele. Importul particularizat SFTP poate fi utilizat în combinație cu [exportul SFTP](export-sftp.md) care vă permite să exportați datele de profil ale clienților necesare pentru îmbogățire. Datele pot fi apoi procesate, îmbogățite, iar importul particularizat SFTP poate fi utilizat pentru a readuce datele îmbogățite înapoi la capacitatea Detalii despre audiență a Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Cerințe preliminare

Pentru a configura importul particularizat SFTP, trebuie îndeplinite următoarele condiții prealabile:

- Aveți acreditări de utilizator (nume de utilizator și parolă) pentru locația SFTP de unde vor fi importate datele.
- Aveți adresa URL și numărul portului (de obicei 22) pentru gazda STFP.
- Aveți numele fișierului și locația fișierului de importat pe gazda SFTP.
- Există un fișier *model.json* care specifică schema pentru datele care urmează să fie importate. Acest fișier trebuie să fie în același director cu fișierul de importat.
- Aveți permisiune de [Administrator](permissions.md#administrator).

## <a name="configuration"></a>Configurație

1. Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**.

1. Pe **Dala de import particularizat SFTP**, selectați **Doresc îmbogățirea datelor**.

   > [!div class="mx-imgBorder"]
   > ![Dala import particularizat SFTP](media/SFTP_Custom_Import_tile.png "Dala import particularizat SFTP")

1. Selectați **Începeți** și furnizați acreditările și adresa pentru serverul SFTP. De exemplu, sftp://mysftpserver.com:22.

1. Introduceți numele fișierului care conține datele și calea către fișier de pe serverul SFTP dacă nu se află în folderul rădăcină.

1. Confirmați toate intrările selectând **Conectare la importul particularizat**.

   > [!div class="mx-imgBorder"]
   > ![Fișă configurare import particularizat SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Fișă configurare import particularizat SFTP")

## <a name="defining-field-mappings"></a>Se definesc mapările de câmp 

Directorul care conține fișierul de importat pe serverul SFTP trebuie să conțină și un fișier *model.json*. Acest fișier definește schema de utilizat pentru importul datelor. Schema trebuie să utilizeze [Common Data Model](/common-data-model/) pentru a specifica maparea câmpului. Un exemplu simplu de fișier model.json arată astfel:

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

Creați în plus față de datele îmbogățite ale clienților. Creați [segmente](segments.md), [măsuri](measures.md), și [exportați datele](export-destinations.md) pentru a oferi clienților dvs. experiențe personalizate.




[!INCLUDE[footer-include](../includes/footer-banner.md)]