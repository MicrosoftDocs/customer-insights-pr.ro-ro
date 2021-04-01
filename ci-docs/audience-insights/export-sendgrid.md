---
title: Exportați datele Customer Insights către SendGrid
description: Aflați cum să configurați conexiunea la SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597296"
---
# <a name="connector-for-sendgrid-preview"></a>Conector pentru SendGrid (previzualizare)

Exportați segmente de profiluri unificate ale clienților în SendGrid și utilizați-le pentru campanii și marketing prin e-mail în SendGrid. 

## <a name="prerequisites"></a>Cerințe preliminare

-   Aveți un [cont SendGrid](https://sendgrid.com/) și acreditările de administrator corespunzătoare.
-   Există liste de persoane de contact în SendGrid și ID-urile corespunzătoare. Pentru mai multe informații, consultați [SendGrid - Gestionați persoanele de contact](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Aveți [segmente configurate](segments.md) în Detalii despre audiență.
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="connect-to-sendgrid"></a>Conectare la SendGrid

1. Accesați **Administrator** > **Destinații de export**.

1. Sub **SendGrid**, selectați **Configurare**.

1. Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Panoul de configurare pentru exportul SendGrid.":::

1. Introduceți **Cheia API SendGrid** [Cheia API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Introduceți **[ID-ul listă SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Conectare** pentru a inițializa conexiunea la SendGrid.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Continuare** pentru a configura exportul.

## <a name="configure-the-connector"></a>Configurați conectorul

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client. Repetați aceiași pași pentru alte câmpuri opționale precum **Prenume**, **Nume**, **Țară/Regiune**, **Stare**, **Oraș** și **Cod poștal**.

1. Selectați segmentele pe care doriți să le exportați. Ferm **recomandăm să nu exportați mai mult de 100.000 de profiluri de clienți în total** la SendGrid. 

1. Selectați **Salvare**.

## <a name="export-the-data"></a>Exportați datele

Puteți [exporta date la cerere](export-destinations.md). Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitări cunoscute

- Până la 100.000 de profiluri în total la SendGrid.
- Exportul către SendGrid este limitat la segmente.
- Exportul până la 100'000 de profiluri către SendGrid poate dura până la câteva ore. 
- Numărul de profiluri pe care le puteți exporta către SendGrid este dependent și limitat de contractul dvs. cu SendGrid.

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către SendGrid, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că SendGrid îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.


[!INCLUDE[footer-include](../includes/footer-banner.md)]