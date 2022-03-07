---
title: Utilizați sursele de date pentru ingerarea datelor
description: Aflați cum să importați date din diverse surse.
ms.date: 12/06/2021
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
ms.openlocfilehash: e7bcf82c4fe3625ef791ec2b0a7651be0356a006
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354064"
---
# <a name="data-sources-overview"></a>Prezentare generală surse de date



Capacitatea Detalii despre audiență din Dynamics 365 Customer Insights se conectează la date dintr-un set larg de surse. Conectarea la un sursă de date este adesea denumită procesul de *ingerare de date*. După ingerarea datelor, puteți [unifica](data-unification.md) și lua măsuri în legătură cu acestea.

## <a name="add-a-data-source"></a>Adăugați o sursă de date

Consultați articolele detaliate pentru cum să adăugați un sursă de date, în funcție de opțiunea pe care o alegeți.

Puteți adăuga următoarele surse de date:

- [Prin zeci de Power Query conectori](connect-power-query.md)
- [Dintr-un folder Common Data Model](connect-common-data-model.md)
- [Din propriul Microsoft Dataverse lake](connect-dataverse-managed-lake.md)
- [De la un Azure Synapse Analytics Bază de date](connect-synapse.md)

> [!NOTE]
> Dacă utilizați versiunea de încercare, secțiunea metode de import include a **Biblioteca de date Customer Insights** opțiune. Alegeți această opțiune pentru a selecta un set de date eșantion disponibil pentru diverse industrii. Pentru mai multe informații, vezi [Dynamics 365 Customer Insights proces](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Adăugați date din sursele de date locale

Ingerarea datelor din sursele de date locale în detalii despre public este acceptată pe baza de fluxuri de date Microsoft Power Platform. Puteți activa fluxurile de date în Customer Insights prin [oferind Microsoft Dataverse URL de mediu](create-environment.md) la configurarea mediului.

Surse de date care sunt create după asocierea a Dataverse mediu cu utilizarea Customer Insights [Power Platform fluxuri de date](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) în mod implicit. Fluxurile de date acceptă conectivitate locală folosind gateway-ul de date. Puteți elimina și recrea surse de date care existau înainte de a Dataverse mediu a fost asociat [folosind local gateway-uri de date](/data-integration/gateway/service-gateway-app).

Gateway-urile de date de la un mediu existent Power BI sau Power Apps vor fi vizibile și le puteți reutiliza în Customer Insights. Pagina surselor de date afișează linkuri pentru a accesa mediul Microsoft Power Platform în care puteți vizualiza și configura gateway-urile de date local.

## <a name="review-ingested-data"></a>Examinați datele ingerate

Veți vedea numele fiecărei surse de date ingerate, starea acesteia și ultima dată când datele au fost actualizate pentru sursa respectivă. Puteți sorta lista surselor de date după fiecare coloană.

> [!div class="mx-imgBorder"]
> ![Sursă de date adăugată.](media/configure-data-datasource-added.png "Sursă de date adăugată")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Încărcarea datelor poate dura timp. După o reîmprospătare reușită, datele ingerate pot fi revizuite din pagina **Entități**. Pentru mai multe informații, consultați [Entități](entities.md).

## <a name="refresh-a-data-source"></a>Reîmprospătați o sursă de date

Sursele de date pot fi reîmprospătate într-un program automat sau reîmprospătate manual la cerere. 

Accesați **Administrator** > **Sistem** > [**Planificare**](system.md#schedule-tab) pentru a configura reîmprospătările planificate ale tuturor surselor de date ingerate.

Pentru a actualiza o sursă de date la cerere, urmați acești pași:

1. În Detalii despre audiență, accesați **Date** > **Surse de date**.

2. Selectați elipsa verticală de lângă sursă de date pe care doriți să o reîmprospătați și selectați **Reîmprospătare** din lista derulantă.

3. Sursa de date este acum declanșată pentru o reîmprospătare manuală. Reîmprospătarea unei surse de date va actualiza atât schema entității, cât și datele pentru toate entitățile specificate în sursa de date.

4. Selectați **Oprire reîmprospătare** dacă doriți să anulați o reîmprospătare existentă iar sursa de date va reveni la ultima sa stare de reîmprospătare.

## <a name="delete-a-data-source"></a>Ștergerea unei surse de date

1. În Detalii despre audiență, accesați **Date** > **Surse de date**.

2. Selectați elipsa verticală de lângă sursă de date pe care doriți să o eliminați și selectați **Ștergți** din meniul derulant.

3. Confirmați ștergerea.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
