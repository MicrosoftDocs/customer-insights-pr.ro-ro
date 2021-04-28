---
title: Exportați datele Customer Insights către DotDigital
description: Aflați cum să configurați conexiunea și să exportați la DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 235bcdfa4a7c4c1a382778bd4f66c1a9f5b7beb1
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759974"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="44f88-103">Exportați listele de segmente în DotDigital (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="44f88-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="44f88-104">Exportați segmente de profiluri de clienți unificate în agende DotDigital și folosiți-le pentru campanii, marketing prin e-mail și pentru a crea segmente de clienți cu DotDigital.</span><span class="sxs-lookup"><span data-stu-id="44f88-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="44f88-105">Cerințe preliminare pentru o conexiune</span><span class="sxs-lookup"><span data-stu-id="44f88-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="44f88-106">Aveți un [cont DotDigital](https://dotdigital.com/) și acreditările de administrator corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="44f88-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="44f88-107">Există agende în DotDigital și ID-urile corespunzătoare.</span><span class="sxs-lookup"><span data-stu-id="44f88-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="44f88-108">ID-ul poate fi găsit în adresa URL atunci când selectați și deschideți o agendă.</span><span class="sxs-lookup"><span data-stu-id="44f88-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="44f88-109">Pentru mai multe informații, consultați [Agende DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="44f88-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="44f88-110">Aveți [segmente configurate](segments.md) în Detalii despre audiență.</span><span class="sxs-lookup"><span data-stu-id="44f88-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="44f88-111">Profilurile de clienți unificate din segmentele exportate conțin un câmp care reprezintă o adresă de e-mail.</span><span class="sxs-lookup"><span data-stu-id="44f88-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="44f88-112">Limitări cunoscute</span><span class="sxs-lookup"><span data-stu-id="44f88-112">Known limitations</span></span>

- <span data-ttu-id="44f88-113">Până la 1 milion de profiluri per export către DotDigital.</span><span class="sxs-lookup"><span data-stu-id="44f88-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="44f88-114">Exportul către DotDigital este limitat la segmente.</span><span class="sxs-lookup"><span data-stu-id="44f88-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="44f88-115">Exportul de segmente cu un total de 1 milion de profiluri poate dura până la 3 ore din cauza limitărilor din partea furnizorului.</span><span class="sxs-lookup"><span data-stu-id="44f88-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="44f88-116">Numărul de profiluri pe care le puteți exporta către DotDigital este dependent și limitat de contractul dvs. cu DotDigital.</span><span class="sxs-lookup"><span data-stu-id="44f88-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="44f88-117">Configurarea conexiunii la DotDigital</span><span class="sxs-lookup"><span data-stu-id="44f88-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="44f88-118">Salt la **Administrator** > **Conexiuni**.</span><span class="sxs-lookup"><span data-stu-id="44f88-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="44f88-119">Selectați **Adăugați conexiune** și alegeți **DotDigital** pentru a configura conexiunea.</span><span class="sxs-lookup"><span data-stu-id="44f88-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="44f88-120">Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**.</span><span class="sxs-lookup"><span data-stu-id="44f88-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="44f88-121">Numele și tipul conexiunii descriu această conexiune.</span><span class="sxs-lookup"><span data-stu-id="44f88-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="44f88-122">Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.</span><span class="sxs-lookup"><span data-stu-id="44f88-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="44f88-123">Alegeți cine poate utiliza această conexiune.</span><span class="sxs-lookup"><span data-stu-id="44f88-123">Choose who can use this connection.</span></span> <span data-ttu-id="44f88-124">Dacă nu luați nicio măsură, valoarea implicită va fi Administratori.</span><span class="sxs-lookup"><span data-stu-id="44f88-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="44f88-125">Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="44f88-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="44f88-126">Introduceți **numele de utilizator și parola DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="44f88-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="44f88-127">Introduceți **[ID-ul agendei DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="44f88-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="44f88-128">Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.</span><span class="sxs-lookup"><span data-stu-id="44f88-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="44f88-129">Selectați **Conectare** pentru a inițializa conexiunea la DotDigital.</span><span class="sxs-lookup"><span data-stu-id="44f88-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="44f88-130">Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="44f88-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="44f88-131">Selectați **Salvare** pentru a finaliza conexiunea.</span><span class="sxs-lookup"><span data-stu-id="44f88-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="44f88-132">Configurați un export</span><span class="sxs-lookup"><span data-stu-id="44f88-132">Configure an export</span></span>

<span data-ttu-id="44f88-133">Puteți configura acest export dacă aveți acces la o conexiune de acest tip.</span><span class="sxs-lookup"><span data-stu-id="44f88-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="44f88-134">Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="44f88-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="44f88-135">Faceți salt la **Date** > **Exporturi**.</span><span class="sxs-lookup"><span data-stu-id="44f88-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="44f88-136">Pentru a crea un nou export, selectați **Adăugare destinație**.</span><span class="sxs-lookup"><span data-stu-id="44f88-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="44f88-137">În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea DotDigital.</span><span class="sxs-lookup"><span data-stu-id="44f88-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="44f88-138">Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.</span><span class="sxs-lookup"><span data-stu-id="44f88-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="44f88-139">În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul din profilul dvs. de client unificat care reprezintă adresa de e-mail a unui client.</span><span class="sxs-lookup"><span data-stu-id="44f88-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="44f88-140">Repetați aceiași pași pentru alte câmpuri opționale, cum ar fi **Prenume**, **Nume de familie**, **Nume complet**, **Gen**, și **Cod poștal**.</span><span class="sxs-lookup"><span data-stu-id="44f88-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="44f88-141">Selectați segmentele pe care doriți să le exportați.</span><span class="sxs-lookup"><span data-stu-id="44f88-141">Select the segments you want to export.</span></span> <span data-ttu-id="44f88-142">Puteți exporta până la 1 milion de profiluri de client în total către DotDigital.</span><span class="sxs-lookup"><span data-stu-id="44f88-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="44f88-143">Selectați **Salvare**.</span><span class="sxs-lookup"><span data-stu-id="44f88-143">Select **Save**.</span></span>

<span data-ttu-id="44f88-144">Salvarea unui export nu se execută imediat.</span><span class="sxs-lookup"><span data-stu-id="44f88-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="44f88-145">Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="44f88-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="44f88-146">Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="44f88-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="44f88-147">În DotDigital, puteți găsi acum segmentele dvs. în [Agendele DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="44f88-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="44f88-148">Confidențialitatea și conformitatea datelor</span><span class="sxs-lookup"><span data-stu-id="44f88-148">Data privacy and compliance</span></span>

<span data-ttu-id="44f88-149">Când activați Dynamics 365 Customer Insights pentru a transmite date către DotDigital, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal.</span><span class="sxs-lookup"><span data-stu-id="44f88-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="44f88-150">Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că DotDigital îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți.</span><span class="sxs-lookup"><span data-stu-id="44f88-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="44f88-151">Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="44f88-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="44f88-152">Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.</span><span class="sxs-lookup"><span data-stu-id="44f88-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
