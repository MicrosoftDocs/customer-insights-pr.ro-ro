---
title: Îmbinați entitățile în unificarea datelor
description: Îmbinați entitățile pentru a crea profiluri de clienți unificate.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6e64154dc58f679d13033fa55a60cd0c306f62f31548b8ce98ea1ed5f423b3e9
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035017"
---
# <a name="merge-entities"></a>Îmbinare entități

Faza de îmbinare este ultima fază din procesul de unificare a datelor. Scopul său este reconcilierea datelor conflictuale. Exemple de date conflictuale ar putea include un nume de client care se găsește în două seturi de date, dar care apare puțin diferit în fiecare („Grant Marshall” față de „Grant Marshal”) sau un număr de telefon care diferă în format (617-803-091X versus 617803091X ). Fuzionarea acelor puncte de date conflictuale se face pe baza atributelor.

:::image type="content" source="media/merge-fields-page.png" alt-text="Pagina de îmbinare din procesul de unificare a datelor, afișând tabelul cu câmpuri îmbinate care definesc profilul de client unificat.":::

După completarea [fazei de potrivire](match-entities.md), începeți faza de îmbinare selectând dala **Îmbinare** pe pagina **Unificare**.

## <a name="review-system-recommendations"></a>Revizuiți recomandările sistemului

În secțiunea **Date** > **Unificare** > **Îmbinare**, alegeți și excludeți atributele de îmbinat cu entitatea de profil de client unificat. Profilul de client unificat este rezultat al procesului de unificare a datelor. Unele atribute sunt combinate automat de sistem.

Pentru a vedea atributele ce sunt incluse într-unul dintre atributele dvs. îmbinate automat, selectați acel atribut îmbinat în fila de tabel **Câmpurile clienților**. Atributele care compun atributul îmbinat apar în două rânduri noi sub atributul îmbinat.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Separarea, redenumirea, excluderea și editarea câmpurilor îmbinate

Puteți să modificați modul în care sistemul procesează atributele îmbinate pentru a genera profilul de client unificat. Selectați **Afișați mai multe** și alegeți ce vreți să schimbați.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opțiuni din meniul derulant Afișați mai multe pentru a gestiona atributele combinate.":::

Pentru mai multe informații vedeți secțiunile următoare.

## <a name="separate-merged-fields"></a>Câmpuri îmbinate separate

Pentru a separa câmpurile îmbinate, găsiți atributul în tabel. Câmpurile separate sunt afișate drept puncte de date individuale în profilul de client unificat. 

1. Selectați câmpul îmbinat.
  
1. Selectați **Afișați mai multe** și alegeți **Câmpuri separate**.
 
1. Confirmați separarea.

1. Selectați **Salvare** și **Rulare** pentru a procesa modificările.

## <a name="rename-merged-fields"></a>Redenumiți câmpurile îmbinate

Schimbați numele afișat al atributelor combinate. Nu puteți modifica numele entității de ieșire.

1. Selectați câmpul îmbinat.
  
1. Selectați **Afișați mai multe** și alegeți **Redenumire**.

1. Confirmați numele afișat modificat. 

1. Selectați **Salvare** și **Rulare** pentru a procesa modificările.

## <a name="exclude-merged-fields"></a>Câmpuri îmbinate excluse

Excludeți un atribut din profilul de client unificat. Dacă câmpul e utilizat în alte procese, de exemplu într-un segment, eliminați-l din aceste procese înainte de a-l exclude din profilul clientului. 

1. Selectați câmpul îmbinat.
  
1. Selectați **Afișați mai multe** și alegeți **Excludere**.

1. Confirmați excluderea.

1. Selectați **Salvare** și **Rulare** pentru a procesa modificările. 

Pe pagina **Îmbinare**, selectați **Câmpuri excluse** pentru a vedea lista tuturor câmpurilor excluse. Acest panou vă permite să adăugați câmpuri excluse înapoi.

## <a name="manually-combine-fields"></a>Îmbinați manual câmpurile

Specificați manual un atribut îmbinat. 

1. Pe pagina **Combinare**, selectați **Combinați câmpuri**.

1. Furnizați un **Nume** și un **Nume al câmpului de ieșire**.

1. Alegeți un câmp de adăugat. Selectați **Adăugați câmpuri** pentru combinarea mai multor câmpuri.

1. Confirmați excluderea.

1. Selectați **Salvare** și **Rulare** pentru a procesa modificările. 

## <a name="change-the-order-of-fields"></a>Modificarea ordinii câmpurilor

Unele entități conțin mai multe detalii decât altele. Dacă o entitate include cele mai recente date despre un câmp, le puteți oferi prioritate față de alte entități atunci când îmbinați valorile.

1. Selectați câmpul îmbinat.
  
1. Selectați **Afișați mai multe** și alegeți **Editare**.

1. În panoul **Combinați câmpurile**, selectați **Mutați în sus / în jos** pentru a seta ordinea sau glisați și fixați-le în poziția dorită.

1. Confirmați modificarea.

1. Selectați **Salvare** și **Rulare** pentru a procesa modificările.

## <a name="run-your-merge"></a>Executați-vă unificarea

Indiferent dacă fuzionați manual atributele sau lăsați sistemul să le îmbine, puteți rula întotdeauna fuziunea. Selectați **Executare** pe pagina **Îmbinare** pentru a porni procesul.

> [!div class="mx-imgBorder"]
> ![Îmbinare date Salvați și rulați.](media/configure-data-merge-save-run.png "Îmbinare date Salvați și rulați")

Alege **Rulați numai îmbinarea** dacă doriți doar să vedeți rezultatul reflectat în entitatea client unificată. Procesele din aval vor fi reîmprospătate ca [definite în programul de reîmprospătare](system.md#schedule-tab).

Alegeți **Rulați procesele de îmbinare și flux spre aval** pentru a reîmprospăta sistemul cu modificările dvs. Toate procesele, inclusiv îmbogățirea, segmentele și măsurile vor fi reluate automat. După ce toate procesele din aval s-au finalizat, profilurile clienților reflectă orice modificare făcută.

Pentru a face mai multe modificări și a relua pasul, puteți anula o îmbinare în curs. Selectați **Se reîmprospătează ...** și selectați **Anulare operațiune** în panoul lateral care apare.

> [!TIP]
> După rularea procesului de îmbinare, selectați starea procesului pentru a deschide panoul **Detalii despre activitate**. Oferă o prezentare generală despre timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate activității. Selectați **Vezi detalii** pentru a vedea ce entități au participat la procesul de potrivire, dacă soluționarea conflictului a reușit și dacă actualizările au fost publicate cu succes.  
> Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese. În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Cale de drill-down pentru a ajunge la procesarea detaliilor din legătura de stare a activității.":::

## <a name="next-step"></a>Următorul pas

Configurați [Activități](activities.md), [Îmbogățire](enrichment-hub.md), sau [Relații](relationships.md) pentru a obține mai multe informații despre clienți.

Dacă ați configurat deja activități, îmbogățire sau segmente, acestea vor fi procesate automat pentru a utiliza cele mai recente date despre clienți.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
