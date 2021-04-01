---
title: Exportați datele Customer Insights către gazde SFTP
description: Aflați cum să configurați conexiunea la o gazdă SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598400"
---
# <a name="connector-for-sftp-preview"></a>Conector pentru SFTP (previzualizare)

Utilizați datele despre clienți în aplicații terțe, exportându-le către o gazdă Secure File Transfer Protocol(SFTP).

## <a name="prerequisites"></a>Cerințe preliminare

- Disponibilitatea unei gazde SFTP și acreditările corespunzătoare.

## <a name="connect-to-sftp"></a>Conectare la SFTP

1. Accesați **Administrator** > **Destinații de export**.

1. Sub **SFTP**, selectați **Configurare**.

1. Dați destinației dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.

1. Furnizați un **Nume de utilizator**, **Parolă**, **Nume de gazdă** și **Folder de export** pentru contul dvs. de SFTP.

1. Selectați **Verificare** pentru a testa conexiunea.

1. După verificarea cu succes, alegeți dacă doriți să exportați datele **Comprimat cu gzip** sau **Decomprimat** și selectați **delimitator de câmp** pentru fișierele exportate.

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Următorul** pentru a începe configurarea exportului.

## <a name="configure-the-export"></a>Configurarea exportului

1. Selectați entitățile, de exemplu segmente pe care doriți să le exportați.

   > [!NOTE]
   > Fiecare entitate selectată va avea până la cinci fișiere de ieșire atunci când va fi exportată. 

1. Selectați **Salvare**.

## <a name="export-the-data"></a>Exportați datele

Puteți [exporta date la cerere](export-destinations.md). Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitări cunoscute

- Runtime-ul unui export depinde de performanța sistemului dvs. Vă recomandăm două nuclee CPU și 1 Gb de memorie ca configurație minimă a serverului dvs. 
- Entitățile exportatoare cu până la 100 de milioane de profiluri de clienți pot dura 90 de minute când se utilizează configurația minimă recomandată a două nuclee CPU și 1 Gb de memorie. 

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date prin SFTP, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că destinația de export îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.


[!INCLUDE[footer-include](../includes/footer-banner.md)]