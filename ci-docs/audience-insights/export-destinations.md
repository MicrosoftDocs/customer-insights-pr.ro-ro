---
title: Destinații export
description: Exportați date și gestionați destinațiile de export.
ms.date: 07/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5557442983f8c48cd46387009e0060beb6e764bb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596100"
---
# <a name="export-destinations-preview-overview"></a>Prezentare generală destinații export (versiune preliminară)

Pagina **Destinații de export** vă arată toate locațiile pe care le-ați configurat pentru a exporta date. Puteți adăuga, de asemenea, noi destinații pentru export. În plus, arată opțiunile de export disponibile în prezent. Obțineți o privire de ansamblu rapidă, descriere și aflați ce puteți face cu fiecare opțiune de extensibilitate. Exportați profiluri, măsuri și segmente unificate în aplicații acceptate relevante pentru compania dvs.

Acccesați **Admin** > **Destinații de export** pentru a găsi următoarele opțiuni de extensibilitate:

- [Adobe Campaign Standard](export-adobe-campaign-standard.md)
- [Platformă Adobe Experience](export-adobe-experience-platform.md)
- [AdRoll](export-adroll.md)
- [Autopilot](export-autopilot.md)
- [Stocare de bloburi Azure](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [Bot pentru Microsoft Teams](export-teams-bot.md)
- [API Customer Insights](apis.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Customer Service (Program de completare Customer Card)](customer-card-add-in.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Hub vânzări (Program de completare Customer Card)](customer-card-add-in.md)
- [Facebook Ads Manager](export-facebook.md)
- [Google Ads](export-google-ads.md)
- [LiveRamp&reg;](export-liveramp.md)
- [Mailchimp](export-mailchimp.md)
- [Marketo](export-marketo.md)
- [Power Automate](export-power-automate.md)
- [Power Apps](export-power-apps.md)
- [Power BI](export-power-bi.md)
- [SendGrid](export-sendgrid.md)
- [SFTP](export-sftp.md)

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]