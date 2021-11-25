---
title: Utilizați sursele de date pentru ingerarea datelor
description: Aflați cum să importați date din diverse surse.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 27cbd0346b1219c7812f4b90327dd27b645c2b8e
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732170"
---
# <a name="data-sources-overview"></a>Prezentare generală surse de date

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Capacitatea de informații despre public din Dynamics 365 Customer Insights se conectează la date dintr-un set larg de surse. Conectarea la un sursă de date este adesea denumită procesul de *ingerare de date*. După ingerarea datelor, puteți [unifica](data-unification.md) și lua măsuri în legătură cu acestea.

## <a name="add-a-data-source"></a>Adăugați o sursă de date

Consultați articolele detaliate despre cum să adăugați o sursă de date, în funcție de opțiunea pe care o alegeți.

Puteți adăuga o sursă de date în trei moduri principale:

- [Prin zeci de conectori Power Query](connect-power-query.md)
- [Dintr-un folder Common Data Model](connect-common-data-model.md)
- [Din propriul tău lac Microsoft Dataverse](connect-dataverse-managed-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Adăugați date din sursele de date locale

Ingerarea datelor din sursele de date local în statisticile privind publicul este acceptată pe baza fluxurilor de date Microsoft Power Platform. Fluxurile de date pot fi activate în Customer Insights de [furnizând adresa URL a mediului Microsoft Dataverse](create-environment.md) la configurarea mediului.

Sursele de date care sunt create după asocierea unui mediu Dataverse cu Customer Insights vor folosi [Power Platform fluxuri de date](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) în mod implicit. Fluxurile de date acceptă conectivitate locală folosind gateway-ul de date. Eliminați și recreați sursele de date care existau înainte ca un mediu Dataverse să fie asociat [utilizați gateway-urile de date local](/data-integration/gateway/service-gateway-app).

Gateway-urile de date dintr-un mediu existent Power BI sau Power Apps vor fi vizibile și le puteți reutiliza în Customer Insights. Pagina surselor de date arată link-uri pentru a accesa mediul Microsoft Power Platform unde puteți vizualiza și configura gateway-uri de date local.

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
