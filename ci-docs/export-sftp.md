---
title: Exportați date pe gazde SFTP (previzualizare) (conține videoclip)
description: Aflați cum să configurați conexiunea și să exportați către o locație SFTP.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207244"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Exportați date pe gazde SFTP (previzualizare)

Utilizați datele clienților dvs. în aplicații terțe, exportându-le într-o locație Protocol de transfer securizat al fișierelor (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Cerințe preliminare

- Disponibilitatea unei gazde SFTP și acreditările corespunzătoare.

## <a name="known-limitations"></a>Limitări cunoscute

- Destinațiile SFTP din spatele firewall-urilor nu sunt acceptate în prezent.
- Runtime-ul unui export depinde de performanța sistemului dvs. Vă recomandăm două nuclee CPU și 1 Gb de memorie ca configurație minimă a serverului dvs.
- Până la 100 de milioane de profiluri de clienți, ceea ce poate dura 90 de minute când se utilizează configurația minimă recomandată de două nuclee CPU și 1 Gb de memorie.
- Dacă utilizați o cheie SSH pentru autentificare, asigurați-vă că dvs [creați-vă cheia privată](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) ca format PEM sau SSH.COM. Dacă utilizați Putty, convertiți-vă cheia privată prin exportare ca Open SSH. Sunt acceptate următoarele formate de chei private:
  - RSA în format OpenSSL PEM și ssh.com
  - DSA în format OpenSSL PEM și ssh.com
  - ECDSA 256/384/521 în format OpenSSL PEM
  - ED25519 și RSA în format cheie OpenSSH

## <a name="set-up-connection-to-sftp"></a>Configurarea conexiuni la SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **SFTP**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Alegeți dacă doriți să vă autentificați prin SSH sau numele de utilizator/parola pentru conexiunea dvs. și furnizați detaliile necesare. Dacă utilizați o cheie SSH pentru autentificare, asigurați-vă că dvs [creați-vă cheia privată](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) ca format PEM sau SSH.COM. Dacă utilizați Putty, convertiți-vă cheia privată prin exportare ca Open SSH. Sunt acceptate următoarele formate de chei private:
   - RSA în format OpenSSL PEM și ssh.com
   - DSA în format OpenSSL PEM și ssh.com
   - ECDSA 256/384/521 în format OpenSSL PEM
   - ED25519 și RSA în format cheie OpenSSH

1. Selectați **Verificare** pentru a testa conexiunea.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea SFTP. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. Alegeți dacă doriți să vă exportați datele dvs. în mod **Comprimat cu gzip** sau **Dezarhivat** și **delimitatorul de câmp** pentru fișierele exportate.

1. Selectați entitățile, de exemplu segmente, pe care doriți să le exportați.

   > [!NOTE]
   > Fiecare entitate selectată va fi împărțită în maximum cinci fișiere de ieșire atunci când este exportată.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> Exportul de entități care conțin o cantitate mare de date poate duce la mai multe fișiere CSV în același folder pentru fiecare export. Împărțirea exporturilor are loc din motive de performanță, pentru a minimiza timpul necesar pentru finalizarea unui export.

[!INCLUDE [footer-include](includes/footer-banner.md)]
