---
title: Exportați datele Customer Insights către Constant Contact
description: Aflați cum să configurați conexiunea și exportul la Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b54659f028a141fe8f351645d96e933d47568a39
ms.sourcegitcommit: adb9c43ddaba25e511535d78a4bcf8815f154a7b
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/06/2021
ms.locfileid: "6362433"
---
# <a name="export-segments-to-constant-contact-preview"></a>Exportați segmente în Constant Contact (previzualizare)

Exportați segmente de profiluri de clienți unificate în Constant Contact și folosiți-le pentru activități de marketing. 

## <a name="prerequisites-for-a-connection"></a>Cerințe preliminare pentru o conexiune

-   Aveți un [Cont Constant Contact](https://www.constantcontact.com/account-home) și acreditările de administrator corespunzătoare.
-   Aveți [segmente configurate](segments.md) în Detalii despre audiență.
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Puteți exporta până la 1 milion de profiluri per export către Constant Contact.
- Exportul către Constant Contact este limitat la segmente.
- Exportul de până la 1 milion de profiluri pe Constant Contact poate dura până la 1 oră. 
- Numărul de profiluri pe care le puteți exporta în Constant Contact depinde și este limitat de contractul dvs. cu Constant Contact.

## <a name="set-up-connection-to-constant-contact"></a>Configurați conexiunea la Constant Contact

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Constant Contact** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Conectați** pentru a inițializa conexiunea la Constant Contact.

1. Selectați **Autentificați-vă cu contact constant** și furnizați acreditările de administrator pentru contactul constant. 

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Constant Contact. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

1. Introduceți [**ID-ul listei de Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists). Deschideți o listă în Constant Contact pentru a găsi ID-ul listei în URL.

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client. Este necesar să exportați segmente către Constant Contact.

1. Opțional, puteți exporta Prenume și Nume de familie ca câmpuri suplimentare pentru a crea e-mailuri mai personalizate. Selectați **Adăugare atribut** pentru a mapa aceste câmpuri.

1. Selectați segmentele pe care doriți să le exportați.

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Constant Contact, permiteți transferul de date în afara limitelor de conformitate cu Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi date cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Constant Contact respectă orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.
