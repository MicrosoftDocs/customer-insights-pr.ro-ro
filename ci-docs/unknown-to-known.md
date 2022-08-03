---
title: Personalizați-vă experiențele cu date despre utilizatori cunoscuți și necunoscuți
description: Încorporați informațiile despre utilizatorii anterior necunoscuți atunci când le cunoașteți identitatea.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: ff99721bef0004bc8cae1ec14ff9df16cbb0682e
ms.sourcegitcommit: ece8ff732490ecd3b3421ab273f331e6fd46a7f7
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/19/2022
ms.locfileid: "9173823"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Personalizați-vă experiențele cu date despre utilizatori cunoscuți și necunoscuți

Gestionarea datelor despre clienți nu este o provocare nouă, dar devine din ce în ce mai dificilă pe măsură ce utilizatorii navighează pe diferitele canale digitale oferite de mărci. Un utilizator care este cunoscut (autentificat) pe un canal devine necunoscut (neautentificat) pe altul dacă nu este autentificat. Problema este adesea că utilizatorii neautentificați (necunoscuti) nu au un ID comun. Ar putea fi folosit pentru a asocia atribute semnificative ale profilurilor și pentru a genera profiluri unificate pentru clienți. Customer Insights ajută la rezolvarea acestei probleme prin ingerarea datelor din metodele de urmărire pe sistemele dumneavoastră sursă. Profilurile necunoscute și cunoscute consolidate oferă organizațiilor o vizualizare completă a profilurilor actualizate și a tranzacțiilor, comportamentelor și datelor demografice ale acestora. Chiar și un pas mai departe, oferind o rezoluție a identității care vă permite să unificați activitatea clienților pe mai multe canale, inclusiv site-ul dvs. web, achiziția în magazin, programele de loialitate și așa mai departe.

## <a name="sample-scenario"></a>Eșantion de scenariu

Să ne gândim la un lanț de cafea, care are o bază largă de clienți care cumpără cafea și alimente din magazine și comandă produse online. Adesea, vizitatorii online nu sunt autentificați atunci când navighează pe produse, ceea ce îi face „utilizatori necunoscuți”. Este dificil pentru lanțul de cafea să livreze oferte și experiențe personalizate dacă utilizatorii sunt necunoscuți. Pe de altă parte, clienții se pot conecta în contul lor și pot deveni „utilizatori cunoscuți” ai companiei prin aderarea la un sistem de loialitate, care la rândul său permite experiențe mai personalizate. Customer Insights poate ajuta lanțul de cafea să obțină informații despre utilizatori cunoscuți și necunoscuți anterior.

Cu Customer Insights, compania poate combina profilurile clienților cu datele de activitate din sesiuni neautentificate (necunoscute) după ce un utilizator se conectează și devine cunoscut. Lanțul de cafea poate aduce date din alte surse de date folosind conectori încorporați în Customer Insights pentru a fuziona identitățile clienților de pe diverse canale.

## <a name="prerequisites"></a>Cerințe preliminare

- Datele web sunt colectate și conțin „ID-uri de vizitator” pentru toți vizitatorii.
- Datele web conțin „ID-uri de utilizator autentificate” pentru vizitatorii conectați. Aceste ID-uri sunt legate de sistemul de loialitate.
- Datele despre evenimente de mare valoare, cum ar fi „Vizualizare produs” și „Checkout” sunt definite și incluse în datele sursă împreună cu marcajul de timp al evenimentului și un ID de eveniment.

Următorul tabel arată un exemplu simplificat cum ar putea fi capturate evenimentele web de mare valoare.

|EventID|EventTimeStamp|Numele de utilizator|LoyaltyID|Numele evenimentului|
|--|--|--|--|--|
|1|07-23-2022 10:00:00|abc123|--|Vizualizare produs|
|2|07-23-2022 10:05:00|abc123|707|Conectare prin loialitate|
|3|07-23-2022 10:10:00|abc123|707|Finalizare achiziție|
|4|07-23-2022 10:20:00|xyz789|--|Vizualizare produs|

## <a name="data-ingestion"></a>Ingestie date

Datele despre clienți pot proveni de pe site-ul dvs. web ca date despre evenimente și pot fi stocate în propriile dvs. servicii de analiză a datelor interne sau terță parte. Datele web conțin utilizatori cunoscuți și necunoscuți dacă site-ul web are un flux de autentificare care se integrează cu un serviciu de autentificare. De exemplu, un sistem de comerț electronic care solicită utilizatorilor să furnizeze detaliile lor complete pentru a finaliza o tranzacție de cumpărare. Sau un sistem de loialitate care necesită autentificare pentru a confirma un destinatar valid al reducerilor de recompense.

Datele despre eveniment din exemplul nostru de mai sus conțin ID-urile de profil distincte ale utilizatorilor cunoscuți și necunoscuți. În evenimentele 1 și 4, utilizatorii sunt necunoscuți, în timp ce în evenimentele 2 și 3 utilizatorul cu ID abc123 se înscrie la un program de fidelitate.

:::image type="content" source="media/website-data-source.png" alt-text="Surse de date, inclusiv site-ul web Contoso.":::

Pentru mai multe informații despre opțiunile disponibile pentru asimilarea datelor, consultați [Prezentare generală a surselor de date](data-sources.md).

## <a name="data-unification"></a>Unificarea datelor

Convergerea identităților necunoscute cu identitățile cunoscute ajută la activarea personalizării pe baza comportamentelor utilizatorilor, indiferent de starea profilului acestora (cunoscută sau necunoscută). Conținutul personalizat pentru toți utilizatorii îi ajută pe clienți să ajungă rapid la cele mai relevante produse sau servicii de care sunt interesați în acel moment.

Deoarece unii dintre utilizatorii din datele noastre sunt cunoscuți, putem folosi Customer Insights pentru a combina acele date cu profilul utilizatorului. Pentru mai multe informații despre unificarea profilurilor clienților, consultați [Prezentare generală a unificării datelor](data-unification.md).

1. Selectați câmpurile sursă din entitatea de date web. Utilizați datele de profil care sunt stocate în datele dvs. web și selectați câmpurile care reprezintă ID-uri cu date demografice.

   :::image type="content" source="media/website-source-fields.png" alt-text="Câmpuri sursă pentru web sursă de date.":::

1. Adăugați reguli pentru a îmbina înregistrările duplicate. Pentru datele web, alegeți datele cele mai completate.

1. Configurați regulile și condițiile de potrivire. Datele despre evenimentele profilurilor web din acest exemplu vor fi corelate pe ID-uri cu profilurile din alte surse de date care conțin informații despre clienți. Configurați reguli de potrivire exactă pentru ID-uri ca reguli separate cu fiecare dintre celelalte entități de profil care au o cheie primară corespunzătoare sau o potrivire a ID-ului. În exemplu, datele de profil de eveniment web sunt utilizate ca ultima entitate de potrivire, astfel încât alte date de profil să fie combinate mai întâi.
   1. Nu se verifică **Includeți toate înregistrările** creează profiluri unificate pentru utilizatori cunoscuți și include ID-urile de utilizator necunoscute corespunzătoare. Este util în scenariile în care sunteți interesat să vizualizați activitățile comportamentale anterioare ale utilizatorilor cunoscuți, când aceștia erau încă necunoscuți.
   1. Control **Includeți toate înregistrările** creează înregistrări de profil separate pentru utilizatori necunoscuți. Utilizatorii necunoscuți primesc un ID unic de client. În viitor, când un profil cunoscut este asociat în datele profilului evenimentelor web, atunci călătoria utilizatorului nou cunoscut poate fi vizualizată și utilizată pentru personalizare pe baza datelor comportamentale necunoscute din trecut.

:::image type="content" source="media/website-match-rule.png" alt-text="Regula de potrivire pentru entitatea site-ului sursă de date.":::

## <a name="get-insights"></a>Obțineți detalii

Dacă sunt create profiluri de clienți pentru utilizatori necunoscuți și cunoscuți, datele despre evenimentele web de mare valoare pot fi folosite ca [Activități](activities.md). Aceste activități pot fi folosite pentru a crea mai multe informații. De exemplu, clienții care au vizitat un site web în urmă cu șase luni (când erau încă necunoscuți) sau clienții care nu au un ID de loialitate nu au finalizat nicio plată.

:::image type="content" source="media/website-known-unknown.png" alt-text="Captură de ecran a paginii client cu clienți cunoscuți și necunoscuți.":::

[Îmbogăţi](enrichment-hub.md) datele dvs., construiți [măsuri](measures.md), și creați [segmente](segments.md) pentru activare ulterioară.

De exemplu, puteți crea segmente de utilizatori cunoscuți care s-au uitat la unele produse, dar nu au finalizat finalizarea plății.

Pentru mai multe informații, vezi [Prezentare generală a segmentelor](segments.md).

## <a name="activate-insights"></a>Activați statistici

Există mai multe moduri de a vă exporta datele și de a lua măsuri pe baza informațiilor de bază.

Pentru mai multe informații, vezi [Prezentare generală a exporturilor](export-destinations.md).
