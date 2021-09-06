---
title: Creați și configurați o versiune de încercare a Customer Insights
description: Pași pentru obținerea unui abonament de încercare pentru Dynamics 365 Customer Insights și configurați-l.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f038dedd369ac9e623146b66528efa87c47a8c23769037d8709fa9b804a0b723
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035430"
---
# <a name="set-up-a-trial-environment"></a>Configurarea unui mediu de încercare 

O versiune de încercare a Dynamics 365 Customer Insights vă permite să examinați capacitatea cheie și să aflați mai multe despre diferitele caracteristici. Un abonament de încercare este șters după expirare. Mediile de încercare sunt create de utilizatori individuali care devin administratori ai mediului de încercare. Aceștia pot invita mai mulți utilizatori la încercarea lor și pot configura diferitele caracteristici.

## <a name="create-a-trial-environment"></a>Creați un mediu de încercare

Vă puteți înscrie pentru o versiune de încercare pe [pagina de înscriere versiune de încercare](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Alegeți opțiunea **Înregistrați-vă pentru o versiune de încercare gratuită** și selectați **Înregistrați-vă acum**.

1. Furnizați adresa de e-mail a muncii sau a școlii, spuneți-ne mai multe despre dvs. și selectați **Începeți**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialog pentru a vă înscrie pentru o instanță versiune de încercare":::

1. Revizuiți termenii și condițiile, și selectați **Continuați** pentru a confirma.

1. Furnizați un **Nume** pentru noul dvs. mediu. 

1. Stabiliți mediul **Tip** ca **Versiune de încercare**.

1. În câmpul **Selectați o demonstrație de industrie**, puteți alege opțional un set de date specifice industriei. Puteți de asemenea [trece la o demonstrație de industrie](#use-industry-specific-demo-data-sets-in-audience-insights) mai târziu și începeți cu setul de date implicit.

1. Alegeți **Regiunea** pentru mediul dvs.

1. Opțional, dacă sunteți administratorul unei organizații Dynamics 365: Selectați **Setări avansate** și furnizați adresa URL a organizației dvs. pentru a utiliza caracteristici de predicție, cum ar fi predicția de retragere a clienților. 

1. Selectați **Creare**. 

Configurarea mediului durează câteva minute. După finalizare, sunteți redirecționat către mediul demo sau demo-ul din industrie pe care îl alegeți în pasul de mai sus. Acum puteți explora aplicația cu date demo numai în citire. Pentru a adăuga propriile date în mediu, consultați [Creați date demonstrative specifice scenariului în propriul mediu](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Captură de ecran a unui mediu de încercare nou creat.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Utilizați seturi de date demonstrative specifice industriei în statistici privind publicul

Conectarea surselor de date reale este unul dintre pașii critici în utilizarea puterii Customer Insights. Pentru a încerca funcții fără a vă interfera cu propriile date, puteți utiliza opțional date demo specifice industriei. Există câteva seturi de date demonstrative disponibile pentru următoarele industrii: 

-   Auto
-   Servicii bancare
-   Bunuri de consum
-   Instituții guvernamentale
-   Asistență medicală
-   Ospitalitate
-   Asigurări
-   Producție 
-   Servicii profesionale
-   Comerț cu amănuntul

### <a name="see-industry-specific-demo-data-in-trials"></a>Vedeți datele demo specifice industriei în versiuni de încercare

Pentru o versiune numai în citire a Customer Insights, adaptată la o anumită industrie sau scenariu, începeți în mediul Demonstrație. 
 
1.  În detaliile publicului, alegeți mediul **Demonstrație** în selectorul de mediu.

2.  Pe **Acasă**, alegeți o opțiune din meniul derulant Selectați o demonstrație de industrie.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Alegeți o industrie pentru mediul de încercare.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Creați date demonstrative specifice scenariului în propriul mediu

În calitate de administrator, selectați selectorul de mediu din antetul aplicației pentru a crea un mediu nou. În noul mediu, vă puteți configura propriile surse de date și puteți configura aplicația în funcție de cerințele dvs. 

1.  În Detalii despre audiență, accesați **Date** > **Surse de date**.

2.  Pentru a importa propriile surse de date, accesați [ghid privind ingestia de date](data-sources.md).     
   Dacă preferați să lucrați cu eșantion de date care vă permit să încercați consumul de date, puteți ingera datele demo din industrie în mediul dvs. Alegeți opțiunea **Importați din Datahub** și urmați pașii de mai jos.

3.  Selectați cardul de industrie care se potrivește scenariului dvs. 

4.  Examinați și actualizați opțional numele sugerat al sursei de date. 

5.  Selectați **Următorul** pentru a ingera datele eșantionului. 

Acum puteți utiliza datele ingerate pentru a adapta Customer Insights la scenariul dvs. Pentru a vedea un mediu specific datelor demo ingerate, alegeți opțiunea **<Industry> Demonstrație** în selectorul de mediu.

## <a name="limitations-in-trials"></a>Limitări în versiuni de încercare

- Versiunile de încercare sunt active timp de 30 de zile în mod prestabilit. Cu toate acestea, le puteți extinde după ziua 23 când vă conectați la versiunea dvs. de încercare.
- Nu puteți utiliza propriul cont de stocare Azure Data Lake Storage pentru a stoca date de ieșire în timpul unei versiuni de încercare. Cu toate acestea, puteți ingera date dintr-un cont de stocare Data Lake.
- Puteți stoca până la 3 GB date în mediul Dataverse care se aprovizionează automat atunci când porniți o versiune de încercare Customer Insights.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Copiați datele dintr-o versiune de încercare într-un abonament plătit

În general, vă recomandăm să începeți din nou cu propriile date atunci când faceți upgrade la versiunea plătită a Customer Insights. 

Opțional, vă puteți copia datele dintr-un mediu de încercare dacă achiziționați Customer Insights. Trebuie să fiți administratorul perioadei de încercare Customer Insights și administratorul global al entității găzduite Microsoft 365 sau administratorul Dynamics 365 din organizația dvs. pentru a migra setările dintr-un mediu de încercare într-un mediu plătit. 

După ce v-ați conectat pentru prima dată la instanța dvs. plătită de Customer Insights, vi se cere să creați un mediu nou. În acest proces, puteți alege să copiați configurația dintr-un mediu existent și să migrați majoritatea setărilor. Dacă aveți permisiunile menționate mai sus, mediul de încercare se va afișa în această listă. Pentru mai multe informații, consultați [Copiați configurația mediului](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Pașii următori

Consultați următoarele articole pentru a vă ajuta să începeți cu configurarea Customer Insights. 

- [Adăugați mai mulți utilizatori și atribuiți permisiuni](permissions.md).
- [Ingerați sursele de date](data-sources.md) și rulați-le prin [procesul de unificare a datelor](data-unification.md) pentru a obține [profiluri unificate ale clienților](customer-profiles.md).
- [Îmbogățiți profilurile unificate ale clienților](enrichment-hub.md) sau [rulați modele predictive](predictions-overview.md).
- Creați [segmente](segments.md) pentru a grupa clienții și [măsuri](measures.md) și a revizui indicatorii KPI.
- Configurați [conexiuni](connections.md) și [exporturi](export-destinations.md) pentru a procesa subseturi de date în alte aplicații.