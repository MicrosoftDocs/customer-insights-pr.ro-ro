---
title: Pagina principală în detalii privind publicul
description: Începeți să explorați aplicația din pagina de pornire.
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597250"
---
# <a name="create-a-new-environment"></a>Creați un nou mediu

## <a name="create-a-trial-environment"></a>Creați un mediu de încercare

Vă puteți înscrie pentru o versiune de încercare pe [pagina de înscriere versiune de încercare](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Versiunile de încercare expiră după 30 de zile.

1. Alegeți opțiunea **Înregistrați-vă pentru o versiune de încercare gratuită** și selectați **Înregistrați-vă acum**.

1. Furnizați adresa de e-mail de la muncă sau a școlii, spuneți-ne mai multe despre dvs. și selectați **Următorul**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialog pentru a vă înscrie pentru o instanță versiune de încercare":::

1. Furnizați un **Nume** pentru noul dvs. mediu. 

1. Selectați tipul de versiune de încercare.

1. Alegeți **Regiunea** pentru mediul dvs.

1. Opțional, pentru administratorii unei organizații Dynamics 365: Selectați **Setări complexe** și furnizați adresa URL a organizației dvs. pentru a utiliza caracteristicile de predicție, cum ar fi retragerea clienților.

1. Selectați **Creare**. 

După crearea mediului, veți vedea mediul **Demo** care vă permite să explorați aplicația cu date fictive. Puteți modifica datele eșantion pentru a se potrivi industriei dvs. Selectați pictograma **Setări** din antet și selectați **Setări demonstrative**. În plus, puteți schimba tema vizuală. 

Dvs. [treceți la mediul](#switch-environments) pe care l-ați creat în timpul procesului de înscriere pentru a lucra cu propriile date.

## <a name="create-a-new-production-or-sandbox-environment"></a>Creați un nou mediu de producție sau un mediu sandbox

În mediul dvs., selectați selectorul **Medii** în antetul aplicației și selectați **Nou**.

Urmați pașii ca și cum ați fi [creat un mediu de încercare](#create-a-trial-environment). În mod implicit, datele sunt stocate în Data Lake gestionat de Customer Insights. Obțineți o opțiune suplimentară atunci când selectați **Setări complexe** pentru a vă stoca datele în propriul Azure Data Lake. Furnizați numele contului și cheia de cont pentru a stabili o conexiune la Azure Data Lake. 

> [!IMPORTANT]
> Prin salvarea datelor în Azure Data Lake Storage dvs., sunteți de acord că datele vor fi transferate și stocate în locația geografică corespunzătoare pentru acel cont de stocare Azure, care poate diferi de locul în care sunt stocate datele în Dynamics 365 Customer Insights. [Aflați mai multe de la Centrul de autorizare Microsoft.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Explorați pagina de pornire

Puteți [accesa informații despre public din Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) pe următoarea adresă URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
Pagina **Pornire** afișează o prezentare generală a segmentelor, măsurilor și datelor de îmbogățire (dacă este configurată) după finalizarea fazelor de [mapare](map-entities.md), [potrivire](match-entities.md), și [îmbinare](merge-entities.md).

> [!div class="mx-imgBorder"] 
> ![Detalii în pagina de pornire](media/home-page-insights.png "Detalii în pagina de pornire")

Sub **Segmente recente**, vedeți grupuri de clienți pe baza atributelor demografice, comportamentale sau tranzacționale pe care le-ați definit. [Crearea de segmente](segments.md) vă ajută să vă grupați baza de clienți și să vă vizați mai bine activitățile comerciale.

**Măsuri recente** arată dale cu [indicatori cheie de performanță (KPI)](measures.md) pe care le-ați definit. De exemplu, probabilitatea medie ca un client să renunțe sau cheltuielile medii online pe client.

Secțiunea **Îmbogățiri recente** listează rezultatele proceselor de îmbogățire finalizate recent. [Îmbogățirile](enrichment-hub.md) adaugă informații despre baza dvs. de clienți. De exemplu, prin înțelegerea intereselor și mărcilor pentru care au afinitate.

## <a name="switch-environments"></a>Comutați medii

Selectați controlul **Mediu** din colțul din dreapta sus al paginii pentru a modifica mediile.

> [!div class="mx-imgBorder"] 
> ![Comutați mediul](media/home-page-environment-switcher.png "Comutați mediul")

Administratorii pot crea și gestiona [medii multiple](manage-environments.md). Menținerea a mai mult de un mediu poate fi utilă când, de exemplu, organizația dvs. acționează pe plan internațional și trebuie să separați datele și informațiile în moduri diferite.

## <a name="next-step"></a>Următorul pas

Pentru a vedea propriile informații pe pagina de pornire, va trebui mai întâi să [adăugați surse de date](data-sources.md) și să [unificați](data-unification.md) datele dvs. pentru a crea profiluri de clienți.


[!INCLUDE[footer-include](../includes/footer-banner.md)]