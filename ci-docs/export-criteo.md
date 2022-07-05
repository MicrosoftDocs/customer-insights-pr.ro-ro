---
title: Exportați segmente în Criteo (previzualizare)
description: Aflați cum să configurați conexiunea și să exportați în Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ace9056d200a3179e442132004324a01f0d247b6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082791"
---
# <a name="export-segments-to-criteo-preview"></a>Exportați segmente în Criteo (previzualizare)

Exportați segmente de profiluri de clienți unificate pentru a genera campanii, a oferi marketing prin e-mail și a utiliza anumite grupuri de clienți cu Criteo.

## <a name="prerequisites-for-connection"></a>Cerințe preliminare pentru conexiune

-   Tu ai [Cont Criteo Dynamics Retargeting](https://www.criteo.com/login/) și acreditările de administrator corespunzătoare.
-   Aveți [segmente configurate](segments.md).
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Până la 1 milion de profiluri de clienți per export către Criteo.
- Exportul în Criteo este limitat la segmente.
- Exportarea de segmente cu un total de 1 milion de profiluri de clienți poate dura până la 30 minute. 
- Numărul de profiluri de clienți pe care le puteți exporta în Criteo depinde și este limitat de contractul dvs. cu Criteo.

## <a name="set-up-connection-to-criteo"></a>Configurați conexiunea la Criteo

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Criteo** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea datelor și conformitatea** și selectați **Conectați** pentru a inițializa conexiunea la Criteo.

1. Selectați **Autentificați-vă cu Criteo** și furnizați numele de utilizator și acreditările dvs. de administrator pentru Criteo. 

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În **Conexiune pentru export** câmp, alegeți o conexiune din secțiunea Criteo. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip. 

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client. 

1. Opțional, puteți exporta **ID agent de publicitate** și **Nume**

1. Selectați segmentele pe care doriți să le exportați. 

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Criteo, permiteți transferul de date în afara limitei de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele personale. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru a vă asigura că Criteo îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.


[!INCLUDE[footer-include](includes/footer-banner.md)]
