---
title: Exportați datele Customer Insights în Iterable
description: Aflați cum să configurați conexiunea și să exportați în Iterable.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4de499fcc4a5a0dcc2dfd3bae02913c81a59647b
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/31/2022
ms.locfileid: "8524594"
---
# <a name="export-segment-lists-to-iterable-preview"></a>Exportați liste de segmente în Iterable (previzualizare)

Exportați segmente de profiluri de clienți unificate în Iterable și utilizați-le pentru activități de marketing.

## <a name="prerequisites"></a>Cerințe preliminare

-   Ai un [cont iterabil](https://iterable.com/) și acreditările de administrator corespunzătoare.
-   Aveți [segmente configurate](segments.md) în Detalii despre audiență.
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Exportarea în Iterable este limitată la segmente.
- Exportarea a până la 1 milion de profiluri de clienți în Iterable poate dura până la 30 de minute. 
- Numărul de profiluri de clienți pe care le puteți exporta în Iterable depinde și este limitat de contractul dvs. cu Iterable.

## <a name="set-up-connection-to-iterable"></a>Configurați conexiunea la Iterable

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Iterabil** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Furnizați-vă [Cheie API iterabilă](https://support.iterable.com/hc/en-us/articles/360043464871) pentru a continua conectarea. 

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Conectați** pentru a inițializa conexiunea la Iterable.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În **Conexiune pentru export** câmp, alegeți o conexiune din secțiunea Iterable. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

3. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client. Este necesar să exportați segmente în Iterable. Lista creată în Iterable va primi exact același nume ca și numele segmentului dvs. în Dynamics 365 Customer Insights.

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Iterable, permiteți transferul de date în afara limitei de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele personale. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru a vă asigura că Iterable îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.
