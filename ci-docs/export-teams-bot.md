---
title: Robot Teams pentru Dynamics 365 Customer Insights (previzualizare)
description: Căutați profiluri unificate ale clienților în Microsoft Teams cu ajutorul unui robot.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 62a0216de848b5a3a81fdd6ac078feb551fcfec6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082602"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Robot Teams pentru Dynamics 365 Customer Insights (previzualizare)

Conectați-vă cu Microsoft Teams pentru a permite unui robot să caute profiluri de clienți unificate în canalele Teams.

> [!div class="mx-imgBorder"]
> ![Robot Teams care afișează o înregistrare de client.](media/teams-bot.png "Robot Teams care afișează o înregistrare de client")

## <a name="prerequisites"></a>Cerințe preliminare

Pentru a configura și configura robotul, trebuie îndeplinite următoarele cerințe preliminare:

- Există cel puțin o [sursă de date adăugată](data-sources.md).
- [Procesul de unificare](data-unification.md) este complet.
- Câmpurile sunt adăugate la [indexul de căutare și filtrare](search-filter-index.md).
- Customer Insights și Teams sunt în aceeași organizație.
- Mediul dvs. are publicul țintă principal stabilit pentru clienții individuali. Conturile de afaceri nu sunt acceptate.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Configurați robotul

1. Mergi la **Admin** > **Export Destinații**.
1. Pe fila Microsoft Teams, selectați **Configura**.
1. Sunteți redirecționat către zona **Aplicații** în Teams. De asemenea, puteți deschide Teams și puteți selecta **Aplicații** în colțul din stânga jos sau [obțineți direct din AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Cautați **Customer Insights** și selectați aplicația.
1. Selectați **Adăugare**.
1. După conectarea la Customer Insights în Teams, veți vedea un mesaj de bun venit și puteți începe.

## <a name="things-you-can-do-with-the-bot"></a>Lucruri pe care le puteți face cu robotul

Robotul oferă funcții de căutare pentru profiluri de clienți unificate.

- Introduceți **căutare** urmat de un nume, adresă de e-mail sau orice alt câmp din profilul de client unificat care este adăugat la indexul de căutare și filtru.

  Veți primi un card cu până la 15 câmpuri din profilul clientului rezultat. Mai multe potriviri returnează o listă de rezultate în care puteți selecta un profil. Puteți adăuga termenul de căutare în ghilimele duble pentru a căuta o potrivire exactă.

- Dacă organizația dvs. menține mai multe medii Customer Insights în aceeași organizație, puteți introduce **switchinstance** pentru a alege la ce mediu doriți să conectați robotul.

- Introduceți **ajutor** pentru a vedea o listă de comenzi disponibile pentru robot.  


[!INCLUDE [footer-include](includes/footer-banner.md)]