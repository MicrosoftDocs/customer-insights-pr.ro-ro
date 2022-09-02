---
title: Exportați jurnalele de diagnosticare (previzualizare)
description: Aflați cum să trimiteți jurnalele către Microsoft Azure Monitorizați.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: c573c46fda895d36d29712e75fe28b261c9b399a
ms.sourcegitcommit: 0b5bfe0145dbd325fa518df4561d6a0a9a352264
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/25/2022
ms.locfileid: "9352816"
---
# <a name="export-diagnostic-logs-preview"></a>Exportați jurnalele de diagnosticare (previzualizare)

Redirecționați jurnalele din Customer Insights folosind Azure Monitor. Jurnalele de resurse Azure Monitor vă permit să monitorizați și să trimiteți jurnalele către [Azure Storage](https://azure.microsoft.com/services/storage/) ,[Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) , sau transmiteți-le în flux [Huburi de evenimente Azure](https://azure.microsoft.com/services/event-hubs/).

Customer Insights trimite următoarele jurnale de evenimente:

- **Evenimente de audit**
  - **APIEvent** - permite urmărirea modificărilor prin intermediul Dynamics 365 Customer Insights UI.
- **Evenimente operaționale**
  - **WorkflowEvent** - vă permite să configurați [surse de date](data-sources.md) ,[unifica](data-unification.md) ,[îmbogăţi](enrichment-hub.md) , și [export](export-destinations.md) date în alte sisteme. Acești pași pot fi efectuati individual (de exemplu, declanșați un singur export). De asemenea, pot rula orchestrate (de exemplu, reîmprospătarea datelor din surse de date care declanșează procesul de unificare, care va aduce îmbogățiri și va exporta datele într-un alt sistem). Pentru mai multe informații, consultați [Schema WorkflowEvent](#workflow-event-schema) .
  - **APIEvent** - trimite toate apelurile API ale instanței clienților către Dynamics 365 Customer Insights . Pentru mai multe informații, consultați [Schema APIEvent](#api-event-schema) .

## <a name="set-up-the-diagnostic-settings"></a>Configurați setările de diagnosticare

### <a name="prerequisites"></a>Cerințe preliminare

- Un activ [Abonament Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/) .
- [Administrator](permissions.md#admin) permisiunile din Customer Insights.
- O resursă validă pe Azure care urmează [cerințele destinației](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) pentru Azure Storage, Azure Event Hub sau Azure Log Analytics.
- [Rol de colaborator și administrator de acces utilizator](/azure/role-based-access-control/role-assignments-portal) pe resursa de destinație pe Azure. Resursa poate fi o Azure Data Lake Storage cont, un hub de evenimente Azure sau un spațiu de lucru Azure Log Analytics. Această permisiune este necesară în timpul configurării setărilor de diagnosticare în Customer Insights, dar poate fi modificată după configurarea cu succes.
- Cel puțin cel **Cititor** rol pe grupul de resurse din care face parte resursa.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Configurați diagnosticarea cu Azure Monitor

1. În Customer Insights, accesați **Admin** > **Sistem** și selectați **Diagnosticare** fila.

1. Selectați **Adăugați destinația** .

   :::image type="content" source="media/diagnostics-pane.png" alt-text="Conexiune de diagnosticare.":::

1. Furnizați un nume în **Nume pentru destinația de diagnosticare** camp.

1. Selectează **Tipul de resursă** (Cont de stocare, Hub de evenimente sau Log Analytics).

1. Selectează **Abonament**, **de resurse**, și **Resursă** pentru resursa de destinație. Vedea [Configurare pe resursa destinație](#configuration-on-the-destination-resource) pentru permisiuni și informații de jurnal.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord** .

1. Selectați **Conectați-vă la sistem** pentru a vă conecta la resursa destinație. Jurnalele încep să apară în destinație după 15 minute, dacă API-ul este în uz și generează evenimente.

## <a name="configuration-on-the-destination-resource"></a>Configurare pe resursa destinație

Pe baza alegerii tipului de resursă, apar automat următoarele modificări:

### <a name="storage-account"></a>Cont de stocare

Principalul serviciului Customer Insights primește **Colaborator cont de stocare** permisiunea pe resursa selectată și creează două containere sub spațiul de nume selectat:

- `insight-logs-audit` conținând **evenimente de audit**
- `insight-logs-operational` conținând **evenimente operaționale**

### <a name="event-hub"></a>Hub de evenimente

Principalul serviciului Customer Insights primește **Proprietar de date Azure Event Hubs** permisiunea asupra resursei și creează două Huburi de evenimente sub spațiul de nume selectat:

- `insight-logs-audit` conținând **evenimente de audit**
- `insight-logs-operational` conținând **evenimente operaționale**

### <a name="log-analytics"></a>Log Analytics

Principalul serviciului Customer Insights primește **Log Analytics Contributor** permisiunea asupra resursei. Jurnalele sunt disponibile sub **Bușteni** > **Mese** > **Managementul jurnalului** în spațiul de lucru Log Analytics selectat. Extindeți **Managementul jurnalului** soluție și localizați`CIEventsAudit` și`CIEventsOperational` Mese.

- `CIEventsAudit` conținând **evenimente de audit**
- `CIEventsOperational` conținând **evenimente operaționale**

Sub **Întrebări** fereastra, extindeți **Audit** soluție și localizați exemplele de interogări furnizate prin căutarea`CIEvents` .

## <a name="remove-a-diagnostics-destination"></a>Eliminați o destinație de diagnosticare

1. Mergi la **Admin** > **Sistem** și selectați **Diagnosticare** fila.

1. Selectați destinația de diagnosticare din listă.

   > [!TIP]
   > Eliminarea destinației oprește redirecționarea jurnalului, dar nu șterge resursa din abonamentul Azure. Pentru a șterge resursa din Azure, selectați linkul din **Acțiuni** pentru a deschide portalul Azure pentru resursa selectată și ștergeți-o acolo. Apoi ștergeți destinația de diagnosticare.

1. În **Acțiuni** coloana, selectați **Șterge** pictograma.

1. Confirmați ștergerea pentru a elimina destinația și pentru a opri redirecționarea jurnalului.

## <a name="log-categories-and-event-schemas"></a>Categoriile de jurnal și schemele de evenimente

În prezent [evenimente API](apis.md) și evenimentele fluxului de lucru sunt acceptate și se aplică următoarele categorii și scheme.
Schema de jurnal urmează [Schemă comună Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema) .

### <a name="categories"></a>Categorii

Customer Insights oferă două categorii:

- **Evenimente de audit** :[evenimente API](#api-event-schema) pentru a urmări modificările de configurare ale serviciului. `POST|PUT|DELETE|PATCH` operațiunile intră în această categorie.
- **Evenimente operaționale** :[evenimente API](#api-event-schema) sau [evenimente de flux de lucru](#workflow-event-schema) generate în timpul utilizării serviciului.  De exemplu,`GET` cererile sau evenimentele de execuție a unui flux de lucru.

## <a name="event-schemas"></a>Scheme de evenimente

Evenimentele API și evenimentele fluxului de lucru au o structură comună, dar cu câteva diferențe. Pentru mai multe informații, vezi [Schema de evenimente API](#api-event-schema) sau [schema de evenimente a fluxului de lucru](#workflow-event-schema) .

### <a name="api-event-schema"></a>Schema de evenimente API

| Câmp             | DataType  | Obligatoriu/Opțional | Descriere       | Exemplu        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Marcaj temporal | Obligatoriu          | Marca temporală a evenimentului (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | Șir    | Obligatoriu          | ResourceId al instanței care a emis evenimentul         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | Șir    | Obligatoriu          | Numele operațiunii reprezentate de acest eveniment.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | Șir    | Obligatoriu          | Categoria de jurnal a evenimentului. Fie`Operational` sau`Audit` . Toate solicitările HTTP POST/PUT/PATCH/DELETE sunt etichetate cu`Audit` , orice altceva cu`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | Șir    | Obligatoriu          | Starea evenimentului. `Success`,`ClientError` ,`Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | Șir    | Opțional          | Starea rezultatului evenimentului. Dacă operația corespunde unui apel REST API, acesta este codul de stare HTTP.        | `200`             |
| `durationMs`      | Long      | Opțional          | Durata operațiunii în milisecunde.     | `133`     |
| `callerIpAddress` | Șir    | Opțional          | Adresa IP a apelantului, dacă operațiunea corespunde unui apel API care provine de la o adresă IP disponibilă public.                                                 | `144.318.99.233`         |
| `identity`        | Șir    | Opțional          | Obiect JSON care descrie identitatea utilizatorului sau a aplicației care a efectuat operația.       | Vedea [Identitate](#identity-schema) secțiune.     |  
| `properties`      | Șir    | Opțional          | Obiect JSON cu mai multe proprietăți pentru categoria particulară de evenimente.      | Vedea [Proprietăți](#api-properties-schema) secțiune.    |
| `level`           | Șir    | Obligatoriu          | Nivelul de severitate al evenimentului.    | `Informational`,`Warning` ,`Error` , sau`Critical` .           |
| `uri`             | Șir    | Opțional          | URI de solicitare absolută.    |               |

#### <a name="identity-schema"></a>Schema de identitate

The`identity` Obiectul JSON are următoarea structură

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Câmp                         | Descriere                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Rol atribuit utilizatorului sau aplicației. Pentru mai multe informații, vezi [permisiunile utilizatorului](permissions.md) .                                     |
| `Authorization.RequiredRoles` | Roluri necesare pentru a efectua operația. `Admin` rolului i se permite să facă toate operațiunile.                                                    |
| `Claims`                      | Revendicări ale utilizatorului sau al aplicației JSON web token (JWT). Proprietățile revendicării variază în funcție de organizație și de Azure Active Directory configurație. |

#### <a name="api-properties-schema"></a>Schema proprietăților API

[evenimente API](apis.md) au următoarele proprietăți.

| Câmp                        | Descriere                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Mereu`ApiEvent` , marcând evenimentul de jurnal ca eveniment API.                                                                 |
| `properties.userAgent`       | Agent browser care trimite cererea sau`unknown` .                                                                        |
| `properties.method`          | Metoda HTTP:`GET/POST/PUT/PATCH/HEAD` .                                                                                |
| `properties.path`            | Calea relativă a cererii.                                                                                          |
| `properties.origin`          | URI care indică de unde provine o preluare sau`unknown` .                                                                  |
| `properties.operationStatus` | `Success` for HTTP Status code < 400 <br> `ClientError` for HTTP Status code < 500 <br> `Error` pentru starea HTTP >= 500 |
| `properties.tenantId`        | ID organizație                                                                                                        |
| `properties.tenantName`      | Nume organizație.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId al apelantului.                                                                         |
| `properties.instanceId`      | Informații despre clienți`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Schema evenimentelor fluxului de lucru

Fluxul de lucru conține mai mulți pași. [Ingerați surse de date](data-sources.md),[unifica](data-unification.md),[îmbogăţi](enrichment-hub.md), și [export](export-destinations.md) date. Toți acești pași pot rula individual sau orchestrați cu următoarele procese.

#### <a name="operation-types"></a>Tipuri de operații

| Tipul operațiunii     | Grupare                                     |
| ----------------- | ----------------------------------------- |
| Ingestie         | [Surse de date](data-sources.md)           |
| Pregătirea datelor   | [Surse de date](data-sources.md)           |
| Hartă               | [Unificarea datelor](data-unification.md)   |
| Corespondență             | [Unificarea datelor](data-unification.md)   |
| Îmbinare             | [Unificarea datelor](data-unification.md)   |
| ProfileStore      | [Profiluri de client](customer-profiles.md) |
| Căutarea            | [Profiluri de client](customer-profiles.md) |
| Activitate          | [Activități](activities.md)                  |
| AttributeMeasures | [Segmente și Măsuri](segments.md)      |
| EntityMeasures    | [Segmente și Măsuri](segments.md)      |
| Măsuri          | [Segmente și Măsuri](segments.md)      |
| Segmentare      | [Segmente și Măsuri](segments.md)      |
| Îmbogățire        | [Îmbogățire](enrichment-hub.md)                                          |
| Intelligence      | [Predicții](predictions-overview.md)                                          |
| AiBuilder         | [Predicții](predictions-overview.md)                                          |
| Detalii          | [Predicții](predictions-overview.md)                                          |
| Export            | [Exporturi](export-destinations.md)                                          |
| ModelManagement   | [Predicții](custom-models.md)                                           |
| Relație      | [Unificarea datelor](relationships.md)                                           |

#### <a name="field-description"></a>Descrierea câmpului

| Câmp           | DataType  | Obligatoriu/Opțional | Descriere                                                                                                                                                   | Exemplu                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Marcaj temporal | Obligatoriu          | Marca temporală a evenimentului (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | Șir    | Obligatoriu          | ResourceId al instanței care a emis evenimentul.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | Șir    | Obligatoriu          | Numele operațiunii reprezentate de acest eveniment. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Vedea [Tipuri de operații](#operation-types) pentru trimitere. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | Șir    | Obligatoriu          | Categoria de jurnal a evenimentului. Mereu`Operational` pentru evenimente Workflow                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | Șir    | Obligatoriu          | Starea evenimentului. `Running`,`Skipped`,`Successful`,`Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Long      | Opțional          | Durata operațiunii în milisecunde.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | Șir    | Opțional          | Obiect JSON cu mai multe proprietăți pentru categoria particulară de evenimente.                                                                                        | Vezi subsecțiunea [Proprietăți flux de lucru](#workflow-properties-schema)                                                                                                       |
| `level`         | Șir    | Obligatoriu          | Nivelul de severitate al evenimentului.                                                                                                                                  | `Informational`, `Warning` sau `Error`                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>Schema proprietăților fluxului de lucru

Evenimentele fluxului de lucru au următoarele proprietăți.

| Câmp              | Workflow | Activitate | Descriere            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Da      | Da  | Mereu`WorkflowEvent`, marcând evenimentul ca eveniment de flux de lucru.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Da      | Da  | Identificatorul rulării fluxului de lucru. Toate evenimentele fluxului de lucru și sarcinilor din cadrul execuției fluxului de lucru au același lucru `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Da      | Da  | Identificatorul operației, vezi [Tipuri de operații](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Da      | No   | Numai fluxul de lucru. Numărul de sarcini declanșate de fluxul de lucru.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Da      | No   | Opțional. Numai evenimente de flux de lucru. The Azure Active Directory [objectId al utilizatorului](/azure/marketplace/find-tenant-object-id#find-user-object-id) cine a declanșat fluxul de lucru, vezi și `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Da      | No   | `full` sau`incremental` reîmprospăta.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Da      | No   | `OnDemand` sau `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Da      | No   | `Running` sau `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Da      | Da  | Marca temporală UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Da      | Da  | Marca temporală UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Da      | Da  | Marca temporală UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Da      | Da  | Informații despre clienți`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Da  | - Pentru OperationType =`Export`, identificatorul este ghidul configurației de export. <br> - Pentru OperationType =`Enrichment`, este ghidul îmbogățirii <br> - Pentru OperationType`Measures` și`Segmentation`, identificatorul este numele entității. |
| `properties.friendlyName`                    | No       | Da  | Numele ușor de utilizat al exportului sau al entității care este procesată.                                                                                                                                                                                           |
| `properties.error`                           | No       | Da  | Opțional. Mesaj de eroare cu mai multe detalii.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Da  | Opțional. Pentru OperationType`Export` numai. Identifică tipul de export. Pentru mai multe informații, vezi [prezentare generală a destinațiilor de export](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Da  | Opțional. Pentru OperationType`Export` numai. Conține o listă de entități configurate în export.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Da  | Opțional. Pentru OperationType`Export` numai. Mesaj detaliat pentru export.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Da  | Opțional. Pentru OperationType`Segmentation` numai. Indică numărul total de membri pe care îl are segmentul.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]
