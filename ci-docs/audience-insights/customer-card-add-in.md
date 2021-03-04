---
title: Instalați și configurați Programul de completare card client
description: Instalarea și configurarea programului de completare card client pentru Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268059"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="64c5e-103">Program de completare card client (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="64c5e-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="64c5e-104">Obțineți o vizualizare la 360 de grade a clienților dvs. direct în aplicațiile Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="64c5e-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="64c5e-105">Vizualizați datele demografice, informațiile și cronologiile de activitate cu ajutorul programului de completare card client.</span><span class="sxs-lookup"><span data-stu-id="64c5e-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="64c5e-106">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="64c5e-106">Prerequisites</span></span>

- <span data-ttu-id="64c5e-107">Aplicația Dynamics 365 (cum ar fi Hub de vânzări sau Hub de servicii pentru clienți), versiunea 9.0 și ulterior cu Interfață unificată activată.</span><span class="sxs-lookup"><span data-stu-id="64c5e-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="64c5e-108">Profilurile clienților [ingerate din aplicația Dynamics 365 folosind Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="64c5e-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="64c5e-109">Utilizatorii programului de completare card client trebuie să fie [adăugați ca utilizatori](permissions.md) în Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="64c5e-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="64c5e-110">[Capabilități de căutare și filtrare configurate](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="64c5e-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="64c5e-111">Control demografic: câmpurile demografice (cum ar fi vârsta sau sexul), sunt disponibile în profilul de client unificat.</span><span class="sxs-lookup"><span data-stu-id="64c5e-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="64c5e-112">Controlul îmbogățirii: necesită [îmbogățiri](enrichment-hub.md) active aplicate profilurilor clienților.</span><span class="sxs-lookup"><span data-stu-id="64c5e-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="64c5e-113">Control inteligent: Necesită date generate în Azure Machine Learning ([Predicții](predictions.md) sau [Modele particularizate](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="64c5e-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="64c5e-114">Controlul măsurii: Necesită [măsuri configurate](measures.md).</span><span class="sxs-lookup"><span data-stu-id="64c5e-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="64c5e-115">Controlul cronologiei: Necesită [activități configurate](activities.md).</span><span class="sxs-lookup"><span data-stu-id="64c5e-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="64c5e-116">Instalați suplimentul cardului client</span><span class="sxs-lookup"><span data-stu-id="64c5e-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="64c5e-117">Adăugarea programului de completare Card client este o soluție pentru aplicațiile de implicare a clienților din Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="64c5e-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="64c5e-118">Pentru a instala soluția, accesați AppSource și căutați **Card de client Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="64c5e-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="64c5e-119">Selectați [Programul de completare card de client AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) și selectați **Obțineți acum**.</span><span class="sxs-lookup"><span data-stu-id="64c5e-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="64c5e-120">Este posibil să fie nevoie să vă autentificați cu datele dvs. de acreditare pentru aplicația Dynamics 365 pentru a instala soluția.</span><span class="sxs-lookup"><span data-stu-id="64c5e-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="64c5e-121">Poate dura ceva timp pentru ca soluția să fie instalată în mediul dvs.</span><span class="sxs-lookup"><span data-stu-id="64c5e-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="64c5e-122">Configurați programul de completare pentru card client</span><span class="sxs-lookup"><span data-stu-id="64c5e-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="64c5e-123">În calitate de administrator, accesați secțiunea **Setări** din Dynamics 365 și selectați **Soluții**.</span><span class="sxs-lookup"><span data-stu-id="64c5e-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="64c5e-124">Selectați legătura **Nume afișat** pentru soluția **Dynamics 365 Customer Insights Program de completare card client (Previzualizare)**.</span><span class="sxs-lookup"><span data-stu-id="64c5e-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64c5e-125">![Selectați numele afișat](media/select-display-name.png "Selectați numele afișat")</span><span class="sxs-lookup"><span data-stu-id="64c5e-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="64c5e-126">Selectați **Conectare** și introduceți acreditările pentru contul de administrator pe care îl utilizați pentru a configura Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="64c5e-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="64c5e-127">Verificați dacă funcția de blocare a ferestrelor pop-up a browserului nu blochează fereastra de autentificare atunci când selectați butonul **Conectare**.</span><span class="sxs-lookup"><span data-stu-id="64c5e-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="64c5e-128">Selectați mediul de la care doriți să preluați date.</span><span class="sxs-lookup"><span data-stu-id="64c5e-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="64c5e-129">Definiți maparea câmpului către înregistrări în aplicația Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="64c5e-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="64c5e-130">Pentru a mapa un contact, selectați câmpul din entitatea Client care se potrivește cu ID-ul entității dvs. de contact.</span><span class="sxs-lookup"><span data-stu-id="64c5e-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="64c5e-131">Pentru a mapa un cont, selectați câmpul din entitatea Client care se potrivește cu ID-ul entității dvs. de cont.</span><span class="sxs-lookup"><span data-stu-id="64c5e-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64c5e-132">![Câmpul ID persoană de contact](media/contact-id-field.png "Câmpul ID persoană de contact")</span><span class="sxs-lookup"><span data-stu-id="64c5e-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="64c5e-133">Selectați **Salvare configurație** pentru a salva setările.</span><span class="sxs-lookup"><span data-stu-id="64c5e-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="64c5e-134">În continuare, trebuie să atribuiți roluri de securitate în Dynamics 365, astfel încât utilizatorii să poată personaliza și vedea cardul de client.</span><span class="sxs-lookup"><span data-stu-id="64c5e-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="64c5e-135">În Dynamics 365, accesați **Setări** > **Securitate** > **Utilizatori**.</span><span class="sxs-lookup"><span data-stu-id="64c5e-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="64c5e-136">Selectați utilizatorii pentru a edita rolurile utilizatorului și selectați **Gestionați roluri**.</span><span class="sxs-lookup"><span data-stu-id="64c5e-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="64c5e-137">Atribuiți rolul **Utilizator standard card Customer Insights** pentru utilizatorii care vor personaliza conținutul afișat pe card pentru întreaga organizație.</span><span class="sxs-lookup"><span data-stu-id="64c5e-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="64c5e-138">Adăugare controale Card client la formulare</span><span class="sxs-lookup"><span data-stu-id="64c5e-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="64c5e-139">Pentru a adăuga controale pentru cardul clientului în formularul dvs. de contact, accesați secțiunea **Setări** > **Particularizări** în Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="64c5e-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="64c5e-140">Selectați **Particularizați sistemul**.</span><span class="sxs-lookup"><span data-stu-id="64c5e-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="64c5e-141">Navigați la entitatea **Persoană de contact**, extindeți-o și selectați **Formulare**.</span><span class="sxs-lookup"><span data-stu-id="64c5e-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="64c5e-142">Selectați formularul de contact la care doriți să adăugați controalele Card client.</span><span class="sxs-lookup"><span data-stu-id="64c5e-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="64c5e-143">![Selectați formularul de contact](media/contact-active-forms.png "Selectați formularul de contact")</span><span class="sxs-lookup"><span data-stu-id="64c5e-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="64c5e-144">Pentru a adăuga un control, în editorul de formulare, trageți orice câmp din **Exploratorul de câmp** în locul în care doriți să apară controlul.</span><span class="sxs-lookup"><span data-stu-id="64c5e-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="64c5e-145">Selectați câmpul pe formularul pe care tocmai l-ați adăugat și selectați **Modificare proprietăți**.</span><span class="sxs-lookup"><span data-stu-id="64c5e-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="64c5e-146">Accesați fila **Controale** și selectați **Adăugare control**.</span><span class="sxs-lookup"><span data-stu-id="64c5e-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="64c5e-147">Alegeți unul dintre controalele particularizate disponibile și selectați **Adăugați**.</span><span class="sxs-lookup"><span data-stu-id="64c5e-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="64c5e-148">În caseta de dialog **Proprietăți câmp**, debifați caseta de selectare **Afișare etichetă pe formular**.</span><span class="sxs-lookup"><span data-stu-id="64c5e-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="64c5e-149">Selectați opțiunea **Web** pentru control.</span><span class="sxs-lookup"><span data-stu-id="64c5e-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="64c5e-150">Pentru controlul Îmbogățire, selectați tipul de îmbogățire pe care doriți să-l afișați configurand câmpul **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="64c5e-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="64c5e-151">Adăugați un control separat de îmbogățire pentru fiecare tip de îmbogățire.</span><span class="sxs-lookup"><span data-stu-id="64c5e-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="64c5e-152">Selectați **Salvați** și **Publicați** pentru a publica formularul de contact actualizat.</span><span class="sxs-lookup"><span data-stu-id="64c5e-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="64c5e-153">Accesați formularul de contact publicat.</span><span class="sxs-lookup"><span data-stu-id="64c5e-153">Go to the published contact form.</span></span> <span data-ttu-id="64c5e-154">Veți vedea controlul nou adăugat.</span><span class="sxs-lookup"><span data-stu-id="64c5e-154">You'll see the newly added control.</span></span> <span data-ttu-id="64c5e-155">Este posibil să fie nevoie să vă conectați, prima dată când îl utilizați.</span><span class="sxs-lookup"><span data-stu-id="64c5e-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="64c5e-156">Pentru a particulariza ceea ce doriți să afișați în controlul particularizat, selectați butonul de editare din colțul din dreapta sus.</span><span class="sxs-lookup"><span data-stu-id="64c5e-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="64c5e-157">Faceți upgrade la programul de completare Customer Card</span><span class="sxs-lookup"><span data-stu-id="64c5e-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="64c5e-158">Programul de completare pentru Customer Card nu se actualizează automat.</span><span class="sxs-lookup"><span data-stu-id="64c5e-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="64c5e-159">Pentru a face upgrade la cea mai recentă versiune, urmați această procedură în aplicația Dynamics 365 care are instalat programul de completare.</span><span class="sxs-lookup"><span data-stu-id="64c5e-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="64c5e-160">În aplicația Dynamics 365, accesați **Setări** > **Particularizare** și selectați **Soluții**.</span><span class="sxs-lookup"><span data-stu-id="64c5e-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="64c5e-161">În tabelul cu programe de completare căutați **CustomerInsightsCustomerCard** și selectați rândul.</span><span class="sxs-lookup"><span data-stu-id="64c5e-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="64c5e-162">Selectați **Aplicați actualizarea soluției** în bara de acțiune.</span><span class="sxs-lookup"><span data-stu-id="64c5e-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Actualizați soluția în zona de particularizare a aplicațiilor Dynamics 365":::

1. <span data-ttu-id="64c5e-164">După ce începeți procesul de actualizare, veți vedea un indicator de încărcare până la finalizarea actualizării.</span><span class="sxs-lookup"><span data-stu-id="64c5e-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="64c5e-165">Dacă nu există o versiune mai nouă, actualizarea va afișa un mesaj de eroare.</span><span class="sxs-lookup"><span data-stu-id="64c5e-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]