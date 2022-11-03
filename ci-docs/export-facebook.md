---
title: Exportați segmente către Facebook Manager de anunțuri (previzualizare) (conține videoclip)
description: Aflați cum să configurați conexiunea și să exportați la Facebook Ads Manager.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724631"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Exportați segmente către Facebook Manager de anunțuri (previzualizare)

Exportați segmente de profiluri de client unificate către Managerul de reclame Facebook pentru a crea campanii pe Facebook și Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Cerințe preliminare

- A [Facebook Cont de reclame](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) care include a [Facebook Cont de afaceri](https://business.facebook.com/).
- Privilegii de administrator pe [Facebook Cont de reclame](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).
- Termenii pentru public personalizat trebuie să fie acceptați de către utilizatorul care configurează conexiunea în Customer Insights.

## <a name="known-limitations"></a>Limitări cunoscute

- Până la 10 milioane de profiluri de clienți per export către Facebook Ads Manager, care poate dura până la 90 de minute.
- Numai segmente.
- Facebook Integrarea reclamelor nu acceptă utilizatorii cu mai mult de 25 de conturi publicitare.
- Facebook *lista de clienti* introduceți [audiențe personalizate](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) numai.
  > [!NOTE]
  > În unele cazuri, este posibil să vedeți segmente de public personalizate de diferite tipuri în lista drop-down. Dacă selectați un alt tip decât *lista de clienti*, exportul eșuează.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Configurarea conexiunii la Facebook Ads Manager

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Facebook Manager de reclame**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. [Permiteți contribuitorilor să folosească conexiunea pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autentificare cu Facebook Ads:

   1. Selectați **Continuați cu Facebook** pentru a vă conecta la contul Facebook Ads.

   1. Acceptați permisiunea **ads_management** după autentificare cu Facebook.

   1. Selectați **Contul publicitar Facebook** cu care doriți să lucrați.

   1. Selectați un **Public particularizat existent** din lista derulantă sau creați un **Public nou particularizat**.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În **Conexiune pentru export** câmp, alegeți o conexiune din Facebook Secțiunea Manager de anunțuri. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. În **Conectați datele** câmp, selectați **E-mail**, **și adresa**, sau **Telefon** a trimite la Facebook Manager de reclame.

1. Mapați atributele corespunzătoare de la entitatea clientului dvs. unificat pentru identificatorul de cheie selectat.
   > [!TIP]
   > Cele mai bune șanse pentru o corespondență apar dacă selectați **E-mail** ca identificator cheie. Adăugarea identificatorilor suplimentari poate îmbunătăți corespondența.

1. Selectați **Adăugați un atribut** pentru a mapa mai multe atribute de trimis către Facebook Ads Manager. Atributele din Facebook Ads Manager mapează la următoarele nume ușor de utilizat: **FN** = **Prenume**, **LN** = **Nume de familie**, **FI** = **Prima inițială**, **TELEFON** = **Telefon**, **GEN** = **Gen**, **DOB** = **Data nașterii**, **ST** = **Statul**, **CT** = **Oraș**, **ZIP** = **Cod poștal**, **ȚARA** = **Țară/Regiune**

1. Selectați segmentele pe care doriți să le exportați.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
