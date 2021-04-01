---
title: Găsiți clienți similari cu AI
description: Găsiți segmente de clienți similare cu inteligență artificială.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f588f45ed11efffbb335003642a4b92810153017
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596790"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="00ec2-103">Clienți similari (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="00ec2-103">Similar Customers (preview)</span></span>

<span data-ttu-id="00ec2-104">Această caracteristică vă permite să găsiți clienți similari în baza de clienți utilizând inteligența artificială.</span><span class="sxs-lookup"><span data-stu-id="00ec2-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="00ec2-105">Trebuie să aveți cel puțin un segment creat pentru a utiliza această caracteristică.</span><span class="sxs-lookup"><span data-stu-id="00ec2-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="00ec2-106">Extinderea criteriilor unui segment existent vă ajută să găsiți clienți similari cu acel segment.</span><span class="sxs-lookup"><span data-stu-id="00ec2-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="00ec2-107">*Găsiți clienți similari* utilizează mijloace automate pentru a evalua datele și a face predicții pe baza acestor date și, prin urmare, are capacitatea de a fi utilizat ca metodă de profilare, deoarece acest termen este definit prin Regulamentul general privind protecția datelor („GDPR”).</span><span class="sxs-lookup"><span data-stu-id="00ec2-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="00ec2-108">Utilizarea acestei funcții de către client pentru prelucrarea datelor poate fi supusă RGPD sau altor legi sau reglementări.</span><span class="sxs-lookup"><span data-stu-id="00ec2-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="00ec2-109">Sunteți responsabil pentru a vă asigura că utilizarea de către dvs. a Dynamics 365 Customer Insights, inclusiv predicțiile, respectă toate legile și reglementările aplicabile, inclusiv legile legate de confidențialitate, date cu caracter personal, date biometrice, protecția datelor și confidențialitatea comunicărilor.</span><span class="sxs-lookup"><span data-stu-id="00ec2-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="00ec2-110">Găsirea unor clienți similari</span><span class="sxs-lookup"><span data-stu-id="00ec2-110">Finding similar customers</span></span>

1. <span data-ttu-id="00ec2-111">În Detalii despre audiență, accesați **Segmente** și selectați segmentul pe care doriți să vă bazați noul segment.</span><span class="sxs-lookup"><span data-stu-id="00ec2-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="00ec2-112">Acesta este *segmentul sursă* al dvs.</span><span class="sxs-lookup"><span data-stu-id="00ec2-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="00ec2-113">În bara de acțiuni, selectați **Găsiți clienți similari**.</span><span class="sxs-lookup"><span data-stu-id="00ec2-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="00ec2-114">Examinați numele sugerat pentru noul segment și schimbați-l dacă este necesar.</span><span class="sxs-lookup"><span data-stu-id="00ec2-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="00ec2-115">Examinați câmpurile care definesc noul dvs. segment.</span><span class="sxs-lookup"><span data-stu-id="00ec2-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="00ec2-116">Aceste câmpuri definesc baza pe care sistemul va încerca să găsească clienți similari cu segmentul dvs. sursă.</span><span class="sxs-lookup"><span data-stu-id="00ec2-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="00ec2-117">În mod implicit, sistemul va selecta câmpurile recomandate.</span><span class="sxs-lookup"><span data-stu-id="00ec2-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="00ec2-118">Câmpurile care pot reduce semnificativ performanța modelului sunt excluse automat:</span><span class="sxs-lookup"><span data-stu-id="00ec2-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="00ec2-119">Câmpuri cu următoarele tipuri de date: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="00ec2-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="00ec2-120">Câmpuri cu o cardinalitate (numărul de elemente dintr-un câmp) mai mică de 2 sau mai mare de 30</span><span class="sxs-lookup"><span data-stu-id="00ec2-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="00ec2-121">Alegeți dacă doriți să includeți **Toți clienții** sau numai clienții dintr-un **Segment specific existent** în noul dvs. segment.</span><span class="sxs-lookup"><span data-stu-id="00ec2-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="00ec2-122">Excludeți clienții din segmentul sursă selectând caseta de selectare **Excludeți pe toți din segmentul sursă**.</span><span class="sxs-lookup"><span data-stu-id="00ec2-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="00ec2-123">În mod implicit, sistemul sugerează să includeți doar 20% din mărimea publicului țintă în rezultatul dvs.</span><span class="sxs-lookup"><span data-stu-id="00ec2-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="00ec2-124">Editați acest prag în funcție de necesități.</span><span class="sxs-lookup"><span data-stu-id="00ec2-124">Edit this threshold as needed.</span></span> <span data-ttu-id="00ec2-125">Creșterea pragului va reduce precizia.</span><span class="sxs-lookup"><span data-stu-id="00ec2-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="00ec2-126">Selectați **Rulează** în partea de jos a paginii pentru a începe o sarcină de clasificare binară (o metodă a învățare programată) care analizează setul de date.</span><span class="sxs-lookup"><span data-stu-id="00ec2-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="00ec2-127">Vizualizați segmentul similar</span><span class="sxs-lookup"><span data-stu-id="00ec2-127">View the similar segment</span></span>

<span data-ttu-id="00ec2-128">După procesarea segmentului similar, veți găsi noul segment listat pe pagina **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="00ec2-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="00ec2-129">![Segment de clienți similar](media/expanded-segment.png "Segment de clienți similar")</span><span class="sxs-lookup"><span data-stu-id="00ec2-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="00ec2-130">Selectați **Vizualizare** în bara de acțiuni pentru a deschide detaliile segmentului.</span><span class="sxs-lookup"><span data-stu-id="00ec2-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="00ec2-131">Această vizualizare conține informații despre distribuția rezultatelor în cadrul [scorurilor de similaritate](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="00ec2-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="00ec2-132">De asemenea, veți găsi valorile scorului de similaritate în **Previzualizarea membrilor segmentului**.</span><span class="sxs-lookup"><span data-stu-id="00ec2-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="00ec2-133">Utilizați rezultatul unui segment similar</span><span class="sxs-lookup"><span data-stu-id="00ec2-133">Use the output of a similar segment</span></span>

<span data-ttu-id="00ec2-134">Puteți [lucra cu rezultatul unui segment similar](segments.md) așa cum faceți cu alte segmente.</span><span class="sxs-lookup"><span data-stu-id="00ec2-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="00ec2-135">De exemplu, exportați segmentul sau construiți o măsură.</span><span class="sxs-lookup"><span data-stu-id="00ec2-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="00ec2-136">Reîmprospătați și editați un segment similar</span><span class="sxs-lookup"><span data-stu-id="00ec2-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="00ec2-137">Pentru a reîmprospăta un segment similar, selectați-l pe pagina **Segmente** și selectați **Reîmprospătare** în bara de acțiune.</span><span class="sxs-lookup"><span data-stu-id="00ec2-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="00ec2-138">Editarea unui segment similar va reprocesa datele dumneavoastră.</span><span class="sxs-lookup"><span data-stu-id="00ec2-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="00ec2-139">Segmentul creat anterior este actualizat cu datele reîmprospătate.</span><span class="sxs-lookup"><span data-stu-id="00ec2-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="00ec2-140">Pentru a edita un segment similar, selectați-l pe pagina **Segmente** și selectați **Editare** în bara de acțiune.</span><span class="sxs-lookup"><span data-stu-id="00ec2-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="00ec2-141">Aplicați modificările și selectați **Rulează** pentru a începe procesarea.</span><span class="sxs-lookup"><span data-stu-id="00ec2-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="00ec2-142">Ștergeți un segment similar</span><span class="sxs-lookup"><span data-stu-id="00ec2-142">Delete a similar segment</span></span>

<span data-ttu-id="00ec2-143">Selectați segmentul de pe pagina **Segmente** și selectați **Ștergeți** în bara de acțiune.</span><span class="sxs-lookup"><span data-stu-id="00ec2-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="00ec2-144">Apoi, confirmați ștergerea.</span><span class="sxs-lookup"><span data-stu-id="00ec2-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="00ec2-145">Despre scoruri de similaritate</span><span class="sxs-lookup"><span data-stu-id="00ec2-145">About similarity scores</span></span>

<span data-ttu-id="00ec2-146">Modelul învățare programată a clasificării binare atribuie un scor clienților din segmentul similar.</span><span class="sxs-lookup"><span data-stu-id="00ec2-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="00ec2-147">Scorul se bazează pe similaritatea cu clienții din segmentul sursă.</span><span class="sxs-lookup"><span data-stu-id="00ec2-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="00ec2-148">Scorurile de similaritate sub 0,55 cuprinde clienții din sistemul clasificat ca *nesimilar* al clienților din segmentul sursă</span><span class="sxs-lookup"><span data-stu-id="00ec2-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="00ec2-149">Scorurile de similaritate între 0,55 - 0,7 sunt clasificate ca fiind *oarecum similar*</span><span class="sxs-lookup"><span data-stu-id="00ec2-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="00ec2-150">Scorurile de similaritate între 0,7 - 0,85 sunt clasificate ca fiind *similar*</span><span class="sxs-lookup"><span data-stu-id="00ec2-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="00ec2-151">Scorurile de similaritate între 0,85 - 1 sunt clienții pe care sistemul îi clasifică drept *foarte similari*</span><span class="sxs-lookup"><span data-stu-id="00ec2-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="00ec2-152">Clienții cu scoruri de similaritate sub 0,4 nu sunt incluși în rezultatul modelului.</span><span class="sxs-lookup"><span data-stu-id="00ec2-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="00ec2-153">Sistemul nu îi consideră suficient de similari cu segmentul sursă.</span><span class="sxs-lookup"><span data-stu-id="00ec2-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]