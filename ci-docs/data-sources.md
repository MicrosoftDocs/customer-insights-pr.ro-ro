---
title: Prezentare generală surse de date
description: Aflați cum să importați sau să ingerați date din diverse surse.
ms.date: 09/29/2022
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
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610067"
---
# <a name="data-sources-overview"></a>Prezentare generală surse de date

Dynamics 365 Customer Insights oferă conexiuni pentru a aduce date dintr-un set larg de surse. Conectarea la un sursă de date este adesea denumită procesul de *ingerare de date*. După ce ați ingerat datele, puteți [unifica](data-unification.md), generați informații și activați datele pentru a construi experiențe personalizate.

## <a name="add-or-edit-data-sources"></a>Adăugați sau editați surse de date

Puteți atașa sau importa surse de date în Customer Insights. Linkurile de mai jos oferă instrucțiuni despre adăugarea și editarea surselor de date.

**Atașați un sursă de date**

Dacă aveți date pregătite într-unul dintre serviciile de date Azure de la Microsoft, Customer Insights se poate conecta cu ușurință la sursă de date fără a fi nevoie să reingere datele. Selectați una dintre următoarele opțiuni:
- [Azure Data Lake Storage(fișiere csv sau parchet într-un folder Common Data Model)](connect-common-data-model.md)
- [Azure Synapse Analytics(baze de date lacuri)](connect-synapse.md)
- [Microsoft Dataverse lacul de date](connect-dataverse-managed-lake.md)

**Importă și transformă**

Dacă utilizați surse de date locale, Microsoft sau date terță parte, importați și transformați datele folosind Power Query conectori.
- [Power Query conectori](connect-power-query.md)

## <a name="review-data-sources"></a>Examinați sursele de date

Dacă mediul dvs. a fost configurat pentru a utiliza stocarea Customer Insights și utilizați surse de date locale, utilizați Power Platform fluxuri de date. Cu Power Platform fluxuri de date, puteți vizualiza sursele de date partajate și sursele de date gestionate de alții. The **Surse de date** pagina listează sursele de date în trei secțiuni:
- **Impartit** : Surse de date care pot fi gestionate de toți administratorii Customer Insights. Power Platform fluxuri de date, propriul cont de stocare și atașarea la a Dataverse -lacul de date gestionat sunt exemple de surse de date partajate.
- **Gestionat de mine** :Power Platform fluxuri de date create și gestionate numai de dvs. Alți administratori Customer Insights pot vedea numai aceste fluxuri de date, dar nu le pot edita, reîmprospăta sau șterge.
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

Sursele de date pot fi reîmprospătate într-un program automat sau reîmprospătate manual la cerere. [Surse de date on-premise](connect-power-query.md#add-data-from-on-premises-data-sources) se reîmprospătează în propriile programări care sunt configurate în timpul ingerării datelor. Pentru sfaturi de depanare, consultați [Depanați PPDF Power Query -based sursă de date probleme de reîmprospătare](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues).

Pentru sursele de date atașate, asimilarea datelor consumă cele mai recente date disponibile de la acel sursă de date.

Mergi la **Admin** > **Sistem** > [**Programa**](schedule-refresh.md) pentru a configura reîmprospătările programate de sistem ale surselor de date ingerate.

Pentru a reîmprospăta un sursă de date la cerere:

1. Accesați **Date** > **Surse de date**.

1. Selectați sursă de date pe care doriți să îl reîmprospătați și selectați **Reîmprospăta**. Sursa de date este acum declanșată pentru o reîmprospătare manuală. Reîmprospătarea unei surse de date va actualiza atât schema entității, cât și datele pentru toate entitățile specificate în sursa de date.

1. Selectați starea pentru a deschide **Detalii despre progres** panoul și vizualizați progresul. Pentru a anula lucrarea, selectați **Anulează jobul** în partea de jos a panoului.

## <a name="corrupt-data-sources"></a>Surse de date corupte

Datele ingerate pot avea înregistrări corupte, ceea ce poate duce la finalizarea procesului de ingerare a datelor cu erori sau avertismente.

> [!NOTE]
> Dacă asimilarea datelor se finalizează cu erori, procesarea ulterioară (cum ar fi unificarea sau crearea activității) care folosește acest sursă de date va fi omisă. Dacă ingerarea este finalizată cu avertismente, procesarea ulterioară continuă, dar este posibil ca unele înregistrări să nu fie incluse.

Aceste erori pot fi văzute în detaliile sarcinii.

:::image type="content" source="media/corrupt-task-error.png" alt-text="Detaliu despre sarcină care arată o eroare de date corupte.":::

Înregistrările corupte sunt afișate în entitățile create de sistem.

### <a name="fix-corrupt-data"></a>Remediați datele corupte

1. Pentru a vedea datele corupte, accesați **Date** > **Entități** și căutați entitățile corupte din **Sistem** secțiune. Schema de denumire a entităților corupte: „DataSourceName_EntityName_corrupt”.

1. Selectați o entitate coruptă și apoi **Date** fila.

1. Identificați câmpurile corupte dintr-o înregistrare și motivul.

   :::image type="content" source="media/corruption-reason.png" alt-text="Motivul corupției." lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **Date** > **Entități** arată doar o parte din înregistrările corupte. Pentru a vizualiza toate înregistrările corupte, exportați fișierele într-un container din contul de stocare folosind [Procesul de export Customer Insights](export-destinations.md). Dacă ați folosit propriul cont de stocare, puteți consulta și folderul Customer Insights din contul de stocare.

1. Remediați datele corupte. De exemplu, pentru sursele de date Azure Data Lake, [remediați datele din Data Lake Storage sau actualizați tipurile de date din fișierul manifest/model.json](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data). Pentru Power Query surse de date, remediați datele din fișierul sursă și [corectați tipul de date pasul de transformare](connect-power-query.md#data-type-does-not-match-data) pe **Power Query - Editați interogările** pagină.

După următoarea reîmprospătare a sursă de date, înregistrările corectate sunt ingerate către Customer Insights și transmise proceselor din aval.

De exemplu, o coloană „zi de naștere” are tipul de date setat ca „dată”. Înregistrarea unui client are ziua de naștere înregistrată ca „01/01/19777”. Sistemul semnalează această înregistrare ca fiind coruptă. Schimbați ziua de naștere în sistemul sursă la „1977”. După o reîmprospătare automată a surselor de date, câmpul are acum un format valid și înregistrarea este eliminată din entitatea coruptă.

[!INCLUDE [footer-include](includes/footer-banner.md)]
