---
title: Crearea și gestionarea mediilor
description: Aflați cum să vă înscrieți pentru serviciu și cum să gestionați mediile.
ms.date: 11/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 65c6a68f550c2873ec30c6ac54f1752d880ce12c
ms.sourcegitcommit: fb9f118b4e16b5aabb3e503463efca21718f5d72
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/12/2021
ms.locfileid: "7799651"
---
# <a name="manage-environments"></a>Gestionați mediile

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Comutați medii

Selectați controlul **Mediu** din colțul din dreapta sus al paginii pentru a modifica mediile.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Captură de ecran a comenzii pentru a schimba mediul.":::

Administratorii pot [crea](create-environment.md) și gestiona medii.

## <a name="edit-an-existing-environment"></a>Editați un mediu existent

Puteți edita câteva dintre detaliile mediilor existente.

1.  Selectați selectorul **Mediu** în antetul aplicației.

2.  Selectați pictograma **Editare**.

3. În caseta **Editați mediul**, puteți actualiza setările de mediu.

Pentru informații suplimentare despre setările de mediu, consultați [Creați un mediu nou](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Conectați-vă la Microsoft Dataverse
   
The **Microsoft Dataverse** pasul vă permite să conectați Customer Insights cu mediul dvs. Dataverse.

A folosi [modele out-of-box predicție](predictions-overview.md#out-of-box-models), configurați partajarea datelor cu Dataverse. Sau puteți activa absorbția de date din sursele de date local, furnizând adresa URL a mediului Microsoft Dataverse pe care o administrează organizația dvs. Selectați **Activați partajarea datelor** pentru a partaja datele de ieșire ale Customer Insights cu un lac de date gestionat de Dataverse.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Opțiuni de configurare pentru a activa partajarea datelor cu Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights nu acceptă următoarele scenarii de partajare:
> - Dacă salvați toate datele în propriul dvs. Azure Data Lake Storage, nu veți putea activa partajarea datelor cu un lac de date gestionat de Dataverse.
> - Dacă activați partajarea datelor cu Dataverse, nu veți putea [să creeze valori prezise sau lipsă într-o entitate](predictions.md).

## <a name="copy-the-environment-configuration"></a>Copiați configurația mediului

Când creați un mediu nou, puteți alege să copiați configurația dintr-un mediu existent. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captură de ecran a opțiunilor de setări din setările de mediu.":::

Veți vedea o listă cu toate mediile disponibile în organizația dvs. de unde puteți copia datele.

Sunt copiate următoarele setări de configurare:

- Surse de date ingerate/importate
- Configurarea unificării datelor (mapare, potrivire, îmbinare)
- Segmente
- Măsuri
- Relaţii
- Activități
- Index de căutare și filtrare
- Destinații export
- Reîmprospătare planificată
- Îmbogățiri
- Management model
- Atribuiri rol

Următoarele date *nu* sunt copiate:

- Profiluri de client.
- Acreditările sursă de date. Va trebui să furnizați acreditările pentru fiecare sursă de date și să reîmprospătați sursele de date manual.

- Surse de date din folderul Common Data Model și din lacul de date gestionat de Dataverse. Va trebui să creați acele surse de date manual cu același nume ca în mediul sursă.

Când copiați un mediu, veți vedea un mesaj de confirmare a faptului că noul mediu a fost creat. Selectați **Accesați sursele de date** pentru a vedea lista surselor de date.

Toate sursele de date vor arăta o stare **Acreditări necesare**. Editați sursele de date și introduceți acreditările pentru a le reîmprospăta.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista surselor de date care au fost copiate și care necesită autentificare.":::

După reîmprospătarea surselor de date, accesați **Date** > **Unificare**. Aici veți găsi setările din mediul sursă. Editați-le după cum este necesar sau selectați **Rulează** pentru a începe procesul de unificare a datelor și a crea entitatea clientului unificat.

Când unificarea datelor este completă, accesați **Măsuri** și **Segmente** pentru a le reîmprospăta și pe acestea.

## <a name="reset-an-existing-environment"></a>Resetați un mediu existent

Ca administrator, puteți reseta un mediu la o stare goală dacă doriți să ștergeți toate configurațiile și să eliminați datele ingerate.

1.  Selectați selectorul **Mediu** în antetul aplicației. 

2.  Selectați mediul pe care doriți să îl resetați și selectați punctele de suspensie (**...**). 

3. Alegeți opțiunea **Resetați**. 

4.  Pentru a confirma ștergerea, introduceți numele mediului și selectați **Resetare**.

## <a name="delete-an-existing-environment"></a>Ștergerea unui mediu existent

În calitate de administrator, puteți șterge un mediu pe care îl administrați.

1.  Selectați selectorul **Mediu** în antetul aplicației.

2.  Selectați mediul pe care doriți să îl resetați și selectați punctele de suspensie (**...**). 

3. Alegeți opțiunea **Ștergere**. 

4.  Pentru a confirma ștergerea, introduceți numele mediului și selectați **Ștergere**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
