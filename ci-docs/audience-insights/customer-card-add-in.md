---
title: Aplicații program de completare Card client pentru Dynamics 365
description: Afișați date din detalii privind publicul în aplicațiile Dynamics 365 cu acest supliment.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059603"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="54ec8-103">Program de completare card client (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="54ec8-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="54ec8-104">Obțineți o vizualizare la 360 de grade a clienților dvs. direct în aplicațiile Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="54ec8-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="54ec8-105">Cu programul de completare Card de clienți instalat într-o aplicație Dynamics 365 acceptată, puteți alege să afișați date demografice, detalii și cronologii de activitate.</span><span class="sxs-lookup"><span data-stu-id="54ec8-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="54ec8-106">Programul de completare va prelua date din Customer Insights fără a afecta datele din aplicația Dynamics 365 conectată.</span><span class="sxs-lookup"><span data-stu-id="54ec8-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="54ec8-107">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="54ec8-107">Prerequisites</span></span>

- <span data-ttu-id="54ec8-108">Programul de completare funcționează numai cu aplicații bazate pe model Dynamics 365, cum ar fi Sales sau Customer Service, versiunea 9.0 și versiunile ulterioare.</span><span class="sxs-lookup"><span data-stu-id="54ec8-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="54ec8-109">Pentru ca datele dvs. din Dynamics 365 să se mapeze la profilurile de clienți din detalii despre public, ele trebuie să fie [ingerate din aplicația Dynamics 365 folosind conectorul Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="54ec8-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="54ec8-110">Toți utilizatorii Dynamics 365 ai programului de completare Card client trebuie să fie [adăugați ca utilizatori](permissions.md) în detaliile despre public pentru a vedea datele.</span><span class="sxs-lookup"><span data-stu-id="54ec8-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="54ec8-111">[Sunt necesare capacități de căutare și filtrare configurate](search-filter-index.md) în detaliile despre public pentru ca datele să funcționeze.</span><span class="sxs-lookup"><span data-stu-id="54ec8-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="54ec8-112">Fiecare control de program de completare se bazează pe date specifice din detaliile privind audiența:</span><span class="sxs-lookup"><span data-stu-id="54ec8-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="54ec8-113">Controlul măsurii: Necesită [măsuri configurate](measures.md).</span><span class="sxs-lookup"><span data-stu-id="54ec8-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="54ec8-114">Controlul inteligent: necesită date generate folosind [predicții](predictions.md) sau [modele particularizate](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="54ec8-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="54ec8-115">Control demografic: câmpurile demografice (cum ar fi vârsta sau sexul), sunt disponibile în profilul de client unificat.</span><span class="sxs-lookup"><span data-stu-id="54ec8-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="54ec8-116">Controlul îmbogățirii: necesită [îmbogățiri](enrichment-hub.md) active aplicate profilurilor clienților.</span><span class="sxs-lookup"><span data-stu-id="54ec8-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="54ec8-117">Controlul cronologiei: Necesită [activități configurate](activities.md).</span><span class="sxs-lookup"><span data-stu-id="54ec8-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="54ec8-118">Instalați suplimentul cardului client</span><span class="sxs-lookup"><span data-stu-id="54ec8-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="54ec8-119">Adăugarea programului de completare Card client este o soluție pentru aplicațiile de implicare a clienților din Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="54ec8-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="54ec8-120">Pentru a instala soluția, accesați AppSource și căutați **Card de client Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="54ec8-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="54ec8-121">Selectați [Programul de completare card de client AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) și selectați **Obțineți acum**.</span><span class="sxs-lookup"><span data-stu-id="54ec8-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="54ec8-122">Este posibil să fie nevoie să vă autentificați cu datele dvs. de acreditare pentru aplicația Dynamics 365 pentru a instala soluția.</span><span class="sxs-lookup"><span data-stu-id="54ec8-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="54ec8-123">Poate dura ceva timp pentru ca soluția să fie instalată în mediul dvs.</span><span class="sxs-lookup"><span data-stu-id="54ec8-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="54ec8-124">Configurați programul de completare pentru card client</span><span class="sxs-lookup"><span data-stu-id="54ec8-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="54ec8-125">În calitate de administrator, accesați secțiunea **Setări** din Dynamics 365 și selectați **Soluții**.</span><span class="sxs-lookup"><span data-stu-id="54ec8-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="54ec8-126">Selectați legătura **Nume afișat** pentru soluția **Dynamics 365 Customer Insights Program de completare card client (Previzualizare)**.</span><span class="sxs-lookup"><span data-stu-id="54ec8-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="54ec8-127">![Selectați numele afișat](media/select-display-name.png "Selectați numele afișat")</span><span class="sxs-lookup"><span data-stu-id="54ec8-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="54ec8-128">Selectați **Conectare** și introduceți acreditările pentru contul de administrator pe care îl utilizați pentru a configura Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="54ec8-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="54ec8-129">Verificați dacă funcția de blocare a ferestrelor pop-up a browserului nu blochează fereastra de autentificare atunci când selectați butonul **Conectare**.</span><span class="sxs-lookup"><span data-stu-id="54ec8-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="54ec8-130">Selectați mediul Customer Insights de la care doriți să preluați date.</span><span class="sxs-lookup"><span data-stu-id="54ec8-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="54ec8-131">Definiți maparea de la câmp la înregistrări în aplicația Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="54ec8-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="54ec8-132">În funcție de datele din Customer Insights, puteți alege să mapați următoarele opțiuni:</span><span class="sxs-lookup"><span data-stu-id="54ec8-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="54ec8-133">Pentru a mapa un contact, selectați câmpul din entitatea Client care se potrivește cu ID-ul entității dvs. de contact.</span><span class="sxs-lookup"><span data-stu-id="54ec8-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="54ec8-134">Pentru a mapa un cont, selectați câmpul din entitatea Client care se potrivește cu ID-ul entității dvs. de cont.</span><span class="sxs-lookup"><span data-stu-id="54ec8-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="54ec8-135">![Câmpul ID persoană de contact](media/contact-id-field.png "Câmpul ID persoană de contact")</span><span class="sxs-lookup"><span data-stu-id="54ec8-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="54ec8-136">Selectați **Salvare configurație** pentru a salva setările.</span><span class="sxs-lookup"><span data-stu-id="54ec8-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="54ec8-137">În continuare, trebuie să atribuiți roluri de securitate în Dynamics 365, astfel încât utilizatorii să poată personaliza și vedea cardul de client.</span><span class="sxs-lookup"><span data-stu-id="54ec8-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="54ec8-138">În Dynamics 365, accesați **Setări** > **Securitate** > **Utilizatori**.</span><span class="sxs-lookup"><span data-stu-id="54ec8-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="54ec8-139">Selectați utilizatorii pentru a edita rolurile utilizatorului și selectați **Gestionați roluri**.</span><span class="sxs-lookup"><span data-stu-id="54ec8-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="54ec8-140">Atribuiți rolul **Utilizator standard card Customer Insights** pentru utilizatorii care vor personaliza conținutul afișat pe card pentru întreaga organizație.</span><span class="sxs-lookup"><span data-stu-id="54ec8-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="54ec8-141">Adăugare controale Card client la formulare</span><span class="sxs-lookup"><span data-stu-id="54ec8-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="54ec8-142">Pentru a adăuga controale pentru cardul clientului în formularul dvs. de contact, accesați secțiunea **Setări** > **Particularizări** în Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="54ec8-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="54ec8-143">Selectați **Particularizați sistemul**.</span><span class="sxs-lookup"><span data-stu-id="54ec8-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="54ec8-144">Navigați la entitatea **Persoană de contact**, extindeți-o și selectați **Formulare**.</span><span class="sxs-lookup"><span data-stu-id="54ec8-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="54ec8-145">Selectați formularul de contact la care doriți să adăugați controalele Card client.</span><span class="sxs-lookup"><span data-stu-id="54ec8-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="54ec8-146">![Selectați formularul de contact](media/contact-active-forms.png "Selectați formularul de contact")</span><span class="sxs-lookup"><span data-stu-id="54ec8-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="54ec8-147">Pentru a adăuga un control, în editorul de formulare, trageți orice câmp din **Exploratorul de câmp** în locul în care doriți să apară controlul.</span><span class="sxs-lookup"><span data-stu-id="54ec8-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="54ec8-148">Selectați câmpul pe formularul pe care tocmai l-ați adăugat și selectați **Modificare proprietăți**.</span><span class="sxs-lookup"><span data-stu-id="54ec8-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="54ec8-149">Accesați fila **Controale** și selectați **Adăugare control**.</span><span class="sxs-lookup"><span data-stu-id="54ec8-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="54ec8-150">Alegeți unul dintre controalele particularizate disponibile și selectați **Adăugați**.</span><span class="sxs-lookup"><span data-stu-id="54ec8-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="54ec8-151">În caseta de dialog **Proprietăți câmp**, debifați caseta de selectare **Afișare etichetă pe formular**.</span><span class="sxs-lookup"><span data-stu-id="54ec8-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="54ec8-152">Selectați opțiunea **Web** pentru control.</span><span class="sxs-lookup"><span data-stu-id="54ec8-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="54ec8-153">Pentru controlul Îmbogățire, selectați tipul de îmbogățire pe care doriți să-l afișați configurand câmpul **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="54ec8-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="54ec8-154">Adăugați un control separat de îmbogățire pentru fiecare tip de îmbogățire.</span><span class="sxs-lookup"><span data-stu-id="54ec8-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="54ec8-155">Selectați **Salvați** și **Publicați** pentru a publica formularul de contact actualizat.</span><span class="sxs-lookup"><span data-stu-id="54ec8-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="54ec8-156">Accesați formularul de contact publicat.</span><span class="sxs-lookup"><span data-stu-id="54ec8-156">Go to the published contact form.</span></span> <span data-ttu-id="54ec8-157">Veți vedea controlul nou adăugat.</span><span class="sxs-lookup"><span data-stu-id="54ec8-157">You'll see the newly added control.</span></span> <span data-ttu-id="54ec8-158">Este posibil să fie nevoie să vă conectați, prima dată când îl utilizați.</span><span class="sxs-lookup"><span data-stu-id="54ec8-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="54ec8-159">Pentru a particulariza ceea ce doriți să afișați în controlul particularizat, selectați butonul de editare din colțul din dreapta sus.</span><span class="sxs-lookup"><span data-stu-id="54ec8-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="54ec8-160">Faceți upgrade la programul de completare Customer Card</span><span class="sxs-lookup"><span data-stu-id="54ec8-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="54ec8-161">Programul de completare pentru Customer Card nu se actualizează automat.</span><span class="sxs-lookup"><span data-stu-id="54ec8-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="54ec8-162">Pentru a face upgrade la cea mai recentă versiune, urmați această procedură în aplicația Dynamics 365 care are instalat programul de completare.</span><span class="sxs-lookup"><span data-stu-id="54ec8-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="54ec8-163">În aplicația Dynamics 365, accesați **Setări** > **Particularizare** și selectați **Soluții**.</span><span class="sxs-lookup"><span data-stu-id="54ec8-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="54ec8-164">În tabelul cu programe de completare căutați **CustomerInsightsCustomerCard** și selectați rândul.</span><span class="sxs-lookup"><span data-stu-id="54ec8-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="54ec8-165">Selectați **Aplicați actualizarea soluției** în bara de acțiune.</span><span class="sxs-lookup"><span data-stu-id="54ec8-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Actualizați soluția în zona de particularizare a aplicațiilor Dynamics 365":::

1. <span data-ttu-id="54ec8-167">După ce începeți procesul de actualizare, veți vedea un indicator de încărcare până la finalizarea actualizării.</span><span class="sxs-lookup"><span data-stu-id="54ec8-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="54ec8-168">Dacă nu există o versiune mai nouă, actualizarea va afișa un mesaj de eroare.</span><span class="sxs-lookup"><span data-stu-id="54ec8-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
