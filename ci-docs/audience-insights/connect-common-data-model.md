---
title: Conectați datele Common Data Model la un cont Azure Data Lake
description: Lucrați cu datele Common Data Model folosind Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643473"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="16e87-103">Conectați-vă la un folder Common Data Model folosind un cont Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="16e87-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="16e87-104">Acest articol oferă informații despre cum să ingerați date dintr-un director Common Data Model folosindu-vă contul Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="16e87-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="16e87-105">Considerații importante</span><span class="sxs-lookup"><span data-stu-id="16e87-105">Important considerations</span></span>

- <span data-ttu-id="16e87-106">Datele din Azure Data Lake trebuie să urmeze standardul Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="16e87-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="16e87-107">Alte formate nu sunt acceptate în acest moment.</span><span class="sxs-lookup"><span data-stu-id="16e87-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="16e87-108">Ingestia de date acceptă exclusiv conturi Azure Data Lake Storage *Gen2*.</span><span class="sxs-lookup"><span data-stu-id="16e87-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="16e87-109">Nu puteți utiliza conturile Azure Data Lake Storage Gen1 pentru a ingera date.</span><span class="sxs-lookup"><span data-stu-id="16e87-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="16e87-110">Pentru a vă autentifica cu o entitate principală de serviciu Azure, asigurați-vă că este configurat în entitatea găzduită.</span><span class="sxs-lookup"><span data-stu-id="16e87-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="16e87-111">pentru mai multe informații, consultați [Conectați detaliile privind publicul la un cont Azure Data Lake Storage Gen2 cu o entitate principală de serviciu Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="16e87-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="16e87-112">Azure Data Lake la care doriți să vă conectați și să ingerați date trebuie să fie în aceeași regiune Azure ca și mediul Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="16e87-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="16e87-113">Conexiunile la un director Common Data Model dintr-un data lake dintr-o altă regiune Azure nu sunt acceptate.</span><span class="sxs-lookup"><span data-stu-id="16e87-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="16e87-114">Pentru a afla regiunea Azure a mediului, accesați **Administrator** > **Sistem** > **Despre** în Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="16e87-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="16e87-115">Datele stocate în serviciile online pot fi stocate într-o locație diferită de locul în care sunt procesate sau stocate datele în Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="16e87-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="16e87-116"> Prin importul sau conectarea la datele stocate în servicii online, sunteți de acord că datele pot fi transferate și stocate cu Dynamics 365 Customer Insights. [Aflați mai multe la Centrul de autorizare Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="16e87-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="16e87-117">Conectare la un folder Common Data Model</span><span class="sxs-lookup"><span data-stu-id="16e87-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="16e87-118">În Detalii despre audiență, accesați **Date** > **Surse de date**.</span><span class="sxs-lookup"><span data-stu-id="16e87-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="16e87-119">Selectați **Adăugați sursa de date**.</span><span class="sxs-lookup"><span data-stu-id="16e87-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="16e87-120">Selectați **Conectare la un director Common Data Model**, introduceți un **Nume** pentru sursa de date și selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="16e87-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span>

1. <span data-ttu-id="16e87-121">Puteți alege între utilizarea unei opțiuni bazate pe resurse și o opțiune bazată pe abonament pentru autentificare.</span><span class="sxs-lookup"><span data-stu-id="16e87-121">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="16e87-122">pentru mai multe informații, consultați [Conectați detaliile privind publicul la un cont Azure Data Lake Storage Gen2 cu o entitate principală de serviciu Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="16e87-122">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="16e87-123">Introduceți informația **Recipient** și selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="16e87-123">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="16e87-124">![Caseta de dialog pentru a introduce detaliile conexiunii pentru Azure Data Lake](media/enter-new-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="16e87-124">![Dialog box to enter connection details for Azure Data Lake](media/enter-new-storage-details.png)</span></span>

1. <span data-ttu-id="16e87-125">În dialogul **Selectați un director Common Data Model**, selectați fișierul model.json din care să importați date și selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="16e87-125">In the **Select a Common Data Model folder** dialog, select the model.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="16e87-126">Orice fișier model.json asociat cu o altă sursă de date din mediu nu va apărea în listă.</span><span class="sxs-lookup"><span data-stu-id="16e87-126">Any model.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="16e87-127">Veți obține o listă de entități disponibile în fișierul model.json selectat.</span><span class="sxs-lookup"><span data-stu-id="16e87-127">You'll get a list of available entities in the selected model.json file.</span></span> <span data-ttu-id="16e87-128">Puteți analiza și selecta din lista de entități disponibile și selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="16e87-128">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="16e87-129">Toate entitățile selectate vor fi ingerate din noua sursă de date.</span><span class="sxs-lookup"><span data-stu-id="16e87-129">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="16e87-130">![Casetă de dialog care arată o listă de entități dintr-un fișier model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="16e87-130">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="16e87-131">Indicați cu ce entități de date doriți să activați profilarea datelor și selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="16e87-131">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="16e87-132">Profilarea datelor permite analiza și alte capacități.</span><span class="sxs-lookup"><span data-stu-id="16e87-132">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="16e87-133">Puteți selecta întreaga entitate, care selectează toate atributele din entitate, sau puteți selecta anumite atribute dorite.</span><span class="sxs-lookup"><span data-stu-id="16e87-133">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="16e87-134">În mod implicit, nu este activată nicio entitate pentru profilarea datelor.</span><span class="sxs-lookup"><span data-stu-id="16e87-134">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="16e87-135">![Casetă de dialog care prezintă o profilare a datelor](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="16e87-135">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="16e87-136">După salvarea selecțiilor, se deschide pagina **Surse de date**.</span><span class="sxs-lookup"><span data-stu-id="16e87-136">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="16e87-137">Acum ar trebui să vedeți conexiunea folderului Common Data Model ca o sursă de date.</span><span class="sxs-lookup"><span data-stu-id="16e87-137">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="16e87-138">Un fișier model.json se poate asocia doar cu o singură sursă de date în același mediu.</span><span class="sxs-lookup"><span data-stu-id="16e87-138">A model.json file can only associate with one data source in the same environment.</span></span> <span data-ttu-id="16e87-139">Cu toate acestea, același fișier model.json poate fi utilizat pentru surse de date în medii multiple.</span><span class="sxs-lookup"><span data-stu-id="16e87-139">However, the same model.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="16e87-140">Editați o sursă de date a folderului Common Data Model</span><span class="sxs-lookup"><span data-stu-id="16e87-140">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="16e87-141">Puteți actualiza cheia de acces pentru contul de stocare care conține directorul Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="16e87-141">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="16e87-142">De asemenea, puteți modifica fișierul model.json.</span><span class="sxs-lookup"><span data-stu-id="16e87-142">You may also change the model.json file.</span></span> <span data-ttu-id="16e87-143">Pentru a conecta la un container diferit de contul de stocare sau să modificați numele contului, trebuie să [creați o nouă conexiune la sursa de date](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="16e87-143">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="16e87-144">În Detalii despre audiență, accesați **Date** > **Surse de date**.</span><span class="sxs-lookup"><span data-stu-id="16e87-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="16e87-145">Lângă sursa de date pe care doriți să o actualizați, selectați elipsa.</span><span class="sxs-lookup"><span data-stu-id="16e87-145">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="16e87-146">Selectați opțiunea **Editare** din listă.</span><span class="sxs-lookup"><span data-stu-id="16e87-146">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="16e87-147">Opțional, actualizați **Cheie de acces** și selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="16e87-147">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Dialog pentru a edita și a actualiza o cheie de acces pentru o sursă de date existentă](media/edit-access-key.png)

5. <span data-ttu-id="16e87-149">Opțional, puteți actualiza de la o conexiune cu cheie de cont la o conexiune bazată pe resurse sau bazată pe abonament.</span><span class="sxs-lookup"><span data-stu-id="16e87-149">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="16e87-150">pentru mai multe informații, consultați [Conectați detaliile privind publicul la un cont Azure Data Lake Storage Gen2 cu o entitate principală de serviciu Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="16e87-150">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="16e87-151">Nu puteți schimba informațiile legate de **Recipient** la actualizarea conexiunii.</span><span class="sxs-lookup"><span data-stu-id="16e87-151">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="16e87-152">![Caseta de dialog pentru a introduce detaliile conexiunii pentru Azure Data Lake](media/enter-existing-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="16e87-152">![Dialog box to enter connection details for Azure Data Lake](media/enter-existing-storage-details.png)</span></span>

6. <span data-ttu-id="16e87-153">Opțional, alegeți un fișier model.json diferit cu un set diferit de entități din container.</span><span class="sxs-lookup"><span data-stu-id="16e87-153">Optionally, choose a different model.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="16e87-154">Opțional, puteți selecta entități suplimentare de ingerat.</span><span class="sxs-lookup"><span data-stu-id="16e87-154">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="16e87-155">De asemenea, puteți elimina orice entități deja selectate dacă nu există dependențe.</span><span class="sxs-lookup"><span data-stu-id="16e87-155">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="16e87-156">Dacă există dependențe la fișierul model.json existent și de setul de entități, veți vedea un mesaj de eroare și nu puteți selecta alt fișier model.json.</span><span class="sxs-lookup"><span data-stu-id="16e87-156">If there are dependencies on the existing model.json file and the set of entities, you'll see an error message and can't select a different model.json file.</span></span> <span data-ttu-id="16e87-157">Eliminați aceste dependențe înainte de a schimba fișierul model.json sau creați o sursă de date nouă cu fișierul model.json pe care doriți să-l utilizați pentru a evita eliminarea dependențelor.</span><span class="sxs-lookup"><span data-stu-id="16e87-157">Remove those dependencies before changing the model.json file or create a new data source with the model.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="16e87-158">Opțional, puteți selecta atribute sau entități suplimentare pentru a activa profilarea datelor sau să le dezactivați pe cele deja selectate.</span><span class="sxs-lookup"><span data-stu-id="16e87-158">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   
