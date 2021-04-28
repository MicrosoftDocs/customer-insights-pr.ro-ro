---
title: Exportați datele Customer Insights către Marketo
description: Aflați cum să configurați conexiunea și să exportați la Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759836"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="9b3bd-103">Exportați segmente către Marketo (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="9b3bd-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="9b3bd-104">Exportați segmentele profilurilor client unificate pentru a genera campanii, a oferi marketing prin e-mail și a folosi anumite grupuri de clienți cu Marketo.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="9b3bd-105">Cerințe preliminare pentru conexiune</span><span class="sxs-lookup"><span data-stu-id="9b3bd-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="9b3bd-106">Aveți un [cont Marketo](https://login.marketo.com/) și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9b3bd-107">Există liste în Marketo și ID-urile corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="9b3bd-108">Pentru informații suplimentare, consultați [Liste Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="9b3bd-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="9b3bd-109">Aveți [segmente configurate](segments.md).</span><span class="sxs-lookup"><span data-stu-id="9b3bd-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="9b3bd-110">Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9b3bd-111">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="9b3bd-111">Known limitations</span></span>

- <span data-ttu-id="9b3bd-112">Până la 1 milion de profiluri per export către Marketo.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="9b3bd-113">Exportul către Marketo este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="9b3bd-114">Exportul de segmente cu un total de 1 milion de profiluri poate dura până la 3 ore.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="9b3bd-115">Numărul de profiluri pe care le puteți exporta către Marketo este dependent și limitat de contractul dvs. cu Marketo.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="9b3bd-116">Configurarea conexiunii la Marketo</span><span class="sxs-lookup"><span data-stu-id="9b3bd-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="9b3bd-117">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9b3bd-118">Selectați **Adăugați conexiune** și alegeți **Marketo** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="9b3bd-119">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9b3bd-120">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9b3bd-121">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9b3bd-122">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-122">Choose who can use this connection.</span></span> <span data-ttu-id="9b3bd-123">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="9b3bd-124">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9b3bd-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9b3bd-125">Introduceți **[ID-ul de client Marketo, secretul clientului și Numele de gazdă punct final REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="9b3bd-126">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor** și selectați **Conectare** pentru a inițializa conexiunea la Marketo.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="9b3bd-127">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="9b3bd-128">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="9b3bd-129">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="9b3bd-129">Configure an export</span></span>

<span data-ttu-id="9b3bd-130">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9b3bd-131">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9b3bd-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9b3bd-132">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9b3bd-133">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9b3bd-134">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Marketo.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="9b3bd-135">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="9b3bd-136">Introduceți **[ID-ul listă Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="9b3bd-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="9b3bd-137">În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="9b3bd-138">Opțional, puteți exporta **Prenume**, **Nume de familie**, **Oraș**, **Stat** și **Țară/Regiune** pentru a crea e-mailuri mai personalizate.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="9b3bd-139">Selectați **Adăugare atribut** pentru a mapa aceste câmpuri.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="9b3bd-140">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-140">Select the segments you want to export.</span></span> <span data-ttu-id="9b3bd-141">Puteți exporta până la 1 milion de profiluri de client în total către Marketo.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="9b3bd-142">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-142">Select **Save**.</span></span>

<span data-ttu-id="9b3bd-143">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9b3bd-144">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9b3bd-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9b3bd-145">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9b3bd-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="9b3bd-146">În Marketo, puteți găsi acum segmentele dvs. sub [Listele Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="9b3bd-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9b3bd-147">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="9b3bd-147">Data privacy and compliance</span></span>

<span data-ttu-id="9b3bd-148">Când activați Dynamics 365 Customer Insights pentru a transmite date către Marketo, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9b3bd-149">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Marketo îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9b3bd-150">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9b3bd-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9b3bd-151">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="9b3bd-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]