---
title: Exportați datele Customer Insights către Mailchimp
description: Aflați cum să configurați conexiunea și să exportați la Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a6bdf43bb40345b868bf2e7d2c91de169c8ba841ba77f732f455f4c4d496a7f5
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033554"
---
# <a name="export-segments-to-mailchimp-preview"></a>Exportați segmente în Mailchimp (previzualizare)

Exportați segmente de profiluri unificate ale clienților către Mailchimp pentru a crea buletine informative și campanii de e-mail.

## <a name="prerequisites-for-connection"></a>Cerințe preliminare pentru conexiune

-   Aveți un [cont Mailchimp](https://mailchimp.com/) și acreditările de administrator corespunzătoare.
-   Există audiențe în Mailchimp și ID-urile corespunzătoare. Pentru informații suplimentare, consultați [Audiențe Mailchimp](https://mailchimp.com/help/create-audience/).
-   Aveți [segmente configurate](segments.md)
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Până la 1 milion de profiluri per export către Mailchimp.
- Exportul către Mailchimp este limitat la segmente.
- Exportarea segmentelor cu 1 milion de profiluri poate dura până la trei ore. 
- Numărul de profiluri pe care le puteți exporta către Mailchimp este dependent și limitat de contractul dvs. cu Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>Configurarea conexiunii la Mailchimp

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Mailchimp** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Conectați** pentru a inițializa conexiunea la Mailchimp.

1. Selectați **Autentificare cu Mailchimp** și furnizați acreditările dvs. Mailchimp.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea. 

## <a name="configure-the-connector"></a>Configurați conectorul

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date**> **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Mailchimp. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

1. Introduceți **[ID public Mailchimp](https://mailchimp.com/help/find-audience-id/)**

3. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client. 

1. Opțional, puteți exporta **Prenume** și **Nume de familie** pentru a crea e-mailuri mai personalizate. Selectați **Adăugare atribut** pentru a mapa aceste câmpuri.

1. Selectați segmentele pe care doriți să le exportați. Puteți exporta până la 1 milion de profiluri de client în total către Mailchimp.

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Mailchimp, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Mailchimp îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
