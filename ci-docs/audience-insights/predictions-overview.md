---
title: Prezentare generală despre scenariile de predicție acceptate
description: Predicție scenarii și opțiuni acoperite de aplicația Dynamics 365 Customer Insights.
ms.date: 12/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5972d5b191ded7db14e2ebe9a4a26570a8ea60ba
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 01/15/2022
ms.locfileid: "7978028"
---
# <a name="predictions-overview"></a>Prezentare generală a predicțiilor

Dynamics 365 Customer Insights vine cu o varietate de opțiuni care folosesc AI și învățare programată pentru a prezice date. 

## <a name="out-of-box-models"></a>Modele predefinite

Cel mai simplu mod de a începe cu prezicerea datelor sunt modelele predefinite, adesea denumite modele predefinite. Acestea necesită doar anumite date și structură pentru a genera informații rapide. În prezent, sunt disponibile următoarele modele: 

# <a name="individual-consumers-b-to-c"></a>[Consumatori individuali (B2C)](#tab/b2c)

- [Valoarea ciclului de viață a clientului](predict-customer-lifetime-value.md): Prezice veniturile potențiale ale unui client pe parcursul întregii interacțiuni cu o companie.
- [Recomandarea produsului](predict-product-recommendation.md): Sugerează seturi de recomandări predictive de produse pe baza comportamentului de cumpărare și a clienților cu modele de achiziție similare.
- [Retragere din abonament](predict-subscription-churn.md): Prezice dacă un client riscă să nu mai utilizeze produsele sau serviciile cu abonament ale firmei dvs.
- [Modificare tranzacțională](predict-transactional-churn.md) : Prezice dacă un client nu va mai cumpăra produsele sau serviciile dvs. într-un anumit interval de timp.
- [Analiza sentimentelor](sentiment-analysis.md) : Analizați sentimentul feedback-ului clienților și identificați aspectele de afaceri care sunt menționate frecvent.

# <a name="business-accounts-b-to-b"></a>[Conturi de afaceri (B2B)](#tab/b2b)

- [Modificare tranzacțională](predict-transactional-churn.md) : Prezice dacă un client nu va mai cumpăra produsele sau serviciile dvs. într-un anumit interval de timp.

---


## <a name="azure-machine-learning-integration"></a>Integrare pentru învățarea programată Azure

Dacă o organizație folosește deja scenarii de învățare programată pe baza experimentelor Azure de învățare programată, caracteristica modelelor personalizate din Customer Insights ajută la conectarea punctelor. Creați fluxuri de lucru care vă ajută să alegeți datele din care doriți să generați statistici și să asociați rezultatele la profilurile dvs. unificate de clienți. Pentru mai multe informații, consultați [Modelele de învățare programată particularizate](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder predicție

Uneori, seturile de date sunt incomplete și unele valori lipsesc. Customer Insights poate ajuta la prezicerea valorilor lipsă pentru entitatea și segmentele clientului. Pentru mai multe informații, consultați [Completați datele parțiale cu predicții](predictions.md).
