---
title: Creați un mediu nou
description: Scopul unui mediu și cum să creați unul nou.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 1f82ff588c2ffbe82c3ee7df2498ac2cca2bad31
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225462"
---
# <a name="create-a-new-environment"></a>Creați un mediu nou 

## <a name="overview"></a>Prezentare generală

Un mediu este un spațiu în care vă gestionați spațiile de lucru și conexiunile. Modul în care utilizați mediile depinde de organizația dvs. și de cazul dvs. de utilizare. De exemplu, puteți să creați:

- Un mediu unic.
- Medii separate pentru testare și producție.
- Medii separate pentru anumite echipe sau departamente din organizația dvs. care conțin evenimente relevante pentru fiecare public.
- Medii separate pentru diferite ramuri globale ale companiei dvs.
- Conexiuni cu capacitatea de detalii despre public pentru Customer Insights.

## <a name="create-a-new-environment"></a>Creați un mediu nou

1. În partea dreaptă a bannerului principal, selectați selectorul de mediu și apoi **+ Nou**.

   :::image type="content" source="media/environment-picker.png" alt-text="Alegeți selectorul de mediu.":::

1. În panoul **Configurare**, tastați un **Numele mediului**.

1. Alegeți **Tip** de cont, în funcție de tipul dvs. de plan.

1. Alegeți **Regiune** și selectați **Următorul**. 

1. Tastați a **Numele spațiului de lucru**, care vă permite să colectați date pentru anumite site-uri web sau aplicații. Pentru informații suplimentare, consultați [Creați un spațiu de lucru](create-workspace.md).

1. Alege **Tipul spațiului de lucru** (web sau mobil) pe care doriți să le creați. 

1. Selectați **Arată setări avansate** pentru a activa sau dezactiva aceste setări opționale:

   - Comutați **Necunoscut la cunoscut** la „activat” pentru a asocia evenimentele web cu utilizatorii care s-au autentificat anterior. Pentru mai multe informații, vezi [Recunoașteți evenimentele web de la vizitatorii autentificați anterior](unknown-to-known.md).
   - Comutați **Filtrați robotul de trafic** la „activat” pentru a elimina traficul web de roboți pentru acest spațiu de lucru. 

1. Selectați **Terminat** după ce ați terminat. 

1. Instalați fragment de cod pentru a începe să primiți date, apoi selectați **Finalizare** pentru a crea spațiul de lucru. Pentru mai multe informații, consultați [Prezentare generală resurse pentru dezvoltator](developer-resources.md).

> [!NOTE]
> Acum puteți adăuga membri și le puteți atribui nivelul de permisiune din lista **Rol**. Pentru mai multe informații, consultați: [Roluri și permisiuni](user-roles.md). 

Pentru mai multe informații, consultați [Gestionați mediile și spațiile de lucru](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Lucrați cu noul dvs. mediu

- [Creați un spațiu de lucru](../engagement-insights/create-workspace.md) și adăugați membri.
- [Adăugați cod pe site-ul dvs. web](../engagement-insights/instrument-website.md) sau [aplicație mobilă](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Vizualizați un [raport în timp real](../engagement-insights/view-reports.md) sau creați [rapoarte personalizate](../engagement-insights/custom-reports.md).
- [Creați evenimente rafinate](../engagement-insights/refined-events.md) pentru export.
- [Exportați datele](../engagement-insights/export-events.md) la Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
