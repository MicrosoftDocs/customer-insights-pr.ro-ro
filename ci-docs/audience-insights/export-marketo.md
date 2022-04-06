---
title: Exportați datele Customer Insights către Marketo
description: Aflați cum să configurați conexiunea și să exportați la Marketo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d56ed779c342bb0855ee84d949f8d3ca604b92c1
ms.sourcegitcommit: a5e4503cf9ce0cea562bab9389748d8ca1451f9d
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/25/2022
ms.locfileid: "8487530"
---
# <a name="export-segments-to-marketo-preview"></a>Exportați segmente către Marketo (previzualizare)

Exportați segmentele profilurilor client unificate pentru a genera campanii, a oferi marketing prin e-mail și a folosi anumite grupuri de clienți cu Marketo.

## <a name="prerequisites-for-connection"></a>Cerințe preliminare pentru conexiune

-   Aveți un [cont Marketo](https://login.marketo.com/) și acreditările de administrator corespunzătoare.
-   Există liste în Marketo și ID-urile corespunzătoare. Pentru informații suplimentare, consultați [Liste Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Aveți [segmente configurate](segments.md).
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Până la 1 milion de profiluri de clienți per export către Marketo.
- Exportul către Marketo este limitat la segmente.
- Exportarea de segmente cu un total de 1 milion de profiluri de clienți poate dura până la 3 ore. 
- Numărul de profiluri de clienți pe care le puteți exporta în Marketo depinde și este limitat de contractul dvs. cu Marketo.

## <a name="set-up-connection-to-marketo"></a>Configurarea conexiunii la Marketo

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Marketo** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți **[ID-ul de client Marketo, secretul clientului și Numele de gazdă punct final REST](https://developers.marketo.com/rest-api/authentication/)**. Numele de gazdă REST Endpoint este doar numele gazdei, fără `https://`. Exemplu:`xyz-abc-123.mktorest.com`. 

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor** și selectați **Conectare** pentru a inițializa conexiunea la Marketo.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Marketo. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

1. Introduceți **[ID-ul listă Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**. ID-ul listei este o valoare pur numerică. De exemplu, dacă ID-ul listei Marketo este ST12345A7, eliminați caracterul înainte și după cifre și introduceți `12345`. 

1. În **Potrivirea datelor** secțiunea, selectați cel puțin un câmp care reprezintă adresa de e-mail a unui client sau ID-ul Marketo al unui client. 

1. Opțional, puteți exporta **Prenume**, **Nume de familie**, **Oraș**, **Stat** și **Țară/Regiune** pentru a crea e-mailuri mai personalizate. Selectați **Adăugare atribut** pentru a mapa aceste câmpuri.

1. Selectați segmentele pe care doriți să le exportați. Puteți exporta până la 1 milion de profiluri de client în total către Marketo.

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). În Marketo, puteți găsi acum segmentele dvs. sub [Listele Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Marketo, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Marketo îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
