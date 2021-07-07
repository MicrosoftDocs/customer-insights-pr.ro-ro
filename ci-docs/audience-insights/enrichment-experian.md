---
title: Îmbogățire cu îmbogățire de terță parte Experian
description: Informații generale despre îmbogățire de terță parte Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309835"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="c492a-103">Îmbogățiți profilurile clienților cu date demografice din Experian (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="c492a-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="c492a-104">Experian este un lider global în raportarea creditelor de consum și de afaceri și servicii de marketing.</span><span class="sxs-lookup"><span data-stu-id="c492a-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="c492a-105">Cu serviciile Experian de îmbogățire a datelor, puteți construi o înțelegere mai profundă a clienților dvs. îmbogățind profilurile clienților cu date demografice, cum ar fi dimensiunea gospodăriei, veniturile și multe altele.</span><span class="sxs-lookup"><span data-stu-id="c492a-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c492a-106">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="c492a-106">Prerequisites</span></span>

<span data-ttu-id="c492a-107">Pentru a configura Experian, trebuie îndeplinite următoarele condiții prealabile:</span><span class="sxs-lookup"><span data-stu-id="c492a-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="c492a-108">Trebuie să aveți un abonament activ la Experian.</span><span class="sxs-lookup"><span data-stu-id="c492a-108">You have an active Experian subscription.</span></span> <span data-ttu-id="c492a-109">Pentru a obține un abonament, [contactați Experian](https://www.experian.com/marketing-services/contact) direct.</span><span class="sxs-lookup"><span data-stu-id="c492a-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="c492a-110">[Aflați mai multe desore Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="c492a-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="c492a-111">O conexiune Experian a fost deja configurată de un administrator *sau* aveți permisiuni de [administrator](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="c492a-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="c492a-112">De asemenea, aveți nevoie de ID-ul de utilizator, ID-ul de parte și numărul de model pentru contul dvs. de transport securizat (ST) activat SSH care a fost Experian creat pentru dvs.</span><span class="sxs-lookup"><span data-stu-id="c492a-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="c492a-113">Țări / regiuni acceptate</span><span class="sxs-lookup"><span data-stu-id="c492a-113">Supported countries/regions</span></span>

<span data-ttu-id="c492a-114">În prezent, acceptăm îmbogățirea profilurilor clienților numai în Statele Unite.</span><span class="sxs-lookup"><span data-stu-id="c492a-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="c492a-115">Configurați îmbogățirea</span><span class="sxs-lookup"><span data-stu-id="c492a-115">Configure the enrichment</span></span>

1. <span data-ttu-id="c492a-116">Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**.</span><span class="sxs-lookup"><span data-stu-id="c492a-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="c492a-117">Selectați **Îmbogățește datele mele** pe dala Experian.</span><span class="sxs-lookup"><span data-stu-id="c492a-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c492a-118">![dala Experian](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="c492a-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="c492a-119">Selectați o [conexiune](connections.md) din lista derulantă.</span><span class="sxs-lookup"><span data-stu-id="c492a-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="c492a-120">Contactați un administrator dacă nu este disponibilă nicio conexiune.</span><span class="sxs-lookup"><span data-stu-id="c492a-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="c492a-121">Dacă sunteți administrator, puteți crea o conexiune selectând **Adăugați conexiune** și alegând Experian din lista derulantă.</span><span class="sxs-lookup"><span data-stu-id="c492a-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="c492a-122">Selectați **Conectați-vă la Experian** pentru a confirma selectarea conexiunii.</span><span class="sxs-lookup"><span data-stu-id="c492a-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="c492a-123">Selectați **Următorul** și alegeți **Set de date client** doriți să vă îmbogățiți cu date demografice din Experian.</span><span class="sxs-lookup"><span data-stu-id="c492a-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="c492a-124">Puteți selecta entitatea **Client** pentru a vă îmbogăți toate profilurile de clienți sau selectați o entitate de segment pentru a îmbogăți numai profilurile de clienți din acel segment.</span><span class="sxs-lookup"><span data-stu-id="c492a-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captură de ecran atunci când alegeți setul de date pentru clienți.":::

1. <span data-ttu-id="c492a-126">Selectați **Următorul** și definiți din ce tip de câmpuri din profilurile dvs. unificate trebuie utilizat pentru a căuta date demografice potrivite din Experian.</span><span class="sxs-lookup"><span data-stu-id="c492a-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="c492a-127">Cel puțin unul dintre câmpurile **Numele și adresa**, **Telefon** sau **E-mail** este necesar.</span><span class="sxs-lookup"><span data-stu-id="c492a-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="c492a-128">Pentru o acuratețe mai mare a potrivirii, pot fi adăugate până la alte două câmpuri.</span><span class="sxs-lookup"><span data-stu-id="c492a-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="c492a-129">Această selecție va afecta câmpurile de mapare la care aveți acces în pasul următor.</span><span class="sxs-lookup"><span data-stu-id="c492a-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="c492a-130">Mai multe atribute de identificare cheie trimise către Experian probabil va produce o rată de potrivire mai mare.</span><span class="sxs-lookup"><span data-stu-id="c492a-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="c492a-131">Selectați **Următorul** pentru a începe maparea câmpului.</span><span class="sxs-lookup"><span data-stu-id="c492a-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="c492a-132">Definiți care câmpuri din profilurile dvs. unificate ar trebui utilizate pentru a căuta date demografice potrivite din Experian.</span><span class="sxs-lookup"><span data-stu-id="c492a-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="c492a-133">Câmpurile obligatorii sunt marcate.</span><span class="sxs-lookup"><span data-stu-id="c492a-133">Required fields are marked.</span></span>

1. <span data-ttu-id="c492a-134">Furnizați un nume pentru îmbogățire și un nume pentru entitatea de ieșire.</span><span class="sxs-lookup"><span data-stu-id="c492a-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="c492a-135">Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.</span><span class="sxs-lookup"><span data-stu-id="c492a-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="c492a-136">Configurați conexiunea pentru Experian</span><span class="sxs-lookup"><span data-stu-id="c492a-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="c492a-137">Trebuie să fiți administrator pentru a configura conexiunile.</span><span class="sxs-lookup"><span data-stu-id="c492a-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="c492a-138">Selectați **Adăugați conexiune** la configurarea unei îmbogățiri *sau* accesați **Administrator** > **Conexiuni** și selectați **Configurat** pe dala Experian.</span><span class="sxs-lookup"><span data-stu-id="c492a-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="c492a-139">Selectați **Începeți lucrul**.</span><span class="sxs-lookup"><span data-stu-id="c492a-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="c492a-140">Introduceți un nume pentru conexiune în caseta **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="c492a-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="c492a-141">Introduceți un ID de utilizator, un ID de parte și un număr de model valide pentru contul dvs. Experian de transport securizat.</span><span class="sxs-lookup"><span data-stu-id="c492a-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="c492a-142">Examinați și furnizați consimțământul pentru **Confidențialitatea și respectarea datelor** prin selectarea **Sunt de acord**.</span><span class="sxs-lookup"><span data-stu-id="c492a-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="c492a-143">Selectați **Verificare** pentru a valida configurația.</span><span class="sxs-lookup"><span data-stu-id="c492a-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="c492a-144">După finalizarea verificării, selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="c492a-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian panou de configurare a conexiunii.":::

## <a name="enrichment-results"></a><span data-ttu-id="c492a-146">Rezultate de îmbogățire</span><span class="sxs-lookup"><span data-stu-id="c492a-146">Enrichment results</span></span>

<span data-ttu-id="c492a-147">Pentru a începe procesul de îmbogățire, selectați **Rulare** din bara de comenzi.</span><span class="sxs-lookup"><span data-stu-id="c492a-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="c492a-148">De asemenea, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei [reîmprospătări programate](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c492a-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c492a-149">Timpul de procesare va depinde de mărimea datelor clienților dvs. și de procesele de îmbogățire stabilite pentru contul dvs. de către Experian.</span><span class="sxs-lookup"><span data-stu-id="c492a-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="c492a-150">După finalizarea procesului de îmbogățire, puteți consulta datele din profilurile clienților nou îmbogățite din **Îmbogățirile mele**.</span><span class="sxs-lookup"><span data-stu-id="c492a-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="c492a-151">În plus, veți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.</span><span class="sxs-lookup"><span data-stu-id="c492a-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="c492a-152">Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.</span><span class="sxs-lookup"><span data-stu-id="c492a-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c492a-153">Pașii următori</span><span class="sxs-lookup"><span data-stu-id="c492a-153">Next steps</span></span>

<span data-ttu-id="c492a-154">Creați în plus față de datele îmbogățite ale clienților.</span><span class="sxs-lookup"><span data-stu-id="c492a-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="c492a-155">Creați [segmente](segments.md) și [măsuri](measures.md), și chiar [exportați datele](export-destinations.md) pentru a oferi clienților dvs. experiențe particularizate.</span><span class="sxs-lookup"><span data-stu-id="c492a-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c492a-156">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="c492a-156">Data privacy and compliance</span></span>

<span data-ttu-id="c492a-157">Când activați Dynamics 365 Customer Insights pentru a transmite date către Experian, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi date cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="c492a-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c492a-158">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru a vă asigura că Experian îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="c492a-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c492a-159">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c492a-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c492a-160">Administratorul dvs. Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="c492a-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
