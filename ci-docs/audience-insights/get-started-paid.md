---
title: Creați și configurați o licență plătită a Customer Insights
description: Pași pentru obținerea unui abonament cu licență pentru Dynamics 365 Customer Insights și configurați-l.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034467"
---
# <a name="get-started-with-a-paid-subscription"></a>Începeți cu un abonament plătit

Acest articol explică cum să creați un mediu nou după ce organizația dvs. a achiziționat un abonament Dynamics 365 Customer Insights. Dacă doriți să achiziționați Customer Insights, opțiunile noastre de contact sunt listate în site-ul web [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/). 

Dacă doriți să încercați serviciul și caracteristicile, consultați [Configurați un mediu de încercare](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Creați un mediu într-o organizație existentă

După achiziționarea unei licențe de abonament pentru Customer Insights, administratorul global al chiriașului Microsoft 365 primește un e-mail care îi invită să creeze mediul. Accesați [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) pentru a începe. 

Customer Insights nu este licențiat per utilizator, deci nu va apărea în zona Licențe. Dacă căutați licența în centrul de administrare Microsoft 365, accesați **Produsele dvs.**. 

> [!NOTE]
> Organizațiile pot crea *două* medii pentru fiecare licență Customer Insights. Dacă organizația dvs. achiziționează mai multe ori licență, vă rugăm să [contactați echipa noastră de asistență](https://go.microsoft.com/fwlink/?linkid=2079641) pentru a crește numărul de medii disponibile. Pentru mai multe informații despre capacitate și capacitate suplimentară, descărcați [Ghid de licențiere Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Pentru crearea unui mediu:

1. În dialogul **Creați un mediu**, selectați **Mediu nou**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Casetă de dialog pentru a crea un mediu nou Customer Insights.":::

   Vă recomandăm să începeți să configurați un mediu de la zero. Cu toate acestea, dacă sunteți administrator sau membru al unui mediu de încercare, ați putea [copia date dintr-un alt mediu](manage-environments.md#copy-the-environment-configuration), alegând **Copiați din mediul existent**. Veți vedea o listă cu toate mediile disponibile în organizația dvs. de unde puteți copia datele.

1. Furnizați următoarele detalii:
   - **Nume**: Numele pentru acest mediu. Acest câmp este deja completat dacă ați copiat dintr-un mediu existent, dar îl puteți modifica.
   - **Regiune**: Regiunea în care este implementat și găzduit serviciul.
   - **Tip**: Selectați dacă doriți să creați un mediu de tip producție sau sandbox. Mediile Sandbox nu permit reîmprospătarea datelor programate și sunt destinate pre-implementării și testării.
   
1. Opțional, puteți selecta **Setări complexe**:

   - **Se salvează toate datele în**: Specifică unde doriți să stocați datele de ieșire generate de Customer Insights. Veți avea două opțiuni: **Depozitare Customer Insights** (un Azure Data Lake administrat de echipa Customer Insights) și **Azure Data Lake Storage** (Azure Data Lake Storage al dvs). Opțiunea de stocare a Customer Insights este selectată în mod implicit.

     > [!NOTE]
     > Prin salvarea datelor în Azure Data Lake Storage, sunteți de acord că datele vor fi transferate și stocate în locația geografică corespunzătoare pentru respectivul cont de stocare Azure, care poate diferi de locul în care sunt stocate datele în Dynamics 365 Customer Insights. [Aflați mai multe de la Centrul de autorizare Microsoft.](https://www.microsoft.com/trust-center)
     >
     > În prezent, entitățile ingerate din fluxurile de date Power BI sunt stocate în Microsoft Dataverse-Data Lake gestionat. 
     > 
     > Acceptăm numai conturi Azure Data Lake Storage din aceeași regiune Azure pe care ați selectat-o la crearea mediului. 
     > 
     > Noi acceptăm numai conturi Azure Data Lake Storage care au activat spațiul de nume ierarhic.


   - Pentru opțiunea Azure Data Lake Storage, puteți alege între o opțiune bazată pe resurse și o opțiune bazată pe abonament pentru autentificare. pentru mai multe informații, consultați [Conectați detaliile privind publicul la un cont Azure Data Lake Storage Gen2 cu o entitate principală de serviciu Azure](connect-service-principal.md). Numele **Recipient** nu poate fi schimbat și va fi `customerinsights`.
   
   - Dacă doriți să utilizați [modele predefinite](predictions-overview.md#out-of-box-models), configurați partajarea datelor cu Microsoft Dataverse, sau activați ingestia de date din sursele de date local, furnizați adresa URL de mediu Microsoft Dataverse sub **Configurați partajarea datelor cu Microsoft Dataverse și activați capabilități suplimentare**. Selectați **Activați partajarea datelor** pentru a partaja datele de ieșire Customer Insights cu un Microsoft Dataverse Data Lake gestionat.

     > [!NOTE]
     > - Partajarea datelor cu Microsoft Dataverse Data Lage gestionat nu este acceptat atunci când salvați toate datele pe propriul Azure Data Lake Storage.
     > - [Predicție a valorilor lipsă într-o entitate](predictions.md) momentan nu este acceptat atunci când activați partajarea datelor cu Microsoft Dataverse Data Lake gestionat.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Opțiuni de configurare pentru a permite partajarea datelor cu Microsoft Dataverse.":::

   Când procesele de sistem, cum ar fi ingestia de date, sunt complete, sistemul creează dosare corespunzătoare în contul de stocare pe care l-ați specificat. Fișierele de date și fișierele model.json sunt create și adăugate în dosare pe baza numelui procesului.

   Dacă creați mai multe medii de Customer Insights și alegeți să salvați entitățile de ieșire din acele medii în contul dvs. de stocare, vor fi create dosare separate pentru fiecare mediu cu ci_<environmentid> în recipient.

1. Selectați **Creare** pentru a configura mediul. 

## <a name="configure-an-environment"></a>Configurați un mediu

Consultați următoarele articole pentru a vă ajuta să începeți cu configurarea Customer Insights. 

- [Adăugați mai mulți utilizatori și atribuiți permisiuni](permissions.md).
- [Ingerați sursele de date](data-sources.md) și rulați-le prin [procesul de unificare a datelor](data-unification.md) pentru a obține [profiluri unificate ale clienților](customer-profiles.md).
- [Îmbogățiți profilurile unificate ale clienților](enrichment-hub.md) sau [rulați modele predictive](predictions-overview.md).
- Creați [segmente](segments.md) pentru a grupa clienții și [măsuri](measures.md) și a revizui indicatorii KPI.
- Configurați [conexiuni](connections.md) și [exporturi](export-destinations.md) pentru a procesa subseturi de date în alte aplicații.
