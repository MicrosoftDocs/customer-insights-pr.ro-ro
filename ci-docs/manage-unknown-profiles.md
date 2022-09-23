---
title: Gestionați profiluri necunoscute cu Customer Insights
description: Lucrați cu profiluri de clienți necunoscute care sunt create și gestionate în Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: d7e5050ee5832df5ecf40a352f7ea8d42830fa45
ms.sourcegitcommit: f6b6a4c4ce9cf12e449488b24aab80a2cbfe0c47
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/21/2022
ms.locfileid: "9556411"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Gestionați profiluri necunoscute cu Customer Insights

Utilizatorii de internet sunt adesea neidentificați și anonimi online. Dacă nu sunt autentificați pentru că folosesc dispozitive sau canale diferite, este valabil chiar și pentru cei mai fideli clienți. Deoarece cookie-urile terță parte vor dispărea în curând, gestionarea preferințelor utilizatorilor pe baza datelor de la prima parte este crucială pentru a obține experiențe personalizate diferențiate. Pentru multe mărci, utilizatorii cunoscuți sau autentificați sunt o minoritate, în ciuda așteptărilor crescânde ale clienților cu privire la personalizare. Este minunat pentru companii să știe cine sunt clienții lor, pe baza unor date fiabile, detaliate și unificate.

Personalizarea memorabilă depinde de bogăția și caracterul complet al datelor despre clienți, iar Customer Insights vă ajută să atingeți aceste obiective. Nu trebuie să limitați sau să opriți utilizarea datelor colectate la începutul călătoria clientului. Customer Insights vă permite să vă aduceți propriile date pentru a crea un profil de client pentru utilizatori necunoscuți. Apoi puteți utiliza acel profil pentru acțiuni suplimentare, în ciuda informațiilor de contact lipsă. Importați date primare din surse precum sistemele web, mobile sau CRM în Customer Insights pentru a îmbogăți continuu profilurile clienților. Pe măsură ce unificați mai multe interacțiuni, [întoarce *necunoscut* client într-o *cunoscut* client](unknown-to-known.md).

## <a name="sample-scenario"></a>Exemplu de scenariu

Comerțul electronic este canalul cu cea mai rapidă creștere în ultimul deceniu. Să presupunem că un utilizator își folosește dispozitivul mobil pentru a vă naviga pe site-ul dvs. de comerț electronic. Site-ul web atribuie vizitatorului „mobile_guest123” ca un identificator unic și începeți să colectați activități comportamentale pe baza activității sale online. De exemplu, ce pagini au vizitat, cât timp au petrecut pe acele pagini sau pe ce linkuri au făcut clic. Nu le cunoașteți numele sau adresa de e-mail, dar aceste date pot oferi mărcilor informații semnificative despre acest utilizator specific. La rândul său, puteți pune aceste informații să funcționeze data viitoare când utilizatorul vizitează site-ul. Interogați Customer Insights pentru „mobile_guest123” pentru a prelua lista de segmente a utilizatorului, cum ar fi „organic”, „clienți cu precomandă pe mobil”, „clienți cu valoare mare” etc. sau pentru a prelua profilul pentru a crea experiențe web personalizate. De asemenea, puteți exporta datele în orice sistem de activare pentru a face același lucru.

## <a name="prerequisites"></a>Cerințe preliminare

- Ingerați date primare în Customer Insights
- Fiecare entitate are un ID unic care este setat ca cheie primară
- Fiecare entitate cu o cheie primară pentru personalizare este unificată
- Sistemul de management al conținutului site-ului dvs. este capabil să utilizeze API-uri (pentru personalizarea web bazată pe comunicarea directă cu Customer Insights)

Următorul tabel arată un exemplu simplificat cum ar putea fi capturate evenimentele web de mare valoare.

|EventID|EventTimeStamp|Numele de utilizator|Cheia principala|Numele evenimentului|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|CookieID1|Vizualizare produs|
|2|09-18-2022 10:05:00|abc123|CookieID1|Vizualizare produs|
|3|09-18-2022 10:10:00|abc123|CookieID1|Adăugați la coș|
|4|09-21-2022 09:05:00|abc123|CookieID1|Vizualizare produs|

## <a name="data-ingestion"></a>Ingestie date

Pentru mai multe informații despre opțiunile disponibile pentru asimilarea datelor, consultați [Prezentare generală a surselor de date](data-sources.md).

## <a name="data-unification"></a>Unificarea datelor

Pentru mai multe informații despre unificarea profilurilor clienților, consultați [Prezentare generală a unificării datelor](data-unification.md).

## <a name="get-insights"></a>Obțineți detalii

[Îmbogăţi](enrichment-hub.md) datele dvs., construiți [măsuri](measures.md), și creați [segmente](segments.md) pentru activare ulterioară.

De exemplu, puteți crea segmente de utilizatori necunoscuți care au răsfoit aceleași pagini de produse, dar nu au finalizat finalizarea plății.

## <a name="activation"></a>Activare

Cu datele tale din Customer Insights și știrile tale gata să te apuci de treabă, poți folosi Customer Insights pentru personalizare:

1. Folosește [API-ul OData](apis.md) pentru a prelua un membru de segment sau un profil de client Pentru mai multe exemple, consultați [Exemple de interogări OData pentru API-urile Customer Insights](odata-examples.md).

1. [Export](export-destinations.md) datele dumneavoastră către sistemele dumneavoastră de activare.

Exemplu: un utilizator necunoscut vizitează un site web de mai multe ori și vizitează pagini de produse pentru diferite modele de pantofi din piele. Cu aceste date disponibile în Customer Insights, puteți include utilizatorul necunoscut în segmentul de persoane care sunt interesate de pantofi din piele. Utilizați acest segment pentru a informa personalizarea construcției site-ului dvs. pentru vizitatorii care revin. La următoarea vizită, site-ul recunoaște utilizatorul necunoscut și i-ar putea oferi un cupon de 10% la pantofii din piele.

[!INCLUDE [footer-include](includes/footer-banner.md)]
