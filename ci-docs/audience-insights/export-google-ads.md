---
title: Exportați datele Customer Insights către Google Ads
description: Aflați cum să configurați conexiunea la Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568487"
---
# <a name="connector-for-google-ads-preview"></a>Conector pentru Google Ads (previzualizare)

Exportați segmente de profiluri de clienți unificate în lista de audiență Google Ads și folosiți-le pentru publicitate în Căutarea Google, Gmail, YouTube și Rețeaua de vizualizare Google. 

## <a name="prerequisites"></a>Cerințe preliminare

-   Aveți un [cont Google Ads](https://ads.google.com/) și acreditările de administrator corespunzătoare.
-   Există audiențe în Google Ads și ID-urile corespunzătoare. Pentru informații suplimentare, consultați [Audiențe Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Aveți [segmente configurate](segments.md)
-   Profilurile de clienți unificate din segmentele exportate conțin câmpuri care reprezintă o adresă de e-mail, prenumele și numele de familie

## <a name="connect-to-google-ads"></a>Conectare la Google Ads

1. Accesați **Administrator** > **Destinații de export**.

1. Sub **Google Ads**, selectați **Configurare**.

1. Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.

1. Introduceți **[ID-ul de client Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Introduceți **[Tokenul de dezvoltator aprobat de Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Introduceți **[ID-ul de audiență Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** și selectați **Conectare** pentru a inițializa conexiunea la Google Ads.

1. Selectați **Autentificare cu Google Ads** și furnizați acreditările dvs. Google Ads.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Exportați captura de ecran pentru conexiunea Google Ads":::

1. Selectați **Continuare** pentru a configura exportul.

## <a name="configure-the-connector"></a>Configurați conectorul

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client. Repetați aceiași pași pentru câmpurile **Prenume** și **Nume de familie**.

1. Selectați segmentele pe care doriți să le exportați. Puteți exporta până la 1 milion de profiluri de client în total către Google Ads.

1. Selectați **Salvare**.

## <a name="export-the-data"></a>Exportați datele

Puteți [exporta date la cerere](export-destinations.md). Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab). În Google Ads, puteți găsi acum segmentele dvs. sub [Segmente de audiență Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Limitări cunoscute

- Până la 1 milion de profiluri per export către Google Ads.
- Exportul către Google Ads este limitat la segmente.
- Exportul de segmente cu un total de 1 milion de profiluri poate dura până la 5 minute din cauza limitărilor din partea furnizorului. 
- Potrivirea în Google Ads poate dura până la 48 de ore.

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Google Ads, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Google Ads îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.
