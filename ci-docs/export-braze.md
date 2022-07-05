---
title: Exportați segmente în Braze (previzualizare)
description: Aflați cum să configurați conexiunea și să exportați în Braze.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082686"
---
# <a name="export-segments-to-braze-preview"></a>Exportați segmente în Braze (previzualizare)

Exportați segmente de profiluri de clienți unificate în Braze și utilizați-le pentru activități de marketing.

## <a name="prerequisites"></a>Cerințe preliminare

- A [cont Braze](https://www.braze.com/) și acreditările de administrator corespunzătoare.
- Existent [segmente în Braze](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/).
- [Segmente configurate](segments.md) în Customer Insights.
- Profilurile unificate ale clienților din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail și un ID de client Braze.

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

1. În **Conexiune pentru export** câmp, alegeți o conexiune din secțiunea Braze. Dacă nu vedeți această secțiune, nu sunt disponibile conexiuni de acest tip.  

1. Adauga o **Numele de afișare** pentru exportul dvs.

1. Adăugați identificatorul API al segmentului Braze în care doriți să exportați în **Identificatorul API al segmentului Braze** camp. Identificatorul îl găsiți în detaliile segmentului de pe platforma Braze.

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client. În **Număr de înregistrare client** câmp, selectați câmpul care reprezintă ID-ul Braze al clientului. Este necesar să exportați segmente în Braze. Puteți alege mai multe câmpuri opțional.

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Braze, permiteți transferul de date în afara limitei de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele personale. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru a vă asigura că Braze îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.
