---
title: Exportați datele Customer Insights către DotDigital
description: Aflați cum să configurați conexiunea și să exportați la DotDigital.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f9302e17c07238d837dcafb82baecb5aedda17de
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231633"
---
# <a name="export-segments-to-dotdigital-preview"></a>Exportați segmente în DotDigital (previzualizare)

Exportați segmente de profiluri de clienți unificate în agende DotDigital și folosiți-le pentru campanii, marketing prin e-mail și pentru a crea segmente de clienți cu DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Cerințe preliminare pentru o conexiune

-   Aveți un [Cont DotDigital](https://dotdigital.com/) și ați creat un [Utilizator API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user). Va trebui să utilizați acreditările de utilizator API pentru a crea o conexiune
-   Există agende în DotDigital și ID-urile corespunzătoare. ID-ul poate fi găsit în adresa URL atunci când selectați și deschideți o agendă. Pentru mai multe informații, consultați [Agende DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Aveți [segmente configurate](segments.md) în Detalii despre audiență.
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Până la 1 milion de profiluri de clienți per export către DotDigital.
- Exportul către DotDigital este limitat la segmente.
- Exportul de segmente cu un total de 1 milion de profiluri de clienți poate dura până la 3 ore din cauza limitărilor din partea furnizorului. 
- Numărul de profiluri de clienți pe care le puteți exporta în DotDigital depinde și este limitat de contractul dvs. cu DotDigital.

## <a name="set-up-connection-to-dotdigital"></a>Configurarea conexiunii la DotDigital

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **DotDigital** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți **numele de utilizator API și parola DotDigital**. 

1. Introduceți **[ID-ul agendei DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Conectare** pentru a inițializa conexiunea la DotDigital.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea. 

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea DotDigital. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.


1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client. Repetați aceiași pași pentru alte câmpuri opționale, cum ar fi **Prenume**, **Nume de familie**, **Nume complet**, **Gen**, și **Cod poștal**.

1. Selectați segmentele pe care doriți să le exportați. Puteți exporta până la 1 milion de profiluri de client în total către DotDigital.

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 
 
În DotDigital, puteți găsi acum segmentele dvs. în [Agendele DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către DotDigital, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că DotDigital îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
