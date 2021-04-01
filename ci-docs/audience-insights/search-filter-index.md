---
title: Căutați și filtrați profiluri de client
description: Găsiți rapid informații despre profilurile de clienți unificate și filtrați pentru atributele specificate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597158"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="4e355-103">Profilurile clienților: indexul de căutare și filtrare</span><span class="sxs-lookup"><span data-stu-id="4e355-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="4e355-104">Rezultatul unificării datelor clientului dvs. este o entitate de profil pentru clienți care oferă o vizualizare unificată în baza dvs. totală de clienți.</span><span class="sxs-lookup"><span data-stu-id="4e355-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="4e355-105">Pentru [găsirea rapidă a informațiilor despre un anumit client sau grup de clienți](customer-profiles.md), puteți configura capabilitățile **Căutare** și **Filtru** pe pagina **Clienți**.</span><span class="sxs-lookup"><span data-stu-id="4e355-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="4e355-106">Citiți mai departe pentru a afla cum pot edita administratorii atributele de pe pagina **Index de căutare și filtrare**, care sunt disponibile utilizatorilor pentru căutare și filtrare.</span><span class="sxs-lookup"><span data-stu-id="4e355-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e355-107">![Filtru de căutare](media/search-filter.png "Filtru de căutare")</span><span class="sxs-lookup"><span data-stu-id="4e355-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="4e355-108">Adăugați câmpuri și specificați atributele</span><span class="sxs-lookup"><span data-stu-id="4e355-108">Add fields and specify attributes</span></span>

<span data-ttu-id="4e355-109">Dacă este prima dată când definiți atribute căutabile ca administrator, trebuie să definiți mai întâi câmpurile indexate.</span><span class="sxs-lookup"><span data-stu-id="4e355-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="4e355-110">Vă sugerăm să alegeți toate atributele prin care utilizatorii pot căuta și filtra clienții pe pagina **Clienți**.</span><span class="sxs-lookup"><span data-stu-id="4e355-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="4e355-111">Puteți specifica doar atribute care există în entitatea Profil client pe care le-ați creat în timpul procesului de unificare a datelor.</span><span class="sxs-lookup"><span data-stu-id="4e355-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="4e355-112">Deschideți pagina **Clienți** și selectați **Index de căutare și filtrare**.</span><span class="sxs-lookup"><span data-stu-id="4e355-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="4e355-113">Selectați **+ Adăugare** pentru specificarea câmpurilor indexate.</span><span class="sxs-lookup"><span data-stu-id="4e355-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="4e355-114">Selectați atributele din lista pe care doriți să le adăugați ca câmpuri indexate.</span><span class="sxs-lookup"><span data-stu-id="4e355-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="4e355-115">Puteți adăuga întotdeauna mai multe atribute selectând **Adăugare**.</span><span class="sxs-lookup"><span data-stu-id="4e355-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="4e355-116">De asemenea, puteți elimina orice atribute selectate selectând simbolul **Eliminare**.</span><span class="sxs-lookup"><span data-stu-id="4e355-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="4e355-117">Explorați tabelul câmpurilor indexate pentru clienți</span><span class="sxs-lookup"><span data-stu-id="4e355-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="4e355-118">Următoarele informații sunt prezentate în tabel.</span><span class="sxs-lookup"><span data-stu-id="4e355-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="4e355-119">**Nume**: Reprezintă numele atributului așa cum apare în entitatea Profil client.</span><span class="sxs-lookup"><span data-stu-id="4e355-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="4e355-120">**Tip de date**: Specifică dacă tipul de date este un șir, un număr sau o dată.</span><span class="sxs-lookup"><span data-stu-id="4e355-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="4e355-121">**Inclus în căutare**: Specifică dacă acest atribut poate fi utilizat pentru căutarea clienților pe pagina **Clienți** folosind câmpul de **Căutare**.</span><span class="sxs-lookup"><span data-stu-id="4e355-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="4e355-122">**Adăugare filtru**: Control pentru a defini modul în care acest atribut poate fi utilizat pentru filtrare pe pagina **Clienți**.</span><span class="sxs-lookup"><span data-stu-id="4e355-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="4e355-123">Editarea opțiunilor de filtrare pentru un atribut dat</span><span class="sxs-lookup"><span data-stu-id="4e355-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="4e355-124">Meniul **Filtru** din pagina **Clienți** poate include un număr diferit de niveluri de atribute (de exemplu, diferite grupe de vârstă pentru filtrarea clienților).</span><span class="sxs-lookup"><span data-stu-id="4e355-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="4e355-125">Selectați **Adăugare filtru** pentru un atribut dat pe pagina **Indice de căutare și filtrare**.</span><span class="sxs-lookup"><span data-stu-id="4e355-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="4e355-126">Puteți defini numărul de rezultate și ordinea în care vor fi organizate.</span><span class="sxs-lookup"><span data-stu-id="4e355-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="4e355-127">În funcție de tipul de date al atributului, apare unul dintre următoarele panouri.</span><span class="sxs-lookup"><span data-stu-id="4e355-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="4e355-128">Atribute de tip string: specificați numărul de rezultate dorite pe panoul **Opțiuni filtru string** și politica de comandă prin care vor fi organizate.</span><span class="sxs-lookup"><span data-stu-id="4e355-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="4e355-129">Atribute de tip numeric: specificați inervalele incluse pe panoul **Opțiuni filtru număr** și politica de comandă prin care vor fi organizate.</span><span class="sxs-lookup"><span data-stu-id="4e355-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="4e355-130">Atribute de tip date: specificați inervalele incluse pe panoul **Opțiuni filtru date** și politica de comandă prin care vor fi organizate.</span><span class="sxs-lookup"><span data-stu-id="4e355-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="4e355-131">Selectați **Salvare** pentru a vă aplica modificările.</span><span class="sxs-lookup"><span data-stu-id="4e355-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="4e355-132">Selectați **Executare** odată ce sunteți gata să vă aplicați setările.</span><span class="sxs-lookup"><span data-stu-id="4e355-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4e355-133">Pașii următori</span><span class="sxs-lookup"><span data-stu-id="4e355-133">Next steps</span></span>

<span data-ttu-id="4e355-134">Accesați pagina **Clienți** pentru a căuta profiluri de clienți sau utilizați câmpurile indexate pentru a vedea un subset al tuturor profilurilor de clienți.</span><span class="sxs-lookup"><span data-stu-id="4e355-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]