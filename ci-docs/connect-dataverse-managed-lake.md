---
title: Conectați-vă la date într-un data lake gestionat Microsoft Dataverse
description: Importați date dintr-un Microsoft Dataverse Data Lake gestionat.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609811"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Conectați-vă la date într-un data lake gestionat Microsoft Dataverse

Microsoft Dataverse utilizatorii se pot conecta rapid la entități analitice într-un Microsoft Dataverse lac administrat. Numai o sursă de date dintr-un mediu poate folosi același Dataverse data lake gestionat simultan.

> [!NOTE]
> Trebuie să fii administrator pe Dataverse organizație să continue și să vizualizeze lista entităților disponibile în lacul administrat.

## <a name="prerequisites"></a>Cerințe preliminare

- Date stocate în servicii online cum ar fi Azure Data Lake Storage pot fi stocate într-o locație diferită de locul în care sunt datele prelucrate sau stocate Dynamics 365 Customer Insights.Prin importul sau conectarea la date stocate în serviciile online, sunteți de acord că datele pot fi transferate și stocate cu Dynamics 365 Customer Insights . [Aflați mai multe la Centrul de încredere Microsoft](https://www.microsoft.com/trust-center).

- Numai Dataverse entitati cu [urmărirea modificărilor](/power-platform/admin/enable-change-tracking-control-data-synchronization) activate sunt vizibile. Aceste entități pot fi exportate în Dataverse -lacul de date gestionat și utilizat în Customer Insights. Înafara cutiei Dataverse tabelele au activată în mod implicit urmărirea modificărilor. Trebuie să activați urmărirea modificărilor pentru tabelele personalizate. Pentru a verifica dacă a Dataverse tabelul este activat pentru urmărirea modificărilor, accesați [Power Apps](https://make.powerapps.com) > **Date** > **Mese**. Găsiți tabelul care vă interesează și selectați-l. Mergi la **Setări** > **Opțiuni avansate** și revizuiți **Urmareste schimbarile** setare.

## <a name="connect-to-a-dataverse-managed-lake"></a>Conectați-vă la un lake gestionat de Dataverse

1. Accesați **Date** > **Surse de date**.

1. Selectați **Adăugați sursa de date**.

1. Selectaţi **Microsoft Dataverse**.

1. Introduceți a **Nume** pentru sursă de date și opțional **Descriere**.

1. Furnizați **Adresa serverului** pentru organizația Dataverse și selectați **Conectare**.

1. Selectați tabelele pe care doriți să le ingerați ca entități în Customer Insights din lista disponibilă.

   > [!NOTE]
   > Dacă unele tabele sunt deja selectate, acestea ar putea fi utilizate de alte aplicații Dynamics 365 (cum ar fi Dynamics 365 Sales Insights sau Customer Service Insights). Nu aveți posibilitatea să modificați selecția. Aceste tabele vor fi disponibile ca entități după crearea sursei de date.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Caseta de dialog care afișează o listă de entități din mediul Dataverse.":::

1. Salvați selecția pentru a începe sincronizarea tabelelor selectate din Dataverse. Veți găsi conexiunea recent adăugată pe pagina **Surse de date**. Acesta va fi pus în coadă pentru reîmprospătare și va afișa numărul de entități ca 0 până când toate tabelele selectate sunt sincronizate.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Încărcarea datelor poate dura timp. După o reîmprospătare cu succes, datele ingerate pot fi revizuite din [**Entități**](entities.md) pagină.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Editați o sursă de date lake gestionată de Dataverse

Editați selecția entității numai după crearea sursei de date. De exemplu, dacă s-au adăugat entități suplimentare la Dataverse și vreți să le importați și pe acestea.
Pentru a vă conecta la alt data lake Dataverse, [creați o nouă sursă de date](#connect-to-a-dataverse-managed-lake).

1. Accesați **Date** > **Surse de date**.

1. Lângă sursă de date pe care doriți să o actualizați, selectați **Editați | ×**.

1. Selectați entități suplimentare din lista disponibilă de entități.

1. Clic **Salvați** pentru a aplica modificările și a reveni la **Surse de date** pagină.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>Motive obișnuite pentru erori de asimilare sau date corupte

Următoarele verificări rulează pe datele ingerate pentru a expune înregistrările deteriorate:

- Valoarea unui câmp nu se potrivește cu tipul de date al coloanei sale.
- Câmpurile conțin caractere care fac ca coloanele să nu se potrivească cu schema așteptată. De exemplu: ghilimele formatate incorect, ghilimele fără scăpare sau caracterele cu linie nouă.
- Dacă există coloane datetime/date/datetimeoffset, formatul acestora trebuie specificat în model dacă nu respectă formatul standard ISO.

### <a name="schema-or-data-type-mismatch"></a>Nepotrivire între schemă sau tip de date

Dacă datele nu sunt conforme cu schema, înregistrările sunt clasificate ca fiind corupte. Corectați fie datele sursă, fie schema și reingerați datele.

### <a name="datetime-fields-in-the-wrong-format"></a>Câmpuri de dată și oră în format greșit

Câmpurile datetime din entitate nu sunt în format ISO sau en-US. Formatul implicit de dată și oră din Customer Insights este formatul en-US. Toate câmpurile datetime dintr-o entitate ar trebui să fie în același format. Customer Insights acceptă alte formate, cu condiția ca adnotările sau trăsăturile să fie făcute la nivel de sursă sau de entitate în model sau manifest.json. De exemplu:

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  Într-un manifest.json, formatul datetime poate fi specificat la nivel de entitate sau la nivel de atribut. La nivel de entitate, utilizați „exhibitsTraits” în entitatea din *.manifest.cdm.json pentru a defini formatul datatime. La nivel de atribut, utilizați „appliedTraits” în atributul din entityname.cdm.json.

**Manifest.json la nivel de entitate**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json la nivel de atribut**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
