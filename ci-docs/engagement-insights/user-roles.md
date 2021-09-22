---
title: Roluri și permisiuni
description: Prezentare generală a rolurilor și a permisiunilor disponibile membrilor spațiului de lucru.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036708"
---
# <a name="roles-and-permissions"></a>Roluri și permisiuni

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un spațiu de lucru este modul în care stocați și gestionați evenimente și rapoarte. Un membru e un utilizator ce poate accesa un spațiu de lucru. Puteți atribui spațiului dvs. de lucru membri și le puteți defini roluri și permisiuni. Rolurile de administrator gestionează spațiile de lucru și mediile și configurează informații de implicare pentru alți utilizatori. Rolurile colaboratorilor sunt orientate către analiști care nu trebuie să configureze statistici despre implicare, dar doresc să își creeze propriile rapoarte, canale sau segmente.

## <a name="permissions"></a>Permisiuni
  
Următorul grafic identifică permisiunile aferente pentru fiecare rol. 

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
