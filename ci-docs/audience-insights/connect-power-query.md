---
title: Ingerați date prin a Power Query conector (conține video)
description: Conectori pentru surse de date bazate pe Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 727cb9a4d754b6dbd74d6ecab1b183d41f713d8f
ms.sourcegitcommit: aadee829eff111c95eb30c0a97a68dcc87994acf
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/04/2022
ms.locfileid: "8092087"
---
# <a name="connect-to-a-power-query-data-source"></a>Conectați-vă la a Power Query sursă de date

Power Query oferă un set larg de conectori pentru a ingera date. Majoritatea acestor conectori sunt suportați de Dynamics 365 Customer Insights. 

Adăugarea surselor de date pe baza Power Query conectorii urmează, în general, pașii descriși în această secțiune. Cu toate acestea, în funcție de conectorul pe care îl utilizați, sunt necesare informații diferite. Pentru a afla mai multe, consultați documentația despre conectorii individuali din [Power Query referință la conector](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Creați o nouă sursă de date

1. În Detalii despre audiență, accesați **Date** > **Surse de date**.

1. Selectați **Adăugați sursa de date**.

1. Selectați **Microsoft Power Query**.

1. Furnizați un **Nume** pentru sursa de date și selectați **Următorul** pentru a crea sursă de date.

1. Alegeți unul dintre [conectorii disponibili](#available-power-query-data-sources). În acest exemplu, selectăm **Text/CSV** conector.

1. Introduceți detaliile necesare în **Setări de conectare** pentru conectorul selectat și selectați **Următorul** pentru a vedea o previzualizare a datelor.

1. Selectați **Transformați datele**. În acest pas, veți adăuga entități la sursă de date. Entitățile sunt seturi de date. Dacă aveți o bază de date care include mai multe seturi de date, fiecare set de date este propria entitate.

1. The **Power Query - Editați interogări** dialog vă permite să revizuiți și să rafinați datele. Entitățile identificate de sisteme în sursa de date selectată apar în panoul din stânga.

   > [!div class="mx-imgBorder"]
   > ![Editați interogările de dialog.](media/data-manager-configure-edit-queries.png "Editați interogările de dialog")

1. De asemenea, vă puteți transforma datele. Selectați o entitate de editat sau de transformat. Utilizați opțiunile din Power Query fereastra pentru a aplica transformări. Fiecare transformare este listată sub **Pași aplicați**. Power Query oferă numeroase opțiuni de transformare prefabricate. Pentru mai multe informații, vezi [Power Query Transformări](/power-query/power-query-what-is-power-query#transformations).

   Vă recomandăm să utilizați următoarele transformări:

   - Dacă ingerați date dintr-un fișier CSV, primul rând conține adesea anteturi. Mergi la **Transforma** și selectați **Utilizați primul rând ca antete**.
   - Asigurați-vă că tipul de date este setat corespunzător. De exemplu, pentru câmpurile de dată, selectați un tip de dată.

1. Pentru a adăuga entități suplimentare la sursă de date în fișierul **Editați interogările** dialog, accesați **Acasă** și selectați **Obțineți date**.

1. Selectați **salva** în partea de jos a Power Query fereastra pentru a salva transformările. După salvare, veți găsi sursa de date la **Date** > **Surse de date**.

1. Pe pagina **Surse de date**, veți observa că noua sursă de date este în stare **Se reîmprospătează**.

## <a name="available-power-query-data-sources"></a>Disponibil Power Query surse de date

Vezi [Power Query referință la conector](/power-query/connectors/) pentru o listă de conectori pe care îi puteți utiliza pentru a importa date în Customer Insights. 

Conectori cu o bifă în **Informații despre clienți (fluxuri de date)** coloana sunt disponibile pentru a crea noi surse de date pe baza Power Query. Consultați documentația unui conector specific pentru a afla mai multe despre cerințele preliminare, limitările și alte detalii.

## <a name="edit-power-query-data-sources"></a>Editați | ×Power Query surse de date

> [!NOTE]
> Este posibil să nu fie posibilă modificarea surselor de date care sunt utilizate în prezent într-unul dintre procesele aplicației (*segmentare*, *potrivire* sau *îmbinare*, de exemplu). 
>
> În **Setări** pagina, puteți urmări progresul fiecărui proces activ. Când se termină un proces, aveți posibilitatea să reveniți la pagina **Surse de date** și să efectuați modificările.

1. În Detalii despre audiență, accesați **Date** > **Surse de date**.

2. Selectați elipsa verticală de lângă sursă de date pe care doriți să o modificați și selectați **Editaț** din meniul derulant.

   > [!div class="mx-imgBorder"]
   > ![Opțiunea editare.](media/edit-option-data-sources.png "Opțiunea editare")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Aplicați modificările și transformările dvs. în **Power Query - Editați interogări** dialog așa cum este descris în [Creați un nou sursă de date](#create-a-new-data-source) secțiune.

4. Selectați **salva** în Power Query după finalizarea modificărilor pentru a salva modificările.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
