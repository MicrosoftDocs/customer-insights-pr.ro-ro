---
title: Reîmprospătare incrementală pentru Power Query și surse de date Azure Data Lake
description: Actualizează datele noi și actualizate pentru surse mari de date pe baza Power Query sau surse de date Azure Data Lake.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: de39743eb8728fac34e417724c5f73bf44309c89
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207152"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Reîmprospătare incrementală pentru Power Query și surse de date Azure Data Lake

Reîmprospătare incrementală pentru sursele de date pe baza Power Query sau Azure Data Lake oferă următoarele avantaje:

- **Reîmprospătări mai rapide** - Numai datele care s-au schimbat se reîmprospătează. De exemplu, este posibil să reîmprospătați doar ultimele cinci zile ale unui set de date istoric.
- **Fiabilitate crescută** - Cu actualizări mai mici, nu trebuie să mențineți conexiunile la sisteme volatile pentru o perioadă lungă de timp, reducând riscul apariției problemelor de conectare.
- **Consum redus de resurse** - Reîmprospătarea doar a unui subset din datele dvs. totale duce la utilizarea mai eficientă a resurselor de calcul și reduce amprenta asupra mediului.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Configurați reîmprospătarea incrementală pentru sursele de date pe baza Power Query

Customer Insights permite reîmprospătarea incrementală pentru sursele de date importate prin intermediul Power Query care sprijină ingestia incrementală. De exemplu, bazele de date SQL Azure cu câmpuri de dată și oră, care indică momentul în care înregistrările de date au fost actualizate ultima dată.

1. [Creați un nou sursă de date bazat pe Power Query](connect-power-query.md).

1. Selectați un sursă de date care acceptă reîmprospătarea incrementală, cum ar fi [Baza de date Azure SQL](/power-query/connectors/azuresqldatabase).

1. Selectați entitățile sau tabelele de ingerat.

1. Finalizați etapele de transformare și selectați **Următorul**.

1. În caseta de dialog **Configurați reîmprospătare incrementală**, selectați **Configurat** pentru a deschide **Setări de reîmprospătare incrementală**. Dacă selectați **Salt**, sursa de date va reîmprospăta întregul set de date.
   > [!TIP]
   > Puteți aplica, de asemenea, reîmprospătarea incrementală mai târziu prin editarea unei surse de date existente.

1. Pe **Setări de reîmprospătare incrementală**, veți configura reîmprospătarea incrementală pentru toate entitățile pe care le-ați selectat la crearea sursei de date.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Configurați setările de reîmprospătare incrementală.":::

1. Selectați o entitate și furnizați următoarele detalii:

   - **Definiți cheia principală**: Selectați o cheie primară pentru entitate sau tabel.
   - **Definiți câmpul „ultima actualizare”**: Acest câmp va afișa doar atributele de tip dată sau oră. Selectați un atribut care indică momentul în care înregistrările au fost actualizate ultima dată. Acesta va fi utilizat pentru a identifica înregistrările care se încadrează în intervalul de timp de reîmprospătare incrementală.
   - **Verificați dacă există actualizări la fiecare**: Specificați cât timp doriți să fie intervalul de timp de reîmprospătare incremental.

1. Selectați **salvare** pentru a finaliza crearea sursei de date. Actualizarea inițială a datelor va fi o reîmprospătare completă. Ulterior, reîmprospătarea de date incrementală se întâmplă așa cum este configurat în pasul anterior.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Configurați reîmprospătarea incrementală pentru sursele de date Azure Data Lake

Customer Insights permite reîmprospătarea incrementală pentru sursele de date conectate Azure Data Lake Storage. Pentru a utiliza absorbția incrementală și reîmprospătarea pentru o entitate, configurați acea entitate atunci când adăugați Azure Data Lake sursă de date sau mai târziu când editați sursă de date. Dosarul de date entității trebuie să conțină următoarele foldere:

- **Date complete** : Dosar cu fișiere de date care conțin înregistrările inițiale
- **Date incrementale** : Folder cu dosare cu ierarhie dată/oră în **aaaa/ll/zz/hh** format care conține actualizările incrementale. **hh** reprezintă ora UTC a actualizărilor și conține **Upsers** și **Șterge** foldere. **Upsers** conține fișiere de date cu actualizări ale înregistrărilor existente sau ale înregistrărilor noi. **Șterge** conține fișiere de date cu înregistrări care trebuie eliminate.

1. Când adăugați sau editați un sursă de date, navigați la **Atribute** panoul pentru entitate.

1. Examinați atributele. Asigurați-vă că un atribut pentru data creată sau ultima actualizare este configurat cu a *dateTime* **Format de date** si a *Calendar.Data* **Tip semantic**. Editați atributul dacă este necesar și selectați **Terminat**.

1. De la **Selectați Entități** panoul, editați entitatea. The **Ingestie incrementală** caseta de selectare este bifată.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Configurați entitățile dintr-o sursă de date pentru reîmprospătare incrementală.":::

   1. Răsfoiți la folderul rădăcină care conține fișierele .csv sau .parquet pentru date complete, suprafețe de date incrementale și ștergeri incrementale de date.
   1. Introduceți extensia pentru datele complete și pentru ambele fișiere incrementale (\. csv sau\. parchet).
   1. Pentru fișierele .csv, selectați delimitatorul de coloană și dacă doriți ca primul rând al fișierului ca antet de coloană.
   1. Selectați **Salvare**.

1. Pentru **Ultima actualizare**, selectați atributul de marcaj temporal al datei.

1. Dacă **Cheia principala** nu este selectat, selectați cheia primară. Cheia primară este un atribut unic pentru entitate. Pentru ca un atribut să fie o cheie primară validă, nu ar trebui să includă valori duplicate, valori lipsă sau valori nule. Atributele tipului de date șir, întreg și GUID sunt acceptate ca chei primare.

1. Selectați **Închide** pentru a salva și a închide panoul.

1. Continuați să adăugați sau să editați sursă de date.

[!INCLUDE [footer-include](includes/footer-banner.md)]
