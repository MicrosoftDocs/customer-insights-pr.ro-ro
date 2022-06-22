---
title: Îmbogățire cu importul particularizat SFTP
description: Informații generale despre îmbogățirea particularizată a importului SFTP.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 657afb6fcb68429680eb677734b4115e69769008
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953734"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Îmbogățiți profilurile clienților cu date particularizate (previzualizare)

Importul particularizat Secure File Transfer Protocol (SFTP) vă permite să importați date care nu trebuie să treacă prin procesul de unificare a datelor. Este un mod flexibil, sigur și ușor de a vă obține datele. Importul particularizat SFTP poate fi utilizat în combinație cu [exportul SFTP](export-sftp.md) care vă permite să exportați datele de profil ale clienților necesare pentru îmbogățire. Datele pot fi apoi procesate și îmbogățite, iar importul personalizat SFTP poate fi utilizat pentru a aduce datele îmbogățite înapoi în Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Cerințe preliminare

- Numele fișierului și locația (calea) fișierului care urmează să fie importat pe gazda SFTP sunt cunoscute.

- A *model.json* este disponibil fișierul care specifică schema modelului comun de date pentru datele care urmează să fie importate. Acest fișier trebuie să fie în același director cu fișierul de importat.

- Un SFTP [conexiune](connections.md) este [configurat](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Exemplu de schemă de fișiere

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>Configurați conexiunea pentru importul particularizat SFTP

Trebuie să fii un [administrator](permissions.md#admin) în Customer Insights și aveți acreditările utilizatorului, adresa URL și numărul portului pentru locația SFTP de unde doriți să importați datele.

1. Selectați **Adăugați conexiune** atunci când configurați o îmbogățire sau mergeți la **Admin** > **Conexiuni** și selectați **Înființat** pe tigla Import personalizat.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Pagina de configurare a conexiunii de import personalizat.":::

1. Introduceți un nume pentru conexiune.

1. Introduceți un nume de utilizator, o parolă și o adresă URL gazdă valide pentru serverul SFTP pe care se află datele de importat.

1. Examinați și furnizați consimțământul pentru [Confidențialitatea și respectarea datelor](#data-privacy-and-compliance) prin selectarea **Sunt de acord**.

1. Selectați **Verifica** pentru a valida configurația și apoi selectați **Salvați**.

### <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date folosind Custom Import, permiteți transferul de date în afara limitei de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele personale. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil să vă asigurați că datele îndeplinesc orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul dvs. Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.

## <a name="configure-the-import"></a>Configurați importul

1. Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**.

1. Selectați **Îmbogățiți-mi datele** pe **Import personalizat SFTP** ţiglă.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Dala import particularizat SFTP":::

1. Examinați prezentarea generală și apoi selectați **Următorul**.

1. Selectați conexiunea. Contactați un administrator dacă unul nu este disponibil.

1. Selectează **Set de date despre client** și alegeți profilul sau segmentul pe care doriți să îl îmbogățiți. The *Client* entitate îmbogățește toate profilurile dvs. de clienți, în timp ce un segment îmbogățește numai profilurile de clienți conținute în acel segment.

1. Selectați **Următorul**.

1. Introduceți **cale** și **Nume de fișier** a fișierului de date pe care doriți să-l importați.

1. Selectați **Următorul**.

1. Furnizeaza un **Nume** pentru îmbogățire și pentru **Numele entității de ieșire**.

1. Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.

1. Selectați **Alerga** pentru a începe procesul de îmbogățire sau aproape pentru a reveni la **Îmbogățiri** pagină.

## <a name="enrichment-results"></a>Rezultate de îmbogățire

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Pașii următori

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
