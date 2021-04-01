---
title: Exportați datele Customer Insights către AdRoll
description: Aflați cum să configurați conexiunea la AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697089"
---
# <a name="connector-for-adroll-preview"></a>Conector pentru AdRoll (previzualizare)

Exportați segmente de profiluri unificate ale clienților în AdRoll și folosiți-le pentru publicitate. 

## <a name="prerequisites"></a>Cerințe preliminare

-   Aveți un [cont AdRoll](https://www.adroll.com/) și acredităările de administrator corespunzătoare.
-   Aveți [segmente configurate](segments.md) în Detalii despre audiență.
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="connect-to-adroll"></a>Conectare la AdRoll

1. Accesați **Administrator** > **Destinații de export**.

1. Sub **AdRoll**, selectați **Configurare**.

1. Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Panoul de configurare pentru conexiunea AdRoll.":::

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Conectare** pentru a inițializa conexiunea la AdRoll.

1. Selectați **Autentificare cu AdRoll** și furnizați acreditările dvs. de administrator pentru AdRoll. 

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Introduceți **Codul de publicitate AdRoll** [AdRoll publicitar](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Selectați **Continuare** pentru a configura exportul.

## <a name="configure-the-connector"></a>Configurați conectorul

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client. Este necesar să exportați segmente în AdRoll.

1. Selectați segmentele pe care doriți să le exportați. Selectați un segment cu cel puțin 100 de membri. Nu puteți exporta segmente mai mici. În plus, dimensiunea maximă a unui segment de export este de 250.000 de membri pe export. 

1. Selectați **Salvare**.

## <a name="export-the-data"></a>Exportați datele

Puteți [exporta date la cerere](export-destinations.md). Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitări cunoscute

- Puteți exporta până la 250.000 de profiluri per export în AdRoll.
- Nu puteți exporta segmente cu mai puțin de 100 de profiluri în AdRoll. 
- Exportul către AdRoll este limitat la segmente.
- Exportul până la 250.000 de profiluri în AdRoll poate dura până la 10 minute. 
- Numărul de profiluri pe care le puteți exporta către AdRoll este dependent și limitat de contractul dvs. cu AdRoll.

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către AdRoll, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că AdRoll îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.
