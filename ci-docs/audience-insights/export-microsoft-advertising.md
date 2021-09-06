---
title: Exportați datele Customer Insights în Microsoft Advertising
description: Aflați cum să configurați conexiunea și exportul la Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f8a4cbb9590f9c5311789154319283530e0a10343cccbe9c7aec99765b4fbf2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031487"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Exportați segmente în Microsoft Advertising (previzualizare)

Exportați segmentele Customer Insights în Microsoft Advertising pentru a crea segmente de public Matched Audiences. Utilizați aceste segmente de public pentru campaniile dvs. publicitare.

## <a name="prerequisites"></a>Cerințe preliminare

-   Un [Cont Microsoft Advertising](https://ads.microsoft.com/) și acreditările de administrator corespunzătoare.
-   Ați acceptat condițiile de utilizare pentru Customer Match. 
-   [Segmente configurate](segments.md) în detalii despre public.
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp cu o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Puteți exporta până la 500 milioane de profiluri per export către Microsoft Advertising.
- Exportul către Microsoft Advertising constantă este limitat la segmente.
- Exportul de până la 500 milioane de profiluri pe Microsoft Advertising poate dura până la 10 minute. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Configurați conexiunea la Microsoft Advertising

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Microsoft Advertising** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit sunt administratorii. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Conectați** pentru a inițializa conexiunea la Microsoft Advertising.

1. Selectați **Autentificare cu Microsoft Advertising** și furnizați acreditările de administrator pentru Microsoft Advertising.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Microsoft Advertising. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

1. Selectați segmentele pentru export. Audiențele de potrivire după clienți din Microsoft Advertising sunt create automat cu numele segmentelor selectate pentru export. Fiecare segment va avea ca rezultat un public separat Matched audience. 

1. Introduceți **ID client Microsoft Advertising și ID cont**. Puteți găsi ID-ul de client (`cid`) și ID-ul contului (`aid`) în parametrii adresei URL când sunteți conectat la Microsoft Advertising.

1. În secțiunea **Potrivirea datelor**, în **E-mail**, selectați câmpul din profilul dvs. de client unificat cu adresa de e-mail a unui client. Este necesar să exportați segmente către Match Advertising.

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Microsoft Advertising, permiteți transferul de date în afara limitelor de conformitate cu Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi date cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Microsoft Advertising respectă orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.
