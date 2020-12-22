---
title: Exportați datele Customer Insights către gazde SFTP
description: Aflați cum să configurați conexiunea la o gazdă SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643518"
---
# <a name="connector-for-sftp-preview"></a>Conector pentru SFTP (previzualizare)

Utilizați datele despre clienți în aplicații terțe, exportându-le către o gazdă Secure File Transfer Protocol(SFTP).

## <a name="prerequisites"></a>Cerințe preliminare

- Disponibilitatea unei gazde SFTP și acreditările corespunzătoare.

## <a name="connect-to-sftp"></a>Conectare la SFTP

1. Accesați **Administrator** > **Destinații de export**.

1. Sub **SFTP**, selectați **Configurare**.

1. Dați destinației dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.

1. Furnizați un **Nume de utilizator**, **Parolă** și **Nume gazdă** pentru contul dvs. SFTP. Exemplu: Dacă folderul rădăcină al serverului dvs. SFTP este /root/folder, și doriți ca datele să fie exportate în /root/folder/ci_export_destination_folder, gazda ar trebui să fie sftp://<server_address>/ci_export_destination_folder".

1. Selectați **Verificare** pentru a testa conexiunea.

1. După verificarea reușită, alegeți dacă doriți să exportați datele **Arhivate** sau **Dezarhivate** și selectați **Delimitatorul de câmp** pentru fișierele exportate.

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Următorul** pentru a începe configurarea exportului.

## <a name="configure-the-connection"></a>Configurați conexiunea

1. Selectați **atributele clientului** pe care doriți să le exportați. Aveți posibilitatea să exportați unul sau mai multe atribute.

1. Selectați **Următorul**.

1. Selectați segmentele pe care doriți să le exportați.

1. Selectați **Salvare**.

## <a name="export-the-data"></a>Exportați datele

Puteți [exporta date la cerere](export-destinations.md). Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date prin SFTP, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că destinația de export îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.
