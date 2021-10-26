---
title: Exportați datele Customer Insights către Omnisend
description: Aflați cum să configurați conexiunea și să exportați la Omnisend.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5496efa075fa3474c579366d143ea55e86ec3995
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/08/2021
ms.locfileid: "7619043"
---
# <a name="export-segments-to-omnisend-preview"></a>Exportați segmente către Omnisend (previzualizare)

Exportați segmente de profiluri de clienți unificate în Omnisend și folosiți-le pentru activități de marketing.

## <a name="prerequisites"></a>Cerințe preliminare

-   Aveți un [Cont Omnisend](https://www.omnisend.com/) și acreditările de administrator corespunzătoare.
-   Aveți [segmente configurate](segments.md) în Detalii despre audiență.
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Puteți exporta până la 1 milion de profiluri de clienți per export către Omnisend și poate dura până la 4 ore până la finalizare.
- Exportul către Omnisend este limitat la segmente.
- Numărul de profiluri de clienți pe care le puteți exporta în Omnisend depinde de contractul dvs. cu Omnisend.

## <a name="set-up-connection-to-omnisend"></a>Configurarea conexiunii la Omnisend

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Omnisend** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, este vorba doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți [Cheie API Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Conectați** pentru a inițializa conexiunea la Omnisend.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Omnisend. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client. Este necesar să exportați segmente către Omnisend. Opțional, puteți exporta Prenume, Nume de familie, Adresă, Țară/Regiune, Stat, Oraș și Cod poștal pentru a crea e-mailuri mai personalizate. Selectați **Adăugare atribut** pentru a mapa aceste câmpuri.

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Ommisend, permiteți transferul de date în afara limitelor de conformitate cu Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi date cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Ommisend respectă orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.
