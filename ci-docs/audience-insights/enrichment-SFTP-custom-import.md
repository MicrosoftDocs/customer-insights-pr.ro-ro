---
title: Îmbogățire cu importul particularizat SFTP
description: Informații generale despre îmbogățirea particularizată a importului SFTP.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595870"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="f8534-103">Îmbogățiți profilurile clienților cu date particularizate (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="f8534-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="f8534-104">Importul particularizat Secure File Transfer Protocol (SFTP) vă permite să importați date care nu trebuie să treacă prin procesul de unificare a datelor.</span><span class="sxs-lookup"><span data-stu-id="f8534-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="f8534-105">Este un mod flexibil, sigur și ușor de a vă obține datele.</span><span class="sxs-lookup"><span data-stu-id="f8534-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="f8534-106">Importul particularizat SFTP poate fi utilizat în combinație cu [exportul SFTP](export-sftp.md) care vă permite să exportați datele de profil ale clienților necesare pentru îmbogățire.</span><span class="sxs-lookup"><span data-stu-id="f8534-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="f8534-107">Datele pot fi apoi procesate, îmbogățite, iar importul particularizat SFTP poate fi utilizat pentru a readuce datele îmbogățite înapoi la capacitatea Detalii despre audiență a Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f8534-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f8534-108">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="f8534-108">Prerequisites</span></span>

<span data-ttu-id="f8534-109">Pentru a configura importul particularizat SFTP, trebuie îndeplinite următoarele condiții prealabile:</span><span class="sxs-lookup"><span data-stu-id="f8534-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f8534-110">Aveți acreditări de utilizator (nume de utilizator și parolă) pentru locația SFTP de unde vor fi importate datele.</span><span class="sxs-lookup"><span data-stu-id="f8534-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="f8534-111">Aveți adresa URL și numărul portului (de obicei 22) pentru gazda STFP.</span><span class="sxs-lookup"><span data-stu-id="f8534-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="f8534-112">Aveți numele fișierului și locația fișierului de importat pe gazda SFTP.</span><span class="sxs-lookup"><span data-stu-id="f8534-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="f8534-113">Există un fișier *model.json* care specifică schema pentru datele care urmează să fie importate.</span><span class="sxs-lookup"><span data-stu-id="f8534-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="f8534-114">Acest fișier trebuie să fie în același director cu fișierul de importat.</span><span class="sxs-lookup"><span data-stu-id="f8534-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="f8534-115">Aveți permisiune de [Administrator](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="f8534-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="f8534-116">Configurație</span><span class="sxs-lookup"><span data-stu-id="f8534-116">Configuration</span></span>

1. <span data-ttu-id="f8534-117">Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**.</span><span class="sxs-lookup"><span data-stu-id="f8534-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="f8534-118">Pe **Dala de import particularizat SFTP**, selectați **Doresc îmbogățirea datelor**.</span><span class="sxs-lookup"><span data-stu-id="f8534-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f8534-119">![Dala import particularizat SFTP](media/SFTP_Custom_Import_tile.png "Dala import particularizat SFTP")</span><span class="sxs-lookup"><span data-stu-id="f8534-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="f8534-120">Selectați **Începeți** și furnizați acreditările și adresa pentru serverul SFTP.</span><span class="sxs-lookup"><span data-stu-id="f8534-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="f8534-121">De exemplu, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="f8534-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="f8534-122">Introduceți numele fișierului care conține datele și calea către fișier de pe serverul SFTP dacă nu se află în folderul rădăcină.</span><span class="sxs-lookup"><span data-stu-id="f8534-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="f8534-123">Confirmați toate intrările selectând **Conectare la importul particularizat**.</span><span class="sxs-lookup"><span data-stu-id="f8534-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f8534-124">![Fișă configurare import particularizat SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Fișă configurare import particularizat SFTP")</span><span class="sxs-lookup"><span data-stu-id="f8534-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="f8534-125">Se definesc mapările de câmp</span><span class="sxs-lookup"><span data-stu-id="f8534-125">Defining field mappings</span></span> 

<span data-ttu-id="f8534-126">Directorul care conține fișierul de importat pe serverul SFTP trebuie să conțină și un fișier *model.json*.</span><span class="sxs-lookup"><span data-stu-id="f8534-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="f8534-127">Acest fișier definește schema de utilizat pentru importul datelor.</span><span class="sxs-lookup"><span data-stu-id="f8534-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="f8534-128">Schema trebuie să utilizeze [Common Data Model](/common-data-model/) pentru a specifica maparea câmpului.</span><span class="sxs-lookup"><span data-stu-id="f8534-128">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="f8534-129">Un exemplu simplu de fișier model.json arată astfel:</span><span class="sxs-lookup"><span data-stu-id="f8534-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="f8534-130">Rezultate de îmbogățire</span><span class="sxs-lookup"><span data-stu-id="f8534-130">Enrichment results</span></span>

<span data-ttu-id="f8534-131">Pentru a începe procesul de îmbogățire, selectați **Rulare** din bara de comenzi.</span><span class="sxs-lookup"><span data-stu-id="f8534-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f8534-132">De asemenea, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei [reîmprospătări programate](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f8534-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f8534-133">Timpul de procesare va depinde de mărimea datelor de importat și de conexiunea la serverul SFTP.</span><span class="sxs-lookup"><span data-stu-id="f8534-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="f8534-134">După finalizarea procesului de îmbogățire, puteți examina datele de îmbogățire particularizate nou importate în secțiunea **Îmbogățirile mele**.</span><span class="sxs-lookup"><span data-stu-id="f8534-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="f8534-135">În plus, veți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.</span><span class="sxs-lookup"><span data-stu-id="f8534-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f8534-136">Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.</span><span class="sxs-lookup"><span data-stu-id="f8534-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f8534-137">Pașii următori</span><span class="sxs-lookup"><span data-stu-id="f8534-137">Next steps</span></span>

<span data-ttu-id="f8534-138">Creați în plus față de datele îmbogățite ale clienților.</span><span class="sxs-lookup"><span data-stu-id="f8534-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f8534-139">Creați [segmente](segments.md), [măsuri](measures.md), și [exportați datele](export-destinations.md) pentru a oferi clienților dvs. experiențe personalizate.</span><span class="sxs-lookup"><span data-stu-id="f8534-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]