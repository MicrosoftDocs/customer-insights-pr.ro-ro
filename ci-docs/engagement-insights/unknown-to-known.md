---
title: Recunoașteți evenimentele web de la vizitatori autentificați anterior cu necunoscut până la cunoscut
description: Funcția necunoscută până la cunoscută vă permite să asociați evenimentele de pe un site web cu vizitatorii care s-au autentificat anterior.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: 75ce776fd5be1c426508ae6f5c239c86bdd3ec39
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230695"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Recunoașteți evenimentele web de la vizitatori autentificați anterior

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Caracteristica **necunoscut la cunoscut** în capabilitatea Statistici de implicare permite asocierea evenimentelor de pe un site web cu vizitatorii care s-au autentificat anterior. Dacă funcția este dezactivată, vizitatorii care s-au autentificat în timpul unei vizite anterioare și apoi au plecat nu sunt identificați dacă nu se autentifică din nou la întoarcere. 

De exemplu, o persoană a vizitat un site web săptămâna trecută, s-a conectat la contul de utilizator de pe site și a navigat în catalogul de produse. Persoana se întoarce în săptămâna următoare pentru a răsfoi mai multe produse fără să se conecteze la contul său. Proprietarul site-ului care utilizează caracteristica **necunoscut la cunoscut** ar ști că aceeași persoană s-a întors și ce a făcut pe site. Acest lucru permite raportarea și analiza mai precisă a activităților site-ului web.

## <a name="enable-unknown-to-known"></a>Activați necunoscut la cunoscut

Trebuie să fiți [administratorul spațiului de lucru](user-roles.md) pentru a activa această caracteristică. 

1. În statistici despre implicare, accesați **Administrator** > **Spațiu de lucru**. 
2. Selectați fila **Setări**.
3. În secțiunea **Necunoscut la cunoscut**, setați comutatorul la **Activat**.

![Activați necunoscut la cunoscut](media/U2Ktoggle.png "Activați necunoscut la cunoscut")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Adăugarea codului JavaScript la fragmentului dvs. de urmărire a site-ului

Un site web poate captura **authId utilizator** cu următorul exemplu JavaScript folosind [SDK web pentru statistici de implicare](advanced-SDK-implementation.md). Pentru ca caracteristica **necunoscut la cunoscut** să funcționeze trebuie să capturați autentificarea *și* să activați userMapping:True în fragementul JavaScript ca în exemplul de mai jos.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
