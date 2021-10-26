---
title: Exportați datele Customer Insights către Anunțuri LinkedIn
description: Aflați cum să configurați conexiunea și să exportați la Anunțuri LinkedIn.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 948a7e980df5714034009c92282e78cf2bdcb231
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618306"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Exportați segmente în Anunțuri LinkedIn (previzualizare)

Exportați segmente de profiluri de clienți unificate în Anunțuri LinkedIn pentru a crea segmente Matched Audiences. Utilizați segmentele de Matched Audiences pentru direcționarea către companii și direcționarea prin contact.

## <a name="prerequisites"></a>Cerințe preliminare

-   Aveți un [Cont LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) și acreditările de administrator corespunzătoare.
-   Aveți [segmente configurate](segments.md) în Detalii despre audiență.
-   Profilurile de clienți din segmentele exportate conțin un câmp cu o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Puteți exporta până la 100.000 de profiluri de clienți per export către LinkedIn Ads.
- Exportul către Anunțuri LinkedIn este limitat la segmente.
- Exportul până la 100.000 de profiluri de clienți în LinkedIn Ads poate dura până la 10 minute. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Configurați conexiunea la spațiul de Anunțuri LinkedIn.

1. În statisticile publicului, accesați **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Anunțuri LinkedIn** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită este Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Furnizați-vă [ID-ul de cont LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Conectați** pentru a inițializa conexiunea la Monitor de campanie.

1. Selectați **Autentificare cu LinkedIn** și furnizați acreditările de administrator pentru LinkedIn Campaign Manager.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

Puteți configura un export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea LinkedIn. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

1. Alegeți dacă doriți să exportați date pentru a face [direcționarea prin contact](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) sau [direcționarea către companii](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) pe LinkedIn. 

1. În secțiunea **Potrivirea datelor**, pentru direcționarea prin contact, selectați cel puțin un câmp care reprezintă adresa de e-mail a unui client, Apple Ad ID, Google Ad ID, Google User ID sau nume și prenume. Dacă alegeți direcționarea în funcție de companie, selectați cel puțin un câmp care să reprezinte numele companiei, domeniul de e-mail, adresa URL a paginii LinkedIn, simbolul stocului sau site-ul web. Câmpuri suplimentare pot fi selectate pentru a defini în continuare exportul. 

1. Selectați segmentele pe care doriți să le exportați. Publicul potrivit Matched audiences din LinkedIn Campaign Manager va fi creat automat cu numele segmentelor pe care le-ați selectat pentru export. Fiecare segment va avea ca rezultat un public separat Matched audience. 

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Anunțuri LinkedIn, permiteți transferul de date în afara limitelor de conformitate cu Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi date cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Anunțuri LinkedIn respectă orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.
