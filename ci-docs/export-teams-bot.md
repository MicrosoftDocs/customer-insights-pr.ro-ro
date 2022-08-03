---
title: Robot Teams pentru Dynamics 365 Customer Insights (previzualizare)
description: Căutați profiluri unificate ale clienților în Microsoft Teams cu ajutorul unui robot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195857"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Robot Teams pentru Dynamics 365 Customer Insights (previzualizare)

Conectați-vă cu Microsoft Teams pentru a permite unui robot să caute profiluri de clienți unificate în canalele Teams.

:::image type="content" source="media/teams-bot.png" alt-text="Robot Teams care afișează o înregistrare de client":::

## <a name="prerequisites"></a>Cerințe preliminare

- Cel puțin unul [sursă de date adăugat](data-sources.md).
- [Procesul de unificare](data-unification.md) este complet.
- Câmpurile sunt adăugate la [index de căutare și filtrare](search-filter-index.md).
- Customer Insights și Teams sunt în aceeași organizație.
- Mediul dvs. are publicul țintă principal stabilit pentru clienții individuali. Conturile de afaceri nu sunt acceptate.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Configurați robotul

1. Salt la **Administrator** > **Conexiuni**.
1. Pe fila Microsoft Teams, selectați **Configura**.
1. Sunteți redirecționat către zona **Aplicații** în Teams. De asemenea, puteți deschide Teams și puteți selecta **Aplicații** în colțul din stânga jos sau [obțineți direct din AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Cautați **Customer Insights** și selectați aplicația.
1. Selectați **Adăugare**.
1. conectați-vă la Customer Insights în Teams. Se afișează un mesaj de bun venit.

## <a name="things-you-can-do-with-the-bot"></a>Lucruri pe care le puteți face cu robotul

Robotul oferă funcții de căutare pentru profiluri de clienți unificate.

- introduce **căutare** urmat de un nume, adresă de e-mail sau orice alt câmp din profilul unificat al clientului care este adăugat la indexul de căutare și filtrare.

  Veți primi un card cu până la 15 câmpuri din profilul clientului rezultat. Mai multe potriviri returnează o listă de rezultate în care puteți selecta un profil. Pentru a căuta o potrivire exactă, adăugați termenul de căutare între ghilimele duble.

- Dacă organizația dvs. menține mai multe medii Customer Insights în aceeași organizație, intrați **instanță de comutare** pentru a alege mediul la care doriți să conectați botul.

- Introduceți **ajutor** pentru a vedea o listă de comenzi disponibile pentru robot.  

[!INCLUDE [footer-include](includes/footer-banner.md)]