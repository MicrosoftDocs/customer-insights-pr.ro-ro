---
title: Creați medii în Customer Insights
description: Pași pentru crearea de medii cu un abonament licențiat pentru Dynamics 365 Customer Insights.
ms.date: 10/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 95afd1fedb98a451e4978ee66be2ea98ad7a4a76
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645720"
---
# <a name="create-an-environment-in-audience-insights"></a>Creați un mediu în detalii despre public

Acest articol explică cum să creați un mediu nou după ce organizația dvs. a achiziționat un abonament Dynamics 365 Customer Insights. 

Organizațiile pot crea *două* medii pentru fiecare licență Customer Insights. Dacă organizația dvs. achiziționează mai multe licențe, [contactați echipa noastră de asistență](https://go.microsoft.com/fwlink/?linkid=2079641) pentru a crește numărul de medii disponibile. Pentru mai multe informații despre capacitate și capacitate suplimentară, descărcați [Ghid de licențiere Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Dacă doriți să încercați serviciul, consultați [Configurați un mediu de încercare](../trial-signup.md).

## <a name="create-a-new-environment"></a>Creați un mediu nou

După achiziționarea unei licențe de abonament pentru Customer Insights, administratorul global al chiriașului Microsoft 365 primește un e-mail care îi invită să creeze mediul. Accesați [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) pentru a începe. 

O experiență ghidată vă ajută să parcurgeți pașii pentru a aduna toate informațiile necesare pentru un nou mediu. Aveți nevoie de [permisiuni de administrator](permissions.md) în perspectivele publicului pentru a crea sau gestiona medii.

1. În statisticile publicului, deschideți selectorul de mediu și selectați **+ Nou**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Alegeți selectorul de mediu.":::

1. Urmați experiența ghidată prezentată în secțiunile următoare.

### <a name="step-1-provide-environment-information"></a>Pasul 1: Furnizați informații despre mediu

În pasul **Informații de bază**, alegeți dacă doriți să creați un mediu de la zero sau [copiați date dintr-un alt mediu](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Casetă de dialog pentru a crea un mediu nou Customer Insights.":::

Furnizați următoarele detalii:
   - **Nume**: Numele pentru acest mediu. Acest câmp este deja completat dacă ați copiat dintr-un mediu existent, dar îl puteți modifica.
   - **Alegeți-vă afacerea**: Alegeți publicul principal pentru noul mediu. Puteți lucra cu clienți individuali (B2C) sau [conturi de business](work-with-business-accounts.md) (B2B).
   - **Tip**: Selectați dacă doriți să creați un mediu de tip producție sau sandbox. Mediile Sandbox nu permit reîmprospătarea datelor programate și sunt destinate pre-implementării și testării. Mediile Sandbox utilizează același public principal ca mediul de producție selectat în prezent.
   - **Regiune**: Regiunea în care este implementat și găzduit serviciul.

### <a name="step-2-configure-data-storage"></a>Pasul 2: configurați stocarea datelor

În pasul **Stocarea datelor**, alege unde să stochezi datele din statisticile publicului.

Veți avea două opțiuni: **Depozitare Customer Insights** (un Azure Data Lake administrat de echipa Customer Insights) și **Azure Data Lake Storage** (Azure Data Lake Storage al dvs). Opțiunea de stocare a Customer Insights este selectată în mod implicit.

:::image type="content" source="media/data-storage-environment.png" alt-text="Alegeți Azure Data Lake Storage pentru a stoca datele statistice ale publicului dvs. în.":::

Prin salvarea datelor în Azure Data Lake Storage, sunteți de acord că datele vor fi transferate și stocate în locația geografică corespunzătoare pentru acel cont de stocare Azure. Această locație poate diferi de locul în care sunt stocate datele în Dynamics 365 Customer Insights. Aflați mai multe la [Microsoft Trust Center](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights acceptă în prezent următoarele:
> - Entități ingerate din fluxurile de date Power BI care sunt stocate într-un Data Lake gestionat de Microsoft Dataverse.  
> - Conturi Azure Data Lake Storage din aceeași regiune Azure pe care ați selectat-o la crearea mediului.
> - Conturi Azure Data Lake Storage care au *spațiu de nume ierarhic*.

Pentru opțiunea Azure Data Lake Storage, puteți alege între o opțiune bazată pe resurse și o opțiune bazată pe abonament pentru autentificare. pentru mai multe informații, consultați [Conectați detaliile privind publicul la un cont Azure Data Lake Storage Gen2 cu o entitate principală de serviciu Azure](connect-service-principal.md). Numele **Recipient** va fi `customerinsights` și nu poate fi schimbat.

Când procesele de sistem, cum ar fi ingestia de date, sunt finalizate, sistemul creează dosare corespunzătoare în contul de stocare pe care l-ați specificat. Fișierele de date și fișierele *model.json* sunt create și adăugate în dosare pe baza numelui procesului.

Dacă creați mai multe medii ale Customer Insights și alegeți să salvați entitățile de ieșire din acele medii în contul dvs. de stocare, Customer Insights creează dosare separate pentru fiecare mediu cu `ci_environmentID` în recipient.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Pasul 3: Conectați-vă la Microsoft Dataverse
   
Pasul **Microsoft Dataverse** vă permite să conectați Customer Insights cu mediul Dataverse.

Pentru a utiliza [modele predicție predefinite](predictions-overview.md#out-of-box-models), configurați partajarea datelor cu Dataverse. Sau puteți activa ingestia de date din sursele de date local, furnizând URL de mediu Microsoft Dataverse administrat de organizația dvs. Selectați **Activați partajarea datelor** pentru a partaja datele de ieșire Customer Insights cu un Dataverse Data Lake gestionat.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Opțiuni de configurare pentru a permite partajarea datelor cu Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights nu acceptă următoarele scenarii de partajare:
> - Dacă salvați toate datele pe propriul Azure Data Lake Storage, nu veți putea activa partajarea datelor cu un Data Lake gestionat de Microsoft Dataverse.
> - Dacă activați partajarea datelor cu un Data Lake gestionat de Microsoft Dataverse, nu veți putea [crea valori prezise sau lipsă într-o entitate](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Pasul 4: finalizați setările

În pasul **Recenzie**, parcurgeți toate setările specificate. Când totul pare complet, selectați **Creare** pentru a configura mediul. 

De asemenea, puteți modifica majoritatea setărilor ulterior. Pentru informații suplimentare, consultați [Gestionare medii](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Lucrați cu noul dvs. mediu

Consultați următoarele articole pentru a vă ajuta să începeți cu configurarea Customer Insights. 

- [Adăugați mai mulți utilizatori și atribuiți permisiuni](permissions.md).
- [Ingerați sursele de date](data-sources.md) și rulați-le prin [procesul de unificare a datelor](data-unification.md) pentru a obține [profiluri unificate ale clienților](customer-profiles.md).
- [Îmbogățiți profilurile unificate ale clienților](enrichment-hub.md) sau [rulați modele predictive](predictions-overview.md).
- [Creați segmente](segments.md) pentru a grupa clienții și [măsuri](measures.md) și a revizui indicatorii KPI.
- [Configurați conexiuni](connections.md) și [exporturi](export-destinations.md) pentru a procesa subseturi de date în alte aplicații.
