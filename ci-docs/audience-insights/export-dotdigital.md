---
title: Exportați datele Customer Insights către DotDigital
description: Aflați cum să configurați conexiunea la DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644463"
---
# <a name="connector-for-dotdigital-preview"></a>Conector pentru DotDigital (previzualizare)

Exportați segmente de profiluri de clienți unificate în agende DotDigital și folosiți-le pentru campanii, marketing prin e-mail și pentru a crea segmente de clienți cu DotDigital. 

## <a name="prerequisites"></a>Cerințe preliminare

-   Aveți un [cont DotDigital](https://dotdigital.com/) și acreditările de administrator corespunzătoare.
-   Există agende în DotDigital și ID-urile corespunzătoare. ID-ul poate fi găsit în adresa URL atunci când selectați și deschideți o agendă. Pentru mai multe informații, consultați [Agende DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Aveți [segmente configurate](segments.md) în Detalii despre audiență.
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="connect-to-dotdigital"></a>Conectarea la DotDigital

1. Accesați **Administrator** > **Destinații de export**.

1. Sub **DotDigital**, selectați **Configurare**.

1. Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Panoul de configurare pentru exportul DotDigital.":::

1. Introduceți **numele de utilizator și parola DotDigital**.

1. Introduceți **[ID-ul agendei DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Conectare** pentru a inițializa conexiunea la DotDigital.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Continuare** pentru a configura exportul.

## <a name="configure-the-connector"></a>Configurați conectorul

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client. Repetați aceiași pași pentru alte câmpuri opționale, cum ar fi **Prenume**, **Nume de familie**, **Nume complet**, **Gen**, și **Cod poștal**.

1. Selectați segmentele pe care doriți să le exportați. Puteți exporta până la 1 milion de profiluri de client în total către DotDigital.

1. Selectați **Salvare**.

## <a name="export-the-data"></a>Exportați datele

Puteți [exporta date la cerere](export-destinations.md). Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab). În DotDigital, puteți găsi acum segmentele dvs. în [Agendele DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Limitări cunoscute

- Până la 1 milion de profiluri per export către DotDigital.
- Exportul către DotDigital este limitat la segmente.
- Exportul de segmente cu un total de 1 milion de profiluri poate dura până la 3 ore din cauza limitărilor din partea furnizorului. 
- Numărul de profiluri pe care le puteți exporta către DotDigital este dependent și limitat de contractul dvs. cu DotDigital.

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către DotDigital, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că DotDigital îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.
