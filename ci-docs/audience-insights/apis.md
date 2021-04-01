---
title: Lucrați cu API-uri
description: Folosirea de API-uri și înțelegerea limitărilor.
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 011fa700563c53534554a6b73e87c2391bfdf714
ms.sourcegitcommit: a872f59e6febe4d4bd678ddd0b60a1660acca0f3
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/24/2021
ms.locfileid: "5710475"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="d7717-103">Lucrul cu API-urile Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d7717-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="d7717-104">Dynamics 365 Customer Insights oferă API-uri pentru a vă crea propriile aplicații bazate pe datele dvs. în Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d7717-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d7717-105">Detaliile acestor API-uri sunt listate în [Referința pentru API-uri Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="d7717-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="d7717-106">Acestea includ informații suplimentare despre operațiuni, parametri și răspunsuri.</span><span class="sxs-lookup"><span data-stu-id="d7717-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="d7717-107">Acest articol vă ghidează să accesați API-urile Customer Insights, să creați o înregistrare de aplicație Azure și să vă ajute să începeți cu bibliotecile client disponibile.</span><span class="sxs-lookup"><span data-stu-id="d7717-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="d7717-108">Începeți să încercați API-urile Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d7717-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="d7717-109">[Conectați-vă](https://home.ci.ai.dynamics.com) la Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d7717-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="d7717-110">Dacă nu aveți încă un abonament, [înscrieți-vă pentru o versiune de încercare a Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="d7717-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="d7717-111">Pentru a activa API-urile din mediul dvs. Customer Insights, accesați **Administrator** > **Permisiuni**.</span><span class="sxs-lookup"><span data-stu-id="d7717-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="d7717-112">Veți avea nevoie de permisiuni de administrator pentru asta.</span><span class="sxs-lookup"><span data-stu-id="d7717-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="d7717-113">Accesați fila **API-uri** și selectați butonul **Permite**.</span><span class="sxs-lookup"><span data-stu-id="d7717-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="d7717-114">Activarea API-urilor creează o cheie de abonament primară și una secundară pentru instanța dvs. care este folosită în solicitările API.</span><span class="sxs-lookup"><span data-stu-id="d7717-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="d7717-115">Puteți regenera cheile selectând **Regenerare cheie primară** sau **Regenerare cheie secundară** din **Administrator** > **Permisiuni** > **API-uri**.</span><span class="sxs-lookup"><span data-stu-id="d7717-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Activați API-urile Customer Insights":::

1. <span data-ttu-id="d7717-117">Selectați **Explorați API-urile noastre** pentru [a încerca API-urile](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="d7717-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="d7717-118">Alegeți o operațiune API și selectați **Încearcă**.</span><span class="sxs-lookup"><span data-stu-id="d7717-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="d7717-119">În panoul lateral, setați valoarea în meniul vertical **Autorizare** la **implicit**.</span><span class="sxs-lookup"><span data-stu-id="d7717-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="d7717-120">Antetului `Authorization` i se adaugă un token pentru purtător.</span><span class="sxs-lookup"><span data-stu-id="d7717-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="d7717-121">Cheia dvs. de abonament va fi populată automat.</span><span class="sxs-lookup"><span data-stu-id="d7717-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="d7717-122">Opțional, adăugați toți parametrii de interogare necesari.</span><span class="sxs-lookup"><span data-stu-id="d7717-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="d7717-123">Derulați până în partea de jos a panoului lateral și selectați **Trimitere**.</span><span class="sxs-lookup"><span data-stu-id="d7717-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="d7717-124">Răspunsul HTTP va apărea curând mai jos.</span><span class="sxs-lookup"><span data-stu-id="d7717-124">The HTTP response will soon appear below.</span></span>


   :::image type="content" source="media/try-apis.gif" alt-text="Gif animat care arată cum se selectează testarea API-urilor.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="d7717-126">Creați o nouă înregistrare a aplicației în portalul Azure</span><span class="sxs-lookup"><span data-stu-id="d7717-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="d7717-127">Acești pași vă ajută să începeți să utilizați API-urile Customer Insights într-o aplicație Azure utilizând permisiuni delegate.</span><span class="sxs-lookup"><span data-stu-id="d7717-127">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="d7717-128">Asigurați-vă că ați terminat întâi [Secțiunea Introducere](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="d7717-128">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="d7717-129">Conectați-vă la [portalul Azure](https://portal.azure.com) cu contul care poate accesa datele Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d7717-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="d7717-130">În stânga, selectați **Înregistrări aplicații**.</span><span class="sxs-lookup"><span data-stu-id="d7717-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="d7717-131">Selectați **Înregistrare nouă** furnizați un nume de aplicație și alegeți tipul de cont.</span><span class="sxs-lookup"><span data-stu-id="d7717-131">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="d7717-132">Opțional, adăugați o adresă URL de redirecționare.</span><span class="sxs-lookup"><span data-stu-id="d7717-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="d7717-133">http://localhost este suficient pentru dezvoltarea unei aplicații pe computerul dvs. local.</span><span class="sxs-lookup"><span data-stu-id="d7717-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="d7717-134">În noua înregistrare a aplicației, accesați **Permisiuni API**.</span><span class="sxs-lookup"><span data-stu-id="d7717-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Gif animat pentru a seta permisiunea API în înregistrarea aplicației.":::

1. <span data-ttu-id="d7717-136">Selectați **Adăugați o permisiune** și selectați **Customer Insights** în panoul lateral.</span><span class="sxs-lookup"><span data-stu-id="d7717-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="d7717-137">Pentru **Tip permisiune**, selectați **Permisiuni delegate** și selectați permisiunea **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="d7717-137">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="d7717-138">Selectați **Adăugare permisiuni**.</span><span class="sxs-lookup"><span data-stu-id="d7717-138">Select **Add permissions**.</span></span> <span data-ttu-id="d7717-139">Dacă trebuie să accesați API-ul fără conectarea unui utilizator, consultați secțiunea [Permisiuni pentru aplicații de la server la server](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="d7717-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="d7717-140">Selectați **Acordă consimțământul administratorului pentru...** pentru a finaliza înregistrarea aplicației.</span><span class="sxs-lookup"><span data-stu-id="d7717-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="d7717-141">Puteți utiliza ID-ul aplicației/clientului pentru această înregistrare a aplicației cu Biblioteca de autentificare Microsoft (MSAL) pentru a obține un token pentru purtător pe care îl trimiteți cu cererea dvs. către API.</span><span class="sxs-lookup"><span data-stu-id="d7717-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="GIF animat pentru a acorda consimțământul administratorului.":::

<span data-ttu-id="d7717-143">Pentru mai multe informații despre MSAL, consultați [Prezentare generală a bibliotecii de autentificare Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="d7717-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="d7717-144">Pentru mai multe informații despre înregistrarea aplicațiilor în Azure, consultați [Noua experiență de înregistrare a aplicației în portalul Azure](/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="d7717-144">For more information about app registration in Azure, see [The new Azure portal app registration experience](/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="d7717-145">Pentru informații despre utilizarea API-urilor cu bibliotecile clienților noștri, consultați [Biblioteci client Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="d7717-145">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="d7717-146">Permisiuni pentru aplicații de la server la server</span><span class="sxs-lookup"><span data-stu-id="d7717-146">Server-to-server application permissions</span></span>

<span data-ttu-id="d7717-147">[Secțiunea înregistrarea aplicației](#create-a-new-app-registration-in-the-azure-portal) descrie modul de înregistrare a unei aplicații care necesită conectarea unui utilizator pentru autentificare.</span><span class="sxs-lookup"><span data-stu-id="d7717-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="d7717-148">Aflați cum să creați o înregistrare a aplicației care nu necesită interacțiunea utilizatorului și care poate fi rulată pe un server.</span><span class="sxs-lookup"><span data-stu-id="d7717-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="d7717-149">În înregistrarea aplicației dvs. în portalul Azure, accesați **Permisiuni API**.</span><span class="sxs-lookup"><span data-stu-id="d7717-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="d7717-150">Selectați **Adăugați o permisiune** și selectați **Customer Insights** în panoul lateral.</span><span class="sxs-lookup"><span data-stu-id="d7717-150">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="d7717-151">Pentru **Tip permisiune**, selectați **Permisiuni aplicație** și selectați permisiunea **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="d7717-151">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="d7717-152">Selectați **Adăugare permisiuni**.</span><span class="sxs-lookup"><span data-stu-id="d7717-152">Select **Add permissions**.</span></span>

1. <span data-ttu-id="d7717-153">Pentru a da consimțământul administratorului pentru această permisiune de aplicație, trebuie să adăugați o entitate principală de serviciu.</span><span class="sxs-lookup"><span data-stu-id="d7717-153">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="d7717-154">Instalați modulul (AD) PowerShell Azure Active Directory: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="d7717-154">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="d7717-155">Conectați-vă la contul AD: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="d7717-155">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="d7717-156">Puteți găsi ID-ul entității găzduite din **Prezentare generală** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="d7717-156">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="d7717-157">Rulați următoarea comandă pentru a adăuga o entitate principală de serviciu Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Parametrul AppId se referă la aplicația API Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d7717-157">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Eșantion entitate principală de serviciu":::

1. <span data-ttu-id="d7717-159">Reveniți la **Permisiuni API** pentru înregistrarea aplicației.</span><span class="sxs-lookup"><span data-stu-id="d7717-159">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="d7717-160">Selectați **Acordă consimțământul administratorului pentru...** pentru a finaliza înregistrarea aplicației.</span><span class="sxs-lookup"><span data-stu-id="d7717-160">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="GIF animat pentru a acorda consimțământul administratorului.":::

1. <span data-ttu-id="d7717-162">În concluzie, trebuie să adăugăm numele înregistrării aplicației ca utilizator în Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d7717-162">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="d7717-163">Deschideți Customer Insights, accesați **Administrator** > **Permisiuni** și selectați **Adăugare utilizator**.</span><span class="sxs-lookup"><span data-stu-id="d7717-163">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="d7717-164">Căutați numele înregistrării aplicației dvs., selectați-l din rezultatele căutării și selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="d7717-164">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="d7717-165">Biblioteci client Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d7717-165">Customer Insights client libraries</span></span>

<span data-ttu-id="d7717-166">Această secțiune vă ajută să începeți să utilizați bibliotecile client disponibile pentru API-urile Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d7717-166">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="d7717-167">Toate codurile sursă ale bibliotecii și exemplele de aplicații pot fi găsite pe [pagina GitHub Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="d7717-167">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="d7717-168">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="d7717-168">C# NuGet</span></span>

<span data-ttu-id="d7717-169">Aflați cum să începeți să utilizați bibliotecile client C# de la NuGet.org. Pentru mai multe informații despre pachetul NuGet, consultați [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="d7717-169">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="d7717-170">În prezent, acest pachet vizează cadrele netstandard2.0 și netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="d7717-170">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="d7717-171">Adăugați biblioteca client C# la un proiect C#</span><span class="sxs-lookup"><span data-stu-id="d7717-171">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="d7717-172">În Visual Studio, deschideți **Manager pachet NuGet** pentru proiectul dumneavoastră.</span><span class="sxs-lookup"><span data-stu-id="d7717-172">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="d7717-173">Căutați **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="d7717-173">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="d7717-174">Selectați **Instalare** pentru a adăuga pachetul la proiect.</span><span class="sxs-lookup"><span data-stu-id="d7717-174">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="d7717-175">Alternativ, rulați această comandă în **Consola Manager pachet NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="d7717-175">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Adăugați pachetul NuGet la un proiect Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="d7717-177">Utilizați biblioteca de client C#</span><span class="sxs-lookup"><span data-stu-id="d7717-177">Use the C# client library</span></span>

1. <span data-ttu-id="d7717-178">Folosiți [Biblioteca de autentificare Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) pentru a obține un `AccessToken` folosind [înregistrarea aplicației Azure](#create-a-new-app-registration-in-the-azure-portal) existentă.</span><span class="sxs-lookup"><span data-stu-id="d7717-178">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="d7717-179">După autentificarea și achiziționarea cu succes a unui token, construiți un nou `HttpClient` sau utilizați unul existent cu suplimentul **DefaultRequestHeaders „Autorizare”** setat la **Purtător <access token>** și **Ocp-Apim-Subscription-Key** setat la [**cheie de abonament** din mediul dvs. Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="d7717-179">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="d7717-180">Resetați antetul **Autorizare** când este cazul.</span><span class="sxs-lookup"><span data-stu-id="d7717-180">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="d7717-181">De exemplu, când tokenul a expirat.</span><span class="sxs-lookup"><span data-stu-id="d7717-181">For example, when the token expired.</span></span>

1. <span data-ttu-id="d7717-182">Introduceți această `HttpClient` în construcția clientului `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="d7717-182">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Eșantion de httpclient":::

1. <span data-ttu-id="d7717-184">Efectuați apeluri cu clientul pentru „metodele de extensie”, de exemplu, `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="d7717-184">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="d7717-185">Dacă accesul la `Microsoft.Rest.HttpOperationResponse` subiacent este preferat, utilizați „metode de mesaj http”, de exemplu `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="d7717-185">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="d7717-186">Răspunsul va fi probabil de tip `object` deoarece metoda poate returna mai multe tipuri (de exemplu, `IList<InstanceInfo>` și `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="d7717-186">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="d7717-187">Pentru a verifica tipul de returnare, puteți folosi în siguranță funcția cast pentru obiectele din tipurile de răspuns specificate în [pagina de detalii API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) pentru respectiva operațiune.</span><span class="sxs-lookup"><span data-stu-id="d7717-187">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="d7717-188">Dacă sunt necesare mai multe informații la cerere, utilizați **metode mesaj http** pentru a accesa obiectul de răspuns brut.</span><span class="sxs-lookup"><span data-stu-id="d7717-188">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="d7717-189">Pachetul NodeJS</span><span class="sxs-lookup"><span data-stu-id="d7717-189">NodeJS package</span></span>

<span data-ttu-id="d7717-190">Utilizați bibliotecile client NodeJS disponibile prin NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="d7717-190">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="d7717-191">Pachet Python</span><span class="sxs-lookup"><span data-stu-id="d7717-191">Python package</span></span>

<span data-ttu-id="d7717-192">Utilizați bibliotecile client Python disponibile prin PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="d7717-192">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
