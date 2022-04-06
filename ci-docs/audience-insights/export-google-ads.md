---
title: Exportați datele Customer Insights către Google Ads
description: Aflați cum să configurați conexiunea și să exportați la Google Ads.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7a85237f7aff564d6b540b2c11553a52f875fac4
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523815"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportați segmente în Google Ads (previzualizare)

Exportați segmente de profiluri de clienți unificate într-o listă de public pentru Google Ads și folosiți-le pentru a face publicitate în Căutarea Google, Gmail, YouTube și Google Display Network. 


## <a name="prerequisites-for-connection"></a>Cerințe preliminare pentru conexiune

-   Aveți un [cont Google Ads](https://ads.google.com/) și acreditările de administrator corespunzătoare.
-   Îndepliniți cerințele pentru [Politica Customer Match](https://support.google.com/adspolicy/answer/6299717).
-   Îndepliniți cerințele pentru [remarketing al dimensiunilor listei](https://support.google.com/google-ads/answer/7558048).
-   Aveți [segmente configurate](segments.md).
-   Profilurile unificate ale clienților din segmentele exportate conțin câmpuri care reprezintă o adresă de e-mail, un telefon, un ID de agent de publicitate mobil, un ID de utilizator terță parte sau o adresă.

## <a name="known-limitations"></a>Limitări cunoscute

- Exportul către Google Ads este limitat la segmente.
- Exportul de segmente cu un total de 1 milion de profiluri de clienți poate dura până la 30 minute din cauza limitărilor din partea furnizorului. 
- Potrivirea în Google Ads poate dura până la 48 de ore.

## <a name="set-up-connection-to-google-ads"></a>Configurarea conexiunii la Google Ads

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Google Ads** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți **[ID-ul de client Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Autentificare cu Google Ads** și furnizați acreditările dvs. Google Ads.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea. 

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Google Ads. Dacă nu vedeți numele acestei secțiuni, atunci nu aveți la dispoziție conexiuni de acest tip.

1. Dacă doriți să creați un nou public, lăsați câmpul Google Audience ID necompletat. Vom crea automat un nou public în contul dvs. Google Ads și vom folosi numele segmentului exportat. Dacă doriți să actualizați un public Google Ads existent, introduceți dvs [ID de public Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. În **Potrivirea datelor** secțiunea, selectați unul sau mai multe câmpuri de date de exportat și selectați câmpul care reprezintă câmpurile de date corespunzătoare în Customer Insights.

1. Selectați segmentele pe care doriți să le exportați. 

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). 

Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Google Ads, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Google Ads îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
