---
title: Exportați datele Customer Insights către Marketo
description: Aflați cum să configurați conexiunea la Marketo.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 74d19a0448123904210c26f7b8760d00296c9cfd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597986"
---
# <a name="connector-for-marketo-preview"></a>Conector pentru Marketo (previzualizare)

Exportați segmentele profilurilor client unificate pentru a genera campanii, a oferi marketing prin e-mail și a folosi anumite grupuri de clienți cu Marketo.

## <a name="prerequisites"></a>Cerințe preliminare

-   Aveți un [cont Marketo](https://login.marketo.com/) și acreditările de administrator corespunzătoare.
-   Există liste în Marketo și ID-urile corespunzătoare. Pentru informații suplimentare, consultați [Liste Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Aveți [segmente configurate](segments.md).
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.

## <a name="connect-to-marketo"></a>Conectare la Marketo

1. Accesați **Administrator** > **Destinații de export**.

1. Sub **Marketo**, selectați **Configurare**.

1. Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.

1. Introduceți **[ID-ul de client Marketo, secretul clientului și Numele de gazdă punct final REST](https://developers.marketo.com/rest-api/authentication/)**.

1. Introduceți **[ID-ul listă Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor** și selectați **Conectare** pentru a inițializa conexiunea la Marketo.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Exportați captura de ecran pentru conexiunea Marketo":::

1. Selectați **Continuare** pentru a configura exportul.

## <a name="configure-the-connector"></a>Configurați conectorul

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client. 

1. Opțional, puteți exporta **Prenume**, **Nume de familie**, **Oraș**, **Stat**, și **Țară/Regiune** ca câmpuri suplimentare pentru a crea e-mailuri mai personalizate. Selectați **Adăugare atribut** pentru a mapa aceste câmpuri.

1. Selectați segmentele pe care doriți să le exportați. Puteți exporta până la 1 milion de profiluri de client în total către Marketo.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Selectați câmpuri și segmente de exportat către Marketo":::

1. Selectați **Salvare**.

## <a name="export-the-data"></a>Exportați datele

Puteți [exporta date la cerere](export-destinations.md). Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab). În Marketo, puteți găsi acum segmentele dvs. sub [Listele Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Limitări cunoscute

- Până la 1 milion de profiluri per export către Marketo.
- Exportul către Marketo este limitat la segmente.
- Exportul de segmente cu un total de 1 milion de profiluri poate dura până la 3 ore. 
- Numărul de profiluri pe care le puteți exporta către Marketo este dependent și limitat de contractul dvs. cu Marketo.

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Marketo, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Marketo îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.


[!INCLUDE[footer-include](../includes/footer-banner.md)]