---
title: Creați un segment pe baza unui model predicție
description: Creați segmente pe baza entității de ieșire a unui model predicție.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610435"
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

1. Selectați modelul pe care doriți să îl revizuiți și selectați **Vedere**.

1. Pe pagina de rezultate, selectați **Creați segment**. Pentru mai multe informații despre pagina cu rezultate, consultați articolul despre model.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Captură de ecran a paginii de rezultate predicție cu evidențiere în acțiunea Creare segment.":::

1. Creați un nou segment folosind atribute din entitatea de ieșire a modelului selectat. Pentru mai multe informații, consultați [Creați și gestionați segmente](segments.md).

> [!TIP]
> De asemenea, puteți crea un segment pentru un model predicție din **Segmente** pagină selectând **Nou** si alegerea **Creați din** > **Inteligența**. Pentru mai multe informații, vezi [Creați un nou segment cu segmente rapide](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
