---
title: Gestionați cookie-urile și consimțământul utilizatorului pentru a stoca datele de utilizator în Dynamics 365 Customer Insights
description: Înțelegeți modul în care cookie-urile și consimțământul utilizatorului sunt utilizate pentru a identifica vizitatorii site-ului web.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c824e50b723fe7f3b421048bb6ab96b7a9efc31f
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558886"
---
# <a name="manage-cookies-and-user-consent"></a>Gestionați cookie-urile și consimțământul utilizatorului

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Capacitatea de statistici de implicare Dynamics 365 Customer Insights folosește cookie-uri și chei (`localStorage`) pentru identificarea vizitatorilor site-ului.

Cookie-urile sunt fișiere mici care stochează informații despre interacțiunile unui utilizator cu site-ul web. Sunt stocate în browsere web. Când utilizatorii vizitează un site web pentru care utilizatorii dvs. au stocat cookie-uri, browserul trimite aceste informații către server, care returnează informații care sunt unice pentru utilizator. Aceasta este tehnologia care permite, de exemplu, unui coș de cumpărături online să păstreze articolele selectate în el, chiar dacă un utilizator navighează departe de site.

## <a name="user-consent"></a>Consimțământul utilizatorului

Așa numitul [Regulament general privind protecția datelor (GDPR)](/dynamics365/get-started/gdpr/) este un regulament al Uniunii Europene (UE) care impune modul în care organizațiile ar trebui să gestioneze confidențialitatea și securitatea utilizatorilor lor. Cookie-urile stochează sau colectează adesea „date cu caracter personal”, cum ar fi un identificator online, care este acoperit de GDPR. Dacă firma dvs. angajează și/sau vinde către persoanele vizate din UE, GDPR vă afectează. [Aflați mai multe despre modul în care Microsoft vă poate ajuta să respectați GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Pentru a permite SDK-urilor de implicare să stocheze cookie-uri sau alte informații sensibile, trebuie să specificați dacă utilizatorii dvs. au consimțit. Acest lucru se întâmplă la inițializarea SDK prin setarea unui câmp `userConsent` din configurație.

Dacă indicați că nu există consimțământul utilizatorului, SDK-ul nu va stoca date și nu va trimite evenimente care pot fi utilizate pentru a urmări comportamentul utilizatorului. Orice date stocate anterior vor fi șterse din browser.

Dacă nu este specificată nicio valoare de consimțământ a utilizatorului, SDK-ul va presupune că utilizatorul a consimțit. Aceasta înseamnă că, dacă dvs. (în calitate de client al nostru) nu specificați o valoare pentru consimțământul utilizatorului în SDK, datele vor fi colectate. Cu toate acestea, dacă specificați că valoarea pentru consimțământul utilizatorului trebuie să fie „adevărată”, datele nu vor fi colectate dacă un utilizator refuză sau nu furnizează consimțământul explicit.

Mai jos este un fragment de cod pentru a inițializa SDK-ul web cu acordul utilizatorului:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Stocarea datelor vizitatorilor în funcție de capacitatea de analiză a implicării

### <a name="cookies"></a>Module cookie

- _msei
    - Stochează ID-ul utilizatorului anonim. Acest cookie este setat în domeniul clientului și expiră peste 365 de zile.

### <a name="local-storage"></a>Stocare locală

Capacitatea de informare a angajamentului folosește și chei (`localStorage`) pentru urmărirea datelor nesensibile. Aceste date sunt stocate complet în browserul propriu-zis, fără trafic trimis către sau de la serverele dvs.

- *EISession.Id*
    - Stochează informații despre sesiunea utilizatorului în curs, cum ar fi ID-ul sesiunii, când a început și când expiră.
- *EISession.Previous*
    - Stochează adresa URL a paginii vizitate anterior în sesiunea curentă.

Cheile din spațiul de stocare local nu expiră automat și vor fi resetate în următoarea sesiune SDK.

## <a name="deleting-cookies"></a>Ștergerea cookie-urilor

Clienții dvs. pot șterge manual cookie-urile și cheile de stocare locale în orice moment prin setările browserului lor.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
