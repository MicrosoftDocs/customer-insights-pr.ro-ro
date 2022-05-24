---
title: Utilizați sursele de date pentru ingerarea datelor
description: Aflați cum să importați date din diverse surse.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 1fe8d6e8098831ecc8ff28e571340c56a654de6d
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/11/2022
ms.locfileid: "8739223"
---
# <a name="data-sources-overview"></a>Prezentare generală surse de date



Dynamics 365 Customer Insights se conectează la date dintr-un set larg de surse. Conectarea la un sursă de date este adesea denumită procesul de *ingerare de date*. După ingerarea datelor, puteți [unifica](data-unification.md) și lua măsuri în legătură cu acestea.

## <a name="add-a-data-source"></a>Adăugați o sursă de date

Consultați articolele detaliate pentru a afla cum să adăugați un sursă de date, în funcție de opțiunea pe care o alegeți.

Puteți adăuga următoarele surse de date:

- [Prin zeci de Power Query conectori](connect-power-query.md)
- [Dintr-un folder Common Data Model](connect-common-data-model.md)
- [Din propriul Microsoft Dataverse lake](connect-dataverse-managed-lake.md)
- [De la un Azure Synapse Analytics Bază de date](connect-synapse.md)

## <a name="add-data-from-on-premises-data-sources"></a>Adăugați date din sursele de date locale

Ingerarea datelor din sursele de date local este acceptată pe baza Microsoft Power Platform fluxuri de date. Puteți activa fluxurile de date în Customer Insights prin [oferind Microsoft Dataverse URL de mediu](create-environment.md) la configurarea mediului.

Surse de date care sunt create după asocierea a Dataverse mediu cu utilizarea Customer Insights [Power Platform fluxuri de date](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) în mod implicit. Fluxurile de date acceptă conectivitate locală folosind gateway-ul de date. Puteți elimina și recrea surse de date care existau înainte de a Dataverse mediu a fost asociat [folosind local gateway-uri de date](/data-integration/gateway/service-gateway-app).

Gateway-urile de date de la un mediu existent Power BI sau Power Apps vor fi vizibile și le puteți reutiliza în Customer Insights. Pagina surselor de date afișează linkuri pentru a accesa mediul Microsoft Power Platform în care puteți vizualiza și configura gateway-urile de date local.

> [!IMPORTANT]
> Asigurați-vă că gateway-urile sunt actualizate la cea mai recentă versiune. Puteți instala o actualizare și reconfigura un gateway dintr-un prompt afișat pe ecranul gateway direct sau [descărcați cea mai recentă versiune](https://powerapps.microsoft.com/downloads/). Dacă nu utilizați cea mai recentă versiune de gateway, reîmprospătarea fluxului de date eșuează cu mesaje de eroare precum **Cuvântul cheie nu este acceptat: proprietăți de configurare. Nume parametru: cuvânt cheie**.

## <a name="review-ingested-data"></a>Examinați datele ingerate
Dacă mediul dumneavoastră conține Power Platform fluxurile de date, **Surse de date** pagina conține trei secțiuni: 
- **Impartit** : Surse de date care pot fi gestionate de toți administratorii Customer Insights. Power BI fluxuri de date, propriul cont de stocare și atașarea la a Dataverse -lacul de date gestionat sunt exemple de surse de date partajate.
- **Gestionat de mine** :Power Platform fluxuri de date create și pot fi gestionate numai de dvs. Alți administratori Customer Insights pot vedea numai aceste fluxuri de date, dar nu le pot edita, reîmprospăta sau șterge.
- **Gestionat de alții** :Power Platform fluxuri de date create de alți administratori. Puteți doar să le vizualizați. Acesta listează proprietarul fluxului de date pe care să îl contactați pentru orice asistență.
> [!NOTE]
> Toate entitățile pot fi vizualizate și utilizate de alți utilizatori. Contextualitatea utilizatorului se aplică numai surselor de date și nu entităților care rezultă din aceste fluxuri de date.

Daca nu Power Platform sunt utilizate fluxuri de date, nu veți vedea niciun grup sau secțiune. The **Surse de date** pagina conține doar o listă a tuturor surselor de date.

Veți vedea numele fiecărei surse de date ingerate, starea acesteia și ultima dată când datele au fost actualizate pentru sursa respectivă. Puteți sorta lista surselor de date după fiecare coloană.

> [!div class="mx-imgBorder"]
> ![Sursă de date adăugată.](media/configure-data-datasource-added.png "Sursă de date adăugată")

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Încărcarea datelor poate dura timp. După o reîmprospătare reușită, datele ingerate pot fi revizuite din pagina **Entități**. Pentru mai multe informații, consultați [Entități](entities.md).

## <a name="refresh-a-data-source"></a>Reîmprospătați o sursă de date

Sursele de date pot fi reîmprospătate într-un program automat sau reîmprospătate manual la cerere. 

Accesați **Administrator** > **Sistem** > [**Planificare**](system.md#schedule-tab) pentru a configura reîmprospătările planificate ale tuturor surselor de date ingerate.

Pentru a actualiza o sursă de date la cerere, urmați acești pași:

1. Accesați **Date** > **Surse de date**.

2. Selectați elipsa verticală de lângă sursă de date pe care doriți să o reîmprospătați și selectați **Reîmprospătare** din lista derulantă.

3. Sursa de date este acum declanșată pentru o reîmprospătare manuală. Reîmprospătarea unei surse de date va actualiza atât schema entității, cât și datele pentru toate entitățile specificate în sursa de date.

4. Selectați **Oprire reîmprospătare** dacă doriți să anulați o reîmprospătare existentă iar sursa de date va reveni la ultima sa stare de reîmprospătare.

## <a name="delete-a-data-source"></a>Ștergerea unei surse de date

1. Accesați **Date** > **Surse de date**.

2. Selectați elipsa verticală de lângă sursă de date pe care doriți să o eliminați și selectați **Ștergți** din meniul derulant.

3. Confirmați ștergerea.


[!INCLUDE [footer-include](includes/footer-banner.md)]
