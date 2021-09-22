---
title: Adăugați cod pe site-ul dvs. web
description: Cum să adăugați un fragment de cod pentru a captura evenimente pe site-ul dvs. web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035109"
---
# <a name="install-the-code-snippet-on-a-website"></a>Instalați fragmentul de cod pe un site web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Acest articol descrie modul în care un administrator instalează fragmentul de cod pe un site web. Veți începe să vedeți evenimente în spațiul dvs. de lucru la scurt timp după adăugarea scriptului pe site-ul dvs. web. Pentru mai multe informații, consultați [Gestionați spații de lucru și medii](manage-environments-workspaces.md). Pentru a captura evenimente în aplicații mobile, consultați [Prezentare generală a resurselor pentru dezvoltatori](developer-resources.md).


### <a name="prerequisites"></a>Cerințe preliminare

* Trebuie să aveți permisiuni de administrator pentru spațiul de lucru pentru a stoca datele.
* Site-ul sau proiectul dvs. trebuie găzduit online pentru a putea trimite date despre activitate. Datele trimise dintr-un fișier local nu vor fi acceptate de către server.


## <a name="add-code-to-your-website"></a>Adăugați cod pe site-ul dvs. web
1.  Accesați **Administrator** > **Spațiu de lucru** și apoi selectați **Ghid de instalare**.
1. Selectați **Copiați codul** pentru a copia fragmentul de cod. În mod implicit, cheia de ingestie pentru spațiul dvs. de lucru este încorporată în fragmentul de cod.
:::image type="content" source="media/copy-code.png" alt-text="Captură de ecran a paginii fragmentului de cod.":::
3. Adăugați fragmentul de cod copiat pe site-ul dvs. web, lângă <head> etichetă și înainte de orice alt script sau etichete CSS.
4.  Publicați site-ul web actualizat și așteptați câteva minute pentru a capta traficul web primit.
5.  Pentru a vă vedea datele, selectați spațiul de lucru din comutatorul de spațiu de lucru din panoul de navigare. Apoi, selectați unul dintre rapoarte în secțiunea **Descoperiți**.

## <a name="configuration-options"></a>Opțiuni de configurare

Puteți modifica următoarele opțiuni de configurare în fragmentul de cod:

- **ingestionKey**: Cheia de ingestie utilizată pentru a trimite evenimente în spațiul dvs. de lucru. Puteți schimba cheia de ingestie pentru a trimite evenimente către un alt spațiu de lucru. O cheie de ingestie este unică pentru fiecare spațiu de lucru. 
- **autoCapture**: Specifică dacă sunt capturate vizualizările de pagină și interacțiunile cu site-ul web. Are două opțiuni:
    - **vizualizare**: Setat la *adevărat* pentru a captura vizualizări de pagină. Vizualizările de pagină sunt capturate ca *Vizualizare* [evenimente](glossary.md#event), un tip de [eveniment de bază](glossary.md#base-event).
    - **clic**: Setat la *adevărat* pentru a capta interacțiunile vizitatorilor pe site. Interacțiunile sunt capturate ca *Acțiune* [evenimente](glossary.md#event), un tip de [eveniment de bază](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
