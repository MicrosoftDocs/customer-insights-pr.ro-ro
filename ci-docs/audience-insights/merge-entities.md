---
title: Îmbinați entitățile în unificarea datelor
description: Îmbinați entitățile pentru a crea profiluri de clienți unificate.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597848"
---
# <a name="merge-entities"></a>Îmbinare entități

Faza de îmbinare este ultima fază din procesul de unificare a datelor. Scopul său este reconcilierea datelor conflictuale. Exemple de date conflictuale ar putea include un nume de client care se găsește în două seturi de date, dar care apare puțin diferit în fiecare („Grant Marshall” față de „Grant Marshal”) sau un număr de telefon care diferă în format (617-803-091X versus 617803091X ). Fuzionarea acelor puncte de date conflictuale se face pe baza atributelor.

După completarea [fazei de potrivire](match-entities.md), începeți faza de îmbinare selectând dala **Îmbinare** pe pagina **Unificare**.

## <a name="review-system-recommendations"></a>Revizuiți recomandările sistemului

Pe pagina **Îmbinare**, alegeți și excludeți atributele de îmbinat în cadrul entității dvs. de profil de client unificat (rezultatul procesului de configurare). Unele atribute sunt combinate automat de sistem.

### <a name="view-merged-attributes"></a>Vizualizare atribute îmbinate

Pentru a vizualiza atributele care sunt incluse într-unul dintre atributele combinate automat, selectați acel atribut combinat. Cele două atribute care compun acel atribut combinat apar în două rânduri noi sub atributul îmbinat.

> [!div class="mx-imgBorder"]
> ![Selectați atributul îmbinat](media/configure-data-merge-profile-attributes.png "Selectați atributul îmbinat")

### <a name="separate-merged-attributes"></a>Separați atribute îmbinate

Pentru a separa sau a despărți oricare dintre atributele combinate automat, găsiți atributul în tabelul **Atribute profil**.

1. Selectați butonul elipsă (...).
  
2. În lista verticală, selectați **Câmpuri separate**.

### <a name="remove-merged-attributes"></a>Eliminați atribute îmbinate

Pentru a exclude un atribut de la entitatea profilului de client final, găsiți-l în tabelul **Atribute profil**.

1. Selectați butonul elipsă (...).
  
2. În lista verticală, selectați **Nu îmbinați**.

   Atributul este mutat la secțiunea **Eliminat din înregistrarea client**.

## <a name="manually-add-a-merged-attribute"></a>Adăugați manual un atribut combinat

Pentru a adăuga un atribut combinat, accesați pagina **Îmbinare**.

1. Selectați **Adăugați atributul îmbinat**.

2. Furnizați un **Nume** pentru a-l identifica mai târziu pe pagina **Îmbinare**.

3. Opțional, furnizați un **Numele afișat** ce apare în entitatea de profil a clientului unificată.

4. Configurare **Selectați atributele dublate** pentru a selecta atributele pe care doriți să le îmbinați dintre entitățile potrivite. De asemenea, puteți căuta atribute.

5. Configurați **Clasificare după importanță** pentru a acorda prioritate unui atribut asupra celorlalte. De exemplu, dacă entitatea *WebAccountCSV* include cele mai precise date despre atribute *Nume complete*, puteți acorda prioritate acestei entități *ContactCSV* prin selectarea *WebAccountCSV*. Ca urmare, *WebAccountCSV* trece la prima prioritate, în timp ce *ContactCSV* trece la a doua prioritate atunci când asamblați valori pentru atributul *Numele complet*.

## <a name="run-your-merge"></a>Executați-vă unificarea

Indiferent dacă fuzionați manual atributele sau lăsați sistemul să le îmbine, puteți rula întotdeauna fuziunea. Selectați **Executare** pe pagina **Îmbinare** pentru a porni procesul.

> [!div class="mx-imgBorder"]
> ![Îmbinare date Salvați și rulați](media/configure-data-merge-save-run.png "Îmbinare date Salvați și rulați")

Pentru a face modificări suplimentare și a relua pasul, puteți anula o îmbinare în curs. Selectați **Se reîmprospătează ...** și selectați **Anulare operațiune** în panoul lateral care apare.

După schimbarea textului de la **Se reîmprospătează ...** la **Reușit**, îmbinarea s-a finalizat și a rezolvat contradicțiile din datele dvs. în conformitate cu politicile pe care le-ați definit. Atributele îmbinate și neîmbinate sunt incluse în entitatea de profil unificat. Atributele excluse nu sunt incluse în entitatea de profil unificat.

Dacă nu a fost prima dată când ați executat o îmbinare cu succes, toate procesele din aval, inclusiv îmbogățirea, segmentarea și măsurile se vor repeta în mod automat. După ce toate procesele din aval au fost reluate, profilurile clienților reflectă orice modificări pe care le-ați efectuat.

> [!TIP]
> Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese. În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies). Puteți selecta starea unui proces pentru a vedea detalii despre evoluția întregii lucrări. După selectarea **Vizualizare detalii** pentru una dintre sarcinile jobului, găsiți informații suplimentare: timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate sarcinii.

## <a name="next-step"></a>Următorul pas

Configurați [Activități](activities.md), [Îmbogățire](enrichment-microsoft-graph.md), sau [Relații](relationships.md) pentru a obține mai multe informații despre clienți.

Dacă ați configurat deja activități, îmbogățire sau relații sau dacă ați definit segmente, acestea vor fi procesate automat pentru a utiliza cele mai recente date despre clienți.




[!INCLUDE[footer-include](../includes/footer-banner.md)]