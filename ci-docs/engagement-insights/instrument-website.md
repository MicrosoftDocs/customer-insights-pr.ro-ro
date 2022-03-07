---
title: Adăugați cod pe site-ul dvs. web
description: Cum să adăugați un fragment de cod pentru a capta evenimente Dynamics 365 Customer Insights la website-ul dvs.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 99e1c04877993a9cd81912e3d400402aab06a7de
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231037"
---
# <a name="install-the-web-sdk-on-a-website"></a>Instalați SDK-ul web pe un site web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Acest articol descrie modul în care un administrator instalează setul de instrumente de dezvoltare web (SDK) pe un site web. Veți începe să vedeți evenimente în spațiul dvs. de lucru la scurt timp după instrumentarea site-ului dvs. web. Pentru mai multe informații, consultați [Gestionați spații de lucru și medii](manage-environments-workspaces.md). Pentru a captura evenimente în aplicații mobile, consultați [Prezentare generală a resurselor pentru dezvoltatori](developer-resources.md).


### <a name="prerequisites"></a>Cerințe preliminare

* Trebuie să aveți permisiuni de administrator pentru spațiul de lucru pentru a stoca datele.
* Site-ul sau proiectul dvs. trebuie găzduit online pentru a putea trimite date despre activitate. Datele trimise dintr-un fișier local nu vor fi acceptate de către server.


## <a name="add-web-sdk-to-your-website"></a>Adăugați SDK web la site-ul dvs. web

Accesați **Administrator** > **Spațiu de lucru** și apoi selectați **Ghid de instalare**. Există două opțiuni pentru a instala SDK web. Primul este să utilizați un link de descărcare, iar al doilea este să instalați un pachet de gestionare a pachetelor de noduri (NPM).

### <a name="option-1-using-the-download-link"></a>Opțiunea 1: Utilizând linkul de descărcare

1. Selectați **Copiați codul** pentru a copia fragmentul de cod. În mod implicit, cheia de ingestie pentru spațiul dvs. de lucru este încorporată în fragmentul de cod.
  :::image type="content" source="media/copy-code.png" alt-text="Captură de ecran a paginii fragmentului de cod.":::

1. Adăugați codul copiat pe site-ul dvs. web, lângă <head> etichetă și înainte de orice alt script sau etichete CSS.
1. Publicați site-ul web actualizat și așteptați câteva minute pentru a capta traficul web primit.
1. Pentru a vă vedea datele, selectați spațiul de lucru din comutatorul de spațiu de lucru din panoul de navigare. Apoi, selectați unul dintre rapoarte în secțiunea **Descoperiți**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>Opțiunea 2: utilizarea pachetului NPM (recomandat pentru aplicațiile web bazate pe JavaScript)

1. Accesați [Pagina web NPM](https://www.npmjs.com/package/engagementinsights-web) și urmați instrucțiunile pentru a instala și configura pachetul web SDK NPM.
1. Publicați site-ul web actualizat și așteptați câteva minute pentru a capta traficul web primit.
1. Pentru a vă vedea datele, selectați spațiul de lucru din comutatorul de spațiu de lucru din panoul de navigare. Apoi, selectați unul dintre rapoarte în secțiunea **Descoperiți**.

## <a name="configuration-options"></a>Opțiuni de configurare

Puteți modifica următoarele opțiuni de configurare în fragmentul de cod:

- **ingestionKey**: Cheia de ingestie utilizată pentru a trimite evenimente în spațiul dvs. de lucru. Puteți schimba cheia de ingestie pentru a trimite evenimente către un alt spațiu de lucru. O cheie de ingestie este unică pentru fiecare spațiu de lucru.
- **autoCapture**: Specifică dacă sunt capturate vizualizările de pagină și interacțiunile cu site-ul web. Are două opțiuni:
    - **vizualizare**: Setat la *adevărat* pentru a captura vizualizări de pagină. Vizualizările de pagină sunt capturate ca *Vizualizare* [evenimente](glossary.md#event), un tip de [eveniment de bază](glossary.md#base-event).
    - **clic**: Setat la *adevărat* pentru a capta interacțiunile vizitatorilor pe site. Interacțiunile sunt capturate ca *Acțiune* [evenimente](glossary.md#event), un tip de [eveniment de bază](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
