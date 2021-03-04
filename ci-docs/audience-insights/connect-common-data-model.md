---
title: Conectați datele Common Data Model la un cont Azure Data Lake
description: Lucrați cu datele Common Data Model folosind Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 247e4d9c47ff2373065ebf3c6d554323e45a120b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267875"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="fee92-103">Conectați-vă la un folder Common Data Model folosind un cont Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="fee92-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="fee92-104">Acest articol oferă informații despre cum să ingerați date dintr-un director Common Data Model folosindu-vă contul Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="fee92-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="fee92-105">Considerații importante</span><span class="sxs-lookup"><span data-stu-id="fee92-105">Important considerations</span></span>

- <span data-ttu-id="fee92-106">Datele din Azure Data Lake trebuie să urmeze standardul Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="fee92-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="fee92-107">Alte formate nu sunt acceptate în acest moment.</span><span class="sxs-lookup"><span data-stu-id="fee92-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="fee92-108">Ingestia de date acceptă exclusiv conturi Azure Data Lake Storage *Gen2*.</span><span class="sxs-lookup"><span data-stu-id="fee92-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="fee92-109">Nu puteți utiliza conturile Azure Data Lake Storage Gen1 pentru a ingera date.</span><span class="sxs-lookup"><span data-stu-id="fee92-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="fee92-110">Pentru a vă autentifica cu o entitate principală de serviciu Azure, asigurați-vă că este configurat în entitatea găzduită.</span><span class="sxs-lookup"><span data-stu-id="fee92-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="fee92-111">pentru mai multe informații, consultați [Conectați detaliile privind publicul la un cont Azure Data Lake Storage Gen2 cu o entitate principală de serviciu Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="fee92-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="fee92-112">Azure Data Lake la care doriți să vă conectați și să ingerați date trebuie să fie în aceeași regiune Azure ca și mediul Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fee92-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="fee92-113">Conexiunile la un director Common Data Model dintr-un data lake dintr-o altă regiune Azure nu sunt acceptate.</span><span class="sxs-lookup"><span data-stu-id="fee92-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="fee92-114">Pentru a afla regiunea Azure a mediului, accesați **Administrator** > **Sistem** > **Despre** în Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="fee92-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="fee92-115">Datele stocate în serviciile online pot fi stocate într-o locație diferită de locul în care sunt procesate sau stocate datele în Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fee92-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="fee92-116"> Prin importul sau conectarea la datele stocate în servicii online, sunteți de acord că datele pot fi transferate și stocate cu Dynamics 365 Customer Insights. [Aflați mai multe la Centrul de autorizare Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="fee92-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="fee92-117">Conectare la un folder Common Data Model</span><span class="sxs-lookup"><span data-stu-id="fee92-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="fee92-118">În Detalii despre audiență, accesați **Date** > **Surse de date**.</span><span class="sxs-lookup"><span data-stu-id="fee92-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="fee92-119">Selectați **Adăugați sursa de date**.</span><span class="sxs-lookup"><span data-stu-id="fee92-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="fee92-120">Selectați **Conectare la un director Common Data Model**, introduceți un **Nume** pentru sursa de date și selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="fee92-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="fee92-121">Recomandări de nume:</span><span class="sxs-lookup"><span data-stu-id="fee92-121">Name guidelines:</span></span> 
   - <span data-ttu-id="fee92-122">Începeți cu o literă.</span><span class="sxs-lookup"><span data-stu-id="fee92-122">Start with a letter.</span></span>
   - <span data-ttu-id="fee92-123">Folosiți numai litere și cifre.</span><span class="sxs-lookup"><span data-stu-id="fee92-123">Use letters and numbers only.</span></span> <span data-ttu-id="fee92-124">Nu sunt permise caracterele speciale și spațiile.</span><span class="sxs-lookup"><span data-stu-id="fee92-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="fee92-125">Folosiți între 3 și 64 de caractere.</span><span class="sxs-lookup"><span data-stu-id="fee92-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="fee92-126">Puteți alege între utilizarea unei opțiuni bazate pe resurse și o opțiune bazată pe abonament pentru autentificare.</span><span class="sxs-lookup"><span data-stu-id="fee92-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="fee92-127">pentru mai multe informații, consultați [Conectați detaliile privind publicul la un cont Azure Data Lake Storage Gen2 cu o entitate principală de serviciu Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="fee92-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="fee92-128">Introduceți informația **Recipient** și selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="fee92-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fee92-129">![Casetă de dialog pentru a introduce noi detalii de conexiune pentru Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="fee92-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="fee92-130">Aveți nevoie de unul dintre următoarele roluri, fie la container, fie la contul de stocare menționat mai sus, pentru a vă putea conecta la și crea o sursă de date:</span><span class="sxs-lookup"><span data-stu-id="fee92-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="fee92-131">Cititor de date Blob de stocare</span><span class="sxs-lookup"><span data-stu-id="fee92-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="fee92-132">Proprietar de date Blob de stocare</span><span class="sxs-lookup"><span data-stu-id="fee92-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="fee92-133">Contribuitor de date blob de stocare</span><span class="sxs-lookup"><span data-stu-id="fee92-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="fee92-134">În dialogul **Selectați un director Common Data Model**, selectați fișierul model.json sau manifest.json din care să importați date și selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="fee92-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="fee92-135">Orice fișier model.json sau manifest.json asociat cu o altă sursă de date din mediu nu va apărea în listă.</span><span class="sxs-lookup"><span data-stu-id="fee92-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="fee92-136">Veți obține o listă de entități disponibile în fișierul model.json sau manifest.json selectat.</span><span class="sxs-lookup"><span data-stu-id="fee92-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="fee92-137">Puteți analiza și selecta din lista de entități disponibile și selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="fee92-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="fee92-138">Toate entitățile selectate vor fi ingerate din noua sursă de date.</span><span class="sxs-lookup"><span data-stu-id="fee92-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fee92-139">![Casetă de dialog care arată o listă de entități dintr-un fișier model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="fee92-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="fee92-140">Indicați cu ce entități de date doriți să activați profilarea datelor și selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="fee92-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="fee92-141">Profilarea datelor permite analiza și alte capacități.</span><span class="sxs-lookup"><span data-stu-id="fee92-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="fee92-142">Puteți selecta întreaga entitate, care selectează toate atributele din entitate, sau puteți selecta anumite atribute dorite.</span><span class="sxs-lookup"><span data-stu-id="fee92-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="fee92-143">În mod implicit, nu este activată nicio entitate pentru profilarea datelor.</span><span class="sxs-lookup"><span data-stu-id="fee92-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fee92-144">![Casetă de dialog care prezintă o profilare a datelor](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="fee92-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="fee92-145">După salvarea selecțiilor, se deschide pagina **Surse de date**.</span><span class="sxs-lookup"><span data-stu-id="fee92-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="fee92-146">Acum ar trebui să vedeți conexiunea folderului Common Data Model ca o sursă de date.</span><span class="sxs-lookup"><span data-stu-id="fee92-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="fee92-147">Un fișier model.json sau manifest.json se poate asocia doar cu o singură sursă de date în același mediu.</span><span class="sxs-lookup"><span data-stu-id="fee92-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="fee92-148">Cu toate acestea, același fișier model.json sau manifest.json poate fi utilizat pentru surse de date în medii multiple.</span><span class="sxs-lookup"><span data-stu-id="fee92-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="fee92-149">Editați o sursă de date a folderului Common Data Model</span><span class="sxs-lookup"><span data-stu-id="fee92-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="fee92-150">Puteți actualiza cheia de acces pentru contul de stocare care conține directorul Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="fee92-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="fee92-151">De asemenea, puteți schimba fișierul model.json sau manifest.json.</span><span class="sxs-lookup"><span data-stu-id="fee92-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="fee92-152">Pentru a conecta la un container diferit de contul de stocare sau să modificați numele contului, trebuie să [creați o nouă conexiune la sursa de date](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="fee92-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="fee92-153">În Detalii despre audiență, accesați **Date** > **Surse de date**.</span><span class="sxs-lookup"><span data-stu-id="fee92-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="fee92-154">Lângă sursa de date pe care doriți să o actualizați, selectați elipsa.</span><span class="sxs-lookup"><span data-stu-id="fee92-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="fee92-155">Selectați opțiunea **Editare** din listă.</span><span class="sxs-lookup"><span data-stu-id="fee92-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="fee92-156">Opțional, actualizați **Cheie de acces** și selectați **Următorul**.</span><span class="sxs-lookup"><span data-stu-id="fee92-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Dialog pentru a edita și a actualiza o cheie de acces pentru o sursă de date existentă](media/edit-access-key.png)

5. <span data-ttu-id="fee92-158">Opțional, puteți actualiza de la o conexiune cu cheie de cont la o conexiune bazată pe resurse sau bazată pe abonament.</span><span class="sxs-lookup"><span data-stu-id="fee92-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="fee92-159">pentru mai multe informații, consultați [Conectați detaliile privind publicul la un cont Azure Data Lake Storage Gen2 cu o entitate principală de serviciu Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="fee92-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="fee92-160">Nu puteți schimba informațiile legate de **Recipient** la actualizarea conexiunii.</span><span class="sxs-lookup"><span data-stu-id="fee92-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Casetă de dialog pentru a introduce detaliile conexiunii pentru Azure Data Lake la un cont de stocare existent](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="fee92-162">Aveți nevoie de unul dintre următoarele roluri, fie la container, fie la contul de stocare menționat mai sus, pentru a vă putea conecta la și crea o sursă de date:</span><span class="sxs-lookup"><span data-stu-id="fee92-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="fee92-163">Cititor de date Blob de stocare</span><span class="sxs-lookup"><span data-stu-id="fee92-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="fee92-164">Proprietar de date Blob de stocare</span><span class="sxs-lookup"><span data-stu-id="fee92-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="fee92-165">Contribuitor de date blob de stocare</span><span class="sxs-lookup"><span data-stu-id="fee92-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="fee92-166">Opțional, alegeți un fișier model.json sau manifest.json diferit cu un set diferit de entități din container.</span><span class="sxs-lookup"><span data-stu-id="fee92-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="fee92-167">Opțional, puteți selecta entități suplimentare de ingerat.</span><span class="sxs-lookup"><span data-stu-id="fee92-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="fee92-168">De asemenea, puteți elimina orice entități deja selectate dacă nu există dependențe.</span><span class="sxs-lookup"><span data-stu-id="fee92-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="fee92-169">Dacă există dependențe de fișierul model.json sau manifest.json existent și setul de entități, veți vedea un mesaj de eroare și nu puteți selecta un fișier model.json sau manifest.json diferit.</span><span class="sxs-lookup"><span data-stu-id="fee92-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="fee92-170">Eliminați aceste dependențe înainte de a schimba fișierul model.json sau manifest.json sau creați un nou sursă de date cu fișierul model.json sau manifest.json pe care doriți să îl utilizați pentru a evita eliminarea dependențelor.</span><span class="sxs-lookup"><span data-stu-id="fee92-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="fee92-171">Opțional, puteți selecta atribute sau entități suplimentare pentru a activa profilarea datelor sau să le dezactivați pe cele deja selectate.</span><span class="sxs-lookup"><span data-stu-id="fee92-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]