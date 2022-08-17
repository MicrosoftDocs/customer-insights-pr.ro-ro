---
title: Atribuiți permisiuni de utilizator
description: Aflați mai multe despre permisiuni și roluri de utilizator.
ms.date: 08/08/2022
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
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245434"
---
# <a name="assign-user-permissions"></a>Atribuiți permisiuni de utilizator

Accesul la Customer Insights este limitat la utilizatorii din organizația dvs. care sunt adăugați la aplicație de către un administrator. Un administrator poate adăuga, edita sau elimina utilizatori. Un utilizator poate fi un singur utilizator, grup sau aplicație. Există trei tipuri de roluri pe care un utilizator le poate avea:

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
- Complet **Unificarea datelor** care au ca rezultat entitatea de profil unificat al clientului.
- Definiți **Relații** și **Activități**.
- Creați segmente folosind pagina **Segmente**.
- Creați măsuri folosind pagina **Măsuri**.
- Gestionați configurația și îmbogățiți profilurile clienților din pagina **Îmbogățire** (numai pentru îmbogățirea primară).
- Gestionați și creați exporturi pe baza [conexiuni partajate cu colaboratorii](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Administrator

- Toate permisiunile disponibile pentru Colaborator.
- Modificați setările pe **Sistem** pagina, inclusiv limba de lucru, programele de reîmprospătare pentru procesele sistemului dvs. și exportarea jurnalelor de diagnosticare.
- Modificați setările pe **Securitate** pagina, inclusiv utilizatori, chei API, linkuri private și seif pentru chei.
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

## <a name="add-users"></a>Adăugați utilizatori

1. Mergi la **Admin** > **Securitate** și selectați **Utilizatori** fila.

1. Selectați **Adăugare utilizatori** pentru a deschide panoul **Adăugare/Editare permisiuni**.

1. Folosește **Căutare** câmp pentru a găsi Azure Active Directory utilizator sau grup pe care doriți să-l adăugați. Alege un **Rol** de atribuit acelui utilizator sau grup.

1. Selectați **Salvare**. Mediul curent este partajat automat cu utilizatorul sau membrii grupului. Utilizatorii pot accesa aplicația Customer Insights și pot lucra în funcție de rolul specificat.

## <a name="view-current-permissions"></a>Vizualizați permisiunile curente

Mergi la **Admin** > **Securitate** și selectați **Utilizatori** pentru a vedea lista de utilizatori activi și alocarea rolurilor acestora. Puteți sorta lista de utilizatori după orice coloană sau puteți utiliza caseta de căutare pentru a găsi un anumit utilizator.

## <a name="manage-current-users"></a>Gestionați utilizatorii actuali

Mergi la **Admin** > **Securitate** și selectați **Utilizatori** fila. Puteți sorta lista de utilizatori după orice coloană sau puteți utiliza caseta de căutare pentru a găsi utilizatorul pe care doriți să-l gestionați.

Selectați un utilizator pentru a vedea acțiunile disponibile.

- **Editați | ×** pentru a edita rolul utilizatorului în Customer Insights. Selectați **Salvați** pentru a confirma modificarea.
- **Elimina** pentru a elimina utilizatorul de a avea acces la Customer Insights. Selectați **Ștergere**, apoi confirmați ștergerea.

[!INCLUDE [footer-include](includes/footer-banner.md)]
