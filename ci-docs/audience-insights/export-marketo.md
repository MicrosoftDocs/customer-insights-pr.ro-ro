---
title: Exportați datele Customer Insights către Marketo
description: Aflați cum să configurați conexiunea și să exportați la Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059331"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="0983d-103">Exportați segmente către Marketo (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="0983d-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="0983d-104">Exportați segmentele profilurilor client unificate pentru a genera campanii, a oferi marketing prin e-mail și a folosi anumite grupuri de clienți cu Marketo.</span><span class="sxs-lookup"><span data-stu-id="0983d-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="0983d-105">Cerințe preliminare pentru conexiune</span><span class="sxs-lookup"><span data-stu-id="0983d-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="0983d-106">Aveți un [cont Marketo](https://login.marketo.com/) și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="0983d-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0983d-107">Există liste în Marketo și ID-urile corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="0983d-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="0983d-108">Pentru informații suplimentare, consultați [Liste Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="0983d-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="0983d-109">Aveți [segmente configurate](segments.md).</span><span class="sxs-lookup"><span data-stu-id="0983d-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="0983d-110">Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.</span><span class="sxs-lookup"><span data-stu-id="0983d-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0983d-111">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="0983d-111">Known limitations</span></span>

- <span data-ttu-id="0983d-112">Până la 1 milion de profiluri per export către Marketo.</span><span class="sxs-lookup"><span data-stu-id="0983d-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="0983d-113">Exportul către Marketo este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="0983d-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="0983d-114">Exportul de segmente cu un total de 1 milion de profiluri poate dura până la 3 ore.</span><span class="sxs-lookup"><span data-stu-id="0983d-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="0983d-115">Numărul de profiluri pe care le puteți exporta către Marketo este dependent și limitat de contractul dvs. cu Marketo.</span><span class="sxs-lookup"><span data-stu-id="0983d-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="0983d-116">Configurarea conexiunii la Marketo</span><span class="sxs-lookup"><span data-stu-id="0983d-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="0983d-117">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="0983d-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0983d-118">Selectați **Adăugați conexiune** și alegeți **Marketo** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="0983d-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="0983d-119">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="0983d-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0983d-120">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="0983d-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0983d-121">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="0983d-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0983d-122">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="0983d-122">Choose who can use this connection.</span></span> <span data-ttu-id="0983d-123">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="0983d-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0983d-124">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0983d-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0983d-125">Introduceți **[ID-ul de client Marketo, secretul clientului și Numele de gazdă punct final REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="0983d-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="0983d-126">Numele de gazdă REST Endpoint este doar numele gazdei, fără `https://`.</span><span class="sxs-lookup"><span data-stu-id="0983d-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="0983d-127">Exemplu:`xyz-abc-123.mktorest.com`.</span><span class="sxs-lookup"><span data-stu-id="0983d-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="0983d-128">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor** și selectați **Conectare** pentru a inițializa conexiunea la Marketo.</span><span class="sxs-lookup"><span data-stu-id="0983d-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="0983d-129">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0983d-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0983d-130">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="0983d-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0983d-131">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="0983d-131">Configure an export</span></span>

<span data-ttu-id="0983d-132">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="0983d-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0983d-133">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0983d-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0983d-134">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="0983d-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0983d-135">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="0983d-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0983d-136">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Marketo.</span><span class="sxs-lookup"><span data-stu-id="0983d-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="0983d-137">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="0983d-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0983d-138">Introduceți **[ID-ul listă Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span><span class="sxs-lookup"><span data-stu-id="0983d-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="0983d-139">ID-ul listei este o valoare pur numerică.</span><span class="sxs-lookup"><span data-stu-id="0983d-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="0983d-140">De exemplu, dacă ID-ul listei Marketo este ST12345A7, eliminați caracterul înainte și după cifre și introduceți `12345`.</span><span class="sxs-lookup"><span data-stu-id="0983d-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="0983d-141">În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="0983d-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="0983d-142">Opțional, puteți exporta **Prenume**, **Nume de familie**, **Oraș**, **Stat** și **Țară/Regiune** pentru a crea e-mailuri mai personalizate.</span><span class="sxs-lookup"><span data-stu-id="0983d-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="0983d-143">Selectați **Adăugare atribut** pentru a mapa aceste câmpuri.</span><span class="sxs-lookup"><span data-stu-id="0983d-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="0983d-144">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="0983d-144">Select the segments you want to export.</span></span> <span data-ttu-id="0983d-145">Puteți exporta până la 1 milion de profiluri de client în total către Marketo.</span><span class="sxs-lookup"><span data-stu-id="0983d-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="0983d-146">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="0983d-146">Select **Save**.</span></span>

<span data-ttu-id="0983d-147">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="0983d-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0983d-148">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0983d-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0983d-149">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0983d-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="0983d-150">În Marketo, puteți găsi acum segmentele dvs. sub [Listele Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="0983d-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0983d-151">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="0983d-151">Data privacy and compliance</span></span>

<span data-ttu-id="0983d-152">Când activați Dynamics 365 Customer Insights pentru a transmite date către Marketo, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="0983d-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0983d-153">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Marketo îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="0983d-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0983d-154">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0983d-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0983d-155">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="0983d-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
