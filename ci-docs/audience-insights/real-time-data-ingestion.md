---
title: Ingerarea și limitările datelor în timp real
description: Informații generale despre capacitățile în timp real în detalii despre public.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3c84cfe7441eb026c1fd45eda1f72421388d01d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598584"
---
# <a name="real-time-data-ingestion-preview"></a>Ingestie date în timp real (previzualizare)

Funcționalitatea aproape în timp real vă permite să vedeți, în câteva secunde, cele mai recente interacțiuni pe care clienții dvs. le-au făcut cu produsele sau serviciile dvs.

[Reîmprospătări programate](system.md#schedule-tab) includ un număr mare de înregistrări și mai multe operațiuni complexe. În primul rând, datele sunt extrase din sursa de date. În continuare, datele sunt unificate, apoi îmbogățite cu informații suplimentare. Fiecare rulare a acestui proces poate dura de la câteva minute la câteva ore.

Funcționalitatea în timp real oferă date imediat pentru consum, până când actualizarea planificată ulterioară extrage aceste date din sursa de date.

Actualizările în timp real au un termen de expirare, după care nu mai suprascriu valoarea din sursă de date:

- Actualizările profilului vor fi păstrate timp de 4 ore
- Activitățile se vor păstra timp de 30 de zile

Aceste valori sunt parametrii de apel API pe care îi puteți modifica. Ei urmăresc să se asigure că datele dvs. sursă rămân sursa de adevăr. Dacă doriți ca actualizările în timp real să fie incluse mai mult timp, trebuie să le adăugați la o sursă de date, astfel încât să fie trase în timpul următoarei reîmprospătări programate.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Actualizarea în timp real a câmpurilor unificate de profil ale clientului

Profilurile actualizate vor fi afișate în vizualizarea cardului clientului sau în orice altă vizualizare, în câteva secunde.

Deoarece operațiunile în timp real au loc după unificarea datelor, acestea se aplică numai profilurilor de clienți unificate. În consecință, modificările profilului în timp real nu vor actualiza măsurile, apartenența la segment sau îmbogățirile.

### <a name="limitations"></a>Limitări

- Profilurile clienților pot fi actualizate, dar nu pot fi create sau șterse.
- Exportul actualizărilor în timp real către sisteme externe, de exemplu Power BI, nu este posibilă în acest moment.

## <a name="real-time-creation-of-activities"></a>Crearea în timp real a activităților

API-ul în timp real vă permite să publicați o activitate nouă din sistemul dvs. sursă (o înregistrare sursă individuală) într-un profil de client unificat. Noua activitate va fi disponibilă ca activitate unificată în cronologia profilului de client unificat în câteva secunde. Puteți vedea cronologia în vizualizarea cardului clientului sau orice altă integrare cronologică pe care ați configurat-o.

> [!NOTE]
>
> - Activitățile nu se pot muta. Nu se schimbă odată ce au fost create.
> - În prezent, segmentele și măsurile nu se vor actualiza în funcție de noua activitate.
> - Activitățile adăugate doar prin API-ul în timp real nu fac parte din exporturi și nu vor fi afișate în PowerBI.

Există două moduri de conectare la API-ul în timp real:

- [indirect ](#connect-via-the-dynamics-365-customer-insights-connector), folosind [conectorul Dynamics 365 Customer Insights](/connectors/customerinsights/)
- [direct](#connect-directly-to-the-real-time-api), cu cod

Ambele moduri au în comun următoarele condiții preliminare:

- Un mediu Customer Insights
- Profiluri de client unificate
- Activități configurate și rulate
- Permisiuni de Contribuitor sau Administrator pentru autentificarea contului

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Conectare prin intermediul conectorului Dynamics 365 Customer Insights

API-ul în timp real poate ingera date dintr-un conector dedicat Power Platform, [conectorul Dynamics 365 Customer Insights](/connectors/customerinsights/), fără a fi nevoie să scrieți și să implementați niciun cod.    
Conectorul poate efectua aceleași acțiuni în timp real ca API-ul. Aveți nevoie de o licență validă pentru conectori premium. Pentru mai multe informații, consultați [întrebările frecvente despre licențierea Power Apps și Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps și/sau Power Automate](/connectors/)
- Azure [Logic Apps](/azure/connectors/apis-list)

Pentru detalii despre crearea fluxurilor, consultați secțiunea [documentație Power Automate](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Conectare direct la API-ul în timp real

Puteți utiliza capabilitățile în timp real construindu-vă propriul canal și conectându-vă direct la API-ul în timp real.    
Puteți posta o activitate în formatul sistemului sursă sau în formatul UnifiedActivity. Obțineți formatul făcând un apel API către /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Detalii despre acest API, inclusiv parametrii și răspunsurile, pot fi găsite în secțiunea **EntityData** de pe [Referința API-urilor Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Pentru informații suplimentare, consultați [Lucrul cu API-uri Customer Insights](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Înțelegeți utilizarea dvs. în timp real cu telemetria

Obțineți o prezentare generală a volumului de solicitări către API-ul în timp real și informații despre problemele pe care le poate întâmpina sistemul. Puteți [accesa telemetria în timp real](system.md#api-usage-tab). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]