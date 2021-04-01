---
title: Exportați datele Customer Insights către Autopilot
description: Aflați cum să configurați conexiunea la Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596146"
---
# <a name="connector-for-autopilot-preview"></a>Conector pentru Autopilot (previzualizare)

Exportați segmente de profiluri unificate ale clienților în Autopilot și utilizați-le pentru marketing prin e-mail în Autopilot. 

## <a name="prerequisites"></a>Cerințe preliminare

-   Aveți un [cont Autopilotl](https://www.autopilothq.com/) și acreditările de administrator corespunzătoare.
-   Aveți [segmente configurate](segments.md) în Detalii despre audiență.
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="connect-to-autopilot"></a>Conectare la Autopilot

1. Accesați **Administrator** > **Destinații de export**.

1. Sub **Autopilot**, selectați **Configurare**.

1. Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Panoul de configurare pentru conexiunea Autopilot.":::

1. Introduceți **Cheie API pentru Autopilot** [Cheie API pentru Autopilot](https://autopilot.docs.apiary.io/#).

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Conectare** pentru a inițializa conexiunea la Autopilot.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Continuare** pentru a configura exportul.

## <a name="configure-the-connector"></a>Configurați conectorul

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client. Repetați aceiași pași pentru alte câmpuri opționale, cum ar fi **Prenume**, **Nume**.

1. Selectați segmentele pe care doriți să le exportați. Ferm **recomandăm să nu exportați mai mult de 100.000 de profiluri de clienți în total** la Autopilot. 

1. Selectați **Salvare**.

## <a name="export-the-data"></a>Exportați datele

Puteți [exporta date la cerere](export-destinations.md). Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitări cunoscute

- Puteți exporta până la 100.000 de profiluri de client în total către Autopilot.
- Exportul către Autopilot este limitat la segmente.
- Exportul până la 100'000 de profiluri către Autopilot poate dura până la câteva ore. 
- Numărul de profiluri pe care le puteți exporta către Autopilot este dependent și limitat de contractul dvs. cu Autopilot.

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Autopilot, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Autopilot îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.


[!INCLUDE[footer-include](../includes/footer-banner.md)]