---
title: Utilizați sursele de date pentru ingerarea datelor
description: Aflați cum să importați date din diverse surse.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887909"
---
# <a name="data-sources-overview"></a>Prezentare generală surse de date

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Capacitatea Detalii despre audiență din Dynamics 365 Customer Insights se conectează la date dintr-un set larg de surse. Conectarea la un sursă de date este adesea denumită procesul de *ingerare de date*. După ingerarea datelor, puteți [unifica](data-unification.md) și lua măsuri în legătură cu acestea.

## <a name="add-a-data-source"></a>Adăugați o sursă de date

Consultați articolele detaliate despre cum să adăugați o sursă de date, în funcție de opțiunea pe care o alegeți.

Puteți adăuga o sursă de date în trei moduri principale:

- [Prin zeci de conectori Power Query](connect-power-query.md)
- [Dintr-un folder Common Data Model](connect-common-data-model.md)
- [Din propriul Common Data Service lake](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Adăugați date din sursele de date locale

Ingerarea datelor din sursele de date locale în Detalii despre audiență este acceptată pe baza de fluxuri de date Power Platform. Fluxurile de date pot fi activate în Customer Insights prin [furnizarea adresei URL a mediului Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) la configurarea mediului.

Sursele de date care sunt create după asocierea unui mediu Dataverse cu Customer Insights vor utiliza [fluxuri de date Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) în mod implicit. Fluxurile de date acceptă conectivitate locală folosind gateway-urile de date. Eliminați și recreați sursele de date care existau înainte ca mediul Dataverse să fi fost asociat pentru a utiliza gateway-urile de date locale.

Gateway-urile de date de la un mediu existent Power BI sau Power Apps vor fi vizibile și le puteți reutiliza în Customer Insights. Pagina surselor de date afișează linkuri pentru a accesa mediul Power Platform în care puteți vizualiza și configura gateway-urile de date locale.

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Captură de ecran a paginii surselor de date care prezintă link-uri care indică spre mediul Power Platform.":::

## <a name="review-ingested-data"></a>Examinați datele ingerate

Veți vedea numele fiecărei surse de date ingerate, starea acesteia și ultima dată când datele au fost actualizate pentru sursa respectivă. Puteți sorta lista surselor de date după fiecare coloană.

> [!div class="mx-imgBorder"]
> ![Sursă de date adăugată](media/configure-data-datasource-added.png "Sursă de date adăugată")

|Stare  |Descriere  |
|---------|---------|
|Reușit   |Sursa de date a fost ingerată cu succes dacă este menționat un timp în coloana **Reîmprospătat**.
|Neînceput   |Sursa de date nu are încă date ingerate sau este încă în modul schiță.         |
|Se reîmprospătează    |Ingestia datelor este în curs. Aveți posibilitatea de a revoca această operațiune selectând **Oprire reîmprospătare** în coloana **Acțiuni**. Oprirea reîmprospătării unei surse de date o va readuce la ultima stare de reîmprospătare.       |
|Nereușite     |Ingerarea de date s-a efectuat cu erori.         |

Selectați valoarea în coloana **Stare** a oricărei sursă de date pentru a revizui mai multe detalii. În panoul **Detalii despre progres**, extindeți **Surse de date**. Selectați **Consultați detalii** pentru mai multe informații despre starea de reîmprospătare, inclusiv detalii despre erori și actualizări de proces descendent.

Încărcarea datelor ar putea lua ceva timp. După o reîmprospătare reușită, datele ingerate pot fi revizuite din pagina **Entități**. Pentru mai multe informații, consultați [Entități](entities.md).

## <a name="refresh-a-data-source"></a>Reîmprospătați o sursă de date

Sursele de date pot fi reîmprospătate într-un program automat sau reîmprospătate manual la cerere. 

Accesați **Administrator** > **Sistem** > [**Planificare**](system.md#schedule-tab) pentru a configura reîmprospătările planificate ale tuturor surselor de date ingerate.

Pentru a actualiza o sursă de date la cerere, urmați acești pași:

1. În Detalii despre audiență, accesați **Date** > **Surse de date**

2. Selectați elipsele verticale de lângă sursa de date pe care doriți să o reîmprospătați și selectați **Reîmprospătare** din lista verticală.

3. Sursa de date este acum declanșată pentru o reîmprospătare manuală. Reîmprospătarea unei surse de date va actualiza atât schema entității, cât și datele pentru toate entitățile specificate în sursa de date.

4. Selectați **Oprire reîmprospătare** dacă doriți să anulați o reîmprospătare existentă iar sursa de date va reveni la ultima sa stare de reîmprospătare.

## <a name="delete-a-data-source"></a>Ștergerea unei surse de date

1. În Detalii despre audiență, accesați **Date** > **Surse de date**.

2. Selectați elipsa verticală de lângă sursa de date pe care doriți să o eliminați și selectați **Ștergeți** din meniul cu selectare multiplă.

3. Confirmați ștergerea.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
