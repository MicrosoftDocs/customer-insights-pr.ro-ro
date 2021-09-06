---
title: Exportați datele Customer Insights către Snapchat
description: Aflați cum să configurați conexiunea și să exportați la Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 421dcd5ba5421597cf9dea71a9f9f25c7972a4f26fb49d4b042f8667a317ab5d
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033416"
---
# <a name="export-segments-to-snapchat-preview"></a>Exportați segmente în Snapchat (previzualizare)

Exportați segmente de profiluri de clienți unificate în Snapchat și folosiți-le pentru publicitate. 

## <a name="prerequisites-for-a-connection"></a>Cerințe preliminare pentru o conexiune

-   Aveți un [Cont Snapchat Business](https://business.snapchat.com/), un [Cont Snapchat Ads](https://ads.snapchat.com/) și acreditările de administrator corespunzătoare.
-   Aveți [segmente configurate](segments.md) în Detalii despre audiență.
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Exportul către Snapchat este limitat la segmente.
- Exportul de până la 1 milion de profiluri pe Snapchat poate dura până la 15 minute. 

## <a name="set-up-connection-to-snapchat"></a>Configurarea conexiunii la Snapchat

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Snapchat** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Conectați** pentru a inițializa conexiunea la Snapchat.

1. Selectați **Autentificare cu Snapchat** și furnizați acreditările de administrator pentru Snapchat. 

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Snapchat. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

1. Introduceți [**ID-ul de audiență Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client. Este necesar să exportați segmente către Snapchat.

1. Selectați segmentele pe care doriți să le exportați. 

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Snapchat, permiteți transferul de date în afara limitelor de conformitate cu Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi date cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Snapchat respectă orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.
