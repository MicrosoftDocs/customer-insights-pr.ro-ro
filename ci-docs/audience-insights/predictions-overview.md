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
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095741"
---
# <a name="predictions-overview"></a><span data-ttu-id="a0f52-103">Prezentare generală a predicțiilor</span><span class="sxs-lookup"><span data-stu-id="a0f52-103">Predictions overview</span></span>

<span data-ttu-id="a0f52-104">Dynamics 365 Customer Insights vine cu o varietate de opțiuni care folosesc AI și învățare programată pentru a prezice date.</span><span class="sxs-lookup"><span data-stu-id="a0f52-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="a0f52-105">Modele predefinite</span><span class="sxs-lookup"><span data-stu-id="a0f52-105">Out-of-box models</span></span>

<span data-ttu-id="a0f52-106">Cel mai simplu mod de a începe cu prezicerea datelor sunt modelele predefinite, adesea denumite modele predefinite.</span><span class="sxs-lookup"><span data-stu-id="a0f52-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="a0f52-107">Acestea necesită doar anumite date și structură pentru a genera informații rapide.</span><span class="sxs-lookup"><span data-stu-id="a0f52-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="a0f52-108">În prezent, sunt disponibile următoarele modele:</span><span class="sxs-lookup"><span data-stu-id="a0f52-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="a0f52-109">[Valoarea ciclului de viață a clientului](predict-customer-lifetime-value.md): Prezice veniturile potențiale ale unui client pe parcursul întregii interacțiuni cu o companie.</span><span class="sxs-lookup"><span data-stu-id="a0f52-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="a0f52-110">[Recomandarea produsului](predict-product-recommendation.md): Sugerează seturi de recomandări predictive de produse pe baza comportamentului de cumpărare și a clienților cu modele de achiziție similare.</span><span class="sxs-lookup"><span data-stu-id="a0f52-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="a0f52-111">[Retragere din abonament](predict-subscription-churn.md): Prezice dacă un client riscă să nu mai utilizeze produsele sau serviciile cu abonament ale firmei dvs.</span><span class="sxs-lookup"><span data-stu-id="a0f52-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="a0f52-112">[Modificare tranzacțională](predict-transactional-churn.md) : Prezice dacă un client nu va mai cumpăra produsele sau serviciile dvs. într-un anumit interval de timp.</span><span class="sxs-lookup"><span data-stu-id="a0f52-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="a0f52-113">Integrare pentru învățarea programată Azure</span><span class="sxs-lookup"><span data-stu-id="a0f52-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="a0f52-114">Dacă o organizație folosește deja scenarii de învățare programată pe baza experimentelor Azure de învățare programată, caracteristica modelelor personalizate din Customer Insights ajută la conectarea punctelor.</span><span class="sxs-lookup"><span data-stu-id="a0f52-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="a0f52-115">Creați fluxuri de lucru care vă ajută să alegeți datele din care doriți să generați statistici și să asociați rezultatele la profilurile dvs. unificate de clienți.</span><span class="sxs-lookup"><span data-stu-id="a0f52-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="a0f52-116">Pentru mai multe informații, consultați [Modelele de învățare programată particularizate](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="a0f52-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="a0f52-117">Predicție AI Builder</span><span class="sxs-lookup"><span data-stu-id="a0f52-117">AI Builder prediction</span></span>

<span data-ttu-id="a0f52-118">Uneori, seturile de date sunt incomplete și unele valori lipsesc.</span><span class="sxs-lookup"><span data-stu-id="a0f52-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="a0f52-119">Customer Insights poate ajuta la prezicerea valorilor lipsă pentru entitatea și segmentele clientului.</span><span class="sxs-lookup"><span data-stu-id="a0f52-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="a0f52-120">Pentru mai multe informații, consultați [Completați datele parțiale cu predicții](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="a0f52-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
