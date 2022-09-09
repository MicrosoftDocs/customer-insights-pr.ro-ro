---
title: Programați reîmprospătarea sistemului
description: Programați ora la care sistemul ar trebui să fie reîmprospătat
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 949ea071ca41127b0c45488d5d7af3f6aa4e1c35
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/02/2022
ms.locfileid: "9395971"
---
# <a name="schedule-system-refresh"></a>Programați reîmprospătarea sistemului

Programați reîmprospătările automate ale tuturor [surse de date ingerate](data-sources.md). Actualizările automate vă ajută să vă asigurați că actualizările din sursele de date sunt reflectate în profilurile dvs. de clienți unificate.

> [!NOTE]
> Power Query sursele de date gestionate de dvs. se reîmprospătează în propriile lor programe. Pentru a programa reîmprospătarea acestora Power Query surse de date, configurați setările de reîmprospătare pe acel sursă de date specific din **Surse de date** pagină.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Setări de reîmprospătare a fluxului de date.":::

## <a name="set-system-refresh-schedule"></a>Setați programul de reîmprospătare a sistemului

1. Mergi la **Admin** > **Sistem** și selectați **Programa** fila.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Programați fila de reîmprospătare din pagina Sistem.":::

1. Starea implicită pentru reîmprospătarea programată este **Dezactivat**. Pentru a activa actualizarea programată, schimbați comutarea din partea de sus a ecranului la **Activat**.

1. Alegeți între **Săptămânal** (implicit) și reîmprospătare **Zilnică**. Dacă intenționați să programați actualizări săptămânale, selectați una sau mai multe zile în care doriți să rulați actualizarea.

1. Setați-vă **Fusul orar**, apoi utilizați meniul vertical **Oră** pentru a seta temporizarea reîmprospătării. Dacă doriți să programați mai multe actualizări într-o singură zi, selectați **Adăugați altă oră**. Puteți adăuga până la patru reîmprospătări.

1. Selectați **Salvare** pentru a vă aplica modificările.

[!INCLUDE [footer-include](includes/footer-banner.md)]
