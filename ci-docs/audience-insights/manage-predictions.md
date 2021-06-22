---
title: Sarcini partajate pentru scenarii de predicție
description: Aflați cum să gestionați, să depanați și să rafinați predicțiile.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095742"
---
# <a name="manage-predictions"></a><span data-ttu-id="6a66e-103">Gestionați predicțiile</span><span class="sxs-lookup"><span data-stu-id="6a66e-103">Manage predictions</span></span>

<span data-ttu-id="6a66e-104">Acest articol discută câteva sarcini pe care le partajează majoritatea scenariilor de predicție.</span><span class="sxs-lookup"><span data-stu-id="6a66e-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="6a66e-105">Depanarea unei predicții eșuate</span><span class="sxs-lookup"><span data-stu-id="6a66e-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="6a66e-106">Mergeți la **Informații** > **Predicții** și selectați fila **Previziunile mele**.</span><span class="sxs-lookup"><span data-stu-id="6a66e-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="6a66e-107">Selectați elipsele verticale de lângă predicția pentru care doriți să vedeți jurnalele de erori.</span><span class="sxs-lookup"><span data-stu-id="6a66e-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="6a66e-108">Selectați **Jurnale**.</span><span class="sxs-lookup"><span data-stu-id="6a66e-108">Select **Logs**.</span></span>

1. <span data-ttu-id="6a66e-109">Analizarea tuturor erorilor.</span><span class="sxs-lookup"><span data-stu-id="6a66e-109">Review all the errors.</span></span> <span data-ttu-id="6a66e-110">Există mai multe tipuri de erori care pot apărea și ce descriu condiția care a cauzat eroarea.</span><span class="sxs-lookup"><span data-stu-id="6a66e-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="6a66e-111">De exemplu, o eroare pentru date insuficiente pentru o predicție exactă este de obicei rezolvată prin încărcarea de date suplimentare în Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6a66e-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="6a66e-112">Raport de utilizare a datelor de intrare</span><span class="sxs-lookup"><span data-stu-id="6a66e-112">Input data usability report</span></span>

<span data-ttu-id="6a66e-113">Raportul de utilizare a datelor de intrare oferă o imagine consolidată a erorilor și avertismentelor pe care le pot genera predicțiile dvs. predefinite.</span><span class="sxs-lookup"><span data-stu-id="6a66e-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="6a66e-114">De asemenea, oferă recomandări despre cum să îmbunătățim performanța modelului.</span><span class="sxs-lookup"><span data-stu-id="6a66e-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="6a66e-115">Raportul este disponibil după ce un model a finalizat procesul de instruire.</span><span class="sxs-lookup"><span data-stu-id="6a66e-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="6a66e-116">Este creat pentru fiecare model separat, indiferent dacă s-a finalizat cu succes sau nu.</span><span class="sxs-lookup"><span data-stu-id="6a66e-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="6a66e-117">În prezent, această caracteristică funcționează numai pentru modelul Transaction Churn.</span><span class="sxs-lookup"><span data-stu-id="6a66e-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="6a66e-118">Vizualizați raportul de utilizare a datelor de intrare</span><span class="sxs-lookup"><span data-stu-id="6a66e-118">View the input data usability report</span></span>

<span data-ttu-id="6a66e-119">După ce un model predefinit a finalizat etapa de instruire, vizualizați raportul:</span><span class="sxs-lookup"><span data-stu-id="6a66e-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="6a66e-120">Selectați punctele de suspensie de lângă numele modelului și alegeți **Raport de utilizare a datelor de intrare**.</span><span class="sxs-lookup"><span data-stu-id="6a66e-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="6a66e-121">Selectați starea unui model selectat **Vedeți raportul de utilizare a datelor de intrare** în panoul lateral.</span><span class="sxs-lookup"><span data-stu-id="6a66e-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="6a66e-122">Selectați unul dintre modelele din listă și selectați **Raport de utilizare a datelor de intrare** în bara de comandă.</span><span class="sxs-lookup"><span data-stu-id="6a66e-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="6a66e-123">Deschideți pagina cu rezultatele modelului și selectați **Raport de utilizare a datelor de intrare** în bara de comandă.</span><span class="sxs-lookup"><span data-stu-id="6a66e-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="6a66e-124">Informații din raportul de utilizare a datelor de intrare</span><span class="sxs-lookup"><span data-stu-id="6a66e-124">Information in the input data usability report</span></span>

<span data-ttu-id="6a66e-125">Următoarele coloane din raport conțin informații utile pentru a îmbunătăți datele pentru model.</span><span class="sxs-lookup"><span data-stu-id="6a66e-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exemplu de raport de utilizare a datelor de intrare care prezintă un tabel cu erori, avertismente și recomandări.":::

- <span data-ttu-id="6a66e-127">Nume: Numele descriptiv al erorii, avertismentului sau al recomandării.</span><span class="sxs-lookup"><span data-stu-id="6a66e-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="6a66e-128">Pas: Faza pentru model, instruire sau scor, la care se referă informațiile.</span><span class="sxs-lookup"><span data-stu-id="6a66e-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="6a66e-129">Stare: Severitatea informațiilor (eroare, avertisment, recomandare).</span><span class="sxs-lookup"><span data-stu-id="6a66e-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="6a66e-130">Nume coloană: Coloana dintr-o entitate care trebuie modificată pentru a îmbunătăți performanța modelului.</span><span class="sxs-lookup"><span data-stu-id="6a66e-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="6a66e-131">Entitate: Numele entității care trebuie modificată pentru a îmbunătăți performanța modelului.</span><span class="sxs-lookup"><span data-stu-id="6a66e-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="6a66e-132">Detalii: Detalii despre eroare, avertisment sau recomandare.</span><span class="sxs-lookup"><span data-stu-id="6a66e-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="6a66e-133">Reîmprospătați o predicție</span><span class="sxs-lookup"><span data-stu-id="6a66e-133">Refresh a prediction</span></span>

<span data-ttu-id="6a66e-134">Predicțiile se vor actualiza reîmprospăta conform aceluiași [program de reîmprospătare a datelor](system.md#schedule-tab) așa cum este configurat în setări.</span><span class="sxs-lookup"><span data-stu-id="6a66e-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="6a66e-135">Le puteți reîmprospăta și manual.</span><span class="sxs-lookup"><span data-stu-id="6a66e-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="6a66e-136">Mergeți la **Informații** > **Predicții** și selectați fila **Previziunile mele**.</span><span class="sxs-lookup"><span data-stu-id="6a66e-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="6a66e-137">Selectați elipsele verticale de lângă predicția pe care doriți să o reîmprospătați.</span><span class="sxs-lookup"><span data-stu-id="6a66e-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="6a66e-138">Selectați **Reîmprospătare**.</span><span class="sxs-lookup"><span data-stu-id="6a66e-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="6a66e-139">Ștergerea unei predicții</span><span class="sxs-lookup"><span data-stu-id="6a66e-139">Delete a prediction</span></span>

<span data-ttu-id="6a66e-140">Ștergerea unui predicții elimină și entitatea acesteia de ieșire.</span><span class="sxs-lookup"><span data-stu-id="6a66e-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="6a66e-141">Mergeți la **Informații** > **Predicții** și selectați fila **Previziunile mele**.</span><span class="sxs-lookup"><span data-stu-id="6a66e-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="6a66e-142">Selectați elipsele verticale de lângă predicția pe care doriți să o ștergeți.</span><span class="sxs-lookup"><span data-stu-id="6a66e-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="6a66e-143">Selectați **Ștergere**.</span><span class="sxs-lookup"><span data-stu-id="6a66e-143">Select **Delete**.</span></span>
