---
title: Robot pentru Microsoft Teams
description: Căutați profiluri unificate ale clienților în Microsoft Teams cu ajutorul unui robot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406695"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="3ffb6-103">Robot Teams pentru Dynamics 365 Customer Insights (previzualizare)</span><span class="sxs-lookup"><span data-stu-id="3ffb6-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="3ffb6-104">Conectați-vă cu Microsoft Teams pentru a permite unui robot să caute profiluri de clienți unificate în canalele Teams.</span><span class="sxs-lookup"><span data-stu-id="3ffb6-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3ffb6-105">![Robot Teams care afișează o înregistrare de client](media/teams-bot.png "Robot Teams care afișează o înregistrare de client")</span><span class="sxs-lookup"><span data-stu-id="3ffb6-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3ffb6-106">Cerințe preliminare</span><span class="sxs-lookup"><span data-stu-id="3ffb6-106">Prerequisites</span></span>

<span data-ttu-id="3ffb6-107">Pentru a configura și configura robotul, trebuie îndeplinite următoarele cerințe preliminare:</span><span class="sxs-lookup"><span data-stu-id="3ffb6-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="3ffb6-108">Există cel puțin o [sursă de date adăugată](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="3ffb6-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="3ffb6-109">[Procesul de unificare](data-unification.md) este complet.</span><span class="sxs-lookup"><span data-stu-id="3ffb6-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="3ffb6-110">Câmpurile sunt adăugate la [indexul de căutare și filtrare](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="3ffb6-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="3ffb6-111">Customer Insights și Teams sunt în aceeași organizație.</span><span class="sxs-lookup"><span data-stu-id="3ffb6-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="3ffb6-112">Configurați robotul</span><span class="sxs-lookup"><span data-stu-id="3ffb6-112">Configure the bot</span></span>

1. <span data-ttu-id="3ffb6-113">În Detalii despre audiență, accesați **Administrator** > **Export destinații**.</span><span class="sxs-lookup"><span data-stu-id="3ffb6-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="3ffb6-114">Pe fila Microsoft Teams, selectați **Configura**.</span><span class="sxs-lookup"><span data-stu-id="3ffb6-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="3ffb6-115">Sunteți redirecționat către zona **Aplicații** în Teams.</span><span class="sxs-lookup"><span data-stu-id="3ffb6-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="3ffb6-116">De asemenea, puteți deschide Teams și puteți selecta **Aplicații** în colțul din stânga jos sau [obțineți direct din AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).</span><span class="sxs-lookup"><span data-stu-id="3ffb6-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="3ffb6-117">Cautați **Customer Insights** și selectați aplicația.</span><span class="sxs-lookup"><span data-stu-id="3ffb6-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="3ffb6-118">Selectați **Adăugare**.</span><span class="sxs-lookup"><span data-stu-id="3ffb6-118">Select **Add**.</span></span>
1. <span data-ttu-id="3ffb6-119">După conectarea la Customer Insights în Teams, veți vedea un mesaj de bun venit și puteți începe.</span><span class="sxs-lookup"><span data-stu-id="3ffb6-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="3ffb6-120">Lucruri pe care le puteți face cu robotul</span><span class="sxs-lookup"><span data-stu-id="3ffb6-120">Things you can do with the bot</span></span>

<span data-ttu-id="3ffb6-121">Robotul oferă funcții de căutare pentru profiluri de clienți unificate.</span><span class="sxs-lookup"><span data-stu-id="3ffb6-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="3ffb6-122">Introduceți **căutare** urmat de un nume, adresă de e-mail sau orice alt câmp din profilul de client unificat care este adăugat la indexul de căutare și filtru.</span><span class="sxs-lookup"><span data-stu-id="3ffb6-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="3ffb6-123">Veți primi un card cu până la 15 câmpuri din profilul clientului rezultat.</span><span class="sxs-lookup"><span data-stu-id="3ffb6-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="3ffb6-124">Mai multe potriviri returnează o listă de rezultate în care puteți selecta un profil.</span><span class="sxs-lookup"><span data-stu-id="3ffb6-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="3ffb6-125">Puteți adăuga termenul de căutare în ghilimele duble pentru a căuta o potrivire exactă.</span><span class="sxs-lookup"><span data-stu-id="3ffb6-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="3ffb6-126">Dacă organizația dvs. menține mai multe medii Customer Insights în aceeași organizație, puteți introduce **switchinstance** pentru a alege la ce mediu doriți să conectați robotul.</span><span class="sxs-lookup"><span data-stu-id="3ffb6-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="3ffb6-127">Introduceți **ajutor** pentru a vedea o listă de comenzi disponibile pentru robot.</span><span class="sxs-lookup"><span data-stu-id="3ffb6-127">Enter **help** to see a list of available commands for the bot.</span></span>  