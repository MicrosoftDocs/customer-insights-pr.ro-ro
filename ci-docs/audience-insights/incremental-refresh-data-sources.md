---
title: Reîmprospătare incrementală pentru sursele de date bazate pe Power Query
description: Reîmprospătați date noi și actualizate pentru surse mari de date bazate pe Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: f614d701aeb06720a60b14549a7fe666f8fe0617
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900300"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Reîmprospătare incrementală pentru sursele de date bazate pe Power Query

Acest articol discută cum să configurați reîmprospătarea incrementală pentru sursele de date pe baza Power Query.

Reîmprospătarea incrementală pentru sursele de date oferă următoarele avantaje:

- **Reîmprospătări mai rapide** - Numai datele care s-au schimbat se reîmprospătează. De exemplu, este posibil să reîmprospătați doar ultimele cinci zile ale unui set de date istoric.
- **Fiabilitate crescută** - Cu actualizări mai mici, nu trebuie să mențineți conexiunile la sisteme volatile pentru o perioadă lungă de timp, reducând riscul apariției problemelor de conectare.
- **Consum redus de resurse** - Reîmprospătarea doar a unui subset din datele dvs. totale duce la utilizarea mai eficientă a resurselor de calcul și reduce amprenta asupra mediului.

## <a name="configure-incremental-refresh"></a>Configurați reîmprospătarea incrementală

Statisticile despre public permit reîmprospătarea incrementală pentru sursele de date importate prin Power Query care acceptă ingestia incrementală. De exemplu, bazele de date SQL Azure cu câmpuri de dată și oră, care indică momentul în care înregistrările de date au fost actualizate ultima dată.

1. [Creați o nouă sursă de date bazată pe Power Query](connect-power-query.md).

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
