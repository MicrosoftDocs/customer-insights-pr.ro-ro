---
title: Exportați datele Customer Insights către Monitor de campanie
description: Aflați cum să configurați conexiunea și exportul la Monitor de campanie.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: be9c92a087ab4664077d18fe8585bf96715c1535
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228168"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Exportați segmente în Monitor de campanie (previzualizare)

Exportați segmente de profiluri de clienți unificate în Monitor de campanie și folosiți-le pentru activități de marketing.

## <a name="prerequisites"></a>Cerințe preliminare

-   Aveți un [Cont Monitor de campanie](https://www.campaignmonitor.com/) și acreditările de administrator corespunzătoare.
-   Aveți [segmente configurate](segments.md) în Detalii despre audiență.
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Puteți exporta până la 1 milion de profiluri de clienți per export către Campaign Monitor.
- Exportul către Monitor de campanie este limitat la segmente.
- Exportul până la 1 milion de profiluri de clienți în Campaign Monitor poate dura până la 20 minute. 
- Numărul de profiluri de clienți pe care le puteți exporta în Campaign Monitor depinde și este limitat de contractul dvs. cu Campaign Monitor.

## <a name="set-up-connection-to-campaign-monitor"></a>Configurați conexiunea la Monitor de campanie

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Monitor de campanie** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Conectați** pentru a inițializa conexiunea la Monitor de campanie.

1. Selectați **Autentificare cu Monitor de campanie** și furnizați acreditările de administrator pentru Monitor de campanie.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Monitor de campanie. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

1. Introduceți [**ID-ul listei de Monitor de campanie**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   Mai întâi, [Generați cheia API](https://www.campaignmonitor.com/api/getting-started/) din **Setările contului** în Monitor de campanie pentru a vedea ID-ul listei API.  

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client. Este necesar să exportați segmente către Monitor de campanie.

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Monitor de campanie, permiteți transferul de date în afara limitelor de conformitate cu Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi date cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Monitor de campanie respectă orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.
