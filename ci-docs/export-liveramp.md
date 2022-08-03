---
title: Exportați segmente către LiveRamp (previzualizare)
description: Aflați cum să configurați conexiunea și exportul la LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196731"
---
# <a name="export-segments-to-liverampreg-preview"></a>Exportați segmente către LiveRamp&reg; (previzualizare)

Activați-vă datele din LiveRamp pentru a vă conecta cu peste 500 de platforme din ecosisteme digitale, sociale și de televiziune. Lucrați cu datele dvs. în LiveRamp pentru a viza, suprima și personaliza campaniile publicitare.

## <a name="prerequisites"></a>Cerințe preliminare

- Un abonament LiveRamp pentru a utiliza acest conector. Pentru a obține un abonament, [contactați LiveRamp](https://liveramp.com/contact/) direct. [Aflați mai multe despre Îndrumări LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Limitări cunoscute

- Exportul LiveRamp utilizează un export SFTP. Destinațiile SFTP din spatele firewall-urilor nu sunt acceptate în prezent.
- Dacă utilizați o cheie SSH pentru autentificare, asigurați-vă că dvs [creați-vă cheia privată](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) ca format PEM sau SSH.COM. Dacă utilizați Putty, convertiți-vă cheia privată prin exportare ca Open SSH. Sunt acceptate următoarele formate de chei private:
  - RSA în format OpenSSL PEM și ssh.com
  - DSA în format OpenSSL PEM și ssh.com
  - ECDSA 256/384/521 în format OpenSSL PEM
  - ED25519 și RSA în format cheie OpenSSH
- Runtime-ul unui export depinde de performanța sistemului dvs. Vă recomandăm două nuclee CPU și 1 Gb de memorie ca configurație minimă a serverului dvs.
- Entitățile exportatoare cu până la 100 de milioane de profiluri de clienți pot dura 90 de minute când se utilizează configurația minimă recomandată a două nuclee CPU și 1 Gb de memorie.
- Numărul real de profiluri (sau date) pe care le puteți exporta în LiveRamp depinde de abonamentul dvs. la LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>Configurarea conexiunii la LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **LiveRamp**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Alegeți dacă doriți să vă autentificați prin SSH sau numele de utilizator/parola pentru conexiunea dvs. și furnizați detaliile necesare.

1. Selectați **Verificare** pentru a testa conexiunea la LiveRamp.

1. După verificarea cu succes, examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea LiveRamp. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. În **Conectați datele** câmp, selectați **E-mail**, **și adresa**, sau **Telefon** pentru a trimite la LiveRamp pentru rezolvarea identității.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="Conector LiveRamp cu mapare de atribute.":::

1. Mapați atributele corespunzătoare din entitatea *Client* pentru identificatorul cheii selectat.

1. Selectați **Adăugați un atribut** pentru a mapa mai multe atribute de trimis către LiveRamp.

   > [!TIP]
   > Trimiterea mai multor atribute de identificare cheie către LiveRamp este probabil să vă obțină o rată de potrivire mai mare.

1. Selectați segmentele pe care doriți să le exportați.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
