---
title: Îmbogățire cu îmbogățiri terță parte Experian
description: Informații generale despre îmbogățirea terță parte Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896388"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="3b33f-103">Îmbogățirea profilurilor clienților cu date demografice de la Experian (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="3b33f-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="3b33f-104">Experian este lider global în raportarea creditelor pentru consumatori și afaceri și servicii de marketing.</span><span class="sxs-lookup"><span data-stu-id="3b33f-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="3b33f-105">Cu Serviciile de îmbogățire a datelor Experian, puteți construi o înțelegere mai profundă a clienților dvs. îmbogățind profilurile clienților cu date demografice, cum ar fi dimensiunea gospodăriei, veniturile și multe altele.</span><span class="sxs-lookup"><span data-stu-id="3b33f-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3b33f-106">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="3b33f-106">Prerequisites</span></span>

<span data-ttu-id="3b33f-107">Pentru a configura Experian, trebuie îndeplinite următoarele condiții prealabile:</span><span class="sxs-lookup"><span data-stu-id="3b33f-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="3b33f-108">Aveți un abonament Experian activ.</span><span class="sxs-lookup"><span data-stu-id="3b33f-108">You have an active Experian subscription.</span></span> <span data-ttu-id="3b33f-109">Pentru a obține un abonament, [contactați Experian](https://www.experian.com/marketing-services/contact) direct.</span><span class="sxs-lookup"><span data-stu-id="3b33f-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="3b33f-110">[Aflați mai multe despre îmbogățirea datelor Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="3b33f-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="3b33f-111">O conexiune Experian a fost deja configurată de un administrator *sau* aveți permisiuni de [administrator](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="3b33f-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="3b33f-112">De asemenea, aveți nevoie de ID de utilizator, ID parte și numărul de model pentru contul dvs. de transport securizat (ST) activat SSH creat de Experian pentru dvs.</span><span class="sxs-lookup"><span data-stu-id="3b33f-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="3b33f-113">Configurați îmbogățirea</span><span class="sxs-lookup"><span data-stu-id="3b33f-113">Configure the enrichment</span></span>

1. <span data-ttu-id="3b33f-114">Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**.</span><span class="sxs-lookup"><span data-stu-id="3b33f-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="3b33f-115">Selectați **Doresc îmbogățirea datelor** din dala Experian.</span><span class="sxs-lookup"><span data-stu-id="3b33f-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3b33f-116">![Dală Experian](media/experian-tile.png "Dală Experian")</span><span class="sxs-lookup"><span data-stu-id="3b33f-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="3b33f-117">Selectați o [conexiune](connections.md) din lista verticală.</span><span class="sxs-lookup"><span data-stu-id="3b33f-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="3b33f-118">Contactați un administrator dacă nu este disponibilă nicio conexiune.</span><span class="sxs-lookup"><span data-stu-id="3b33f-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="3b33f-119">Dacă sunteți administrator, puteți crea o conexiune selectând **Adăugați conexiune** și alegând Experian din meniul cu lista verticală.</span><span class="sxs-lookup"><span data-stu-id="3b33f-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="3b33f-120">Selectați **Conectați-vă la Experian** pentru a confirma alegerea.</span><span class="sxs-lookup"><span data-stu-id="3b33f-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="3b33f-121">Selectați **Următorul** și alegeți **Set de date client** pe care doriți să le îmbogățiți cu date demografice de la Experian.</span><span class="sxs-lookup"><span data-stu-id="3b33f-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="3b33f-122">Puteți selecta entitatea **Client** pentru a vă îmbogăți toate profilurile de clienți sau selectați o entitate de segment pentru a îmbogăți numai profilurile de clienți din acel segment.</span><span class="sxs-lookup"><span data-stu-id="3b33f-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captură de ecran atunci când alegeți setul de date pentru clienți.":::

1. <span data-ttu-id="3b33f-124">Selectați **Următorul** și definiți ce tip de câmpuri din profilurile dvs. unificate ar trebui să fie utilizate pentru a căuta date demografice potrivite de la Experian.</span><span class="sxs-lookup"><span data-stu-id="3b33f-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="3b33f-125">Cel puțin unul dintre câmpurile **Numele și adresa**, **Telefon** sau **E-mail** este necesar.</span><span class="sxs-lookup"><span data-stu-id="3b33f-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="3b33f-126">Pentru o acuratețe mai mare a potrivirii, pot fi adăugate până la alte două câmpuri.</span><span class="sxs-lookup"><span data-stu-id="3b33f-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="3b33f-127">Această selecție va afecta câmpurile de mapare la care aveți acces în pasul următor.</span><span class="sxs-lookup"><span data-stu-id="3b33f-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="3b33f-128">Mai multe atribute de identificare cheie trimise către Experian generează probabil o rată de potrivire mai mare.</span><span class="sxs-lookup"><span data-stu-id="3b33f-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="3b33f-129">Selectați **Următorul** pentru a începe maparea câmpului.</span><span class="sxs-lookup"><span data-stu-id="3b33f-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="3b33f-130">Definiți câmpurile din profilurile dvs. unificate care ar trebui să fie utilizate pentru a căuta date demografice potrivite de la Experian.</span><span class="sxs-lookup"><span data-stu-id="3b33f-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="3b33f-131">Câmpurile obligatorii sunt marcate.</span><span class="sxs-lookup"><span data-stu-id="3b33f-131">Required fields are marked.</span></span>

1. <span data-ttu-id="3b33f-132">Furnizați un nume pentru îmbogățire și un nume pentru entitatea de ieșire.</span><span class="sxs-lookup"><span data-stu-id="3b33f-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="3b33f-133">Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.</span><span class="sxs-lookup"><span data-stu-id="3b33f-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="3b33f-134">Configurați conexiunea pentru Experian</span><span class="sxs-lookup"><span data-stu-id="3b33f-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="3b33f-135">Trebuie să fiți administrator pentru a configura conexiunile.</span><span class="sxs-lookup"><span data-stu-id="3b33f-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="3b33f-136">Selectați **Adăugați conexiune** la configurarea unei îmbogățiri *sau* mergeți la **Administrator** > **Conexiuni** și selectați **Configurare** pe dala Experian.</span><span class="sxs-lookup"><span data-stu-id="3b33f-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="3b33f-137">Selectați **Începeți lucrul**.</span><span class="sxs-lookup"><span data-stu-id="3b33f-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="3b33f-138">Introduceți un nume pentru conexiune în caseta **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="3b33f-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="3b33f-139">Introduceți ID de utilizator, ID parte și număr de model valid pentru contul dvs. de transport securizat Experian.</span><span class="sxs-lookup"><span data-stu-id="3b33f-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="3b33f-140">Analizați și acordați-vă consimțământul pentru **Confidențialitatea și conformitatea datelor** prin selectarea casetei de selectare **De acord**</span><span class="sxs-lookup"><span data-stu-id="3b33f-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="3b33f-141">Selectați **Verificare** pentru a valida configurația.</span><span class="sxs-lookup"><span data-stu-id="3b33f-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="3b33f-142">După finalizarea verificării, selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="3b33f-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Panoul de configurare a conexiunii Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="3b33f-144">Rezultate de îmbogățire</span><span class="sxs-lookup"><span data-stu-id="3b33f-144">Enrichment results</span></span>

<span data-ttu-id="3b33f-145">Pentru a începe procesul de îmbogățire, selectați **Rulare** din bara de comenzi.</span><span class="sxs-lookup"><span data-stu-id="3b33f-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="3b33f-146">De asemenea, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei [reîmprospătări programate](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3b33f-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3b33f-147">Timpul de procesare va depinde de mărimea datelor clienților dvs. și de procesele de îmbogățire stabilite pentru contul dvs. de Experian.</span><span class="sxs-lookup"><span data-stu-id="3b33f-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="3b33f-148">După finalizarea procesului de îmbogățire, puteți consulta datele din profilurile clienților nou îmbogățite din **Îmbogățirile mele**.</span><span class="sxs-lookup"><span data-stu-id="3b33f-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="3b33f-149">În plus, veți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.</span><span class="sxs-lookup"><span data-stu-id="3b33f-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="3b33f-150">Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.</span><span class="sxs-lookup"><span data-stu-id="3b33f-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3b33f-151">Pașii următori</span><span class="sxs-lookup"><span data-stu-id="3b33f-151">Next steps</span></span>

<span data-ttu-id="3b33f-152">Creați în plus față de datele îmbogățite ale clienților.</span><span class="sxs-lookup"><span data-stu-id="3b33f-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="3b33f-153">Creați [segmente](segments.md), [măsuri](measures.md) și chiar [exportați datele](export-destinations.md) pentru a oferi experiențe personalizate clienților.</span><span class="sxs-lookup"><span data-stu-id="3b33f-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3b33f-154">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="3b33f-154">Data privacy and compliance</span></span>

<span data-ttu-id="3b33f-155">Când activați Dynamics 365 Customer Insights pentru a transmite date către Experian, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="3b33f-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3b33f-156">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Experian îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="3b33f-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3b33f-157">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3b33f-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3b33f-158">Administratorul Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="3b33f-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
