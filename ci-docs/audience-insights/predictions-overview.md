---
title: Prezentare generală despre scenariile de predicție acceptate
description: Predicție scenarii și opțiuni acoperite de aplicația Dynamics 365 Customer Insights.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 11b0efeecf8bea893272e67d29b1c6622771110c
ms.sourcegitcommit: a5e4503cf9ce0cea562bab9389748d8ca1451f9d
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/25/2022
ms.locfileid: "8487550"
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

> [!TIP]
> Vă recomandăm să reîmprospătați în mod regulat modelele gata de fabricație cu date actualizate, pentru a vă asigura că acestea vă informează cu exactitate cazul de utilizare în afaceri. Datele sunt reîmprospătate ad-hoc atunci când sistemul ingerează surse de date noi sau actualizate. Cu toate acestea, modelele vor recore doar în acest caz și vor continua să utilizeze datele de antrenament existente.
> 
> Puteți configura un **Actualizați programul** prin setarea programului de reinstruire a modelului în experiența de configurare. Modelul se va reinstrui și va recalifica în acest program, pe care îl puteți schimba oricând.


## <a name="azure-machine-learning-integration"></a>Integrare pentru învățarea programată Azure

Dacă o organizație folosește deja scenarii de învățare programată pe baza experimentelor Azure de învățare programată, caracteristica modelelor personalizate din Customer Insights ajută la conectarea punctelor. Creați fluxuri de lucru care vă ajută să alegeți datele din care doriți să generați statistici și să asociați rezultatele la profilurile dvs. unificate de clienți. Pentru mai multe informații, consultați [Modelele de învățare programată particularizate](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder predicție

Uneori, seturile de date sunt incomplete și unele valori lipsesc. Customer Insights poate ajuta la prezicerea valorilor lipsă pentru entitatea și segmentele clientului. Pentru mai multe informații, consultați [Completați datele parțiale cu predicții](predictions.md).
