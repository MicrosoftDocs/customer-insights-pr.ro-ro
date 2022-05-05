---
title: Reîmprospătare incrementală pentru Power Query surse de date bazate pe
description: Actualizează datele noi și actualizate pentru surse mari de date pe baza Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 3d21baf9804f300802b066df0183fc8f01abba9a
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643666"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Reîmprospătare incrementală pentru sursele de date pe baza Power Query

Acest articol discută cum să configurați reîmprospătarea incrementală pentru sursele de date pe baza Power Query.

Reîmprospătarea incrementală pentru sursele de date oferă următoarele avantaje:

- **Reîmprospătări mai rapide** - Numai datele care s-au schimbat se reîmprospătează. De exemplu, este posibil să reîmprospătați doar ultimele cinci zile ale unui set de date istoric.
- **Fiabilitate crescută** - Cu actualizări mai mici, nu trebuie să mențineți conexiunile la sisteme volatile pentru o perioadă lungă de timp, reducând riscul apariției problemelor de conectare.
- **Consum redus de resurse** - Reîmprospătarea doar a unui subset din datele dvs. totale duce la utilizarea mai eficientă a resurselor de calcul și reduce amprenta asupra mediului.

## <a name="configure-incremental-refresh"></a>Configurați reîmprospătarea incrementală

Customer Insights permite reîmprospătarea incrementală pentru sursele de date importate prin intermediul Power Query care sprijină ingestia incrementală. De exemplu, bazele de date SQL Azure cu câmpuri de dată și oră, care indică momentul în care înregistrările de date au fost actualizate ultima dată.

1. [Creați un nou sursă de date bazat pe Power Query](connect-power-query.md).

1. Furnizeaza un **Nume** pentru sursă de date.

1. Selectați un sursă de date care acceptă reîmprospătarea incrementală, cum ar fi [Baza de date Azure SQL](/power-query/connectors/azuresqldatabase).

1. Selectați entitățile sau tabelele de ingerat.

1. Finalizați etapele de transformare și selectați **Următorul**.

1. În caseta de dialog **Configurați reîmprospătare incrementală**, selectați **Configurat** pentru a deschide **Setări de reîmprospătare incrementală**. Dacă selectați **Salt**, sursa de date va reîmprospăta întregul set de date.
   > [!TIP]
   > Puteți aplica, de asemenea, reîmprospătarea incrementală mai târziu prin editarea unei surse de date existente.

1. Pe **Setări de reîmprospătare incrementală**, veți configura reîmprospătarea incrementală pentru toate entitățile pe care le-ați selectat la crearea sursei de date.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Configurați entitățile dintr-o sursă de date pentru reîmprospătare incrementală.":::

1. Selectați o entitate și furnizați următoarele detalii:

   - **Definiți cheia principală**: Selectați o cheie primară pentru entitate sau tabel.
   - **Definiți câmpul „ultima actualizare”**: Acest câmp va afișa doar atributele de tip dată sau oră. Selectați un atribut care indică momentul în care înregistrările au fost actualizate ultima dată. Acesta va fi utilizat pentru a identifica înregistrările care se încadrează în intervalul de timp de reîmprospătare incrementală.
   - **Verificați dacă există actualizări la fiecare**: Specificați cât timp doriți să fie intervalul de timp de reîmprospătare incremental.

1. Selectați **salvare** pentru a finaliza crearea sursei de date. Actualizarea inițială a datelor va fi o reîmprospătare completă. Ulterior, reîmprospătarea de date incrementală se întâmplă așa cum este configurat în pasul anterior.


[!INCLUDE [footer-include](includes/footer-banner.md)]
