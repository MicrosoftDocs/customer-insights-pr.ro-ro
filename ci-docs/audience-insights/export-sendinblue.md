---
title: Exportați datele Customer Insights către Sendinblue
description: Aflați cum să configurați conexiunea și să exportați către Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314661"
---
# <a name="export-segments-to-sendinblue-preview"></a>Exportați segmente în Sendinblue (previzualizare)

Exportațio segmentele profilelor unificate de client pentru a genera campanii, a furniza marketing de e-mail și utiliza grupuri specifice de clienți cu Sendinblue.

## <a name="prerequisites-for-connection"></a>Cerințe preliminare pentru conexiune

-   Aveți un [Cont Sendinblue](https://www.sendinblue.com/) și acreditările de administrator corespunzătoare.
-   Există liste existente în Sendinblue și ID-urile corespunzătoare.
-   Aveți [segmente configurate](segments.md).
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Până la 1 milion de profiluri pe export către Sendinblue.
- Exportul către Sendinblue este limitat la segmente.
- Exportarea segmentelor cu un total de 1 milion de profiluri poate dura până la 90 de minute. 
- Numărul de profiluri pe care le puteți exporta în Sendinblue depinde și este limitat de contractul dvs. cu Sendinblue.

## <a name="set-up-connection-to-sendinblue"></a>Configurați conexiunea la Sendinblue

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Sendinblue** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, este vorba doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți **[Cheia API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Selectați **Sunt de acord** să confirm **Confidențialitatea și respectarea datelor** și selectați **Conectați** pentru a inițializa conexiunea la Sendinblue.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Sendinblue. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

1. Introduceți **ID-ul listei Sendinblue** 

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client. 

1. Opțional, puteți exporta **Prenume**, **Nume de familie**, și **Telefon**  pentru a crea e-mailuri mai particularizate. Selectați **Adăugare atribut** pentru a mapa aceste câmpuri.

1. Selectați segmentele pe care doriți să le exportați. 

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Sendinblue, permiteți transfer de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi date cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru a vă asigura că Sendinblue îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
