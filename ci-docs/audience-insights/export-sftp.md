---
title: Exportați date despre Customer Insights către gazde SFTP (conține videoclip)
description: Aflați cum să configurați conexiunea și să exportați către o locație SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 542bd908010cf0a8ccc12f15d54e0a3d5b72f189
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934902"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>Exportați segmente și alte date către SFTP (previzualizare)

Utilizați datele clienților dvs. în aplicații terțe, exportându-le într-o locație Protocol de transfer securizat al fișierelor (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>Cerințe preliminare pentru conexiune

- Disponibilitatea unei gazde SFTP și acreditările corespunzătoare.

## <a name="known-limitations"></a>Limitări cunoscute

- Destinațiile SFTP din spatele firewall-urilor nu sunt acceptate momentan. 
- Runtime-ul unui export depinde de performanța sistemului dvs. Vă recomandăm două nuclee CPU și 1 Gb de memorie ca configurație minimă a serverului dvs. 
- Entitățile exportatoare cu până la 100 de milioane de profiluri de clienți pot dura 90 de minute când se utilizează configurația minimă recomandată a două nuclee CPU și 1 Gb de memorie. 

## <a name="set-up-connection-to-sftp"></a>Configurarea conexiuni la SFTP

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **SFTP** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Furnizați un **Nume de utilizator**, **Parolă**, **Nume de gazdă** și **Folder de export** pentru contul dvs. de SFTP.

1. Selectați **Verificare** pentru a testa conexiunea.

1. Alegeți dacă doriți să vă exportați datele dvs. în mod **Comprimat cu gzip** sau **Dezarhivat** și **delimitatorul de câmp** pentru fișierele exportate.

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea SFTP. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

1. Selectați entitățile, de exemplu segmente pe care doriți să le exportați.

   > [!NOTE]
   > Fiecare entitate selectată va fi împărțită în maximum cinci fișiere de ieșire la export. 

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date prin SFTP, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că destinația de export îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
