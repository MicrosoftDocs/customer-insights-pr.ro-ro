---
title: Îmbogățire cu importul particularizat SFTP
description: Informații generale despre îmbogățirea particularizată a importului SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304665"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="dd46f-103">Îmbogățiți profilurile clienților cu date particularizate (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="dd46f-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="dd46f-104">Importul particularizat Secure File Transfer Protocol (SFTP) vă permite să importați date care nu trebuie să treacă prin procesul de unificare a datelor.</span><span class="sxs-lookup"><span data-stu-id="dd46f-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="dd46f-105">Este un mod flexibil, sigur și ușor de a vă obține datele.</span><span class="sxs-lookup"><span data-stu-id="dd46f-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="dd46f-106">Importul particularizat SFTP poate fi utilizat în combinație cu [exportul SFTP](export-sftp.md) care vă permite să exportați datele de profil ale clienților necesare pentru îmbogățire.</span><span class="sxs-lookup"><span data-stu-id="dd46f-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="dd46f-107">Datele pot fi apoi procesate și îmbogățite, iar importul personalizat SFTP poate fi utilizat pentru a readuce datele îmbogățite înapoi la capacitatea de detalii despre public a Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="dd46f-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dd46f-108">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="dd46f-108">Prerequisites</span></span>

<span data-ttu-id="dd46f-109">Pentru a configura importul particularizat SFTP, trebuie îndeplinite următoarele condiții prealabile:</span><span class="sxs-lookup"><span data-stu-id="dd46f-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="dd46f-110">Aveți numele fișierului și locația (calea) fișierului de importat pe gazda SFTP.</span><span class="sxs-lookup"><span data-stu-id="dd46f-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="dd46f-111">Există un fișier *model.json* care specifică [schema Common Data Model](/common-data-model/) pentru ca datele să fie importate.</span><span class="sxs-lookup"><span data-stu-id="dd46f-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="dd46f-112">Acest fișier trebuie să fie în același director cu fișierul de importat.</span><span class="sxs-lookup"><span data-stu-id="dd46f-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="dd46f-113">O conexiune SFTP a fost deja configurată de un administrator *sau* aveți permisiuni de [administrator](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="dd46f-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="dd46f-114">Veți avea nevoie de acreditările utilizatorului, adresa URL și numărul de port pentru locația SFTP de unde doriți să importați date.</span><span class="sxs-lookup"><span data-stu-id="dd46f-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="dd46f-115">Configurați importul</span><span class="sxs-lookup"><span data-stu-id="dd46f-115">Configure the import</span></span>

1. <span data-ttu-id="dd46f-116">Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**.</span><span class="sxs-lookup"><span data-stu-id="dd46f-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="dd46f-117">În **dala de import particularizat SFTP**, selectați **Îmbogățiți datele mele** și apoi selectați **Începeți**.</span><span class="sxs-lookup"><span data-stu-id="dd46f-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Dala import particularizat SFTP":::

1. <span data-ttu-id="dd46f-119">Selectați o [conexiune](connections.md) din lista derulantă.</span><span class="sxs-lookup"><span data-stu-id="dd46f-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="dd46f-120">Contactați un administrator dacă nu este disponibilă nicio conexiune.</span><span class="sxs-lookup"><span data-stu-id="dd46f-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="dd46f-121">Dacă sunteți administrator, puteți crea o conexiune selectând **Adăugare conexiune** și alegând **Importul particularizat SFTP** din lista verticală.</span><span class="sxs-lookup"><span data-stu-id="dd46f-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="dd46f-122">Selectați **Conectați-vă la import particularizat** pentru a selecta conexiunea.</span><span class="sxs-lookup"><span data-stu-id="dd46f-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="dd46f-123">Selectați **Următorul** și introduceți **Cale** și **Nume de fișier** din fișierul de date pe care doriți să îl importați.</span><span class="sxs-lookup"><span data-stu-id="dd46f-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Captură de ecran la introducerea locației datelor.":::

1. <span data-ttu-id="dd46f-125">Selectați **Următorul** și furnizați un nume pentru îmbogățire și un nume pentru entitatea de ieșire.</span><span class="sxs-lookup"><span data-stu-id="dd46f-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="dd46f-126">Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.</span><span class="sxs-lookup"><span data-stu-id="dd46f-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="dd46f-127">Configurați conexiunea pentru importul particularizat SFTP</span><span class="sxs-lookup"><span data-stu-id="dd46f-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="dd46f-128">Trebuie să fiți administrator pentru a configura conexiunile.</span><span class="sxs-lookup"><span data-stu-id="dd46f-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="dd46f-129">Selectați **Adăugați conexiune** la configurarea unei îmbogățiri *sau* mergeți la **Administrator** > **Conexiuni** și selectați **Configurare** pe dala Import particularizat.</span><span class="sxs-lookup"><span data-stu-id="dd46f-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="dd46f-130">Introduceți un nume pentru conexiune în caseta **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="dd46f-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="dd46f-131">Introduceți un nume de utilizator, o parolă și o adresă URL gazdă valide pentru serverul SFTP pe care se află datele de importat.</span><span class="sxs-lookup"><span data-stu-id="dd46f-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="dd46f-132">Analizați și acordați-vă consimțământul pentru **Confidențialitatea și conformitatea datelor** prin selectarea casetei de selectare **Sunt de acord**.</span><span class="sxs-lookup"><span data-stu-id="dd46f-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="dd46f-133">Selectați **Verificare** pentru a valida configurația.</span><span class="sxs-lookup"><span data-stu-id="dd46f-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="dd46f-134">După finalizarea verificării, conexiunea poate fi salvată selectând **Salvați**.</span><span class="sxs-lookup"><span data-stu-id="dd46f-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dd46f-135">![Experian pagină de configurare a conexiunii](media/enrichment-SFTP-connection.png "Experian pagină de configurare a conexiunii")</span><span class="sxs-lookup"><span data-stu-id="dd46f-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="dd46f-136">Se definesc mapările de câmp</span><span class="sxs-lookup"><span data-stu-id="dd46f-136">Defining field mappings</span></span> 

<span data-ttu-id="dd46f-137">Directorul care conține fișierul de importat pe serverul SFTP trebuie să conțină și un fișier *model.json*.</span><span class="sxs-lookup"><span data-stu-id="dd46f-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="dd46f-138">Acest fișier definește schema de utilizat pentru importul datelor.</span><span class="sxs-lookup"><span data-stu-id="dd46f-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="dd46f-139">Schema trebuie utilizată [Common Data Model](/common-data-model/) pentru a specifica maparea câmpului.</span><span class="sxs-lookup"><span data-stu-id="dd46f-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="dd46f-140">Un exemplu simplu de fișier model.json arată astfel:</span><span class="sxs-lookup"><span data-stu-id="dd46f-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="dd46f-141">Rezultate de îmbogățire</span><span class="sxs-lookup"><span data-stu-id="dd46f-141">Enrichment results</span></span>

<span data-ttu-id="dd46f-142">Pentru a începe procesul de îmbogățire, selectați **Rulare** din bara de comenzi.</span><span class="sxs-lookup"><span data-stu-id="dd46f-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="dd46f-143">De asemenea, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei [reîmprospătări programate](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dd46f-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dd46f-144">Timpul de procesare va depinde de mărimea datelor de importat și de conexiunea la serverul SFTP.</span><span class="sxs-lookup"><span data-stu-id="dd46f-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="dd46f-145">După finalizarea procesului de îmbogățire, puteți examina datele de îmbogățire particularizate nou importate în secțiunea **Îmbogățirile mele**.</span><span class="sxs-lookup"><span data-stu-id="dd46f-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="dd46f-146">În plus, veți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.</span><span class="sxs-lookup"><span data-stu-id="dd46f-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="dd46f-147">Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.</span><span class="sxs-lookup"><span data-stu-id="dd46f-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dd46f-148">Pașii următori</span><span class="sxs-lookup"><span data-stu-id="dd46f-148">Next steps</span></span>

<span data-ttu-id="dd46f-149">Creați în plus față de datele îmbogățite ale clienților.</span><span class="sxs-lookup"><span data-stu-id="dd46f-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="dd46f-150">Creați [segmente](segments.md) și [măsuri](measures.md), și [exportați datele](export-destinations.md) pentru a oferi clienților dvs. experiențe particularizate.</span><span class="sxs-lookup"><span data-stu-id="dd46f-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
