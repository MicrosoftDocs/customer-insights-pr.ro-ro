---
title: Gestionare permisiuni utilizator
description: Aflați mai multe despre permisiuni și roluri de utilizator.
ms.date: 02/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: 8022563f8994400b88389c20d7d661d9ea82bab1
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833737"
---
# <a name="user-permissions"></a>Permisiuni utilizator

The **Permisiuni** pagina este locul în care veți configura rolurile și permisiunile pentru utilizarea Customer Insights.

Trebuie să aveți permisiuni de administrator pentru a vedea pagina. Pentru a accesa pagina de permisiuni, accesați **Admin** > **Securitate** > **Utilizatori**.

Există trei tipuri de roluri:

## <a name="viewer"></a>Spectator

- Explorați detalii și segmente în cadrul paginilor **Acasă** și **Segmente**.
- Căutați și filtrați profilurile clienților utilizând pagina **Clienți**. Câmpurile trebuie să poată fi căutate.
- Vizualizați și explorați pagina **Îmbogățire**.
- Explorați și exportați entitățile utilizând pagina **Entități**.
- Vizualizați starea proceselor sistemului folosind pagina **Sistem**.
- Vizualizați exporturile în pagina **Exporturi**.
- Instalați și utilizați tabloul de bord **Power BI Customer Insights**.

## <a name="contributor"></a>Colaborator

- Toate permisiunile disponibile pentru Spectator.
- Încărcați și transformați datele utilizând pagina **Surse de date**.
- Complet ***Unificarea datelor** care au ca rezultat entitatea de profil unificat al clientului.
- Definiți **Relații** și **Activități**.
- Creați segmente folosind pagina **Segmente**.
- Creați măsuri folosind pagina **Măsuri**.
- Gestionați configurația și îmbogățiți profilurile clienților din pagina **Îmbogățire** (numai pentru îmbogățirea primară).
- Gestionați și creați exporturi pe baza conexiunilor partajate cu colaboratorii. [Aflați mai multe despre modul în care administratorii permit colaboratorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Administrator

- Toate permisiunile disponibile pentru Colaborator.
- Modificați setările pe pagina **Sistem**, inclusiv limbajul de lucru și programele de actualizare pentru procesele sistemului.
- Vizualizați și adăugați permisiunile folosind pagina **Permisiuni**.
- Setați definițiile căutare și filtrare pentru pagina Clienți utilizând pagina **Index de căutare și filtrare** (accesibilă prin pagina **Clienți**).
- Gestionați conexiunile și permiteți-le activarea altor roluri de utilizator pe pagina **Conexiuni**.
- Gestionați configurația și îmbogățiți profilurile clienților din pagina **Îmbogățire** (pentru toate îmbogățirile).
- Gestionați și creați exporturi pe pagina **Exporturi**.
- Instalați și utilizați **Program de completare card client**.
- Adăugați și utilizați **conectorul Power Apps**.
- Activați utilizarea [API-urilor Customer Insights](apis.md).
- [Atribuiți proprietatea asupra mediului](manage-environments.md#change-the-owner-of-an-environment) unui alt administrator.

## <a name="admin-owner"></a>Administrator (proprietar)

- Toate permisiunile disponibile pentru administrator.
- [Resetați și ștergeți](manage-environments.md#reset-an-existing-environment-preview) mediul.

## <a name="assign-roles-and-permissions"></a>Alocați roluri și permisiuni

1. Mergi la **Admin** > **Securitate** > **Utilizatori***.

1. Selectați **Adăugare utilizatori** pentru a deschide panoul **Adăugare/Editare permisiuni**.

1. Folosiți câmpul **Căutare** pentru a găsi utilizatorul sau grupul Azure Active Directory ale cărui permisiuni doriți să le ajustați. Alege un **Rol** de atribuit acelui utilizator sau grup.

1. Selectați **Salvare**. Mediul actual va fi distribuit automat utilizatorului sau membrilor grupului ale căror permisiuni le-ați modificat. Utilizatorii pot accesa aplicația Customer Insights și pot lucra în funcție de rolul specificat.

## <a name="view-current-permissions"></a>Vizualizați permisiunile curente

Mergi la **Admin** > **Securitate** > **Utilizatori** pentru a vedea ce atribuții de rol sunt active în prezent.

- Coloana **Tip** specifică un singur utilizator, grup sau aplicație. Sistemul acceptă utilizatori individuali și grupuri.
- Rolurile sunt specificate la coloana **Rol**.
- Selectați orice titlu de coloană pentru a sorta rezultatele după valoarea coloanei respective.
- Utilizați câmpul **Căutare** din partea de sus a paginii pentru a localiza anumiți utilizatori.


[!INCLUDE [footer-include](includes/footer-banner.md)]
