---
title: Prezentare generală surse de date
description: Aflați cum să importați sau să ingerați date din diverse surse.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 591353bf1ba2f9ca05ddd137e1cf29dc0b0fba97
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245664"
---
# <a name="data-sources-overview"></a>Prezentare generală surse de date

Dynamics 365 Customer Insights oferă conexiuni pentru a aduce date dintr-un set larg de surse. Conectarea la un sursă de date este adesea denumită procesul de *ingerare de date*. După ce ați ingerat datele, puteți [unifica](data-unification.md), generați perspective și activați datele pentru a construi experiențe personalizate.

## <a name="add-or-edit-data-sources"></a>Adăugați sau editați surse de date

Puteți atașa sau importa surse de date în Customer Insights. Linkurile de mai jos oferă instrucțiuni despre adăugarea și editarea surselor de date.

**Atașați un sursă de date**

Dacă aveți date pregătite într-unul dintre serviciile de date Azure ale Microsoft, Customer Insights se poate conecta cu ușurință la sursă de date fără a fi nevoie să reingere datele. Selectați una dintre următoarele opțiuni:
- [Azure Data Lake Storage(fișiere csv sau parchet într-un folder Common Data Model)](connect-common-data-model.md)
- [Azure Synapse Analytics(baze de date lacuri)](connect-synapse.md)
- [Microsoft Dataverse lacul de date](connect-dataverse-managed-lake.md)

**Importă și transformă**

Dacă utilizați surse de date locale, Microsoft sau date terță parte, importați și transformați datele folosind Power Query conectori.
- [Power Query conectori](connect-power-query.md)

## <a name="review-data-sources"></a>Examinați sursele de date

Dacă mediul dvs. a fost configurat pentru a utiliza stocarea Customer Insights și utilizați surse de date locale, utilizați Power Platform fluxuri de date. Cu Power Platform fluxuri de date, puteți vizualiza sursele de date partajate și sursele de date gestionate de alții. The **Surse de date** pagina listează sursele de date în trei secțiuni:
- **Impartit** : Surse de date care pot fi gestionate de toți administratorii Customer Insights. Power Platform fluxuri de date, propriul cont de stocare și atașarea la a Dataverse -lacul de date gestionat sunt exemple de surse de date partajate.
- **Gestionat de mine** :Power Platform fluxuri de date create și gestionate numai de dvs. Alți administratori Customer Insights pot vedea doar aceste fluxuri de date, dar nu le pot edita, reîmprospăta sau șterge.
- **Gestionat de alții** :Power Platform fluxuri de date create de alți administratori. Puteți doar să le vizualizați. Acesta listează proprietarul fluxului de date pe care să îl contactați pentru orice asistență.
> [!NOTE]
> Toate entitățile pot fi vizualizate și utilizate de alți utilizatori. În timp ce sursele de date sunt deținute de utilizatorul care le-a creat, entitățile rezultate din asimilarea datelor pot fi folosite de fiecare utilizator al Customer Insights.

Dacă mediul dumneavoastră nu utilizează Power Platform fluxurile de date, **Surse de date** pagina conține doar o listă a tuturor surselor de date. Nu se afișează secțiuni.

## <a name="manage-existing-data-sources"></a>Gestionați sursele de date existente

Mergi la **Date** > **Surse de date** pentru a vedea numele fiecărui sursă de date ingerat, starea acestuia și ultima dată când datele au fost reîmprospătate pentru acea sursă. Puteți sorta lista de surse de date după orice coloană sau puteți utiliza caseta de căutare pentru a găsi sursă de date pe care doriți să-l gestionați.

Selectați un sursă de date pentru a vedea acțiunile disponibile.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Sursă de date adăugată.":::

- [**Editați | ×**](#add-or-edit-data-sources) sursă de date pentru a-și schimba proprietățile.
- [**Reîmprospăta**](#refresh-data-sources) sursă de date pentru a include cele mai recente date.
- [**Îmbogăţi**](data-sources-enrichment.md) sursă de date înainte de unificare.
- **Șterge** sursă de date. Un sursă de date poate fi șters numai dacă datele nu sunt utilizate în nicio prelucrare, cum ar fi unificare, informații, activări sau exporturi.

## <a name="refresh-data-sources"></a>Actualizați sursele de date

Sursele de date pot fi reîmprospătate într-un program automat sau reîmprospătate manual la cerere. [Surse de date on-premise](connect-power-query.md#add-data-from-on-premises-data-sources) se reîmprospătează în propriile programări care sunt configurate în timpul ingerării datelor. Pentru sursele de date atașate, asimilarea datelor consumă cele mai recente date disponibile de la acel sursă de date.

Mergi la **Admin** > **Sistem** > [**Programa**](schedule-refresh.md) pentru a configura reîmprospătările programate de sistem ale surselor de date ingerate.

Pentru a reîmprospăta un sursă de date la cerere:

1. Accesați **Date** > **Surse de date**.

1. Selectați sursă de date pe care doriți să-l reîmprospătați și selectați **Reîmprospăta**. Sursa de date este acum declanșată pentru o reîmprospătare manuală. Reîmprospătarea unei surse de date va actualiza atât schema entității, cât și datele pentru toate entitățile specificate în sursa de date.

1. Selectați starea pentru a deschide **Detalii despre progres** panoul și vizualizați progresul. Pentru a anula lucrarea, selectați **Anulează jobul** în partea de jos a panoului.

[!INCLUDE [footer-include](includes/footer-banner.md)]
