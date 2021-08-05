---
title: Date Customer Insights în Microsoft Dataverse
description: Utilizați entitățile Customer Insights ca tabele în Microsoft Dataverse.
ms.date: 06/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 220e01a06711a5d35b8df09e265017a6d8fd0490
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650057"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Lucrul cu Customer Insights în Microsoft Dataverse

Customer Insights oferă opțiunea de a face entitățile de ieșire disponibile în [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Această integrare permite partajarea ușoară a datelor și dezvoltarea personalizată printr-o abordare cu cod redus/fără cod. Entitățile de ieșire vor fi disponibile ca tabele în Dataverse. Aceste tabele permit scenarii precum [fluxuri de lucru automatizate prin Power Automate](/power-automate/getting-started), [aplicații proiectate pe bază de model](/powerapps/maker/model-driven-apps/) și [aplicații proiectate pe pânză](/powerapps/maker/canvas-apps/) prin Power Apps. Puteți utiliza datele pentru orice altă aplicație care se bazează pe tabele Dataverse. Implementarea actuală acceptă în principal căutările în care datele de la entitățile de detaliile despre public disponibile pot fi preluate pentru un ID de client dat.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Atașați un mediu Dataverse pentru Customer Insights

**Organizații cu medii Dataverse existente**

Organizațiile care folosesc deja Dataverse pot să [folosească unul dintre cele mediile Dataverse existente](get-started-paid.md) atunci când un administrator stabilește informații despre audiență. Prin furnizarea adresei URL pentru mediul Dataverse, se atașează noului mediu de detalii despre public. Pentru a asigura cea mai bună performanță posibilă, Customer Insights și mediile Dataverse trebuie găzduite în aceeași regiune.

Pentru a atașa un mediu Dataverse, extindeți **Setări avansate** atunci când creați mediul de detalii despre public. Furnizați **adresa URL a mediului Microsoft Dataverse** și bifați caseta de selectare la **Activați partajarea datelor**.

:::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="alt.":::

**Nouă organizație**

Dacă creați o nouă organizație atunci când configurați Customer Insights, veți primi automat un nou mediu Dataverse.

> [!NOTE]
> Dacă organizațiile dvs. utilizează deja Dataverse în entitatea lor găzduită, este important să ne amintim că [crearea mediului Dataverse este controlată de un administrator](/power-platform/admin/control-environment-creation.md). De exemplu, dacă ați configurat un nou mediu de informații privind publicul cu contul organizațional și administratorul a dezactivat crearea de medii de încercare Dataverse pentru toată lumea, cu excepția administratorilor, nu puteți crea un mediu de încercare nou.
> 
> Mediile de încercare Dataverse create în Customer Insights au 3 GB de spațiu de stocare, care nu va conta pentru capacitatea totală autorizată pentru entitatea găzduită. Abonamentele plătite primesc autorizare Dataverse de 15 GB pentru baza de date și 20 GB pentru stocarea fișierelor.

## <a name="output-entities"></a>Entități de ieșire

Unele entități de ieșire din detaliile despre public sunt disponibile ca tabele în Dataverse. Secțiunile de mai jos descriu schema așteptată a acestor tabele.

- [Profil client](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Îmbogățire](#enrichment)
- [Predicția](#prediction)


### <a name="customerprofile"></a>Profil client

Acest tabel conține profilul de client unificat de la Customer Insights. Schema pentru un profil de client unificat depinde de entitățile și atributele utilizate în procesul de îmbinare. O schemă de profil client conține de obicei un subset de atribute din [Definiția Common Data Model a CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tabelul AlternateKey conține chei ale entităților, care au participat la procesul de unificare.

|Column  |Tip  |Descriere  |
|---------|---------|---------|
|DataSourceName    |Șir         | Numele pentru sursa de date. De exemplu: `datasource5`        |
|EntityName        | Șir        | Numele entității din detalii despre public. De exemplu: `contact1`        |
|AlternateValue    |Șir         |ID alternativ care este mapat la ID-ul clientului. Exemplu: `cntid_1078`         |
|KeyRing           | Text multilinie        | Valoare JSON  </br> Eșantion: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | Șir        | ID-ul profilului de client unificat.         |
|AlternateKeyId     | GUID         |  GUID determinist AlternateKey bazat pe msdynci_identifier       |
|msdynci_identifier |   Șir      |   `DataSourceName|EntityName|AlternateValue`  </br> Eșantion: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Acest tabel conține activități ale utilizatorilor care sunt disponibile în Customer Insights.

| Column            | Tip        | Descriere                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Șir      | ID de profil client                                                                      |
| ActivityId        | Șir      | ID-ul intern al activității clienților (cheie primară)                                       |
| SourceEntityName  | Șir      | Nume al entității sursă                                                                |
| SourceActivityId  | Șir      | Cheie primară de la entitatea sursă                                                       |
| ActivityType      | Șir      | Tipul activității semantice sau numele activității particularizate                                        |
| ActivityTimeStamp | DATETIME    | Marca de timp a activității                                                                      |
| Funcția             | Șir      | Titlul sau numele activității                                                               |
| Descriere       | Șir      | Descrierea activității                                                                     |
| URL               | Șir      | Link către o adresă URL externă specifică activității                                         |
| SemanticData      | Șir JSON | Include o listă de perechi de valori cheie pentru câmpurile de mapare semantică specifice tipului de activitate |
| RangeIndex        | Șir      | Marca de timp Unix utilizată pentru sortarea cronologiei activității și a interogărilor eficiente asupra intervalului |
| mydynci_unifiedactivityid   | GUID | ID-ul intern al activității clienților (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Acest tabel conține datele de ieșire ale măsurilor bazate pe atribute ale clienților.

| Column             | Tip             | Descriere                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | Șir           | ID de profil client        |
| Măsuri           | Șir JSON      | Include o listă de perechi de valori cheie pentru numele măsurii și valorile pentru clientul dat | 
| msdynci_identifier | Șir           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ID de profil client |


### <a name="enrichment"></a>Îmbogățire

Acest tabel conține rezultatul procesului de îmbogățire.

| Column               | Tip             |  Descriere                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | Șir           | ID de profil client                                 |
| EnrichmentProvider   | Șir           | Numele furnizorului pentru îmbogățire                                  |
| EnrichmentType       | Șir           | Tipul de îmbogățire                                      |
| Valori               | Șir JSON      | Lista atributelor produse de procesul de îmbogățire |
| msdynci_enrichmentid | GUID             | GUID determinist generat de msdynci_identifier |
| msdynci_identifier   | Șir           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predicția

Acest tabel conține rezultatul predicțiilor modelelor.

| Column               | Tip        | Descriere                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Șir      | ID de profil client                                  |
| ModelProvider        | Șir      | Numele furnizorului modelului                                      |
| Model                | Șir      | Nume model                                                |
| Valori               | Șir JSON | Lista atributelor produse de model |
| msdynci_predictionid | GUID        | GUID determinist generat de msdynci_identifier | 
| msdynci_identifier   | Șir      |  `Model|ModelProvider|CustomerId`                      |
