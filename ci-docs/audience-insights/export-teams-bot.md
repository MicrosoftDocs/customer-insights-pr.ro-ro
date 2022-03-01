---
title: Robot pentru Microsoft Teams
description: Căutați profiluri unificate ale clienților în Microsoft Teams cu ajutorul unui robot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406695"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Robot Teams pentru Dynamics 365 Customer Insights (previzualizare)

Conectați-vă cu Microsoft Teams pentru a permite unui robot să caute profiluri de clienți unificate în canalele Teams.

> [!div class="mx-imgBorder"]
> ![Robot Teams care afișează o înregistrare de client](media/teams-bot.png "Robot Teams care afișează o înregistrare de client")

## <a name="prerequisites"></a>Cerințe preliminare

Pentru a configura și configura robotul, trebuie îndeplinite următoarele cerințe preliminare:

- Există cel puțin o [sursă de date adăugată](data-sources.md).
- [Procesul de unificare](data-unification.md) este complet.
- Câmpurile sunt adăugate la [indexul de căutare și filtrare](search-filter-index.md).
- Customer Insights și Teams sunt în aceeași organizație.

## <a name="configure-the-bot"></a>Configurați robotul

1. În Detalii despre audiență, accesați **Administrator** > **Export destinații**.
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
