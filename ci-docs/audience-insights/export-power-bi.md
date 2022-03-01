---
title: Conector Power BI
description: Aflați cum să utilizați conectorul Dynamics 365 Customer Insights în Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406667"
---
# <a name="connector-for-power-bi-preview"></a>Conector pentru Power BI (previzualizare)

Creați vizualizări pentru datele dvs. cu Power BI Desktop. Generați informații suplimentare și creați rapoarte cu datele clientului dvs. unificate.

## <a name="prerequisites"></a>Cerințe preliminare

- Aveți profiluri de clienți unificate.
- Cea mai recentă versiune de [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) este instalată pe computerul dvs. [Aflați mai multe despre Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Configurați conectorul pentru Power BI

1. În Power BI Desktop, selectați **Fișier** > **Preluare date**.

1. Selectați **Vedeți mai multe** și căutați **Dynamics 365 Customer Insights**

1. Selectați rezultatul și selectați **Conectare**.

1. **Conectați-vă** cu același cont organizațional pe care îl utilizați pentru Customer Insights și selectați **Conectare**.
   > [!NOTE]
   > Contul pe care îl indicați în acest pas este utilizat pentru a prelua date de la Customer Insights și nu trebuie să fie același cu cel la care sunteți conectat în Power BI. Pentru a reseta contul utilizat pentru preluarea datelor, deschideți Power BI și accesați **Fișier** > **Opțiuni** > **Setări** > **Setări sursă de date**. În lista de surse de date, selectați **Dynamics 365 Customer Insights Autentificare** și selectați **Ștergere permisiuni**.  

1. În caseta de dialog **Navigator**. Veți vedea lista tuturor mediilor la care aveți acces. Extindeți un mediu și deschideți oricare dintre directoare (entități, măsuri, segmente, îmbogățiri). De exemplu, deschideți folderul **Entități**, pentru a vedea toate entitățile pe care le puteți importa.

   ![Power BI Conector Navigator](media/power-bi-navigator.png "Conector Navigator Power BI")

1. Selectați casetele de selectare de lângă entitățile pe care să le includeți și **Încărcare**. Puteți selecta mai multe entități din mai multe medii.

1. Veți vedea o casetă de dialog de încărcare în timp ce sunt încărcate entitățile dvs. Odată ce toate entitățile dvs. selectate s-au încărcat, puteți utiliza capacitățile Power BI pentru a vizualiza datele.

## <a name="large-data-sets"></a>Seturi mari de date

Conectorul Customer Insights pentru Power BI este proiectat pentru a funcționa pentru seturi de date care conțin până la 1 milion de profiluri de clienți. Importul seturilor de date mai mari poate funcționa, dar durează mult. În plus, procesul ar putea rula într-un time-out din cauza limitărilor Power BI. Pentru mai multe informații, consultați [Power BI : Recomandări pentru seturi mari de date](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Lucrați cu un subset de date

Luați în considerare lucrul cu un subset de date. De exemplu, puteți crea [segmente](segments.md) în loc să exportați toate înregistrările clienților către Power BI.
