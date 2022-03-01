---
title: Destinații export
description: Exportați date și gestionați destinațiile de export.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643878"
---
# <a name="export-destinations-preview"></a>Destinații export (previzualizare)

Pagina **Destinații de export** vă arată toate locațiile pe care le-ați configurat pentru a exporta date. Puteți adăuga, de asemenea, noi destinații pentru export. În plus, arată opțiunile de export disponibile în prezent. Obțineți o privire de ansamblu rapidă, descriere și aflați ce puteți face cu fiecare opțiune de extensibilitate. Exportați profiluri, măsuri și segmente unificate în aplicații acceptate relevante pentru compania dvs.

Acccesați **Admin** > **Destinații de export** pentru a găsi următoarele opțiuni de extensibilitate:

- [Program de completare Card Dynamics 365 Customer](customer-card-add-in.md)
- [Facebook Conectorul Ads Manager](export-facebook.md)
- [Conector Power Automate](export-power-automate.md)
- [Conector Power Apps](export-power-apps.md)
- [Conector Power BI](export-power-bi.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Stocare de bloburi Azure](export-azure-blob-storage.md)
- [conector LiveRamp &reg;](export-liveramp.md)
- [Bot pentru Microsoft Teams](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [API Customer Insights](apis.md)

## <a name="add-a-new-export-destination"></a>Adăugați o nouă destinație de export

Pentru a adăuga destinații de export, aveți [permisiuni de administrator](permissions.md). Dacă exportați către servicii Microsoft, presupunem că ambele servicii sunt în aceeași organizație.

1. Accesați **Administrator** > **Destinații de export**.

1. Comutați la fila **Destinațiile mele de export**.

1. Selectați **Adăugați destinația** pentru a crea o nouă destinație de export.

1. În panoul **Adăugați destinația**, selectați **Tipul** destinației de export în meniul derulant.

1. Furnizați detaliile necesare și selectați **Următor** pentru a crea destinația de export.

Puteți selecta, de asemenea **Configurare** pe o dală de pe fila **Descoperire**.

## <a name="view-export-destinations"></a>Vizualizarea Export destinații

După crearea destinațiilor de export, le veți găsi într-un tabel din fila **Destinațiile mele de export**. Acest tabel are trei coloane:

- **Nume afișat**: numele pe care l-ați introdus la crearea destinației.
- **Tip**: Tipul de destinație de export setat atunci când creați destinația.
- **Creat**: data la care ați creat destinația.

## <a name="edit-an-export-destination"></a>Editați o destinație de export

1. Selectați elipsa verticală pentru destinația Export pe care doriți să o editați.

   > [!div class="mx-imgBorder"]
   > ![Elipsă verticală](media/export-destinations-page-ellipsis.png "Elipsă verticală")

1. Selectați **Editare** din meniul de listă derulantă.

1. Modificați valorile care necesită actualizare și selectați **Salvare**.

## <a name="export-data-on-demand"></a>Exportați date la cerere

După configurarea unui conector pentru o destinație de export, exporturile vor rula cu fiecare [actualizare programată](system.md#schedule-tab).

Pentru a exporta date fără a aștepta o actualizare programată, mergeți la fila **Destinațiile mele de export** de pe **Administrator** > **Destinații de export**.

> [!div class="mx-imgBorder"]
> ![Elipsă verticală](media/export-destinations-page-ellipsis.png "Elipsă verticală")

- Selectați **Export** deasupra listei pentru a rula exportul către toate destinațiile de export simultan.
- Selectați punctele de suspensie (...) după un element de listă și apoi alegeți opțiunea **Export** pentru a rula exportul pentru o singură destinație de export.

## <a name="remove-an-export-destination"></a>Eliminați o destinație de export

Pentru a elimina o destinație Export, porniți de la pagina principală **Destinații de export**.

1. Selectați elipsa verticală pentru destinația Export pe care doriți să o eliminați.

   > [!div class="mx-imgBorder"]
   > ![Elipsă verticală](media/export-destinations-page-ellipsis.png "Elipsă verticală")

2. Selectați **Eliminare** din meniul vertical.

3. Confirmați eliminarea selectând **Eliminare** pe ecranul de confirmare.
