---
title: Exportați datele Customer Insights către Autopilot
description: Aflați cum să configurați conexiunea și să exportați la Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c9ada8a6f4e4546990a1360567b400033050119c4c4c9a3df1af8fcaab75e157
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032040"
---
# <a name="export-segments-to-autopilot-preview"></a>Exportați segmente către Autopilot (previzualizare)

Exportați segmente de profiluri unificate ale clienților în Autopilot și utilizați-le pentru marketing prin e-mail în Autopilot. 

## <a name="prerequisites-for-a-connection"></a>Cerințe preliminare pentru o conexiune

-   Aveți un [cont Autopilotl](https://www.autopilothq.com/) și acreditările de administrator corespunzătoare.
-   Aveți [segmente configurate](segments.md) în Detalii despre audiență.
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Puteți exporta până la 100.000 de profiluri de client în total către Autopilot.
- Exportul către Autopilot este limitat la segmente.
- Exportul până la 100'000 de profiluri către Autopilot poate dura până la câteva ore. 
- Numărul de profiluri pe care le puteți exporta către Autopilot este dependent și limitat de contractul dvs. cu Autopilot.

## <a name="set-up-connection-to-autopilot"></a>Configurarea conexiunii la Autopilot

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Autopilot** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

3. Introduceți [Cheie API Autopilot](https://autopilot.docs.apiary.io/#).

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Conectare** pentru a inițializa conexiunea la Autopilot.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Autopilot. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

3. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client. Repetați aceiași pași pentru alte câmpuri opționale, cum ar fi **Prenume**, **Nume**.

1. Selectați segmentele pe care doriți să le exportați. Ferm **recomandăm să nu exportați mai mult de 100.000 de profiluri de clienți în total** la Autopilot. 

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Autopilot, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Autopilot îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
