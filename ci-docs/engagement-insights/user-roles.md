---
title: Roluri și permisiuni
description: Prezentare generală a rolurilor și a permisiunilor disponibile membrilor spațiului de lucru.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ccc6a1b87b4cc28701e276b6e35432356e7647c4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227554"
---
# <a name="roles-and-permissions"></a>Roluri și permisiuni

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un spațiu de lucru este locul în care stocați și gestionați evenimente și rapoarte. Pentru mai multe informații, consultați [Creați un spațiu de lucru și adăugați membri](create-workspace.md). 

Un spațiu de lucru poate include următoarele roluri și permisiuni:

- Rolurile de *Membru* sunt utilizatori care pot accesa un spațiu de lucru. Puteți atribui spațiului dvs. de lucru membri și le puteți defini roluri și permisiuni. 
- Rolurile de *Administrator* gestionează spații de lucru și mediile pot configura detalii despre angajament pentru alți utilizatori. 
- Rolurile de *Colaborator* sunt orientate către analiști care nu trebuie să configureze statistici despre implicare, dar doresc să își creeze propriile rapoarte, canale sau segmente.

## <a name="permissions"></a>Permisiuni
  
Următorul tabel identifică permisiunile pentru fiecare rol. 

| Permisiune | Administrator de mediu | Administrator de spațiu de lucru | Contribuitor la mediu | Colaborator al spațiului de lucru | 
|--|--|--|--|--|
| Creați medii (creatorul devine automat administrator de mediu) | X* | X* | X* | X* |  
| Configurați mediul (membrii mediului, ștergerea mediului) | X |  |  |  |  
| Creați spații de lucru | X |  |  |  |  
| Configurați spațiile de lucru (membrii spațiului de lucru, ștergeți spațiul de lucru) | X | X |  |  |  
| Configurați evenimentele și evenimentele rafinate | X | X | |  |  
| Vizualizare evenimente din spațiul de lucru și evenimente rafinate | X | X | |  |  
| Vizualizare resurse ale spațiului de lucru (rapoarte, segmente și valori)| X | X | X | X |  
| Creați rapoarte particularizate și pâlnii | X | X | X | X |  
| Creați valori și parametri de bază| X | X |  |  |  
| Creare segmente| X | X | X | X |  

*Poate crea medii de încercare numai în versiune preliminară. 

## <a name="add-members"></a>Adăugați membri

Puteți adăuga și elimina membri din spații de lucru și medii. Pentru mai multe informații vedeți [Medii și spații de lucru](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
