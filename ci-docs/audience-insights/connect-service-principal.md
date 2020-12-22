---
title: Conectați-vă la un cont Gen2 Azure Data Lake Storage cu o entitate principală de serviciu
description: utilizați o entitate principală de serviciu Azure pentru Detalii despre audiență pentru a vă conecta la propriul data lake la atașarea la Detalii despre audiență.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644103"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="0f9bf-103">Conectați-vă la un cont Gen2 Azure Data Lake Storage cu o entitate principală de serviciu Azure pentru Detalii despre audiență</span><span class="sxs-lookup"><span data-stu-id="0f9bf-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="0f9bf-104">Instrumentele automate care utilizează serviciile Azure ar trebui să aibă întotdeauna permisiuni restricționate.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="0f9bf-105">În loc ca aplicațiile să se conecteze ca utilizator complet privilegiat, Azure oferă entități principale de serviciu.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="0f9bf-106">Citiți mai departe pentru a afla cum să conectați Detalii despre audiență cu un cont Gen2 Azure Data Lake Storage care utilizează o entitate principală de serviciu Azure în loc de chei de cont de stocare.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="0f9bf-107">Puteți utiliza o entitate principală de serviciu pentru a [adăuga sau edita un folder Common Data Model ca sursă de date](connect-common-data-model.md) sau [crea un mediu nou sau actualiza un mediu existent](manage-environments.md#create-an-environment-in-an-existing-organization) în siguranță.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="0f9bf-108">Aveți nevoie de permisiuni de administrator pentru abonamentul dvs. Azure pentru a crea entitatea principală de serviciu.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="0f9bf-109">Creați entitatea principală de serviciu Azure pentru Detalii despre audiență</span><span class="sxs-lookup"><span data-stu-id="0f9bf-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="0f9bf-110">Înainte de a crea o nouă entitate principală de serviciu pentru Detalii despre audiență, verificați dacă acesta există deja în organizația dvs.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="0f9bf-111">Căutați o entitate principală de serviciu existentă</span><span class="sxs-lookup"><span data-stu-id="0f9bf-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="0f9bf-112">Accesați [portalul de administrare Azure](https://portal.azure.com) și conectați-vă la organizația dvs.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="0f9bf-113">Selectați **Azure Active Directory** din serviciile Azure.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="0f9bf-114">Sub **Gestionare**, selectați **aplicații Enterprise**.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="0f9bf-115">Căutați ID-ul aplicației pentru prima parte din Detalii despre audiență `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` sau numele `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="0f9bf-116">Dacă găsiți o înregistrare potrivită, înseamnă că există o entitate principală de serviciu pentru Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="0f9bf-117">Nu este nevoie să o creați din nou.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captură de ecran care arată entitatea principală de serviciu existentă.":::
   
6. <span data-ttu-id="0f9bf-119">Dacă nu se returnează rezultate, creați o nouă entitate principală de serviciu.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="0f9bf-120">Creare pentru o nouă entitate principală de serviciu</span><span class="sxs-lookup"><span data-stu-id="0f9bf-120">Create a new service principal</span></span>

1. <span data-ttu-id="0f9bf-121">Instalați cea mai recentă versiune a **Azure Active Directory PowerShell pentru reprezentare grafică**.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="0f9bf-122">Pentru mai multe informații, consultați [Instalare Azure Active Directory PowerShell pentru reprezentare grafică](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="0f9bf-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="0f9bf-123">Pe computer, selectați tasta Windows de pe tastatură și căutați **Windows PowerShell** și **Rulați ca administrator**.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="0f9bf-124">În fereastra PowerShell care se deschide, introduceți `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="0f9bf-125">Creați entitatea principală de serviciu pentru Detalii despre audiență cu modulul PowerShell Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="0f9bf-126">În fereastra PowerShell, introduceți `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="0f9bf-127">Înlocuiți „ID-ul entității dvs. găzduite” cu ID-ul propriu-zis al entității găzduite în care doriți să creați entitatea principală de serviciu.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="0f9bf-128">Parametrul numele mediului `AzureEnvironmentName` este opțional.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="0f9bf-129">Introduceți `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="0f9bf-130">Această comandă creează entitatea principală de serviciu pentru Detalii despre audiență în entitatea găzduită selectată.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="0f9bf-131">Acordați permisiuni entității principale de serviciu pentru a accesa contul de stocare</span><span class="sxs-lookup"><span data-stu-id="0f9bf-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="0f9bf-132">Accesați portalul Azure pentru a acorda permisiuni entității principale de serviciu pentru contul de stocare pe care doriți să îl utilizați în Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="0f9bf-133">Accesați [portalul de administrare Azure](https://portal.azure.com) și conectați-vă la organizația dvs.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="0f9bf-134">Deschideți contul de stocare la care doriți să aibă acces entitatea principală de serviciu pentru Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="0f9bf-135">Selectați **Control acces (IAM)** din panoul de navigare și selectați **Adăugare** > **Adăugare atribuire de rol**.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captură de ecran care arată portalul Azure în timp ce se adaugă o atribuire de rol.":::
   
1. <span data-ttu-id="0f9bf-137">În panoul **Adăugare atribuirea de rol**, setați următoarele proprietăți:</span><span class="sxs-lookup"><span data-stu-id="0f9bf-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="0f9bf-138">Rol: *Contribuitor de date blob de stocare*</span><span class="sxs-lookup"><span data-stu-id="0f9bf-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="0f9bf-139">Atribuiți accesul la: *utilizator, grup sau entitate principală de serviciu*</span><span class="sxs-lookup"><span data-stu-id="0f9bf-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="0f9bf-140">Selectați: *Dynamics 365 AI for Customer Insights* ([entitatea principală de serviciu pe care ați creat-o](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="0f9bf-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="0f9bf-141">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-141">Select **Save**.</span></span>

<span data-ttu-id="0f9bf-142">Poate dura până la 15 minute pentru propagarea schimbărilor.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="0f9bf-143">Introduceți ID-ul resursei Azure sau detaliile abonamentului Azure în atașarea contului de stocare la Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="0f9bf-144">Atașați un cont Azure Data Lake Storage în Detalii despre audiență pentru [stocarea datelor de ieșire](manage-environments.md) sau [folosiți-l ca sursă de date](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="0f9bf-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="0f9bf-145">Alegerea opțiunii Azure Data Lake vă permite să alegeți între o abordare bazată pe resurse sau o abordare bazată de abonament.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="0f9bf-146">Urmați pașii de mai jos pentru a furniza informațiile necesare despre abordarea selectată.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="0f9bf-147">Conexiune la contul de stocare bazată pe resurse</span><span class="sxs-lookup"><span data-stu-id="0f9bf-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="0f9bf-148">Accesați [portalul de administrare Azure](https://portal.azure.com), conectați-vă la abonament și deschideți contul de stocare.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="0f9bf-149">Accesați **Setări** > **Proprietăți** din panoul de navigare.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="0f9bf-150">Copiați valoarea ID-ului resursei contului de stocare.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copiați ID-ul resursei contului de stocare.":::

1. <span data-ttu-id="0f9bf-152">În Detalii despre audiență, introduceți ID-ul resursei în câmpul resursei afișat în ecranul de conectare a contului de stocare.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Introduceți informația ID-ului resursei contului de stocare.":::   
   
1. <span data-ttu-id="0f9bf-154">Continuați cu pașii rămași din Detalii despre audiență pentru a atașa contul de stocare.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="0f9bf-155">Conexiune la contul de stocare bazată pe abonament</span><span class="sxs-lookup"><span data-stu-id="0f9bf-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="0f9bf-156">Accesați [portalul de administrare Azure](https://portal.azure.com), conectați-vă la abonament și deschideți contul de stocare.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="0f9bf-157">Accesați **Setări** > **Proprietăți** din panoul de navigare.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="0f9bf-158">Analizați **Abonament**, **Grup de resurse**, și **Numele** din contul de stocare pentru a vă asigura că selectați valorile potrivite în Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="0f9bf-159">În Detalii despre audiență, alegeți valorile sau câmpurile corespunzătoare atunci când atașați contul de stocare.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Introduceți informația ID-ului resursei contului de stocare.":::
   
1. <span data-ttu-id="0f9bf-161">Continuați cu pașii rămași din Detalii despre audiență pentru a atașa contul de stocare.</span><span class="sxs-lookup"><span data-stu-id="0f9bf-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
