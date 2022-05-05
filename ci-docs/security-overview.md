---
title: Setări de securitate în Dynamics 365 Customer Insights
description: Aflați despre setările de securitate în Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653813"
---
# <a name="security-overview-page"></a>Pagina de prezentare generală a securității

The **Securitate** pagina listează opțiuni pentru a configura permisiunile utilizatorului și caracteristicile care ajută la realizarea Dynamics 365 Customer Insights mai sigur. Numai administratorii pot accesa această pagină. 

Mergi la **Admin** > **Securitate** pentru a configura setările.

The **Securitate** pagina include următoarele file:
- [Utilizatori](#users-tab)
- [API-uri](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>Fila Utilizatori

Accesul la Customer Insights este limitat la utilizatorii din organizația dvs. care au fost adăugați la aplicație de către un administrator. The **Utilizatori** fila vă permite să gestionați accesul utilizatorilor și permisiunile acestora. Pentru mai multe informații, vezi [Permisiunile utilizatorului](permissions.md).

## <a name="apis-tab"></a>Fila API-uri

Vizualizați și gestionați cheile pentru a utiliza [API-uri Customer Insights](apis.md) cu datele mediului dumneavoastră.

Puteți crea chei primare și secundare noi selectând **Regenerați primar** sau **Regenerează secundar**. 

Pentru a bloca accesul API la mediu, selectați **Dezactivați**. Dacă API-urile sunt dezactivate, puteți selecta **Permite** pentru a acorda din nou acces.

## <a name="key-vault-tab"></a>Fila Key Vault

The **Seif de chei** fila vă permite să vă conectați și să vă gestionați propria [Seif pentru chei Azure](/azure/key-vault/general/basic-concepts) la mediu.
Seiful de chei dedicat poate fi utilizat pentru a etapiza și a folosi secrete în limita de conformitate a unei organizații. Customer Insights poate folosi secretele din Azure Key Vault pentru [stabiliți conexiuni](connections.md) către sisteme terțe.

Pentru mai multe informații, vedeți [Aduceți-vă propriul seif de chei Azure](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
