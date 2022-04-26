---
title: Conector Power BI
description: Aflați cum să utilizați conectorul Dynamics 365 Customer Insights în Power BI.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 06c5bed74b82f9ae2a764a2eb363348e0edab531
ms.sourcegitcommit: 4b2ad63aa7a4d4f31b573870bccbc40befe5f8fd
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/07/2022
ms.locfileid: "8552071"
---
# <a name="connector-for-power-bi-preview"></a>Conector pentru Power BI (previzualizare)

Creați vizualizări pentru datele dvs. cu Power BI Desktop. Generați informații suplimentare și creați rapoarte cu datele clientului dvs. unificate.

## <a name="prerequisites"></a>Cerințe preliminare

- Aveți profiluri de clienți unificate.
- Cea mai recentă versiune de [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) este instalată pe computer. [Aflați mai multe despre Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Configurați conectorul pentru Power BI

1. În Power BI Desktop, selectați **Fișier** > **Preluare date**.

1. Selectați **Vedeți mai multe** și căutați **Dynamics 365 Customer Insights**

1. Selectați **Conectare**.

1. **Conectați-vă** cu același cont organizațional pe care îl utilizați pentru Customer Insights și selectați **Conectare**.
   > [!NOTE]
   > Contul pe care îl indicați în acest pas este utilizat pentru a prelua date de la Customer Insights și nu trebuie să fie același cu cel la care sunteți conectat în Power BI. Pentru a reseta contul utilizat pentru preluarea datelor, deschideți Power BI și accesați **Fișier** > **Opțiuni** > **Setări** > **Setări sursă de date**. În lista de surse de date, selectați **Dynamics 365 Customer Insights Autentificare** și selectați **Ștergere permisiuni**.  

1. În caseta de dialog **Navigator**. Veți vedea lista tuturor mediilor la care aveți acces. Extindeți un mediu și deschideți oricare dintre directoare (entități, măsuri, segmente, îmbogățiri). De exemplu, deschideți folderul **Entități**, pentru a vedea toate entitățile pe care le puteți importa.

   ![Power BI Conector Navigator.](media/power-bi-navigator.png "Conector Navigator Power BI")

1. Selectați casetele de selectare de lângă entitățile pe care să le includeți și **Încărcare**. Puteți selecta mai multe entități din mai multe medii.

1. Veți vedea o casetă de dialog de încărcare în timp ce sunt încărcate entitățile dvs. Odată ce toate entitățile dvs. selectate s-au încărcat, puteți utiliza capacitățile Power BI pentru a vizualiza datele.

## <a name="large-data-sets"></a>Seturi mari de date

Conectorul Customer Insights pentru Power BI este proiectat pentru a funcționa pentru seturi de date care conțin până la 1 milion de profiluri de clienți. Importul seturilor de date mai mari poate funcționa, dar durează mult. În plus, procesul ar putea rula într-un time-out din cauza limitărilor Power BI. Pentru mai multe informații, consultați [Power BI : Recomandări pentru seturi mari de date](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Lucrați cu un subset de date

Luați în considerare lucrul cu un subset de date. De exemplu, puteți crea [segmente](segments.md) în loc să exportați toate înregistrările clienților către Power BI.

## <a name="troubleshooting"></a>Depanare

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Mediul Customer Insights nu apare în Power BI

Medii care au mai mult de o [relaţie](relationships.md) definită între două entități identice în statistici privind publicul nu vor fi disponibile în conectorul Power BI.

Puteți identifica și elimina relațiile duplicate.

1. În statisticile publicului, accesați **Date** > **Relații** asupra mediului care vă lipsește în Power BI.
2. Identificați relațiile duplicate:
   - Verificați dacă există mai multe relații definite între aceleași două entități.
   - Verificați dacă există o relație creată între două entități care sunt ambele incluse în procesul de unificare. Există o relație implicită definită între toate entitățile incluse în procesul de unificare.
3. Eliminați orice relație duplicat identificată.

După eliminarea relațiilor duplicate, încercați să configurați conectorul Power BI din nou. Mediul ar trebui să fie disponibil acum.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Erori la câmpurile de dată la încărcarea entităților în Power BI Desktop

Când încărcați entități care conțin câmpuri cu un format de dată, cum ar fi LL/ZZ/AAAA, puteți întâlni erori din cauza formatelor locale nepotrivite. Această nepotrivire se întâmplă atunci când fișierul Power BI Desktop este setat în alte setări regionale decât engleza (Statele Unite), deoarece câmpurile de date din statisticile publicului sunt salvate în format SUA.

Fișierul Power BI Desktop are o singură setare regională, care se aplică la preluarea datelor. Obțineți aceste câmpuri de dată interpretate corect, setați localizarea fișierului .BPI la engleză (Statele Unite). [Aflați cum să schimbați setările locale ale unui fișier Power BI desktop](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
