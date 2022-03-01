---
title: 'conector LiveRamp '
description: Aflați cum să exportați datele la LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667199"
---
# <a name="liverampreg-connector-preview"></a>Conector LiveRamp &reg; (previzualizare)

Activați-vă datele în LiveRamp pentru a vă conecta cu peste 500 de platforme pe ecosistemele digitale, sociale și TV. Lucrați cu datele dvs. în LiveRamp pentru a viza, suprima și personaliza campaniile publicitare.

## <a name="prerequisites"></a>Cerințe preliminare

- Pentru a utiliza acest conector aveți nevoie de un abonament LiveRamp.
- Pentru a obține un abonament, [contactați LiveRamp](https://liveramp.com/contact/) direct. [Aflați mai multe despre Îndrumări LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Conectare la LiveRamp

1. În Detalii despre audiență, accesați **Administrator** > **Destinații export**.

1. În dala **LiveRamp**, selectați **Configurare**.

1. Dați destinației dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.

1. Furnizează un **Nume de utilizator** și **Parola** pentru contul dvs. LiveRamp Secure FTP (SFTP).
Aceste acreditări pot fi diferite de datele de acreditare Îndrumări LiveRamp.

1. Selectați **Verificare** pentru a testa conexiunea la LiveRamp.

1. După verificarea cu succes, acordați-vă consimțământul pentru **Confidențialitatea și conformitatea datelor** prin selectarea casetei de selectare **Sunt de acord**.

1. Selectați **Următorul** pentru a configura conectorul LiveRamp.

## <a name="configure-the-connector"></a>Configurați conectorul

1. În câmpul **Alegeți identificatorul de cheie**, selectați **E-mail**,  **Numele și adresa**, sau **Telefon** pentru a trimite la LiveRamp pentru rezolvarea identității.

1. Mapați atributele corespunzătoare de la entitatea clientului dvs. unificat pentru identificatorul de cheie selectat.

1. Selectați **Adăugați atributul** pentru a face o mapare a atributelor suplimentare pe care să le trimiteți la LiveRamp.

   > [!TIP]
   > Trimiterea mai multor atribute de identificare cheie către LiveRamp este probabil să vă obțină o rată de potrivire mai mare.

1. Selectați segmentele pe care doriți să le exportați în LiveRamp.

1. Selectați **Salvare**.

> [!div class="mx-imgBorder"]
> ![Conector LiveRamp cu mapare de atribute](media/export-liveramp-segments.png "Conector LiveRamp cu mapare de atribute")

## <a name="export-the-data"></a>Exportați datele

Exportul va începe curând dacă toate condițiile preliminare pentru export au fost finalizate. Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).
După ce exportul este încheiat cu succes, vă puteți conecta la Îndrumare LiveRamp pentru a activa și distribui datele.

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Liveramp, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Liveramp îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.