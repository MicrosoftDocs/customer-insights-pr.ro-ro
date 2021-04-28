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
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741444"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="c35ad-103">Creați un segment bazat pe un model predicție (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="c35ad-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="c35ad-104">Rezultatele predicțiilor se aplică uneori numai pentru un subset din clienții dvs.</span><span class="sxs-lookup"><span data-stu-id="c35ad-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="c35ad-105">Sporiți personalizarea recomandărilor prin crearea de segmente din rezultatele modelelor predicție.</span><span class="sxs-lookup"><span data-stu-id="c35ad-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="c35ad-106">De exemplu, poate doriți să oferiți recomandări specifice clienților care preferă un anumit tip de serviciu.</span><span class="sxs-lookup"><span data-stu-id="c35ad-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c35ad-107">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="c35ad-107">Prerequisites</span></span>

- <span data-ttu-id="c35ad-108">Cel puțin [Permisiuni de contributor](permissions.md) în Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c35ad-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="c35ad-109">O recomandare a produsului, modificarea tranzacțională, abonamentul sau modelul valorii pe viață a clientului configurat în Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c35ad-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="c35ad-110">Examinați cerințele pentru a configura diferitele modele:</span><span class="sxs-lookup"><span data-stu-id="c35ad-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="c35ad-111">Model de recomandare produse</span><span class="sxs-lookup"><span data-stu-id="c35ad-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="c35ad-112">Model de retragere a abonamentelor</span><span class="sxs-lookup"><span data-stu-id="c35ad-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="c35ad-113">Model de retragere tranzacțional</span><span class="sxs-lookup"><span data-stu-id="c35ad-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="c35ad-114">Valoarea ciclului de viață al clientului</span><span class="sxs-lookup"><span data-stu-id="c35ad-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="c35ad-115">Creați un segment de clienți pe baza predicțiilor</span><span class="sxs-lookup"><span data-stu-id="c35ad-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="c35ad-116">Mergeți la **Informații** > **Predicții** și selectați fila **Previziunile mele**.</span><span class="sxs-lookup"><span data-stu-id="c35ad-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="c35ad-117">Selectați elipsele verticale de lângă modelul pe care doriți să îl examinați și selectați **Vizualizare**.</span><span class="sxs-lookup"><span data-stu-id="c35ad-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="c35ad-118">Pe pagina de rezultate, selectați **Creați segment**.</span><span class="sxs-lookup"><span data-stu-id="c35ad-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="c35ad-119">Pentru mai multe informații despre pagina cu rezultate, consultați articolul despre model.</span><span class="sxs-lookup"><span data-stu-id="c35ad-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Captură de ecran a paginii de rezultate predicție cu evidențiere în acțiunea Creare segment.":::

1. <span data-ttu-id="c35ad-121">Creați un segment nou pe baza entității de ieșire a modelului selectat.</span><span class="sxs-lookup"><span data-stu-id="c35ad-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="c35ad-122">Pentru mai multe informații, consultați [Creați și gestionați segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c35ad-122">For more information, see [Create and manage segments](segments.md).</span></span>