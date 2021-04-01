---
title: Exportați datele Customer Insights către Facebook Ads Manager
description: Aflați cum puteți configura conexiunea la Managerul de reclame Facebook.
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596698"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Conector pentru Managerul de reclame Facebook (previzualizare)

Exportați segmente de profiluri de client unificate către Managerul de reclame Facebook pentru a crea campanii pe Facebook și Instagram.

## <a name="prerequisites"></a>Cerințe preliminare

- Trebuie să aveți un [**Facebook Cont publicitar**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) care include un [**Facebook Cont de afaceri**](https://business.facebook.com/).
- Trebuie să fiți administrator pe [**Facebook Contul publicitar**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Conectați-vă la Managerul de reclame Facebook

1. Accesați **Administrator** > **Destinații de export**.

1. Sub Managerul de reclame **Facebook**, selectați **Configurat**.

1. Dați destinației dvs. de export un nume ușor de recunoscut în câmpul **Nume afișat**.

1. Selectați **Continuă cu Facebook** pentru a vă conecta la Contul dvs. publicitar Facebook.

1. Acceptați permisiunea **ads_management** după autentificare cu Facebook.

1. Selectați **Contul publicitar Facebook** cu care doriți să lucrați.

1. Selectați un **Public personalizat existent** din lista derulantă sau creați un **Public personalizat nou**. Pentru mai multe informații, consultați [**Publicuri în Managerul de reclame Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Continuare** pentru a configura exportul.

## <a name="configure-the-connector"></a>Configurați conectorul

1. În **Alegeți câmpul dvs. de identificare cheie**, selectați **E-mail**, **Nume și adresă** sau **Telefon** pentru a trimite la Managerul de reclame Facebook.

1. Mapați atributele corespunzătoare de la entitatea clientului dvs. unificat pentru identificatorul de cheie selectat.
   > [TIP] Cele mai bune șanse pentru o corespondență apar dacă selectați **E-mail** ca identificator cheie. Adăugarea identificatorilor suplimentari poate îmbunătăți corespondența.

1. Selectați **Adăugați atributul** pentru a mapa atribute suplimentare pentru a trimite la Managerul de reclame Facebook. Atributele din Manager de reclame Facebook mapează la următoarele nume ușor de utilizat: **FN** = **Prenume**, **LN** = **Nume de familie**, **FI** = **Prima inițială**, **TELEFON** = **Telefon**, **GEN** = **Gen**, **DOB** = **Data nașterii**, **ST** = **Statul**, **CT** = **Oraș**, **ZIP** = **Cod poștal / Zip code**, **ȚARA** = **Tara / Regiunea**

1. Selectați segmentele pe care doriți să le exportați.

1. Selectați **Salvare**.

## <a name="export-the-data"></a>Exportați datele

Puteți [exporta date la cerere](export-destinations.md). Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitări cunoscute

- Profil de client de până la 10 milioane pe export către Facebook Ads Manager 
- Exportul către Facebook Ads Manager este limitat la segmente
- Exportul de segmente cu un total de 10 milion de profiluri poate dura până la 90 de minute până la finalizare.

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Facebook Ads Manager, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Facebook Ads îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.


[!INCLUDE[footer-include](../includes/footer-banner.md)]