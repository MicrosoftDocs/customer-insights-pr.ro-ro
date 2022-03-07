---
title: Exportați datele Customer Insights către Mailchimp
description: Aflați cum să configurați conexiunea la Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: edff494f6edf26a8b641cb1d788a715389ddb346
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406668"
---
# <a name="connector-for-mailchimp-preview"></a>Conector pentru Mailchimp (previzualizare)

Exportați segmente de profiluri unificate ale clienților către Mailchimp pentru a crea buletine informative și campanii de e-mail.

## <a name="prerequisites"></a>Cerințe preliminare

-   Aveți un [cont Mailchimp](https://mailchimp.com/) și acreditările de administrator corespunzătoare.
-   Există audiențe în Mailchimp și ID-urile corespunzătoare. Pentru informații suplimentare, consultați [Audiențe Mailchimp](https://mailchimp.com/help/create-audience/).
-   Aveți [segmente configurate](segments.md)
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="connect-to-mailchimp"></a>Conectare la Mailchimp

1. Accesați **Administrator** > **Destinații de export**.

1. Sub **Mailchimp**, selectați **Configurare**.

1. Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Introduceți **[ID-ul de audiență Mailchimp](https://mailchimp.com/help/find-audience-id/)** și selectați **Conectare** pentru a inițializa conexiunea la Mailchimp.

1. Selectați **Autentificare cu Mailchimp** și furnizați acreditările dvs. Mailchimp.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Exportați captura de ecran pentru conexiunea Mailchimp":::

1. Selectați **Continuare** pentru a configura exportul.

## <a name="configure-the-connector"></a>Configurați conectorul

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client. 

1. Opțional, puteți exporta **Prenume** și **Nume de familie** ca câmpuri suplimentare pentru a crea e-mailuri mai personalizate. Selectați **Adăugare atribut** pentru a mapa aceste câmpuri.

1. Selectați segmentele pe care doriți să le exportați. Puteți exporta până la 1 milion de profiluri de client în total către Mailchimp.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Selectați câmpuri și segmente de exportat către Mailchimp":::

1. Selectați **Salvare**.

## <a name="export-the-data"></a>Exportați datele

Puteți [exporta date la cerere](export-destinations.md). Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab). În Mailchimp, puteți găsi acum segmentele dvs. sub [Audiențele Mailchimp](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Limitări cunoscute

- Până la 1 milion de profiluri per export către Mailchimp.
- Exportul către Mailchimp este limitat la segmente.
- Exportul de segmente cu un total de 1 milion de profiluri poate dura până la trei ore datorită limitărilor din partea furnizorului. 
- Numărul de profiluri pe care le puteți exporta către Mailchimp este dependent și limitat de contractul dvs. cu Mailchimp.

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Mailchimp, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Mailchimp îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.
