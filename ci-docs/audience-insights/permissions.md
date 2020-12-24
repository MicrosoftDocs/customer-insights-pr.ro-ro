---
title: Gestionare permisiuni utilizator
description: Aflați mai multe despre permisiuni și roluri de utilizator.
ms.date: 10/27/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7de78c0ef71ec5b83870d396de36a7dcabbd14e5
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689235"
---
# <a name="user-permissions"></a>Permisiuni utilizator

Pagina **Permisiuni** este locul în care veți configura roluri și permisiuni pentru utilizarea detaliilor despre public.

Trebuie să aveți permisiuni de administrator pentru a vedea pagina. Pentru a accesa pagina de permisiuni în detaliile privind publicul, accesați **Administrator** > **Permisiuni**.

Există trei tipuri de roluri:

## <a name="viewer"></a>Spectator

- Explorați detalii și segmente în cadrul paginilor **Acasă** și **Segmente**.
- Căutați și filtrați profilurile clienților utilizând pagina **Clienți**. Câmpurile trebuie să poată fi căutate.
- Vizualizați și explorați pagina **Îmbogățire**.
- Explorați și exportați entitățile utilizând pagina **Entități**.
- Vizualizați starea proceselor sistemului folosind pagina **Sistem**.
- Exportați segmente din pagina **Segmente**.
- Instalați și utilizați tabloul de bord **Power BI Customer Insights**.

## <a name="contributor"></a>Colaborator

- Toate permisiunile disponibile pentru Spectator.
- Încărcați și transformați datele utilizând pagina **Surse de date**.
- Finalizați secțiunile *Unificarea datelor* (**Mapare**, **Potrivire** și **Îmbinare**) care au ca rezultat entitatea de profil a clientului unificat.
- Definiți **Relații** și **Activități**.
- Creați segmente folosind pagina **Segmente**.
- Creați măsuri folosind pagina **Măsuri**.
- Gestionați configurația și îmbogățiți profilurile clienților din pagina **Îmbogățire** (numai pentru îmbogățirea primară).

## <a name="administrator"></a>Administrator

- Toate permisiunile disponibile pentru Colaborator.
- Modificați setările pe pagina **Sistem**, inclusiv limbajul de lucru și programele de actualizare pentru procesele sistemului.
- Vizualizați și adăugați permisiunile folosind pagina **Permisiuni**.
- Setați definițiile căutare și filtrare pentru pagina Clienți utilizând pagina **Index de căutare și filtrare** (accesibilă prin pagina **Clienți**).
- Definiți destinațiile segmentului Dynamics 365 Sales utilizând pagina **Destinații export**.
- Gestionați configurația și îmbogățiți profilurile clienților din pagina **Îmbogățire** (pentru toate îmbogățirile).
- Instalați și utilizați **Program de completare card client**.
- Adăugați și utilizați **conectorul Power Apps**.
- Activați utilizarea [API-urilor Customer Insights](apis.md).

## <a name="assign-roles-and-permissions"></a>Alocați roluri și permisiuni

1. În detalii despre public, accesați **Admin** > **Permisiuni**.

1. Selectați **Adăugare utilizatori** pentru a deschide panoul **Adăugare/Editare permisiuni**.

1. Folosiți câmpul **Căutare** pentru a găsi utilizatorul sau grupul Azure Active Directory ale cărui permisiuni doriți să le ajustați. Alege un **Rol** de atribuit acelui utilizator sau grup.

1. Selectați **Salvare**. Mediul actual va fi distribuit automat utilizatorului sau membrilor grupului ale căror permisiuni le-ați modificat. Utilizatorii pot accesa aplicația Customer Insights și pot lucra în funcție de rolul specificat.

## <a name="view-current-permissions"></a>Vizualizați permisiunile curente

În detaliile despre public, accesați **Administrator** > **Permisiuni** pentru a vedea ce atribuții de roluri sunt active în prezent.

- Coloana **Tip** specifică un singur utilizator, grup sau aplicație. Sistemul acceptă utilizatori individuali și grupuri.
- Rolurile sunt specificate la coloana **Rol**.
- Selectați orice titlu de coloană pentru a sorta rezultatele după valoarea coloanei respective.
- Utilizați câmpul **Căutare** din partea de sus a paginii pentru a localiza anumiți utilizatori.