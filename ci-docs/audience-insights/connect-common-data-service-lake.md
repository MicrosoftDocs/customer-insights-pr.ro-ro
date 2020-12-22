---
title: Conectați-vă la entități din Common Data Service data lake gestionat
description: Importați date dintr-un Common Data Service Data Lake gestionat.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643413"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="9f401-103">Conectați-vă la date într-un data lake gestionat Common Data Service</span><span class="sxs-lookup"><span data-stu-id="9f401-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9f401-104">Acest articol oferă informații despre modul în care clienții Dynamics 365 existenți se pot conecta rapid la entitățile lor analitice din Common Data Service Lake gestionat.</span><span class="sxs-lookup"><span data-stu-id="9f401-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="9f401-105">Trebuie să fiți administrator pe organizația Common Data Service pentru a continua și vedea lista entităților disponibile în datele Lake gestionate.</span><span class="sxs-lookup"><span data-stu-id="9f401-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="9f401-106">Considerații importante</span><span class="sxs-lookup"><span data-stu-id="9f401-106">Important considerations</span></span>

<span data-ttu-id="9f401-107">Date stocate în servicii online cum ar fi Azure Data Lake Storage pot fi stocate într-o locație diferită de locul în care sunt datele prelucrate sau stocate Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9f401-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="9f401-108"> Prin importul sau conectarea la datele stocate în servicii online, sunteți de acord că datele pot fi transferate și stocate cu Dynamics 365 Customer Insights. [Aflați mai multe la Centrul de autorizare Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="9f401-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="9f401-109">Conectați-vă la un lake gestionat de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="9f401-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="9f401-110">În Detalii despre audiență, accesați **Date** > **Surse de date**.</span><span class="sxs-lookup"><span data-stu-id="9f401-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="9f401-111">Selectați **Adăugați sursa de date**.</span><span class="sxs-lookup"><span data-stu-id="9f401-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="9f401-112">Selectați **Conectați-vă la Common Data Service** și selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="9f401-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="9f401-113">Introduceți un **Nume** pentru sursa de date și selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="9f401-113">Enter a **Name** for the data source and select **Next**.</span></span>

5. <span data-ttu-id="9f401-114">Furnizați **Adresa serverului** pentru organizația dvs. Common Data Service și selectați **Autentificare**.</span><span class="sxs-lookup"><span data-stu-id="9f401-114">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9f401-115">![Caseta de dialog pentru introducerea adresei serverului Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="9f401-115">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="9f401-116">Selectați entitățile pe care doriți să le ingerați din lista disponibilă.</span><span class="sxs-lookup"><span data-stu-id="9f401-116">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="9f401-117">Dacă unele entități sunt deja selectate, acestea ar putea fi utilizate de alte aplicații Dynamics 365 (cum ar fi Dynamics 365 Sales Insights sau Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="9f401-117">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="9f401-118">Nu aveți posibilitatea să modificați selecția.</span><span class="sxs-lookup"><span data-stu-id="9f401-118">You can't change the selection.</span></span> <span data-ttu-id="9f401-119">Aceste entități vor fi disponibile după crearea sursei de date.</span><span class="sxs-lookup"><span data-stu-id="9f401-119">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9f401-120">![Caseta de dialog care arată o listă de entități din organizația Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="9f401-120">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="9f401-121">Salvați selecția dvs. pentru a începe sincronizarea entităților selectate cu lake-ul gestionat de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="9f401-121">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="9f401-122">Veți găsi conexiunea recent adăugată pe pagina **Surse de date**.</span><span class="sxs-lookup"><span data-stu-id="9f401-122">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="9f401-123">Acesta va fi pus în coadă pentru actualizare și va arăta numărul entităților ca fiind 0 până când toate entitățile sunt sincronizate.</span><span class="sxs-lookup"><span data-stu-id="9f401-123">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="9f401-124">Numai o sursă de date dintr-un mediu poate folosi același Common Data Service data lake gestionat simultan.</span><span class="sxs-lookup"><span data-stu-id="9f401-124">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="9f401-125">Editați o sursă de date lake gestionată de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="9f401-125">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="9f401-126">Editați selecția entității numai după crearea sursei de date.</span><span class="sxs-lookup"><span data-stu-id="9f401-126">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="9f401-127">De exemplu, dacă s-au adăugat entități suplimentare la Common Data Service și vreți să le importați și pe acestea.</span><span class="sxs-lookup"><span data-stu-id="9f401-127">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="9f401-128">Pentru a vă conecta la un Common Data Service diferit, [creați o sursă de date noi](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="9f401-128">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="9f401-129">În Detalii despre audiență, accesați **Date** > **Surse de date**.</span><span class="sxs-lookup"><span data-stu-id="9f401-129">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="9f401-130">Lângă sursa de date pe care doriți să o actualizați, selectați elipsa.</span><span class="sxs-lookup"><span data-stu-id="9f401-130">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="9f401-131">Selectați opțiunea **Editare** din listă.</span><span class="sxs-lookup"><span data-stu-id="9f401-131">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="9f401-132">Selectați entități suplimentare din lista de entități disponibile și selectați **Salvați**.</span><span class="sxs-lookup"><span data-stu-id="9f401-132">Select additional entities from the available list of entities and select **Save**.</span></span>
