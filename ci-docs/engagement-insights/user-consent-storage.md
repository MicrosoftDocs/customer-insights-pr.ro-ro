---
title: Gestionați cookie-urile și consimțământul utilizatorului pentru a stoca datele utilizatorului
description: Înțelegeți modul în care cookie-urile și consimțământul utilizatorului sunt utilizate pentru a identifica vizitatorii site-ului web.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036753"
---
# <a name="manage-cookies-and-user-consent"></a>Gestionați cookie-urile și consimțământul utilizatorului

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Capacitatea Dynamics 365 Customer Insights Engagement Insight folosește cookie-uri și stocare locală (`localStorage`) pentru a identifica vizitatorii site-ului.

Cookie-urile sunt fișiere mici care stochează informații despre interacțiunile unui utilizator cu site-ul web. Sunt stocate în browsere web. Când utilizatorii vizitează un site web pentru care utilizatorii dvs. au stocat cookie-uri, browserul trimite aceste informații către server, care returnează informații care sunt unice pentru utilizator. Aceasta este tehnologia care permite, de exemplu, unui coș de cumpărături online să păstreze articolele selectate în el, chiar dacă un utilizator navighează departe de site.

## <a name="user-consent"></a>Consimțământul utilizatorului

Așa numitul [Regulament general privind protecția datelor (GDPR)](/dynamics365/get-started/gdpr/) este un regulament al Uniunii Europene (UE) care impune modul în care organizațiile ar trebui să gestioneze confidențialitatea și securitatea utilizatorilor lor. Cookie-urile stochează sau colectează adesea „date cu caracter personal”, cum ar fi un identificator online, care este acoperit de GDPR. Dacă firma dvs. angajează și/sau vinde către persoanele vizate din UE, GDPR vă afectează. [Aflați mai multe despre modul în care Microsoft vă poate ajuta să respectați GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Pentru a permite SDK-urilor de implicare să stocheze cookie-uri sau alte informații sensibile, trebuie să specificați dacă utilizatorii dvs. au consimțit. Acest lucru se întâmplă la inițializarea SDK-ului.

Dacă indicați că nu există consimțământul utilizatorului, SDK-ul nu va stoca date și nu va trimite evenimente care pot fi utilizate pentru a urmări comportamentul utilizatorului. Orice date stocate anterior vor fi șterse din browser.

Dacă nu este specificată nicio valoare de consimțământ a utilizatorului, SDK-ul va presupune că utilizatorul a consimțit. Aceasta înseamnă că, dacă dvs. (în calitate de client al nostru) nu specificați o valoare pentru consimțământul utilizatorului în SDK, datele vor fi colectate. Cu toate acestea, dacă specificați că valoarea pentru consimțământul utilizatorului trebuie să fie „adevărată”, datele nu vor fi colectate dacă un utilizator refuză sau nu furnizează consimțământul explicit.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Stocarea datelor vizitatorilor în funcție de capacitatea de analiză a implicării

### <a name="cookies"></a>Module cookie

- _msei
    - Stochează ID-ul utilizatorului anonim. Acest cookie este setat în domeniul clientului și expiră peste 365 de zile.

### <a name="local-storage"></a>Stocare locală

Capacitatea Detalii despre angajamente folosește și stocarea locală (`localStorage`) pentru a urmări datele nesensibile. Aceste date sunt stocate complet în browserul propriu-zis, fără trafic trimis către sau de la serverele dvs.

- *EISession.Id* 
    - Stochează informații despre sesiunea utilizatorului în curs, cum ar fi ID-ul sesiunii, când a început și când expiră.
- *EISession.Previous*
    - Stochează adresa URL a paginii vizitate anterior în sesiunea curentă.
    
Cheile din spațiul de stocare local nu expiră automat. Acestea vor fi resetate în următoarea sesiune de către SDK.

## <a name="deleting-cookies"></a>Ștergerea cookie-urilor

Clienții dvs. pot șterge manual cookie-urile și cheile de stocare locale în orice moment prin setările browserului lor.


[!INCLUDE[footer-include](../includes/footer-banner.md)]