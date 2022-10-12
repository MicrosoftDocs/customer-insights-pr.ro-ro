---
title: Conectați-vă la a Power Query sursă de date (conține videoclip)
description: Ingerați date prin a Power Query conector (conține video).
ms.date: 09/29/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4cc7e57dfb0f8d050e91adc441c24e849882f5d8
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609911"
---
# <a name="connect-to-a-power-query-data-source"></a>Conectați-vă la a Power Query sursă de date

Power Query oferă un set larg de conectori pentru a ingera date. Majoritatea acestor conectori sunt suportați de Dynamics 365 Customer Insights.

Adăugarea surselor de date pe baza Power Query conectorii urmează, în general, pașii descriși în această secțiune. Cu toate acestea, în funcție de conectorul pe care îl utilizați, sunt necesare informații diferite. Pentru a afla mai multe, consultați documentația despre conectorii individuali din [Power Query referință la conector](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Creați o nouă sursă de date

1. Accesați **Date** > **Surse de date**.

1. Selectați **Adăugați sursa de date**.

1. Selectați **Microsoft Power Query**.

1. Furnizeaza un **Nume** si un optional **Descriere** pentru sursă de date și selectați **Următorul**.

1. Alegeți unul dintre [conectorii disponibili](#available-power-query-data-sources). În acest exemplu, selectăm **Text/CSV** conector.

1. Introduceți detaliile necesare în **Setări de conectare** pentru conectorul selectat și selectați **Următorul** pentru a vedea o previzualizare a datelor.

1. Selectați **Transformați datele**.

1. Examinați și rafinați datele dvs. în **Power Query - Editați interogările** pagină. Entitățile identificate de sisteme în sursa de date selectată apar în panoul din stânga.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Editați interogările de dialog":::

1. Transformă-ți datele. Selectați o entitate de editat sau de transformat. Utilizați opțiunile din Power Query fereastra pentru a aplica transformări. Fiecare transformare este listată sub **Pași aplicați**. Power Query oferă numeroase [transformare preconstruită](/power-query/power-query-what-is-power-query#transformations) Opțiuni.

   > [!IMPORTANT]
   > Vă recomandăm să utilizați următoarele transformări:
   >
   > - Dacă ingerați date dintr-un fișier CSV, primul rând conține adesea anteturi. Mergi la **Transforma** și selectați **Utilizați primul rând ca antete**.
   > - Asigurați-vă că tipul de date este setat corespunzător și se potrivește cu datele. De exemplu, pentru câmpurile de dată, selectați un tip de dată.

1. Pentru a adăuga entități suplimentare la sursă de date în fișierul **Editați interogările** dialog, accesați **Acasă** și selectați **Obțineți date**. Repetați pașii 5-10 până când ați adăugat toate entitățile pentru acest sursă de date. Dacă aveți o bază de date care include mai multe seturi de date, fiecare set de date este propria entitate.

1. Selectați **Salvare**. The **Surse de date** se deschide pagina afișând noul sursă de date în **Înviorător** stare.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Încărcarea datelor poate dura timp. După o reîmprospătare cu succes, datele ingerate pot fi revizuite din [**Entități**](entities.md) pagină.

> [!CAUTION]
>
> - Un sursă de date bazat pe Power Query creează o [fluxul de date în Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Nu schimbați numele unui flux de date în Power Platform centru de administrare care este utilizat în Customer Insights. Redenumirea unui flux de date cauzează probleme cu referințele dintre Customer Insights sursă de date și Dataverse flux de date.
> - Evaluări concurente pentru Power Query sursele de date din Customer Insights au același lucru [limitele de reîmprospătare, cum ar fi Fluxuri de date în PowerBI.com](/power-query/power-query-online-limits#refresh-limits). Dacă o reîmprospătare a datelor eșuează deoarece a atins limita de evaluare, vă recomandăm să ajustați programul de reîmprospătare pentru fiecare flux de date pentru a vă asigura că sursele de date nu sunt procesate în același timp.

### <a name="available-power-query-data-sources"></a>Disponibil Power Query surse de date

Vezi [Power Query referință la conector](/power-query/connectors/) pentru o listă de conectori pe care îi puteți utiliza pentru a importa date în Customer Insights.

Conectori cu o bifă în **Informații despre clienți (fluxuri de date)** coloana sunt disponibile pentru a crea noi surse de date pe baza Power Query. Consultați documentația unui anumit conector pentru a afla mai multe despre cerințele sale preliminare, [limitări de interogare](/power-query/power-query-online-limits), și alte detalii.

## <a name="add-data-from-on-premises-data-sources"></a>Adăugați date din sursele de date locale

Ingerarea datelor din sursele de date local este acceptată pe baza Microsoft Power Platform fluxuri de date (PPDF). Puteți activa fluxurile de date în Customer Insights prin [oferind Microsoft Dataverse URL a mediului](create-environment.md) la configurarea mediului.

Surse de date care sunt create după asocierea a Dataverse mediu cu utilizarea Customer Insights [Power Platform fluxuri de date](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) în mod implicit. Fluxurile de date acceptă conectivitate locală folosind gateway-ul de date. Puteți elimina și recrea surse de date care existau înainte de a Dataverse mediu a fost asociat [folosind local gateway-uri de date](/data-integration/gateway/service-gateway-app).

Gateway-uri de date de la un existent Power BI sau Power Apps mediul va fi vizibil și le puteți reutiliza în Customer Insights dacă gateway-ul de date și mediul Customer Insights se află în aceeași regiune Azure. Pagina surselor de date afișează linkuri pentru a accesa mediul Microsoft Power Platform în care puteți vizualiza și configura gateway-urile de date local.

> [!IMPORTANT]
> Asigurați-vă că gateway-urile sunt actualizate la cea mai recentă versiune. Puteți instala o actualizare și reconfigura un gateway dintr-un prompt afișat pe ecranul gateway direct sau [descărcați cea mai recentă versiune](https://powerapps.microsoft.com/downloads/). Dacă nu utilizați cea mai recentă versiune de gateway, reîmprospătarea fluxului de date eșuează cu mesaje de eroare precum **Cuvântul cheie nu este acceptat: proprietăți de configurare. Nume parametru: cuvânt cheie**.
>
> Erorile cu gateway-urile de date local din Customer Insights sunt adesea cauzate de probleme de configurare. Pentru mai multe informații despre depanarea gateway-urilor de date, consultați [Depanați gateway-ul de date local](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>Editați | ×Power Query surse de date

> [!NOTE]
> Este posibil să nu fie posibilă efectuarea de modificări la sursele de date care sunt utilizate în prezent într-unul dintre procesele aplicației (segmentarea sau unificarea datelor, de exemplu).
>
> În **Setări** pagina, puteți urmări progresul fiecărui proces activ. Când se termină un proces, aveți posibilitatea să reveniți la pagina **Surse de date** și să efectuați modificările.

1. Accesați **Date** > **Surse de date**.

1. Lângă sursă de date pe care doriți să o actualizați, selectați **Editați | ×**.

1. Aplicați modificările și transformările dvs. în **Power Query - Editați interogările** dialog așa cum este descris în [Creați un nou sursă de date](#create-a-new-data-source) secțiune.

1. Selectați **Salvați** pentru a aplica modificările și a reveni la **Surse de date** pagină.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupt-data"></a>Motive obișnuite pentru erori de asimilare sau date corupte

### <a name="data-type-does-not-match-data"></a>Tipul de date nu se potrivește cu datele

Cea mai frecventă nepotrivire a tipurilor de date apare atunci când un câmp de dată nu este setat la formatul de dată corect.

Datele pot fi fixate la sursă și reingerate. Sau remediați transformarea în Customer Insights. Pentru a remedia transformarea:

1. Accesați **Date** > **Surse de date**.

1. Lângă sursă de date cu datele corupte, selectați **Editați | ×**.

1. Selectați **Următorul**.

1. Selectați fiecare dintre interogări și căutați transformări aplicate în „Pași aplicați” care sunt incorecte sau coloane de dată care nu au fost transformate cu un format de dată.

   :::image type="content" source="media/PQ_corruped_date.png" alt-text="Power Query- Editați afișând formatul de dată incorect":::

1. Schimbați tipul de date pentru a se potrivi corect cu datele.

1. Selectați **Salvare**. Acel sursă de date este reîmprospătat.

## <a name="troubleshoot-ppdf-power-query-based-data-source-refresh-issues"></a>Depanați PPDF Power Query -based sursă de date probleme de reîmprospătare

Dacă datele sunt învechite sau primiți erori după o reîmprospătare sursă de date, efectuați următorii pași:

1. Navigați la [Power Platform](https://make.powerapps.com).

1. Selectează **Mediu inconjurator** pentru instanța dvs. de Customer Insights.

1. Navigheaza catre **Fluxuri de date**.

1. Pentru fluxul de date care corespunde sursă de date din Customer Insights, selectați punctele de suspensie verticale (&vellip;) și apoi selectați **Afișează istoricul reîmprospătărilor**.

1. Dacă **stare** a fluxului de date este **Succes**, proprietatea asupra Power Query -based sursă de date s-ar putea fi schimbat:

   1. Examinați programul de reîmprospătare din istoricul de reîmprospătare.
   1. Setați programul noului proprietar și salvați setările.

1. Dacă **stare** a fluxului de date este **A eșuat**:

   1. Descărcați fișierul istoric de reîmprospătare.
   1. Examinați fișierul descărcat pentru motivul eșecului.
   1. Dacă eroarea nu poate fi rezolvată, selectați **?** Pentru a deschide un bilet de asistență. Includeți fișierul de istoric al reîmprospătărilor descărcat.


[!INCLUDE [footer-include](includes/footer-banner.md)]
