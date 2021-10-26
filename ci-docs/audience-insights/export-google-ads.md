---
title: Exportați datele Customer Insights către Google Ads
description: Aflați cum să configurați conexiunea și să exportați la Google Ads.
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ce9579f3d31207e666665237fd8935bb86889f8d
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617938"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportați segmente în Google Ads (previzualizare)

Exportați segmente de profiluri de clienți unificate într-o listă de public pentru Google Ads și folosiți-le pentru a face publicitate în Căutarea Google, Gmail, YouTube și Google Display Network. 

> [!IMPORTANT]
> În prezent, puteți crea o nouă conexiune și puteți exporta date în Google Ads numai dacă aveți deja un token aprobat pentru dezvoltatori Google Ads. Datorită modificărilor politicii, vom actualiza în scurt timp exportul Google Ads și vom oferi o opțiune de export care nu va necesita un token de dezvoltator pentru a asigura continuitatea experienței dvs. și pentru a simplifica exportul către Google Ads. Vă recomandăm să nu configurați mai multe conexiuni cu Google Ads pentru a facilita trecerea mai ușoară la noua opțiune de export.

## <a name="prerequisites-for-connection"></a>Cerințe preliminare pentru conexiune

-   Aveți un [cont Google Ads](https://ads.google.com/) și acreditările de administrator corespunzătoare.
-   Aveți un [token aprobat pentru dezvoltatori Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token). 
-   Îndepliniți cerințele pentru [Politica Customer Match](https://support.google.com/adspolicy/answer/6299717).
-   Îndepliniți cerințele pentru [remarketing al dimensiunilor listei](https://support.google.com/google-ads/answer/7558048).
-   Există audiențe în Google Ads și ID-urile corespunzătoare. Pentru informații suplimentare, consultați [Audiențe Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Aveți [segmente configurate](segments.md).
-   Profilurile de clienți unificate din segmentele exportate conțin câmpuri care reprezintă o adresă de e-mail, prenumele și numele de familie.

## <a name="known-limitations"></a>Limitări cunoscute

- Până la 1 milion de profiluri de clienți per export către Google Ads.
- Exportul către Google Ads este limitat la segmente.
- Exportul de segmente cu un total de 1 milion de profiluri de clienți poate dura până la 5 minute din cauza limitărilor din partea furnizorului. 
- Potrivirea în Google Ads poate dura până la 48 de ore.

## <a name="set-up-connection-to-google-ads"></a>Configurarea conexiunii la Google Ads

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Google Ads** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți **[ID-ul de client Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Introduceți **[Tokenul de dezvoltator aprobat de Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Autentificare cu Google Ads** și furnizați acreditările dvs. Google Ads.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea. 

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Google Ads. Dacă nu vedeți numele acestei secțiuni, atunci nu aveți la dispoziție conexiuni de acest tip.

1. Introduceți **[ID-ul de audiență Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** și selectați **Conectare** pentru a inițializa conexiunea la Google Ads.

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client.

1. Selectați segmentele pe care doriți să le exportați. Puteți exporta până la 1 milion de profiluri de client în total către Google Ads.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). 

Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Google Ads, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Google Ads îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
