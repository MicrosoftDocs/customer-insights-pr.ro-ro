---
title: Ingerați date prin a Power Query conector (conține video)
description: Conectori pentru surse de date bazate pe Power Query.
ms.date: 05/09/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: b99c3b446e580f455f9678d54d9db414aea9b331
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011672"
---
# <a name="connect-to-a-power-query-data-source"></a>Conectați-vă la a Power Query sursă de date

Power Query oferă un set larg de conectori pentru a ingera date. Majoritatea acestor conectori sunt suportați de Dynamics 365 Customer Insights.

Adăugarea surselor de date pe baza Power Query conectorii urmează, în general, pașii descriși în această secțiune. Cu toate acestea, în funcție de conectorul pe care îl utilizați, sunt necesare informații diferite. Pentru a afla mai multe, consultați documentația despre conectorii individuali din [Power Query referință la conector](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Creați o nouă sursă de date

1. Accesați **Date** > **Surse de date**.

1. Selectați **Adăugați sursa de date**.

1. Selectați **Microsoft Power Query**.

1. Furnizeaza un **Nume** și un opțional **Descriere** pentru sursă de date și selectați **Următorul**.

1. Alegeți unul dintre [conectorii disponibili](#available-power-query-data-sources). În acest exemplu, selectăm **Text/CSV** conector.

1. Introduceți detaliile necesare în **Setări de conectare** pentru conectorul selectat și selectați **Următorul** pentru a vedea o previzualizare a datelor.

1. Selectați **Transformați datele**. În acest pas, veți adăuga entități la sursă de date. Entitățile sunt seturi de date. Dacă aveți o bază de date care include mai multe seturi de date, fiecare set de date este propria entitate.

1. The **Power Query - Editați interogări** dialog vă permite să revizuiți și să rafinați datele. Entitățile identificate de sisteme în sursa de date selectată apar în panoul din stânga.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Editați interogările de dialog":::

1. De asemenea, vă puteți transforma datele. Selectați o entitate de editat sau de transformat. Utilizați opțiunile din Power Query fereastra pentru a aplica transformări. Fiecare transformare este listată sub **Pași aplicați**. Power Query oferă numeroase opțiuni de transformare prefabricate. Pentru mai multe informații, vezi [Power Query Transformări](/power-query/power-query-what-is-power-query#transformations).

   Vă recomandăm să utilizați următoarele transformări:

   - Dacă ingerați date dintr-un fișier CSV, primul rând conține adesea anteturi. Mergi la **Transforma** și selectați **Utilizați primul rând ca antete**.
   - Asigurați-vă că tipul de date este setat corespunzător. De exemplu, pentru câmpurile de dată, selectați un tip de dată.

1. Pentru a adăuga entități suplimentare la sursă de date în fișierul **Editați interogările** dialog, accesați **Acasă** și selectați **Obțineți date**. Repetați pașii 6-10 până când ați adăugat toate entitățile pentru acest sursă de date.

1. Selectați **Salvare**. The **Surse de date** se deschide pagina afișând noul sursă de date în **Înviorător** stare.

### <a name="available-power-query-data-sources"></a>Disponibil Power Query surse de date

Vezi [Power Query referință la conector](/power-query/connectors/) pentru o listă de conectori pe care îi puteți utiliza pentru a importa date în Customer Insights.

Conectori cu o bifă în **Informații despre clienți (fluxuri de date)** coloana sunt disponibile pentru a crea noi surse de date pe baza Power Query. Consultați documentația unui anumit conector pentru a afla mai multe despre cerințele sale preliminare, [limitări de interogare](/power-query/power-query-online-limits), și alte detalii.

## <a name="add-data-from-on-premises-data-sources"></a>Adăugați date din sursele de date locale

Ingerarea datelor din sursele de date local este acceptată pe baza Microsoft Power Platform fluxuri de date (PPDF). Puteți activa fluxurile de date în Customer Insights prin [oferind Microsoft Dataverse URL de mediu](create-environment.md) la configurarea mediului.

Surse de date care sunt create după asocierea a Dataverse mediu cu utilizarea Customer Insights [Power Platform fluxuri de date](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) în mod implicit. Fluxurile de date acceptă conectivitate locală folosind gateway-ul de date. Puteți elimina și recrea surse de date care existau înainte de a Dataverse mediu a fost asociat [folosind local gateway-uri de date](/data-integration/gateway/service-gateway-app).

Gateway-urile de date de la un mediu existent Power BI sau Power Apps vor fi vizibile și le puteți reutiliza în Customer Insights. Pagina surselor de date afișează linkuri pentru a accesa mediul Microsoft Power Platform în care puteți vizualiza și configura gateway-urile de date local.

> [!IMPORTANT]
> Asigurați-vă că gateway-urile sunt actualizate la cea mai recentă versiune. Puteți instala o actualizare și reconfigura un gateway dintr-un prompt afișat pe ecranul gateway direct sau [descărcați cea mai recentă versiune](https://powerapps.microsoft.com/downloads/). Dacă nu utilizați cea mai recentă versiune de gateway, reîmprospătarea fluxului de date eșuează cu mesaje de eroare precum **Cuvântul cheie nu este acceptat: proprietăți de configurare. Nume parametru: cuvânt cheie**.

## <a name="edit-power-query-data-sources"></a>Editați | ×Power Query surse de date

> [!NOTE]
> Este posibil să nu fie posibilă modificarea surselor de date care sunt utilizate în prezent într-unul dintre procesele aplicației (*segmentare*, *potrivire* sau *îmbinare*, de exemplu).
>
> În **Setări** pagina, puteți urmări progresul fiecărui proces activ. Când se termină un proces, aveți posibilitatea să reveniți la pagina **Surse de date** și să efectuați modificările.

1. Accesați **Date** > **Surse de date**.

1. Lângă sursă de date pe care doriți să o actualizați, selectați **Editați | ×**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

1. Aplicați modificările și transformările dvs. în **Power Query - Editați interogările** dialog așa cum este descris în [Creați un nou sursă de date](#create-a-new-data-source) secțiune.

1. Selectați **Salvați** în Power Query după finalizarea modificărilor pentru a salva modificările.
