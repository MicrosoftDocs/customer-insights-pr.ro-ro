---
title: Gestionați spațiile de lucru și mediile
description: Cum să creați, redenumiți și să ștergeți spațiile de lucru și mediile.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 09cb3ddf0f8b4507b7eae6668ea3dad08cfcea29
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673812"
---
# <a name="manage-environments-and-workspaces"></a>Gestionați mediile și spațiile de lucru

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Prezentare generală

Acest subiect discută despre cum să gestionați spațiile de lucru și mediile după ce acestea au fost deja create. 

- Un *spațiu de lucru* este un spațiu în care stocați și gestionați evenimente și rapoarte. Aici puteți vizualiza activitatea utilizatorilor în timp real. Când creați un spațiu de lucru, selectați tipul de date pe care să îl trimiteți la spațiul de lucru. În prezent sunt acceptate datele web și aplicațiile mobile. Pentru mai multe informații, vezi [Creați un spațiu de lucru nou și adăugați membri](create-workspace.md).

- Un *mediu* este un spațiu în care vă gestionați spațiile de lucru și conexiunile. Pentru informații suplimentare, consultați [Creați un mediu nou](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Gestionați un spațiu de lucru existent

Puteți întreține simultan mai multe spații de lucru într-un mediu. [Rolul](user-roles.md) dvs. determină modul în care puteți lucra în ele. 

 - Trebuie să fiți administrator de mediu sau un administrator de spațiu de lucru pentru a gestiona spațiul de lucru.
 - În calitate de administrator de spațiu de lucru, puteți redenumi spațiile de lucru existente sau le puteți șterge. 

:::image type="content" source="media/workspace-edit.png" alt-text="Centru de administrare spațiu de lucru.":::

### <a name="edit-a-workspace-name"></a>Editați numele unui spațiu de lucru

1. Accesați **Administrator** > **Spațiu de lucru** și selectați **Setări**.

1. În caseta **Numele spațiului de lucru**, introduceți un nume nou.

1. Selectați **Salvare** pentru a vă aplica modificările.

### <a name="delete-a-workspace"></a>Ștergeți un spațiu de lucru

Ștergerea unui spațiu de lucru elimină definitiv tot conținutul, datele, setările și permisiunile acestuia. Aceasta nu se poate anula.

1. Accesați **Administrator** > **Spațiu de lucru** și selectați **Setări**.

1. Selectați **Ștergeți spațiul de lucru**. 

1. În caseta de dialog **Ștergeți spațiul de lucru**, introduceți **CONFIRMĂ ȘTERGEREA** în toate majusculele. 

1. Selectați **Ștergeți** pentru a șterge definitiv spațiul de lucru.

### <a name="manage-workspace-members"></a>Gestionați membrii spațiului de lucru

1. Accesați **Administrator** > **Spațiu de lucru** și selectați **Membrii**.

1. Selectați **Adăugați membri** pentru a da acces și [atribuiți roluri](user-roles.md). În prezent, numai **Administrator de spațiu de lucru** este disponibil.

1. Selectați **Adăugați membri** pentru a-i adăuga în spațiul dvs. de lucru.

## <a name="manage-an-existing-environment"></a>Gestionați un mediu existent

Ca administrator de mediu, puteți accesa un mediu din panoul de navigare din stânga. Puteți configura setările de mediu, alți administratori de mediu și spațiile de lucru. Selectați filele pentru a vă deplasa între diferite zone din centrul de administrare.

:::image type="content" source="media/environment-edit.png" alt-text="Centrul de administrare pentru mediu.":::

### <a name="edit-an-environment-name"></a>Editați un nume de mediu

1. Accesați **Administrator** > **Mediu** și selectați **Setări**.

1. Actualizați **Numele mediului** și selectați **Salvare** pentru a aplica modificările.

### <a name="delete-an-environment"></a>Ștergerea unui mediu

Administratorii de mediu pot șterge mediile. Înainte de a putea șterge un mediu, trebuie să eliminați toate spațiile de lucru de sub acesta.

1. Accesați **Administrator** > **Mediu** și selectați **Setări**.

1. Selectați **Ștergere mediu**. 

1. În caseta de dialog **Ștergeți spațiul de lucru**, introduceți **CONFIRMĂ ȘTERGEREA** în toate majusculele. 

1. Selectați **Ștergere** pentru a șterge permanent mediul.

### <a name="manage-environment-members"></a>Gestionați membrii mediului

1. Accesați **Administrator** > **Mediu** și selectați **Membrii**.

1. Selectați **Adăugați membri** pentru a actualiza membrii și [atribuiți roluri](user-roles.md). În prezent, numai **Administrator de mediu** este disponibil.

1. Selectați **Adăugați membri** pentru a-i adăuga în mediul dvs.

## <a name="manage-connections"></a>Gestionați conexiunile

Stabilirea conectărilor la detaliile despre public vă permite să vedeți rapoarte în Detalii despre angajamente bazate pe profiluri unificate ale clienților. 

Pentru mai multe informații, consultați [Creați o legătură între detaliile despre public și detalii despre angajament](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Gestionarea datelor personale

Pentru a proteja datele personale ale clientului dvs., puteți șterge sau exporta datele identificabile ale utilizatorului final.

Pentru mai multe informații, consultați [Ștergeți și să exportați date despre evenimente care conțin informații personale](../dsr-rights-requests.md#deleting-and-exporting-event-data-containing-end-user-identifiable-information).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
