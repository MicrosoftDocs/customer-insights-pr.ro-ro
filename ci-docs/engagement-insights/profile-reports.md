---
title: Activați rapoartele de profil predefinite
description: Cum să creați rapoarte de profil predefinite grupate în funcție de sex, vârstă și județ sau regiune de origine.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bf2ec67c9fb99918b87841d3c0b131934e31b58b
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486135"
---
# <a name="out-of-box-profile-reports"></a>Rapoarte de profil predefinite

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un raport este o colecție de vizualizări de date pentru a vă ajuta să înțelegeți cum se comportă utilizatorii. Conectându-vă la informații despre publicul Customer Insights, Detalii despre angajamente pot afișa un raport cu informații despre profilurile unificate ale clienților. Acest raport include numărul de profiluri pe care le aveți, grupate după sex, vârstă și locație geografică.

## <a name="prerequisites"></a>Cerințe preliminare

Mediul detaliilor despre public trebuie să stocheze date într-un cont gestionat de client Azure Data Lake Storage.

Dacă utilizați o versiune de încercare a capacității de detaliilor despre public sau un mediu într-un Data Lake gestionat de Customer Insights, [contactați-ne](https://go.microsoft.com/fwlink/?linkid=2145734) pentru asistență.  


## <a name="enable-the-customer-profile-report"></a>Activați raportul profilului de client

Un administrator de mediu trebuie să [conecteze statistici despre implicare și informații despre public](integrate-audience-insights-engagement-insights.md).

După specificarea detaliilor conexiunii, administratorul poate acorda acces altor persoane din organizație pentru a vedea raportul. Administratorul de mediu care configurează conexiunea are automat acces la raport. 

După finalizarea conexiunii, funcția **Profiluri** va fi disponibilă în panoul de navigare din stânga. 

- Accesați **Descoperire** > **Profiluri** pentru a vedea raportul.

Raportul **Profiluri** conține vizualizări despre sex, vârstă și locația geografică a profilurilor de clienți conectați.

:::image type="content" source="media/customer-profiles.png" alt-text="Raportul profilului de client.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]