---
title: Sarcini partajate pentru scenarii de predicție
description: Aflați cum să gestionați, să depanați și să rafinați predicțiile.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095742"
---
# <a name="manage-predictions"></a>Gestionați predicțiile

Acest articol discută câteva sarcini pe care le partajează majoritatea scenariilor de predicție.

## <a name="troubleshoot-a-failed-prediction"></a>Depanarea unei predicții eșuate

1. Mergeți la **Informații** > **Predicții** și selectați fila **Previziunile mele**.

1. Selectați elipsele verticale de lângă predicția pentru care doriți să vedeți jurnalele de erori.

1. Selectați **Jurnale**.

1. Analizarea tuturor erorilor. Există mai multe tipuri de erori care pot apărea și ce descriu condiția care a cauzat eroarea. De exemplu, o eroare pentru date insuficiente pentru o predicție exactă este de obicei rezolvată prin încărcarea de date suplimentare în Customer Insights.

## <a name="input-data-usability-report"></a>Raport de utilizare a datelor de intrare

Raportul de utilizare a datelor de intrare oferă o imagine consolidată a erorilor și avertismentelor pe care le pot genera predicțiile dvs. predefinite. De asemenea, oferă recomandări despre cum să îmbunătățim performanța modelului.

Raportul este disponibil după ce un model a finalizat procesul de instruire. Este creat pentru fiecare model separat, indiferent dacă s-a finalizat cu succes sau nu.

> [!NOTE]
> În prezent, această caracteristică funcționează numai pentru modelul Transaction Churn.

### <a name="view-the-input-data-usability-report"></a>Vizualizați raportul de utilizare a datelor de intrare

După ce un model predefinit a finalizat etapa de instruire, vizualizați raportul:
- Selectați punctele de suspensie de lângă numele modelului și alegeți **Raport de utilizare a datelor de intrare**.
- Selectați starea unui model selectat **Vedeți raportul de utilizare a datelor de intrare** în panoul lateral.
- Selectați unul dintre modelele din listă și selectați **Raport de utilizare a datelor de intrare** în bara de comandă.
- Deschideți pagina cu rezultatele modelului și selectați **Raport de utilizare a datelor de intrare** în bara de comandă.

### <a name="information-in-the-input-data-usability-report"></a>Informații din raportul de utilizare a datelor de intrare

Următoarele coloane din raport conțin informații utile pentru a îmbunătăți datele pentru model.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exemplu de raport de utilizare a datelor de intrare care prezintă un tabel cu erori, avertismente și recomandări.":::

- Nume: Numele descriptiv al erorii, avertismentului sau al recomandării.
- Pas: Faza pentru model, instruire sau scor, la care se referă informațiile.
- Stare: Severitatea informațiilor (eroare, avertisment, recomandare).
- Nume coloană: Coloana dintr-o entitate care trebuie modificată pentru a îmbunătăți performanța modelului.
- Entitate: Numele entității care trebuie modificată pentru a îmbunătăți performanța modelului.
- Detalii: Detalii despre eroare, avertisment sau recomandare.

## <a name="refresh-a-prediction"></a>Reîmprospătați o predicție

Predicțiile se vor actualiza reîmprospăta conform aceluiași [program de reîmprospătare a datelor](system.md#schedule-tab) așa cum este configurat în setări. Le puteți reîmprospăta și manual.

1. Mergeți la **Informații** > **Predicții** și selectați fila **Previziunile mele**.

1. Selectați elipsele verticale de lângă predicția pe care doriți să o reîmprospătați.

1. Selectați **Reîmprospătare**.

## <a name="delete-a-prediction"></a>Ștergerea unei predicții

Ștergerea unui predicții elimină și entitatea acesteia de ieșire.

1. Mergeți la **Informații** > **Predicții** și selectați fila **Previziunile mele**.

1. Selectați elipsele verticale de lângă predicția pe care doriți să o ștergeți.

1. Selectați **Ștergere**.
