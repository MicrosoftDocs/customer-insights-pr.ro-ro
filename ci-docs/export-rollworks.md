---
title: Exportați datele Customer Insights către RollWorks
description: Aflați cum să configurați conexiunea și să exportați la RollWorks.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ba63f9146b17ebf6daf5b0a9f39c0d6bc32a1bfa
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643706"
---
# <a name="export-segments-to-rollworks-preview"></a>Exportați segmente în RollWorks (previzualizare)

Exportați segmente de profiluri de clienți unificate în RollWorks și folosiți-le pentru publicitate. 

## <a name="prerequisites-for-a-connection"></a>Cerințe preliminare pentru o conexiune

-   Aveți un [Cont RollWorks](https://www.rollworks.com/) și acreditările de administrator corespunzătoare.
-   Tu ai [segmente configurate](segments.md) în Customer Insights.
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Puteți exporta până la 250.000 de profiluri de clienți per export către RollWorks.
- Nu puteți exporta segmente cu mai puțin de 100 de profiluri de clienți în RollWorks. 
- Exportul către RollWorks este limitat la segmente.
- Exportul până la 250.000 de profiluri de clienți în RollWorks poate dura până la 10 minute. 
- Numărul de profiluri de clienți pe care le puteți exporta în RollWorks depinde și este limitat de contractul dvs. cu RollWorks.

## <a name="set-up-connection-to-rollworks"></a>Configurarea conexiunii la RollWorks

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **RollWorks** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Conectați** pentru a inițializa conexiunea la RollWorks.

1. Selectați **Autentificare cu RollWorks** și furnizați acreditările de administrator pentru RollWorks.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea RollWorks. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

1. Introduceți **ID-ul agentului de publicitate RollWorks** [Publicitate RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client. Este necesar să exportați segmente către RollWorks.

1. Selectați segmentele pe care doriți să le exportați. Selectați un segment cu cel puțin 100 de membri. Nu puteți exporta segmente mai mici. În plus, dimensiunea maximă a unui segment de export este de 250.000 de membri pe export. 

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către RollWorks, permiteți transferul de date în afara limitelor de conformitate cu Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi date cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că RollWorks respectă orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.
