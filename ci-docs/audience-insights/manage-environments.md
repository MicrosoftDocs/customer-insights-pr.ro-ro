---
title: Crearea și gestionarea mediilor
description: Aflați cum să vă înscrieți pentru serviciu și cum să gestionați mediile.
ms.date: 10/14/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: ce2fdd435a81bb04148057554c5958e3ab59f125
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645141"
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
- Surse de date din folderul Model de date comune și Dataverse Data Lake gestionat. Va trebui să creați acele surse de date manual cu același nume ca în mediul sursă.

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
