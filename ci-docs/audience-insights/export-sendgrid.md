---
title: Exportați datele Customer Insights către SendGrid
description: Aflați cum să configurați conexiunea și să exportați la SendGrid.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 65d60e7e70e3444b0695b905431bab9a0269ceef
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231587"
---
# <a name="export-segments-to-sendgrid-preview"></a>Exportați segmente către SendGrid (previzualizare)

Exportați segmente de profiluri unificate ale clienților în SendGrid și utilizați-le pentru campanii și marketing prin e-mail în SendGrid. 

## <a name="prerequisites-for-a-connection"></a>Cerințe preliminare pentru o conexiune

-   Aveți un [cont SendGrid](https://sendgrid.com/) și acreditările de administrator corespunzătoare.
-   Există liste de persoane de contact în SendGrid și ID-urile corespunzătoare. Pentru mai multe informații, consultați [SendGrid - Gestionați persoanele de contact](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Aveți [segmente configurate](segments.md) în Detalii despre audiență.
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Până la 100.000 de profiluri de clienți în total la SendGrid.
- Exportul către SendGrid este limitat la segmente.
- Exportul până la 100.000 de profiluri de clienți în SendGrid poate dura până la câteva ore. 
- Numărul de profiluri de clienți pe care le puteți exporta în SendGrid depinde și este limitat de contractul dvs. cu SendGrid.

## <a name="set-up-connection-to-sendgrid"></a>Configurarea conexiunii la SendGrid

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **SendGrid** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți **Cheia API SendGrid** [Cheia API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Conectare** pentru a inițializa conexiunea la SendGrid.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea SendGrid. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

1. Introduceți **[ID-ul listă SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client. Repetați aceiași pași pentru alte câmpuri opționale precum **Prenume**, **Nume**, **Țară/Regiune**, **Stare**, **Oraș** și **Cod poștal**.

1. Selectați segmentele pe care doriți să le exportați. Ferm **recomandăm să nu exportați mai mult de 100.000 de profiluri de clienți în total** la SendGrid. 

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către SendGrid, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că SendGrid îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
