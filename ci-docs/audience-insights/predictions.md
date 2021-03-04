---
title: Completați datele parțiale folosind predicții
description: Utilizați predicții pentru a completa datele incomplete ale clienților.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 577232c7e901dfd54a195c3e9cfac5d1f0f866e6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268287"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="3b374-103">Finalizați-vă datele parțiale cu predicții</span><span class="sxs-lookup"><span data-stu-id="3b374-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="3b374-104">Predicțiile vă permit să creați cu ușurință valori previzionate care vă pot îmbunătăți înțelegerea despre un client.</span><span class="sxs-lookup"><span data-stu-id="3b374-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="3b374-105">Pe pagina **Informații** > **Predicții**, puteți selecta **Predicțiile mele** pentru a vedea predicțiile pe care le-ați configurat în alte părți ale detaliilor privind publicul și vă permit să le personalizați în continuare.</span><span class="sxs-lookup"><span data-stu-id="3b374-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="3b374-106">Nu puteți utiliza această caracteristică dacă mediul dvs. utilizează stocarea Azure Data Lake Gen 2.</span><span class="sxs-lookup"><span data-stu-id="3b374-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="3b374-107">Funcția de predicții folosește mijloace automate pentru a evalua datele și pentru a face predicții bazate pe acele date și, prin urmare, are capacitatea de a fi utilizată ca metodă de profilare, deoarece acest termen este definit de Regulamentul general privind protecția datelor („RGPD”).</span><span class="sxs-lookup"><span data-stu-id="3b374-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="3b374-108">Utilizarea acestei funcții de către client pentru prelucrarea datelor poate fi supusă RGPD sau altor legi sau reglementări.</span><span class="sxs-lookup"><span data-stu-id="3b374-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="3b374-109">Sunteți responsabil pentru a vă asigura că utilizarea de către dvs. a Dynamics 365 Customer Insights, inclusiv predicțiile, respectă toate legile și reglementările aplicabile, inclusiv legile legate de confidențialitate, date cu caracter personal, date biometrice, protecția datelor și confidențialitatea comunicărilor.</span><span class="sxs-lookup"><span data-stu-id="3b374-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3b374-110">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="3b374-110">Prerequisites</span></span>

<span data-ttu-id="3b374-111">Înainte ca organizația dvs. să poată utiliza funcția de predicții, trebuie să fie îndeplinite următoarele cerințe preliminare:</span><span class="sxs-lookup"><span data-stu-id="3b374-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="3b374-112">Organizația dvs. are o instanță [înființată în Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) și se află în aceeași organizație ca Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3b374-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="3b374-113">Mediul dvs. este atașat la instanța Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="3b374-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="3b374-114">Dacă ați [creat un mediu nou](manage-environments.md), configurați-l în dialogul **Creați un mediu** și selectați **Avansat**.</span><span class="sxs-lookup"><span data-stu-id="3b374-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="3b374-115">Dacă ați creat deja un mediu, accesați setările acestuia și selectați **Avansat**.</span><span class="sxs-lookup"><span data-stu-id="3b374-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="3b374-116">Oricum, în secțiunea **Utilizare predicții**, introduceți URL-ul instanței Common Data Service la care doriți să vă atașați mediul.</span><span class="sxs-lookup"><span data-stu-id="3b374-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="3b374-117">Creați o predicție în entitatea client</span><span class="sxs-lookup"><span data-stu-id="3b374-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="3b374-118">În Detalii despre public, accesați **Date** > **Entități**.</span><span class="sxs-lookup"><span data-stu-id="3b374-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="3b374-119">Selectați entitatea **Client**.</span><span class="sxs-lookup"><span data-stu-id="3b374-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="3b374-120">În entitatea **Client: CustomerInsights**, selectați pe fila **Câmpuri**.</span><span class="sxs-lookup"><span data-stu-id="3b374-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="3b374-121">Găsiți numele atributului pentru care doriți să preziceți valorile, apoi selectați pictograma **Prezentare generală** din coloana **Rezumat**.</span><span class="sxs-lookup"><span data-stu-id="3b374-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3b374-122">![Pictograma Prezentare generală](media/intelligence-overviewicon.png "Pictograma Prezentare generală")</span><span class="sxs-lookup"><span data-stu-id="3b374-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="3b374-123">Dacă există o rată mare de valori lipsă pentru atributul dvs., selectați **Prognozare valori lipsă** pentru a continua cu predicția dvs.</span><span class="sxs-lookup"><span data-stu-id="3b374-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3b374-124">![Prezentarea generală a stării cu afișarea butonului valorilor care lipsesc](media/intelligence-overviewpredictmissingvalues.png "Prezentarea generală a stării cu afișarea butonului valorilor care lipsesc")</span><span class="sxs-lookup"><span data-stu-id="3b374-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="3b374-125">Furnizați un **Nume afișat** și un **Nume entitate de ieșire** pentru rezultatele de predicție.</span><span class="sxs-lookup"><span data-stu-id="3b374-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="3b374-126">Se afișează o listă de opțiuni pre-populată unde puteți mapa valorile cu o categorie prognozată.</span><span class="sxs-lookup"><span data-stu-id="3b374-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="3b374-127">În acest caz, singurele dvs. opțiuni de categorie vor fi 0 sau 1, pe măsură ce acestea se potrivesc cu valorile true/false sau cu caracterul binar al predicției.</span><span class="sxs-lookup"><span data-stu-id="3b374-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="3b374-128">În coloana Categorie, mapați valorile câmpului pe care doriți să le clasificați la „0” în predicția finală la „0”, și elementele pe care doriți să le clasificați drept „1” în predicția finală la „1”.</span><span class="sxs-lookup"><span data-stu-id="3b374-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3b374-129">![Exemplu care arată valorile câmpului mapat la categorii](media/intelligence-categorymapping.png "Exemplu care arată valorile câmpului mapat la categorii")</span><span class="sxs-lookup"><span data-stu-id="3b374-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="3b374-130">Selectați **Terminat** iar predicția va fi procesată.</span><span class="sxs-lookup"><span data-stu-id="3b374-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="3b374-131">Procesarea va dura ceva timp, în funcție de dimensiunea și complexitatea datelor.</span><span class="sxs-lookup"><span data-stu-id="3b374-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="3b374-132">Rezultatele vor fi disponibile într-o nouă entitate pe baza **Nume entitate de ieșire** din predicția pe care ai creat-o.</span><span class="sxs-lookup"><span data-stu-id="3b374-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="3b374-133">Creați o predicție în timp ce creați un segment</span><span class="sxs-lookup"><span data-stu-id="3b374-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="3b374-134">Prognozarea valorilor lipsă pentru un atribut specific de alegere este posibilă și la crearea unui segment.</span><span class="sxs-lookup"><span data-stu-id="3b374-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="3b374-135">Mai exact, atunci când creați rapid un segment în funcție fie de entitatea client unificat, fie de entitatea Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="3b374-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="3b374-136">Ca parte a acestui flux,veți alege un atribut specific pentru a vă defini segmentul pe atribute, cum ar fi satisfacția clientului sau suma de achiziție.</span><span class="sxs-lookup"><span data-stu-id="3b374-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="3b374-137">După crearea segmentului, sistemul va sugera o metodă pentru a prezice orice valori lipsă pentru acest atribut.</span><span class="sxs-lookup"><span data-stu-id="3b374-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="3b374-138">În detaliile despre public, accesați **Segmente** și selectați dala **Profiluri**.</span><span class="sxs-lookup"><span data-stu-id="3b374-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="3b374-139">Alegeți un **Câmp** pentru a crea un segment activat și selectați un **Operator**, apoi selectați **Revizuire**.</span><span class="sxs-lookup"><span data-stu-id="3b374-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="3b374-140">Furnizați un **Nume** și un **Numele afișat** pentru segment.</span><span class="sxs-lookup"><span data-stu-id="3b374-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="3b374-141">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="3b374-141">Select **Save**.</span></span>

5. <span data-ttu-id="3b374-142">Dacă segmentul pe care l-ați creat are date incomplete în câmpul sursă, puteți alege să preziceți valorile lipsă.</span><span class="sxs-lookup"><span data-stu-id="3b374-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3b374-143">![Buton de predicție](media/segments-predictoption.png "Buton de predicție")</span><span class="sxs-lookup"><span data-stu-id="3b374-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="3b374-144">Furnizați un **Nume afișat** și un **Nume entitate de ieșire** pentru rezultatele de predicție.</span><span class="sxs-lookup"><span data-stu-id="3b374-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="3b374-145">Selectați **Terminat**.</span><span class="sxs-lookup"><span data-stu-id="3b374-145">Select **Done**.</span></span> <span data-ttu-id="3b374-146">Predicția dvs. va fi generată în scurt timp într-o entitate nouă cu numele pe care l-ați furnizat pentru **Nume entitate de ieșire**.</span><span class="sxs-lookup"><span data-stu-id="3b374-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="3b374-147">Previzualizați o predicție</span><span class="sxs-lookup"><span data-stu-id="3b374-147">View a prediction</span></span>

1. <span data-ttu-id="3b374-148">În Detalii despre public, accesați **Informații** > **Predicții** > **Predicțiile mele**.</span><span class="sxs-lookup"><span data-stu-id="3b374-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="3b374-149">Selectați predicția pe care doriți să o revizuiți.</span><span class="sxs-lookup"><span data-stu-id="3b374-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="3b374-150">Selectați cele trei puncte de suspensie din coloana **Acțiuni** și alegeți **Vizualizare**.</span><span class="sxs-lookup"><span data-stu-id="3b374-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="3b374-151">Veți vedea o serie de puncte de date în vizualizarea predicției dvs.</span><span class="sxs-lookup"><span data-stu-id="3b374-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3b374-152">![Pagina Predicții](media/intelligence-predictionsviewpage.png "Pagina Predicții")</span><span class="sxs-lookup"><span data-stu-id="3b374-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="3b374-153">**Valori previzionate** arată maparea pe care ați creat-o în faza de mapare a valorii câmpului la Categorie.</span><span class="sxs-lookup"><span data-stu-id="3b374-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="3b374-154">Acestea sunt valorile din setul dvs. de date care au fost mapate într-o anumită categorie.</span><span class="sxs-lookup"><span data-stu-id="3b374-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="3b374-155">-**Factori de influență principali** sunt factorii din setul dvs. de date care sunt cel mai probabil să vă fi influențat încrederea predicției pentru ca valoarea câmpului dvs. să fie mapată într-o anumită categorie.</span><span class="sxs-lookup"><span data-stu-id="3b374-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="3b374-156">**Performanța** indică evoluția predicțiilor.</span><span class="sxs-lookup"><span data-stu-id="3b374-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="3b374-157">Selectați linkul pentru a afla mai multe.</span><span class="sxs-lookup"><span data-stu-id="3b374-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="3b374-158">**Previzualizare** arată eșantioane din setul de date de ieșire pentru predicția dvs. și probabilitatea, sau încrederea noastră, a valorii prognozate în care 0 este incert și 1 este sigur.</span><span class="sxs-lookup"><span data-stu-id="3b374-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="3b374-159">Actualizați o predicție</span><span class="sxs-lookup"><span data-stu-id="3b374-159">Update a prediction</span></span>

1. <span data-ttu-id="3b374-160">În Detalii despre public, accesați **Informații** > **Predicții** > **Predicțiile mele**.</span><span class="sxs-lookup"><span data-stu-id="3b374-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="3b374-161">Selectați predicția pe care doriți să o actualizați și selectați pictograma **Actualizare**.</span><span class="sxs-lookup"><span data-stu-id="3b374-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="3b374-162">Predicția va fi planificată pentru procesare.</span><span class="sxs-lookup"><span data-stu-id="3b374-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="3b374-163">Puteți vedea ora la care a fost actualizată ultima dată în coloana **Actualizat** din pagina **Predicții**.</span><span class="sxs-lookup"><span data-stu-id="3b374-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="3b374-164">Editați o predicție</span><span class="sxs-lookup"><span data-stu-id="3b374-164">Edit a prediction</span></span>

<span data-ttu-id="3b374-165">După ce ați creat o predicție, puteți particulariza modelul în AI Builder pentru a mări eficacitatea modelului dvs.</span><span class="sxs-lookup"><span data-stu-id="3b374-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="3b374-166">În Detalii despre public, accesați **Informații** > **Predicții** > **Predicțiile mele**.</span><span class="sxs-lookup"><span data-stu-id="3b374-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="3b374-167">Selectați predicția pe care doriți să o editați.</span><span class="sxs-lookup"><span data-stu-id="3b374-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="3b374-168">Selectați cele trei puncte de suspensie din coloana **Acțiuni** și alegeți **Vizualizare**.</span><span class="sxs-lookup"><span data-stu-id="3b374-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="3b374-169">Selectați **Particularizare în AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="3b374-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="3b374-170">Actualizați-vă modelul în AI Builder.</span><span class="sxs-lookup"><span data-stu-id="3b374-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="3b374-171">[Aflați mai multe despre gestionarea modelelor din AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="3b374-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="3b374-172">Următoarea execuție a predicției dvs. va utiliza modelul actualizat pe care l-ați creat.</span><span class="sxs-lookup"><span data-stu-id="3b374-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="3b374-173">Noile modele create în AI Builder nu vor fi afișate în detaliile despre public decât dacă modelul a fost creat din experiențele enumerate mai sus.</span><span class="sxs-lookup"><span data-stu-id="3b374-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="3b374-174">Eliminați o predicție</span><span class="sxs-lookup"><span data-stu-id="3b374-174">Remove a prediction</span></span>

1. <span data-ttu-id="3b374-175">În Detalii despre public, accesați **Informații** > **Predicții** > **Predicțiile mele**.</span><span class="sxs-lookup"><span data-stu-id="3b374-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="3b374-176">Selectați predicția pe care doriți să o ștergeți.</span><span class="sxs-lookup"><span data-stu-id="3b374-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="3b374-177">Selectați cele trei puncte de suspensie din coloana **Acțiuni** și alegeți **Ștergere**.</span><span class="sxs-lookup"><span data-stu-id="3b374-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="3b374-178">Confirmați ștergerea.</span><span class="sxs-lookup"><span data-stu-id="3b374-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="3b374-179">Depanare</span><span class="sxs-lookup"><span data-stu-id="3b374-179">Troubleshooting</span></span>

<span data-ttu-id="3b374-180">Dacă nu puteți completa procesul Common Data Service atașat din cauza unei erori, puteți încerca să finalizați procesul manual.</span><span class="sxs-lookup"><span data-stu-id="3b374-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="3b374-181">Există două probleme cunoscute care pot apărea în procesul de atașare:</span><span class="sxs-lookup"><span data-stu-id="3b374-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="3b374-182">Soluția de completare a cardului pentru clienți nu este instalată.</span><span class="sxs-lookup"><span data-stu-id="3b374-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="3b374-183">Completați instrucțiunile pentru a [instala și configura soluția](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="3b374-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="3b374-184">Permisiunile pentru aplicații nu sunt acordate.</span><span class="sxs-lookup"><span data-stu-id="3b374-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="3b374-185">Salt la [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="3b374-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="3b374-186">Selectați **Medii**.</span><span class="sxs-lookup"><span data-stu-id="3b374-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="3b374-187">Selectați elipsele de lângă mediul în care doriți să adăugați permisiunea și selectați **Setări**.</span><span class="sxs-lookup"><span data-stu-id="3b374-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="3b374-188">Extindeți **Utilizatori + permisiuni** și selectați **Utilizatori**.</span><span class="sxs-lookup"><span data-stu-id="3b374-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="3b374-189">Selectați **Nou** și selectați **Utilizator**.</span><span class="sxs-lookup"><span data-stu-id="3b374-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="3b374-190">Selectați **Utilizator aplicație** dacă nu este deja selectat și introduceți următoarele informații:</span><span class="sxs-lookup"><span data-stu-id="3b374-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="3b374-191">**Nume de utilizator:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3b374-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="3b374-192">**ID aplicație:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="3b374-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="3b374-193">**Prenumele:** clientului</span><span class="sxs-lookup"><span data-stu-id="3b374-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="3b374-194">**Nume de familie:** Insights</span><span class="sxs-lookup"><span data-stu-id="3b374-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="3b374-195">**E-mail principal:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3b374-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="3b374-196">Selectați **Salvare și închidere**.</span><span class="sxs-lookup"><span data-stu-id="3b374-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="3b374-197">Selectați utilizatorul pe care tocmai l-ați creat.</span><span class="sxs-lookup"><span data-stu-id="3b374-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="3b374-198">Selectați din bara de sus a meniului **Gestionați rolurile**.</span><span class="sxs-lookup"><span data-stu-id="3b374-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="3b374-199">Selectați **Administrator de sistem**, apoi selectați **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b374-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]