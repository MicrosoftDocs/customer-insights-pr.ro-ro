---
title: Ingerare date printr-un conector Power Query
description: Conectori pentru surse de date bazate pe Power Query.
ms.date: 11/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 5d54d33c235e646644e8874e5b0c28898dcff11a
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732233"
---
# <a name="connect-to-a-power-query-data-source"></a>Conectați-vă la o sursă de date Power Query

Power Query oferă un set larg de conectori pentru a ingera date. Majoritatea acestor conectori sunt acceptați de Dynamics 365 Customer Insights. Adăugarea surselor de date pe baza conectorilor Power Query urmează în general pașii descriși în secțiunea următoare. Cu toate acestea, în funcție de conectorul pe care îl utilizați, sunt necesare informații diferite. Pentru mai multe informații, consultați documentația despre conectorii individuali din [Conectorul de referință Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Creați o nouă sursă de date

1. În Detalii despre audiență, accesați **Date** > **Surse de date**.

1. Selectați **Adăugați sursa de date**.

1. Alegeți metoda **Importați date** și selectați **Următorul**.

1. Furnizați un **Nume** pentru sursa de date și selectați **Următorul** pentru a crea sursă de date. Numire recomandări: 
   - Începeți cu o literă.
   - Folosiți numai litere și cifre. Nu sunt permise caracterele speciale și spațiile.
   - Folosiți între 3 și 64 de caractere.

1. Alegeți unul dintre [conectorii disponibili](#available-power-query-data-sources). Pentru acest exemplu, selectăm conectorul **Text/CSV**.

1. Introduceți detaliile necesare în **Setări de conectare** pentru conectorul selectat și selectați **Următorul** pentru a vedea o previzualizare a datelor.

1. Selectați **Transformați datele**. În acest pas, veți adăuga entități la sursă de date. Entitățile sunt seturi de date. Dacă aveți o bază de date care include mai multe seturi de date, fiecare set de date este propria entitate.

1. Dialogul **Power Query - Editați interogările** vă permite să examinați și să rafinați datele. Entitățile identificate de sisteme în sursa de date selectată apar în panoul din stânga.

   > [!div class="mx-imgBorder"]
   > ![Editați interogările de dialog.](media/data-manager-configure-edit-queries.png "Editați interogările de dialog")

1. De asemenea, vă puteți transforma datele. Selectați o entitate de editat sau de transformat. Utilizați opțiunile din fereastra Power Query pentru a aplica transformări. Fiecare transformare este listată sub **Pași aplicați**. Power Query oferă numeroase opțiuni de transformare pre-construite. Pentru informații suplimentare, consultați [Transformări Power Query](/power-query/power-query-what-is-power-query#transformations).

1. Puteți adăuga entități suplimentare la sursa dvs. de date selectând **Preluare date** în dialogul **Editare interogări**.

   Aceste transformări sunt foarte recomandate:

   - Dacă ingerați date dintr-un fișier CSV, primul rând conține adesea anteturi. Accesați **Transformați tabelul** și selectați **Folosiți anteturi ca primul rând**.
   - Asigurați-vă că tipul de date este setat corespunzător.

1. Selectați **Salvare** din partea de jos a ferestrei Power Query pentru a vă salva transformările. După salvare, veți găsi sursa de date la **Date** > **Surse de date**.

1. Pe pagina **Surse de date**, veți observa că noua sursă de date este în stare **Se reîmprospătează**.

## <a name="available-power-query-data-sources"></a>Surse de date Power Query disponibile

Consultați [Conectorul de referință Power Query](/power-query/connectors/) pentru o listă actualizată de conectori pe care îi puteți selecta pentru a importa date în Customer Insights. 

Conectori cu bifă în coloana **Customer Insights (fluxuri de date)** sunt disponibili pentru a crea noi surse de date bazate pe Power Query. Consultați documentația unui conector specific pentru a afla mai multe despre cerințele preliminare, limitările și alte detalii.

## <a name="edit-power-query-data-sources"></a>Editați surse de date Power Query

> [!NOTE]
> Este posibil să nu fie posibilă modificarea surselor de date care sunt utilizate în prezent într-unul dintre procesele aplicației (*segmentare*, *potrivire* sau *îmbinare*, de exemplu). 
>
> Utilizând pagina **Setări**, puteți urmări progresul fiecărui proces activ. Când se termină un proces, aveți posibilitatea să reveniți la pagina **Surse de date** și să efectuați modificările.

1. În Detalii despre audiență, accesați **Date** > **Surse de date**.

2. Selectați elipsa verticală de lângă sursă de date pe care doriți să o modificați și selectați **Editaț** din meniul derulant.

   > [!div class="mx-imgBorder"]
   > ![Opțiunea editare.](media/edit-option-data-sources.png "Opțiunea editare")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Aplicați modificările și transformările dvs. în **Power Query - Editați interogările** așa cum au fost descrise în secțiunea [Creați o nouă sursă de date](#create-a-new-data-source).

4. Selectați **Salvare** în Power Query după finalizarea modificărilor pentru a salva modificările.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
