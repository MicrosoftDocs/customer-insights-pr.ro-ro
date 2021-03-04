---
title: Solicitări de drepturi privind datele subiecților sub RGPD | Microsoft Docs
description: Răspundeți la solicitările persoanei vizate pentru capabilitatea de detalii despre public din Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed9aa09fba938606611c6ce86c2b250c5e19c606
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268701"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="1f73d-103">Solicitări de drepturi privin datele subiecților sub RGPD</span><span class="sxs-lookup"><span data-stu-id="1f73d-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="1f73d-104">Răspundeți la solicitările RGPD ale persoanei vizate pentru capabilitatea de detalii despre public din Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="1f73d-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="1f73d-105">„Dreptul la eliminare” prin înlăturarea datelor cu caracter personal din datele clienților unei organizații reprezintă o protecție-cheie în Regulamentul general privind protecția datelor (RGPD).</span><span class="sxs-lookup"><span data-stu-id="1f73d-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="1f73d-106">Îndepărtarea datelor personale include eliminarea tuturor datelor personale și a jurnalelor generate de sistem, cu excepția informațiilor din jurnalul de audit.</span><span class="sxs-lookup"><span data-stu-id="1f73d-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="1f73d-107">Gestionați solicitările de ștergere a subiectului de date</span><span class="sxs-lookup"><span data-stu-id="1f73d-107">Manage data subject delete requests</span></span>

<span data-ttu-id="1f73d-108">Detaliile despre public oferă următoarele experiențe în cadrul produsului pentru a șterge datele cu caracter personal pentru un anumit client sau utilizator:</span><span class="sxs-lookup"><span data-stu-id="1f73d-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="1f73d-109">**Gestionați ștergerea cererilor datelor clienților**: Datele clienților din Customer Insights sunt ingerate din surse de date originale externe pentru Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1f73d-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="1f73d-110">Toate cererile de ștergere a RGPD trebuie să fie efectuate în sursă originală de date.</span><span class="sxs-lookup"><span data-stu-id="1f73d-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="1f73d-111">**Gestionați solicitările de ștergere pentru datele de utilizator Customer Insights** : Datele pentru utilizatori sunt create de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1f73d-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="1f73d-112">Toate cererile de ștergere a RGPD trebuie să fie efectuate în Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1f73d-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="1f73d-113">Gestionați ștergerea cererilor pentru datele clienților</span><span class="sxs-lookup"><span data-stu-id="1f73d-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="1f73d-114">Un administrator al Customer Insights poate urma acești pași pentru a elimina datele despre clienți care au fost șterse în sursa de date:</span><span class="sxs-lookup"><span data-stu-id="1f73d-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="1f73d-115">Conectați-vă la Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1f73d-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="1f73d-116">În Detalii despre audiență, accesați **Date** > **Surse de date**</span><span class="sxs-lookup"><span data-stu-id="1f73d-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="1f73d-117">Pentru fiecare sursă de date din listă care conține datele șterse ale clienților:</span><span class="sxs-lookup"><span data-stu-id="1f73d-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="1f73d-118">Selectați (...) și apoi selectați **Reîmprospătare**.</span><span class="sxs-lookup"><span data-stu-id="1f73d-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="1f73d-119">Verificați starea sursei de date din **Stare**.</span><span class="sxs-lookup"><span data-stu-id="1f73d-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="1f73d-120">O bifă înseamnă că actualizarea a reușit.</span><span class="sxs-lookup"><span data-stu-id="1f73d-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="1f73d-121">Un triunghi de avertizare înseamnă că a apărut o problemă.</span><span class="sxs-lookup"><span data-stu-id="1f73d-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="1f73d-122">Dacă este afișat un triunghi de avertizare, contactați D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1f73d-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1f73d-123">![Manipularea RGPD de ștergere a cererilor pentru datele clienților](media/gdpr-data-sources.png "Manipularea RGPD de ștergere a cererilor pentru datele clienților")</span><span class="sxs-lookup"><span data-stu-id="1f73d-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="1f73d-124">Gestionați ștergerea cererilor pentru datele utilizatorilor</span><span class="sxs-lookup"><span data-stu-id="1f73d-124">Manage delete requests for user data</span></span>

<span data-ttu-id="1f73d-125">Un administrator al Customer Insights poate urma acești pași pentru ștergerea datelor de utilizator Customer Insights:</span><span class="sxs-lookup"><span data-stu-id="1f73d-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="1f73d-126">Conectați-vă la Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1f73d-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="1f73d-127">În detalii despre public, accesați **Admin** > **Permisiuni**.</span><span class="sxs-lookup"><span data-stu-id="1f73d-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="1f73d-128">Bifați caseta de selectare pentru utilizatorul pe care doriți să-l eliminați.</span><span class="sxs-lookup"><span data-stu-id="1f73d-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="1f73d-129">Selectați **Eliminare**.</span><span class="sxs-lookup"><span data-stu-id="1f73d-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1f73d-130">![Gestionarea cererilor de ștergere conform RGPD a datelor utilizatorilor](media/gdpr-permissions.png "Gestionarea cererilor de ștergere conform RGPD a datelor utilizatorilor")</span><span class="sxs-lookup"><span data-stu-id="1f73d-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="1f73d-131">Răspunsul la cererile de export al datelor persoanei vizate în temeiul RGPD</span><span class="sxs-lookup"><span data-stu-id="1f73d-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="1f73d-132">Ca parte a angajamentului nostru de a ne asocia cu dvs. în călătoria dvs. către Regulamentul general privind protecția datelor (RGPD), am dezvoltat o documentație care vă va ajuta să vă pregătiți.</span><span class="sxs-lookup"><span data-stu-id="1f73d-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="1f73d-133">Această documentație descrie pașii pe care îi puteți face astăzi pentru a sprijini respectarea RGPD atunci când utilizați detalii privind publicul.</span><span class="sxs-lookup"><span data-stu-id="1f73d-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="1f73d-134">Gestionați solicitările de export și vizualizare</span><span class="sxs-lookup"><span data-stu-id="1f73d-134">Manage export and view requests</span></span>

<span data-ttu-id="1f73d-135">Dreptul de portabilitate a datelor permite persoanelor vizate să solicite o copie a datelor cu caracter personal într-un format electronic (definit ca „format structurat, utilizat în mod obișnuit, în format electronic și format interoperabil”) care poate fi transmis unui alt operator de date.</span><span class="sxs-lookup"><span data-stu-id="1f73d-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="1f73d-136">Exportați date despre clienți (administratorul entității găzduite)</span><span class="sxs-lookup"><span data-stu-id="1f73d-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="1f73d-137">Un administrator de entitate găzduită poate urma acești pași pentru a exporta date:</span><span class="sxs-lookup"><span data-stu-id="1f73d-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="1f73d-138">Trimiteți un e-mail la D365CI@microsoft.com specificând adresa de e-mail a clientului în cerere.</span><span class="sxs-lookup"><span data-stu-id="1f73d-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="1f73d-139">Echipa Customer Insights va trimite un e-mail la adresa de e-mail înregistrată a administratorului entității găzduite înregistrate, solicitând confirmarea exportului de date.</span><span class="sxs-lookup"><span data-stu-id="1f73d-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="1f73d-140">Aprobați confirmarea de a exporta datele pentru client solicitate.</span><span class="sxs-lookup"><span data-stu-id="1f73d-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="1f73d-141">Primiți datele exportate prin intermediul adresei de e-mail de administrator de entitate găzduită.</span><span class="sxs-lookup"><span data-stu-id="1f73d-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="1f73d-142">Exportați date de utilizatori (administratorul entității găzduite)</span><span class="sxs-lookup"><span data-stu-id="1f73d-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="1f73d-143">Trimiteți un e-mail la D365CI@microsoft.com specificând adresa de e-mail a utilizatorului în cerere.</span><span class="sxs-lookup"><span data-stu-id="1f73d-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="1f73d-144">Echipa Customer Insights va trimite un e-mail la adresa de e-mail înregistrată a administratorului entității găzduite înregistrate, solicitând confirmarea exportului de date.</span><span class="sxs-lookup"><span data-stu-id="1f73d-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="1f73d-145">Aprobați confirmarea de a exporta datele pentru utilizator solicitate.</span><span class="sxs-lookup"><span data-stu-id="1f73d-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="1f73d-146">Primiți datele exportate prin intermediul adresei de e-mail de administrator de entitate găzduită.</span><span class="sxs-lookup"><span data-stu-id="1f73d-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]