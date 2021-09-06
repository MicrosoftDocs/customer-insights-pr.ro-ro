---
title: Segmente bazate pe ieșirea predicție
description: Creați segmente pe baza entității de ieșire a unui model predicție.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b89754aea2b0da33f27dea5b26d212920f0c090885f951a37cf42ff11c7b6e93
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036434"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Creați un segment bazat pe un model predicție (previzualizare)

Rezultatele predicțiilor se aplică uneori numai pentru un subset din clienții dvs. Sporiți personalizarea recomandărilor prin crearea de segmente din rezultatele modelelor predicție. De exemplu, poate doriți să oferiți recomandări specifice clienților care preferă un anumit tip de serviciu. 

## <a name="prerequisites"></a>Cerințe preliminare

- Cel puțin [Permisiuni de contributor](permissions.md) în Customer Insights.

- O recomandare a produsului, modificarea tranzacțională, abonamentul sau modelul valorii pe viață a clientului configurat în Customer Insights. Examinați cerințele pentru a configura diferitele modele:

  - [Model de recomandare produse](predict-product-recommendation.md)
  - [Model de retragere a abonamentelor](predict-subscription-churn.md)
  - [Model de retragere tranzacțional](predict-transactional-churn.md)
  - [Valoarea ciclului de viață al clientului](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Creați un segment de clienți pe baza predicțiilor

1. Mergeți la **Informații** > **Predicții** și selectați fila **Previziunile mele**.

1. Selectați elipsele verticale de lângă modelul pe care doriți să îl examinați și selectați **Vizualizare**.

1. Pe pagina de rezultate, selectați **Creați segment**. Pentru mai multe informații despre pagina cu rezultate, consultați articolul despre model.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Captură de ecran a paginii de rezultate predicție cu evidențiere în acțiunea Creare segment.":::

1. Creați un segment nou pe baza entității de ieșire a modelului selectat. Pentru mai multe informații, consultați [Creați și gestionați segmente](segments.md).