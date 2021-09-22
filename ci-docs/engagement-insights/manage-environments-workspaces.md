---
title: Gestionați spațiile de lucru și mediile
description: Cum să creați, redenumiți și să ștergeți spațiile de lucru și mediile.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 07/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: bf310b1a50ba7baac5d11d5f22ff42003fbba516efd7d165c00b59adc958da2e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034057"
---
# <a name="manage-environments-and-workspaces"></a>Gestionați mediile și spațiile de lucru

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Prezentare generală

Un spațiu de lucru este un spațiu în care stocați și gestionați evenimente și rapoarte. Aici puteți vizualiza activitatea utilizatorilor în timp real. Când creați un spațiu de lucru, selectați tipul de date pe care să îl trimiteți la spațiul de lucru. În prezent sunt acceptate datele web și aplicațiile mobile.

Un mediu este un spațiu în care vă gestionați spațiile de lucru și conexiunile. Modul în care utilizați mediile depinde de organizația dvs. și de cazul dvs. de utilizare. De exemplu, puteți să creați:

-   Un mediu unic.
-   Medii separate pentru testare și producție.
-   Medii separate pentru anumite echipe sau departamente din organizația dvs. care conțin evenimente relevante pentru fiecare public.
-   Medii separate pentru diferite ramuri globale ale companiei dvs.
-   Conexiuni cu capacitatea de detalii despre public pentru Customer Insights.

## <a name="choose-an-environment-and-create-a-workspace"></a>Alegeți un mediu și creați un spațiu de lucru 

Fiecare spațiu de lucru trebuie să se afle într-un mediu. Puteți selecta un mediu preexistent sau puteți crea unul nou atunci când creați un spațiu de lucru. Apoi puteți alege să adăugați membri ai spațiului de lucru și să începeți să colectați date.

**Pentru a vă crea primul spațiu de lucru**

1. În Detalii despre angajamente, selectați **Nou** din comutatorul spațiului de lucru. 

   :::image type="content" source="media/New-workspace.png" alt-text="Selectorul spațiului de lucru al paginii Customer Insights.":::

1. Alegeți un mediu din listă sau selectați **Creați un mediu nou**.

1. Introduceți un nume în **Nume de spațiu de lucru**. 

1. Selectați tipul de mediu pe care doriți să îl creați, în funcție de dacă doriți să măsurați ce se întâmplă pe un site web sau într-o aplicație mobilă. 

1. Puteți adăuga membri și le puteți atribui nivelul de permisiune din lista **Rol**. Apoi selectați **Terminat** pentru a crea spațiul de lucru sau **Următorul** pentru a instala codul. 

1. Instalați fragment de cod pentru a începe să primiți date și apoi selectați **Terminat**. 

## <a name="manage-a-workspace"></a>Gestionați un spațiu de lucru

Puteți întreține simultan mai multe spații de lucru într-un mediu. [Rolul](user-roles.md) dvs. determină modul în care puteți lucra în ele. 

 - Trebuie să fiți administrator de mediu sau un administrator de spațiu de lucru pentru a gestiona spațiul de lucru.
 - În calitate de administrator de spațiu de lucru, puteți redenumi spațiile de lucru existente sau le puteți șterge. 

### <a name="edit-a-workspace-name"></a>Editați numele unui spațiu de lucru

1. Accesați **Administrator** > **Spațiu de lucru** și selectați **Setări**.

1. În caseta **Numele spațiului de lucru**, introduceți un nume nou.

1. Selectați **Salvare** pentru a vă aplica modificările.

### <a name="delete-a-workspace"></a>Ștergeți un spațiu de lucru

Ștergerea unui spațiu de lucru va elimina definitiv întregul conținut, datele, setările și permisiunile sale. Aceasta nu se poate anula.

1. Accesați **Administrator** > **Spațiu de lucru** și selectați **Setări**.

1. Selectați **Ștergeți spațiul de lucru**. 

1. Introduceți **„CONFIRMAȚI ȘTERGEREA”** în dialogul **Ștergeți spațiul de lucru**. 

1. Selectați **Ștergeți** pentru a șterge definitiv spațiul de lucru.

### <a name="manage-workspace-members"></a>Gestionați membrii spațiului de lucru

1. Accesați **Administrator** > **Spațiu de lucru** și selectați **Membrii**.

1. Selectați **Adăugați membri** pentru a da acces și [atribuiți roluri](user-roles.md). În prezent, numai **Administrator de spațiu de lucru** este disponibil.

1. Dacă configurați o [conectare la detaliile despre public](configure-connections.md), puteți selecta **Permiteți accesul la datele de profil** pentru a permite membrilor să vadă rapoarte bazate pe [profilurile de utilizator](profile-reports.md).

1. Selectați **Adăugați membri** pentru a-i adăuga în spațiul dvs. de lucru.

## <a name="manage-an-environment"></a>Gestionați un mediu

În calitate de administrator de mediu, puteți accesa un mediu din panoul de navigare din stânga. Puteți configura setările de mediu, alți administratori de mediu, spațiile de lucru și [conectare la detaliile despre public](configure-connections.md). Selectați filele pentru a vă deplasa între diferite zone din centrul de administrare.

:::image type="content" source="media/New-environment.png" alt-text="Centrul de administrare pentru mediu.":::

### <a name="create-an-environment"></a>Creați un mediu

1. În selectorul spațiului de lucru, selectați **+Nou**.

1. În experiența ghidată, deschideți meniul derulant **Mediu** și selectați **Creați un mediu nou**. 

1. Furnizați un **Numele mediului**.

   :::image type="content" source="media/create-environment.png" alt-text="Pas în experiența ghidată pentru a specifica detaliile mediului.":::

1. Alegeți **Regiune** și selectați **Următorul**. 

1. Furnizați un nume de spațiu de lucru și alegeți ce tip de spațiu de lucru doriți să creați. 

1.  Opțional, adăugați membri și copiați fragment de cod finalizați procesul de creare.

### <a name="rename-an-environment"></a>Redenumiți un mediu

1. Accesați **Administrator** > **Mediu** și selectați **Setări**.

1. Actualizați **Numele mediului** și selectați **Salvare** pentru a aplica modificările.

### <a name="manage-environment-members"></a>Gestionați membrii mediului

1. Accesați **Administrator** > **Mediu** și selectați **Membrii**.

1. Selectați **Adăugați membri** pentru a actualiza membrii și [atribuiți roluri](user-roles.md). În prezent, numai **Administrator de mediu** este disponibil.

1. Dacă configurați o [conectare la detaliile despre public](configure-connections.md), puteți selecta **Permiteți accesul la datele de profil** pentru a permite membrilor să vadă rapoarte bazate pe [profilurile de utilizator](profile-reports.md).

1. Selectați **Adăugați membri** pentru a-i adăuga în mediul dvs.

### <a name="delete-an-environment"></a>Ștergerea unui mediu

Administratorii de mediu pot șterge mediile. Înainte de a putea șterge un mediu, trebuie să eliminați toate spațiile de lucru de sub acesta.

1. Accesați **Administrator** > **Mediu** și selectați **Setări**.

1. Selectați **Ștergere mediu**. 

1. Introduceți **„CONFIRMAȚI ȘTERGEREA”** în dialogul **Ștergeți spațiul de lucru**. 

1. Selectați **Ștergere** pentru a șterge permanent mediul.

## <a name="manage-connections"></a>Gestionați conexiunile

Stabilirea conectărilor la detaliile despre public vă permite să vedeți rapoarte în Detalii despre angajamente bazate pe profiluri unificate ale clienților. 

Pentru mai multe informații, consultați [Configurarea de conectări](configure-connections.md).

## <a name="manage-personal-data"></a>Gestionarea datelor personale

Pentru a proteja datele personale ale clientului dvs., puteți șterge sau exporta datele identificabile ale utilizatorului final.

Pentru mai multe informații, consultați [Ștergeți și să exportați date despre evenimente care conțin informații personale](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
