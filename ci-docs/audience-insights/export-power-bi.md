---
title: Conector Power BI
description: Aflați cum să utilizați conectorul Dynamics 365 Customer Insights în Power BI.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596054"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="26199-103">Conector pentru Power BI (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="26199-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="26199-104">Creați vizualizări pentru datele dvs. cu Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="26199-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="26199-105">Generați informații suplimentare și creați rapoarte cu datele clientului dvs. unificate.</span><span class="sxs-lookup"><span data-stu-id="26199-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="26199-106">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="26199-106">Prerequisites</span></span>

- <span data-ttu-id="26199-107">Aveți profiluri de clienți unificate.</span><span class="sxs-lookup"><span data-stu-id="26199-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="26199-108">Cea mai recentă versiune de [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) este instalată pe computer.</span><span class="sxs-lookup"><span data-stu-id="26199-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="26199-109">[Aflați mai multe despre Power BI Desktop](/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="26199-109">[Learn more about Power BI Desktop](/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="26199-110">Configurați conectorul pentru Power BI</span><span class="sxs-lookup"><span data-stu-id="26199-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="26199-111">În Power BI Desktop, selectați **Fișier** > **Preluare date**.</span><span class="sxs-lookup"><span data-stu-id="26199-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="26199-112">Selectați **Vedeți mai multe** și căutați **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="26199-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="26199-113">Selectați **Conectare**.</span><span class="sxs-lookup"><span data-stu-id="26199-113">Select **Connect**.</span></span>

1. <span data-ttu-id="26199-114">**Conectați-vă** cu același cont organizațional pe care îl utilizați pentru Customer Insights și selectați **Conectare**.</span><span class="sxs-lookup"><span data-stu-id="26199-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="26199-115">Contul pe care îl indicați în acest pas este utilizat pentru a prelua date de la Customer Insights și nu trebuie să fie același cu cel la care sunteți conectat în Power BI.</span><span class="sxs-lookup"><span data-stu-id="26199-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="26199-116">Pentru a reseta contul utilizat pentru preluarea datelor, deschideți Power BI și accesați **Fișier** > **Opțiuni** > **Setări** > **Setări sursă de date**.</span><span class="sxs-lookup"><span data-stu-id="26199-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="26199-117">În lista de surse de date, selectați **Dynamics 365 Customer Insights Autentificare** și selectați **Ștergere permisiuni**.</span><span class="sxs-lookup"><span data-stu-id="26199-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="26199-118">În caseta de dialog **Navigator**.</span><span class="sxs-lookup"><span data-stu-id="26199-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="26199-119">Veți vedea lista tuturor mediilor la care aveți acces.</span><span class="sxs-lookup"><span data-stu-id="26199-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="26199-120">Extindeți un mediu și deschideți oricare dintre directoare (entități, măsuri, segmente, îmbogățiri).</span><span class="sxs-lookup"><span data-stu-id="26199-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="26199-121">De exemplu, deschideți folderul **Entități**, pentru a vedea toate entitățile pe care le puteți importa.</span><span class="sxs-lookup"><span data-stu-id="26199-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="26199-122">![Power BI Conector Navigator](media/power-bi-navigator.png "Conector Navigator Power BI")</span><span class="sxs-lookup"><span data-stu-id="26199-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="26199-123">Selectați casetele de selectare de lângă entitățile pe care să le includeți și **Încărcare**.</span><span class="sxs-lookup"><span data-stu-id="26199-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="26199-124">Puteți selecta mai multe entități din mai multe medii.</span><span class="sxs-lookup"><span data-stu-id="26199-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="26199-125">Veți vedea o casetă de dialog de încărcare în timp ce sunt încărcate entitățile dvs.</span><span class="sxs-lookup"><span data-stu-id="26199-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="26199-126">Odată ce toate entitățile dvs. selectate s-au încărcat, puteți utiliza capacitățile Power BI pentru a vizualiza datele.</span><span class="sxs-lookup"><span data-stu-id="26199-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="26199-127">Seturi mari de date</span><span class="sxs-lookup"><span data-stu-id="26199-127">Large data sets</span></span>

<span data-ttu-id="26199-128">Conectorul Customer Insights pentru Power BI este proiectat pentru a funcționa pentru seturi de date care conțin până la 1 milion de profiluri de clienți.</span><span class="sxs-lookup"><span data-stu-id="26199-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="26199-129">Importul seturilor de date mai mari poate funcționa, dar durează mult.</span><span class="sxs-lookup"><span data-stu-id="26199-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="26199-130">În plus, procesul ar putea rula într-un time-out din cauza limitărilor Power BI.</span><span class="sxs-lookup"><span data-stu-id="26199-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="26199-131">Pentru mai multe informații, consultați [Power BI : Recomandări pentru seturi mari de date](/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="26199-131">For more information, see [Power BI: Recommendations for large data sets](/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="26199-132">Lucrați cu un subset de date</span><span class="sxs-lookup"><span data-stu-id="26199-132">Work with a subset of data</span></span>

<span data-ttu-id="26199-133">Luați în considerare lucrul cu un subset de date.</span><span class="sxs-lookup"><span data-stu-id="26199-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="26199-134">De exemplu, puteți crea [segmente](segments.md) în loc să exportați toate înregistrările clienților către Power BI.</span><span class="sxs-lookup"><span data-stu-id="26199-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="26199-135">Depanare</span><span class="sxs-lookup"><span data-stu-id="26199-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="26199-136">Mediul Customer Insights nu apare în Power BI</span><span class="sxs-lookup"><span data-stu-id="26199-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="26199-137">Medii care au mai mult de o [relaţie](relationships.md) definită între două entități identice în statistici privind publicul nu vor fi disponibile în conectorul Power BI.</span><span class="sxs-lookup"><span data-stu-id="26199-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="26199-138">Puteți identifica și elimina relațiile duplicate.</span><span class="sxs-lookup"><span data-stu-id="26199-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="26199-139">În statisticile publicului, accesați **Date** > **Relații** asupra mediului care vă lipsește în Power BI.</span><span class="sxs-lookup"><span data-stu-id="26199-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="26199-140">Identificați relațiile duplicate:</span><span class="sxs-lookup"><span data-stu-id="26199-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="26199-141">Verificați dacă există mai multe relații definite între aceleași două entități.</span><span class="sxs-lookup"><span data-stu-id="26199-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="26199-142">Verificați dacă există o relație creată între două entități care sunt ambele incluse în procesul de unificare.</span><span class="sxs-lookup"><span data-stu-id="26199-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="26199-143">Există o relație implicită definită între toate entitățile incluse în procesul de unificare.</span><span class="sxs-lookup"><span data-stu-id="26199-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="26199-144">Eliminați orice relație duplicat identificată.</span><span class="sxs-lookup"><span data-stu-id="26199-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="26199-145">După eliminarea relațiilor duplicate, încercați să configurați conectorul Power BI din nou.</span><span class="sxs-lookup"><span data-stu-id="26199-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="26199-146">Mediul ar trebui să fie disponibil acum.</span><span class="sxs-lookup"><span data-stu-id="26199-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]