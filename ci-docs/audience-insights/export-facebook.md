---
title: Exportați datele despre Customer Insights către Facebook Manager de anunțuri (conține videoclip)
description: Aflați cum să configurați conexiunea și să exportați la Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce1e63f7b20b757780f05895b725003e286f9dac
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 12/18/2021
ms.locfileid: "7935039"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Exportați lista de segmente în Facebook Ads Manager (previzualizare)

Exportați segmente de profiluri de client unificate către Managerul de reclame Facebook pentru a crea campanii pe Facebook și Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites-for-connection"></a>Cerințe preliminare pentru conexiune

- Trebuie să aveți un [**Cont Facebook Ads**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) care include un [**Cont Facebook Business**](https://business.facebook.com/).
- Trebuie să fiți administrator pe [**Contul Facebook Ads**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Limitări cunoscute

- Până la 10 milioane de profiluri de clienți pe export către Facebook Ads Manager.
- Exportul către Facebook Ads Manager este limitat la segmente.
- Creați sau actualizați segmente de public personalizate în Facebook de tip doar *lista de clienți*.
- Exportarea de segmente cu un total de 10 milion de profiluri de clienți poate dura până la 90 minute.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Configurarea conexiunii la Facebook Ads Manager

Înainte ca utilizatorii să poată crea un export, un administrator trebuie să configureze conexiunea la serviciu și să permită contribuitorilor să utilizeze conexiunea.

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Facebook Ads Manager** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autentificare cu Facebook Ads: 

   1. Selectați **Continuați cu Facebook** pentru a vă conecta la contul Facebook Ads.

   1. Acceptați permisiunea **ads_management** după autentificare cu Facebook.

   1. Selectați **Contul publicitar Facebook** cu care doriți să lucrați.

   1. Selectați un **Public particularizat existent** din lista derulantă sau creați un **Public nou particularizat**. Pentru mai multe informații, consultați [**Publicuri în Managerul de reclame Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Puteți crea sau actualiza numai segmente de public personalizate pe Facebook de tipul *lista de clienți* cu acest export. În unele cazuri, vedeți segmente de public particularizate de diferite tipuri în lista derulantă. Selectarea unui alt tip decât *lista de clienți* va duce la un eșec al exportului. 

1. Examinați **Confidențialitatea și conformitatea datelor** și selectați **De acord**.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**. 

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea **Facebook Ads Manager**. Dacă nu vedeți numele acestei secțiuni, atunci nu aveți la dispoziție conexiuni de acest tip.

1. În **Alegeți câmpul dvs. de identificare cheie**, selectați **E-mail**, **Nume și adresă** sau **Telefon** pentru a trimite la Managerul de reclame Facebook. 

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.

1. Mapați atributele corespunzătoare de la entitatea clientului dvs. unificat pentru identificatorul de cheie selectat.
   > [!TIP]
   > Cele mai bune șanse pentru o corespondență apar dacă selectați **E-mail** ca identificator cheie. Adăugarea identificatorilor suplimentari poate îmbunătăți corespondența.

1. Selectați **Adăugați un atribut** pentru a mapa mai multe atribute de trimis către Facebook Ads Manager. Atributele din Facebook Ads Manager mapează la următoarele nume ușor de utilizat: **FN** = **Prenume**, **LN** = **Nume de familie**, **FI** = **Prima inițială**, **TELEFON** = **Telefon**, **GEN** = **Gen**, **DOB** = **Data nașterii**, **ST** = **Statul**, **CT** = **Oraș**, **ZIP** = **Cod poștal**, **ȚARA** = **Țară/Regiune**

1. Selectați segmentele pe care doriți să le exportați.

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). 

Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Facebook Ads Manager, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Facebook Ads îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
