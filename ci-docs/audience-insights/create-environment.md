---
title: Creați medii în Customer Insights
description: Pași pentru crearea de medii cu un abonament licențiat pentru Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: c37afd5649f8cf40d5379f3d39d0cbd96cde3bd3
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354110"
---
# <a name="create-an-environment-in-audience-insights"></a>Creați un mediu în detalii despre public

Acest articol explică cum să creați un mediu nou după ce organizația dvs. a achiziționat un abonament Dynamics 365 Customer Insights. 

Organizațiile pot crea *două* medii pentru fiecare licență Customer Insights. Dacă organizația dvs. achiziționează mai multe licențe, [contactați echipa noastră de asistență](https://go.microsoft.com/fwlink/?linkid=2079641) pentru a crește numărul de medii disponibile. Pentru mai multe informații despre capacitate și capacitate suplimentară, descărcați [Ghid de licențiere Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Dacă doriți să încercați serviciul, consultați [Configurați un mediu de încercare](../trial-signup.md).

## <a name="create-a-new-environment"></a>Creați un mediu nou

După achiziționarea unei licențe de abonament pentru Customer Insights, administratorul global al Microsoft 365 chiriașul primește un e-mail care îl invită să creeze mediul. Accesați [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) pentru a începe. 

O experiență ghidată vă ajută să parcurgeți pașii pentru a aduna toate informațiile necesare pentru un nou mediu. Aveți nevoie de [permisiuni de administrator](permissions.md) în perspectivele publicului pentru a crea sau gestiona medii.

1. În statisticile publicului, deschideți selectorul de mediu și selectați **+ Nou**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Alegeți selectorul de mediu.":::

1. Urmați experiența ghidată prezentată în secțiunile următoare.

### <a name="step-1-provide-environment-information"></a>Pasul 1: Furnizați informații despre mediu

În pasul **Informații de bază**, alegeți dacă doriți să creați un mediu de la zero sau [copiați date dintr-un alt mediu](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Casetă de dialog pentru a crea un mediu nou Customer Insights.":::

Furnizați următoarele detalii:
   - **Nume**: Numele pentru acest mediu. Acest câmp este deja completat dacă ați copiat dintr-un mediu existent, dar îl puteți modifica.
   - **Alegeți-vă afacerea**: alegeți publicul principal pentru noul mediu. Puteți lucra cu consumatori individuali (B-la-C) sau cu [conturi de business](work-with-business-accounts.md) (B-la-B).
   - **Tip**: Selectați dacă doriți să creați un mediu de tip producție sau sandbox. Mediile Sandbox nu permit reîmprospătarea datelor programate și sunt destinate pre-implementării și testării. Mediile Sandbox utilizează același public principal ca mediul de producție selectat în prezent.
   - **Regiune**: Regiunea în care este implementat și găzduit serviciul.

### <a name="step-2-configure-data-storage"></a>Pasul 2: configurați stocarea datelor

În pasul **Stocarea datelor**, alege unde să stochezi datele din statisticile publicului.

Veți avea două opțiuni: **Stocare Customer Insights** (un Azure Data Lake administrat de echipa Customer Insights) și **Azure Data Lake Storage** (Azure Data Lake Storage al dvs). Opțiunea de stocare a Customer Insights este selectată în mod implicit.

:::image type="content" source="media/data-storage-environment.png" alt-text="Alegeți Azure Data Lake Storage pentru a stoca datele statistice ale publicului dvs. în.":::

Prin salvarea datelor în Azure Data Lake Storage, sunteți de acord că datele vor fi transferate și stocate în locația geografică corespunzătoare pentru acel cont de stocare Azure. Această locație poate diferi de locul în care sunt stocate datele în Dynamics 365 Customer Insights. Aflați mai multe la [Microsoft Trust Center](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights acceptă în prezent următoarele:
> - Entități ingerate din fluxurile de date Power BI care sunt stocate într-un Data Lake gestionat de Microsoft Dataverse.  
> - Conturi Azure Data Lake Storage din aceeași regiune Azure pe care ați selectat-o la crearea mediului.
> - Azure Data Lake Storage conturi care sunt Gen2 și au *spațiu de nume ierarhic* activat. Conturile de stocare Azure Data Lake Gen1 nu sunt acceptate.

Pentru opțiunea Azure Data Lake Storage, puteți alege între o opțiune bazată pe resurse și o opțiune bazată pe abonament pentru autentificare. Pentru mai multe informații, vedeți [Conectați-vă la un cont Azure Data Lake Storage folosind un cont principal de serviciu Azure](connect-service-principal.md). Numele **Recipient** va fi `customerinsights` și nu poate fi schimbat.

Când procesele de sistem, cum ar fi ingestia de date, sunt finalizate, sistemul creează dosare corespunzătoare în contul de stocare pe care l-ați specificat. Fișierele de date și fișierele *model.json* sunt create și adăugate în dosare pe baza numelui procesului.

Dacă creați mai multe medii ale Customer Insights și alegeți să salvați entitățile de ieșire din acele medii în contul dvs. de stocare, Customer Insights creează dosare separate pentru fiecare mediu cu `ci_environmentID` în recipient.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Pasul 3: Conectați-vă la Microsoft Dataverse
   
Pasul **Microsoft Dataverse** vă permite să conectați Customer Insights cu mediul Dataverse.

Furnizați-vă pe al dvs Microsoft Dataverse mediu pentru a partaja date (profiluri și perspective) cu aplicațiile de afaceri bazate pe Dataverse, cum ar fi Dynamics 365 Marketing sau aplicațiile bazate pe model în Power Apps. Lăsați acest câmp necompletat dacă nu aveți al dvs Dataverse mediu și vă vom furniza unul.

Conectarea la dvs Dataverse mediul vă permite de asemenea [ingerați date din sursele de date local folosind Power Platform fluxuri de date și gateway-uri](data-sources.md#add-data-from-on-premises-data-sources). De asemenea, puteți utiliza [modele out-of-box predicție](predictions-overview.md?tabs=b2c#out-of-box-models) prin conectarea la a Dataverse mediu inconjurator.

> [!IMPORTANT]
> Informații despre clienți și Dataverse trebuie să fie în aceeași regiune pentru a permite partajarea datelor.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="partajarea datelor cu Microsoft Dataverse activat automat pentru instanțe noi.":::

> [!NOTE]
> Customer Insights nu acceptă următoarele scenarii de partajare:
> - Dacă salvați toate datele pe propriul Azure Data Lake Storage, nu veți putea activa partajarea datelor cu un Data Lake gestionat de Dataverse.
> - Dacă activați partajarea datelor Dataverse, nu veți putea [crea valori prezise sau lipsă într-o entitate](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Pasul 4: finalizați setările

În pasul **Recenzie**, parcurgeți toate setările specificate. Când totul pare complet, selectați **Creare** pentru a configura mediul. 

De asemenea, puteți modifica majoritatea setărilor ulterior. Pentru informații suplimentare, consultați [Gestionare medii](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Lucrați cu noul dvs. mediu

Consultați următoarele articole pentru a vă ajuta să începeți configurarea Customer Insights: 

- [Adăugați mai mulți utilizatori și atribuiți permisiuni](permissions.md).
- [Ingerați sursele de date](data-sources.md) și rulați-le prin [procesul de unificare a datelor](data-unification.md) pentru a obține [profiluri unificate ale clienților](customer-profiles.md).
- [Îmbogățiți profilurile unificate ale clienților](enrichment-hub.md) sau [rulați modele predictive](predictions-overview.md).
- [Creați segmente](segments.md) pentru a grupa clienți și [măsuri](measures.md) pentru a reviziui indicatorii KPI.
- [Configurați conexiuni](connections.md) și [exporturi](export-destinations.md) pentru a procesa subseturi de date în alte aplicații.
