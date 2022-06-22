---
title: Exportați datele despre Customer Insights în Braze
description: Aflați cum să configurați conexiunea și să exportați în Braze.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bfc9b34506dc3385b5edf12b31e74d05f2d20655
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643154"
---
# <a name="export-segment-lists-to-braze-preview"></a>Exportați liste de segmente în Braze (previzualizare)

Exportați segmente de profiluri de clienți unificate în Braze și utilizați-le pentru activități de marketing.

## <a name="prerequisites"></a>Cerințe preliminare

-   Tu ai [cont Braze](https://www.braze.com/) și acreditările de administrator corespunzătoare.
-   Tu ai [segmente configurate](segments.md) în Customer Insights.
-   Profilurile unificate ale clienților din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail și un ID de client Braze. 

## <a name="known-limitations"></a>Limitări cunoscute

- Exportul în Braze este limitat la segmente.
- Exportarea a până la 1 milion de profiluri de clienți în Braze poate dura până la 40 de minute. 
- Numărul de profiluri de clienți pe care le puteți exporta în Braze depinde și este limitat de contractul dvs. cu Braze.

## <a name="set-up-connection-to-braze"></a>Configurați conexiunea la Braze

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Braze** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Furnizați-vă [Cheia API Braze](https://www.braze.com/docs/api/basics/) pentru a continua conectarea. 

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Conectați** pentru a inițializa conexiunea la Braze.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În **Conexiune pentru export** câmp, alegeți o conexiune din secțiunea Braze. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.  

3. În **Potrivirea datelor** secțiunea, în **E-mail** câmp, selectați câmpul care reprezintă adresa de e-mail a unui client, în câmpul „ID client”, selectați câmpul care reprezintă ID-ul Braze al clientului. Este necesar să exportați segmente în Braze. Segmentele din Braze vor fi create cu același nume al segmentului ca în Dynamics 365 Customer Insights. Puteți alege câmpuri suplimentare, opționale, pentru datele de potrivire. 

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Braze, permiteți transferul de date în afara limitei de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele personale. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru a vă asigura că Braze îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.