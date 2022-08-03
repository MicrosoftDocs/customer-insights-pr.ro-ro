---
title: Conector Power BI (previzualizare)
description: Aflați cum să utilizați conectorul Dynamics 365 Customer Insights în Power BI.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196685"
---
# <a name="power-bi-connector-preview"></a>Conector Power BI (previzualizare)

Creați vizualizări pentru datele dvs. cu ajutorul Microsoft Power BI Desktop. Generați informații suplimentare și creați rapoarte cu datele clientului dvs. unificate.

## <a name="prerequisites"></a>Cerințe preliminare

- Profiluri unificate ale clienților.
- Cea mai recentă versiune de [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) este instalată pe computer. [Aflați mai multe despre Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Configurați conectorul pentru Power BI

1. În Power BI Desktop, selectați **Fișier** > **Preluare date**.

1. Selectați **Vedeți mai multe** și căutați **Dynamics 365 Customer Insights**

1. Selectați **Conectare**.

1. **Conectați-vă** cu același cont organizațional pe care îl utilizați pentru Customer Insights și selectați **Conectare**.
   > [!NOTE]
   > Contul pe care îl indicați în acest pas este utilizat pentru a prelua date de la Customer Insights și nu trebuie să fie același cu cel la care sunteți conectat în Power BI. Pentru a reseta contul utilizat pentru preluarea datelor, deschideți Power BI și accesați **Fișier** > **Opțiuni** > **Setări** > **Setări sursă de date**. În lista de surse de date, selectați **Dynamics 365 Customer Insights Autentificare** și selectați **Ștergere permisiuni**.  

1. În **Navigator** caseta de dialog, vizualizați lista tuturor mediilor la care aveți acces. Extindeți un mediu și deschideți oricare dintre directoare (entități, măsuri, segmente, îmbogățiri). De exemplu, deschideți folderul **Entități**, pentru a vedea toate entitățile pe care le puteți importa.

   :::image type="content" source="media/power-bi-navigator.png" alt-text="Power BI Conector Navigator.":::

1. Selectați casetele de selectare de lângă entitățile pe care să le includeți și **Încărcare**. Puteți selecta mai multe entități din mai multe medii.

   O casetă de dialog de încărcare se afișează în timp ce entitățile dvs. sunt încărcate. După ce s-au încărcat toate entitățile selectate, utilizați capacitățile lui Power BI pentru a vizualiza datele.

## <a name="large-data-sets"></a>Seturi mari de date

Conectorul Customer Insights pentru Power BI este proiectat pentru a funcționa pentru seturi de date care conțin până la 1 milion de profiluri de clienți. Importarea de seturi de date mai mari poate funcționa, dar durează mult și poate expira din cauza Power BI limitări. Pentru mai multe informații, consultați [Power BI : Recomandări pentru seturi mari de date](/power-bi/admin/service-premium-what-is#large-datasets).

### <a name="work-with-a-subset-of-data"></a>Lucrați cu un subset de date

Luați în considerare lucrul cu un subset de date. De exemplu, creați [segmente](segments.md) în loc să exportați toate înregistrările clienților în Power BI.

## <a name="troubleshooting"></a>Depanare

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Mediul Customer Insights nu apare în Power BI

Medii care au mai mult de unul [relaţie](relationships.md) definit între două entități identice în Customer Insights nu va fi disponibil în Power BI conector.

Identificați și eliminați relațiile duplicate.

1. Mergi la **Date** > **Relații** asupra mediului în care îți lipsești Power BI.
1. Identificați relațiile duplicate:
   - Verificați dacă există mai multe relații definite între aceleași două entități.
   - Verificați dacă există o relație creată între două entități care sunt ambele incluse în procesul de unificare. Există o relație implicită definită între toate entitățile incluse în procesul de unificare.
1. Eliminați orice relație duplicat identificată.

După eliminarea relațiilor duplicate, încercați să configurați conectorul Power BI din nou.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Erori la câmpurile de dată la încărcarea entităților în Power BI Desktop

Când încărcați entități care conțin câmpuri cu un format de dată, cum ar fi LL/ZZ/AAAA, este posibil să întâmpinați erori din cauza formatelor locale nepotrivite. Această nepotrivire se întâmplă atunci când dvs Power BI Desktop fișierul este setat la o altă localitate decât engleza (Statele Unite), deoarece câmpurile de dată din Customer Insights sunt salvate în format SUA.

Fișierul Power BI Desktop are o singură setare regională, care se aplică la preluarea datelor. Pentru a remedia erorile de dată, [setați localitatea fișierului .BPI](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) în engleză (Statele Unite).

[!INCLUDE [footer-include](includes/footer-banner.md)]
