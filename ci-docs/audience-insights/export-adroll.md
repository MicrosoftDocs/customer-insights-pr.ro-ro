---
title: Exportați datele Customer Insights către AdRoll
description: Aflați cum să configurați conexiunea și să exportați la AdRoll.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a318750077c71a17e5a47c40722f6153e6640f3
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227635"
---
# <a name="export-segments-to-adroll-preview"></a>Exportați segmente în AdRoll (previzualizare)

Exportați segmente de profiluri unificate ale clienților în AdRoll și folosiți-le pentru publicitate. 

## <a name="prerequisites-for-a-connection"></a>Cerințe preliminare pentru o conexiune

-   Aveți un [cont AdRoll](https://www.adroll.com/) și acredităările de administrator corespunzătoare.
-   Aveți [segmente configurate](segments.md) în Detalii despre audiență.
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Puteți exporta până la 250.000 de profiluri de clienți simultan în AdRoll.
- Nu puteți exporta segmente cu mai puțin de 100 de profiluri de clienți în AdRoll. 
- Exportul către AdRoll este limitat la segmente.
- Exportul până la 250.000 de profiluri de clienți în AdRoll poate dura până la 10 minute. 
- Numărul de profiluri de clienți pe care le puteți exporta în AdRoll depinde de contractul dvs. cu AdRoll.

## <a name="set-up-connection-to-adroll"></a>Configurarea conexiunii la AdRoll

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **AdRoll** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Conectare** pentru a inițializa conexiunea la AdRoll.

1. Selectați **Autentificare cu AdRoll** și furnizați acreditările dvs. de administrator pentru AdRoll. 

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea AdRoll. Dacă nu vedeți numele acestei secțiuni, atunci nu aveți la dispoziție conexiuni de acest tip.

1. Introduceți **ID-ul de agent de publicitate AdRoll**. Pentru mai multe informații, consultați [Profiluri de agent de publicitate AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client. Este necesar să exportați segmente în AdRoll.

1. Selectați segmentele pe care doriți să le exportați. Selectați un segment cu cel puțin 100 de membri. Nu puteți exporta segmente mai mici. În plus, dimensiunea maximă a unui segment de export este de 250.000 de membri per export. 

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). 

Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către AdRoll, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că AdRoll îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.
