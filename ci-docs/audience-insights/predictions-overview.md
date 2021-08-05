---
title: Prezentare generală despre scenariile de predicție acceptate
description: Predicție scenarii și opțiuni acoperite de aplicația Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b73046844f6009a2b163b5eaadf5f63f75cda1d8
ms.sourcegitcommit: b78c9680b213204e6b0ed47f0147205083f6a98f
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/12/2021
ms.locfileid: "6539176"
---
# <a name="predictions-overview"></a>Prezentare generală a predicțiilor

Dynamics 365 Customer Insights vine cu o varietate de opțiuni care folosesc AI și învățare programată pentru a prezice date. 

## <a name="out-of-box-models"></a>Modele predefinite

Cel mai simplu mod de a începe cu prezicerea datelor sunt modelele predefinite, adesea denumite modele predefinite. Acestea necesită doar anumite date și structură pentru a genera informații rapide. În prezent, sunt disponibile următoarele modele: 
- [Valoarea ciclului de viață a clientului](predict-customer-lifetime-value.md): Prezice veniturile potențiale ale unui client pe parcursul întregii interacțiuni cu o companie. 
- [Recomandarea produsului](predict-product-recommendation.md): Sugerează seturi de recomandări predictive de produse pe baza comportamentului de cumpărare și a clienților cu modele de achiziție similare.
- [Retragere din abonament](predict-subscription-churn.md): Prezice dacă un client riscă să nu mai utilizeze produsele sau serviciile cu abonament ale firmei dvs.
- [Modificare tranzacțională](predict-transactional-churn.md) : Prezice dacă un client nu va mai cumpăra produsele sau serviciile dvs. într-un anumit interval de timp.

## <a name="azure-machine-learning-integration"></a>Integrare pentru învățarea programată Azure

Dacă o organizație folosește deja scenarii de învățare programată pe baza experimentelor Azure de învățare programată, caracteristica modelelor personalizate din Customer Insights ajută la conectarea punctelor. Creați fluxuri de lucru care vă ajută să alegeți datele din care doriți să generați statistici și să asociați rezultatele la profilurile dvs. unificate de clienți. Pentru mai multe informații, consultați [Modelele de învățare programată particularizate](custom-models.md).

## <a name="ai-builder-prediction"></a>Predicție AI Builder

Uneori, seturile de date sunt incomplete și unele valori lipsesc. Customer Insights poate ajuta la prezicerea valorilor lipsă pentru entitatea și segmentele clientului. Pentru mai multe informații, consultați [Completați datele parțiale cu predicții](predictions.md).
