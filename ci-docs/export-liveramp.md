---
title: Exportați segmente către LiveRamp (previzualizare)
description: Aflați cum să configurați conexiunea și exportul la LiveRamp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 3e30a16dcb276fa6c951ad0b42ed0a4792f87ce3
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050778"
---
# <a name="export-segments-to-liverampreg-preview"></a>Exportați segmente către LiveRamp&reg; (previzualizare)

Activați-vă datele din LiveRamp pentru a vă conecta cu peste 500 de platforme din ecosisteme digitale, sociale și de televiziune. Lucrați cu datele dvs. în LiveRamp pentru a viza, suprima și personaliza campaniile publicitare.

## <a name="prerequisites-for-a-connection"></a>Cerințe preliminare pentru o conexiune

- Pentru a utiliza acest conector aveți nevoie de un abonament LiveRamp.
- Pentru a obține un abonament, [contactați LiveRamp](https://liveramp.com/contact/) direct. [Aflați mai multe despre Îndrumări LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Configurarea conexiunii la LiveRamp

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **LiveRamp** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Furnizează un **Nume de utilizator** și **Parola** pentru contul dvs. LiveRamp Secure FTP (SFTP).
Aceste acreditări pot fi diferite de datele de acreditare Îndrumări LiveRamp.

1. Selectați **Verificare** pentru a testa conexiunea la LiveRamp.

1. După verificarea cu succes, acordați-vă consimțământul pentru **Confidențialitatea și conformitatea datelor** prin selectarea casetei de selectare **Sunt de acord**.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea LiveRamp. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

1. În câmpul **Alegeți identificatorul de cheie**, selectați **E-mail**,  **Numele și adresa**, sau **Telefon** pentru a trimite la LiveRamp pentru rezolvarea identității.
   > [!div class="mx-imgBorder"]
   > ![Conector LiveRamp cu mapare de atribute.](media/export-liveramp-segments.png "Conector LiveRamp cu mapare de atribute")

1. Mapați atributele corespunzătoare din entitatea *Client* pentru identificatorul cheii selectat.

1. Selectați **Adăugați un atribut** pentru a mapa mai multe atribute de trimis către LiveRamp.

   > [!TIP]
   > Trimiterea mai multor atribute de identificare cheie către LiveRamp este probabil să vă obțină o rată de potrivire mai mare.

1. Selectați segmentele pe care doriți să le exportați în LiveRamp.

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Liveramp, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Liveramp îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.

[!INCLUDE [footer-include](includes/footer-banner.md)]
