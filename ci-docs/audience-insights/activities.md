---
title: Activități ale clienților
description: Definiți activitățile clienților și vizualizați-le în cronologia clienților.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667244"
---
# <a name="customer-activities"></a>Activități ale clienților

Combinați activitățile clienților din [diverse surse de date](data-sources.md) în Dynamics 365 Customer Insights pentru a crea o cronologie a clienților care listează activitățile în ordine cronologică. Puteți include cronologia în aplicațiile de Customer Engagement în Dynamics 365 prin intermediul [Program de completare card client](customer-card-add-in.md), sau într-un tablou de bord Power BI.

## <a name="define-an-activity"></a>Definiți o activitate

Sursele dvs. de date includ entități cu date tranzacționale și de activitate din mai multe surse de date. Identificați aceste entități și selectați activitățile pe care doriți să le vizualizați în cronologia clientului. Alegeți entitatea care include activitatea sau activitățile dvs. țintă.

1. În Detalii despre audiență, accesați **Date** > **Activități**.

1. Selectați **Adăugați o activitate**.

   > [!NOTE]
   > O entitate trebuie să aibă cel puțin un atribut de tip **Date** pentru a fi inclus într-o cronologie a clienților și nu puteți adăuga entități fără câmpuri **Date**. Controlul **Adăugați activitate** este dezactivat dacă nu se găsește o astfel de entitate.

1. În panoul **Adăugați activitate**, setați valorile pentru următoarele câmpuri:

   - **Entitate**: Selectați o entitate care include date de tranzacție sau de activitate.
   - **Cheie primară**: Selectați câmpul care identifică în mod unic o înregistrare. Nu ar trebui să conțină valori duplicate, valori goale sau valori lipsă.
   - **Marcă de timp**: Selectați câmpul care reprezintă ora de început a activității dvs.
   - **Eveniment**: Selectați câmpul care este evenimentul pentru activitate.
   - **Adresă web**: Selectați câmpul care reprezintă o adresă URL care furnizează informații suplimentare despre această activitate. De exemplu, sistemul tranzacțional care furnizează această activitate. Această adresă URL poate fi orice câmp din sursa de date sau poate fi construită ca un câmp nou folosind o transformare Power Query. Aceste date URL vor fi stocate în entitatea Activitate unificată, care poate fi consumată în aval folosind API-uri.
   - **Detalii**: Opțional, selectați câmpul care este adăugat pentru detalii suplimentare.
   - **Pictogramă**: Opțional, selectați pictograma care reprezintă această activitate.
   - **Tip de activitate**: Definiți referința de tip de activitate la Common Data Model care descrie cel mai bine definiția semantică a activității.

1. În secțiunee **Configurați relația**, configurați detaliile pentru a conecta datele activității dvs. cu clientul corespunzător.

   > [!div class="mx-imgBorder"]
   > ![Definiți relația dintre entități](media/activities-entities-define.png "Definiți relația dintre entități")

    - **Câmpul entității Activitate**: Selectați câmpul din entitatea dvs. de activitate care va fi utilizat pentru a stabili o relație cu o altă entitate.
    - **Entitate client**: Selectați entitatea clientului sursă corespunzătoare cu care entitatea dvs. de activitate va fi în relație. Vă puteți raporta doar la acele entități de clienți sursă care sunt utilizate în procesul de unificare a datelor.
    - **Câmpul entității clienților**: Acest câmp arată cheia principală a entității clientului sursă, așa cum este selectată în procesul de mapare. Acest câmp cheie principal în entitatea client sursă este utilizat pentru a stabili o relație cu entitatea de activitate.
    - **Nume**: Dacă există deja o relație între această entitate de activitate și entitatea client sursă selectată, numele relației va fi în modul numai în citire. Dacă nu există o astfel de relație, se va crea o nouă relație cu numele furnizat aici.

1. Selectați **Salvare** pentru a vă aplica modificările.

1. În pagina **Activități**, selectați **Executare**.

> [!TIP]
> Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese. În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies). Puteți selecta starea unui proces pentru a vedea detalii despre evoluția întregii lucrări. După selectarea **Vizualizare detalii** pentru una dintre sarcinile jobului, găsiți informații suplimentare: timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate sarcinii.

## <a name="edit-an-activity"></a>Editați o activitate

1. În Detalii despre audiență, accesați **Date** > **Activități**.

2. Selectați entitatea de activitate pe care doriți să o editați și selectați **Editați**. Sau puteți trece deasupra rândului de entitate și selectați pictograma **Editați**.

3. Faceți clic pe pictograma **Editați**.

4. În panoul **Editare activitate**, actualizați valorile și selectați **Salvați**.

5. În pagina **Activități**, selectați **Executare**.

## <a name="delete-an-activity"></a>Ștergeți o activitate

1. În Detalii despre audiență, accesați **Date** > **Activități**.

2. Selectați entitatea de activitate pe care doriți să o eliminați și selectați **Ștergeți**. Sau puteți trece deasupra rândului de entitate și selectați pictograma **Ștergeți**. În plus, puteți selecta mai multe entități de activitate pentru a fi șterse simultan.
   > [!div class="mx-imgBorder"]
   > ![Editarea sau ștergerea relației de entitate](media/activities-entities-edit-delete.png "Editarea sau ștergerea relației de entitate")

3. Selectați pictograma **Ștergeți**.

4. Confirmați ștergerea.
