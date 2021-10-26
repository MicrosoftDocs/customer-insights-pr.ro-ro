---
title: Exportați date din Customer Insights
description: Gestionați exporturile către partajare date.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 45a4c964e9810640c764357a72b9794f4fda89f4
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623148"
---
# <a name="exports-preview-overview"></a>Prezentare generală a exporturilor (previzualizare)

Pagina **Exporturi** vă arată toate exporturile configurate. Exporturile partajează date specifice cu diferite aplicații. Acestea pot include profiluri de clienți, entități, scheme și detalii de mapare. Fiecare export necesită o [conexiune, configurată de un administrator, pentru a gestiona autentificarea și accesul](connections.md).

Faceți salt la **Date** > **Exporturi** pentru a vizualiza pagina exporturilor. Toate rolurile de utilizatori pot vizualiza exporturile configurate. Utilizați câmpul de căutare din bara de comenzi pentru a găsi exporturile după numele, numele conexiunii sau tipul conexiunii.

## <a name="export-types"></a>Tipuri de export

Există două tipuri principale de exporturi:  

- **Exporturi de date** vă permit să exportați orice tip de entitate disponibilă în statistici privind publicul. Entitățile pe care le selectați pentru export sunt exportate cu toate câmpurile de date, metadate, scheme și detalii de mapare. 
- **Segmentați exporturile** vă permite să exportați entități de segment din statistici privind publicul. Segmentele reprezintă o listă a profilurilor clienților. Când configurați exportul, selectați câmpurile de date incluse, în funcție de sistemul țintă către care exportați datele. 

### <a name="export-segments"></a>Export segmente

**Exportarea segmentelor în medii pentru conturi de afaceri (B2B) sau clienți individuali (B2C)**  
Majoritatea opțiunilor de export acceptă ambele tipuri de medii. Exportul de segmente către diferite sisteme țintă are cerințe specifice. În general, un membru al segmentului, profilul clientului, conține informații de contact. Deși acest lucru este de obicei cazul segmentelor construite pe clienți individuali (B2C), nu este neapărat cazul segmentelor bazate pe conturi de afaceri (B2B). 

**Segmentați mediile de export pentru conturi de afaceri (B2B)**  
- Segmentele din contextul mediilor pentru conturile de afaceri sunt construite pe baza entității *cont*. Pentru a exporta segmente de cont așa cum este, sistemul țintă trebuie să accepte segmente de cont pure. Acesta este cazul pentru [LinkedIn](export-linkedin-ads.md) când alegeți opțiunea **companie** la definirea exportului.
- Toate celelalte sisteme țintă necesită câmpuri de la entitatea de contact. Pentru a vă asigura că segmentele de cont pot prelua date din contactele asociate, definiția segmentului dvs. trebuie să proiecteze atributele entității de contact. Aflați mai multe despre cum să [configurați segmente și atribute de proiect](segment-builder.md).

**Segmentați exporturile în medii pentru clienți individuali (B2C)**  
- Segmentele din contextul mediilor pentru clienții individuali sunt construite pe baza entității *profil client unificat*. Fiecare segment care îndeplinește cerințele sistemelor țintă (de exemplu, o adresă de e-mail) poate fi exportat.

**Limite la exporturile pe segmente**  
- Sistemele țintă terțe pot limita numărul de profiluri de clienți pe care le puteți exporta. 
- Pentru clienții individuali, veți vedea numărul real de membri ai segmentului atunci când selectați un segment pentru export. Veți primi un avertisment dacă un segment este prea mare. 
- Pentru conturile de afaceri, veți vedea numărul de conturi dintr-un segment; cu toate acestea, numărul de contacte care pot fi proiectate nu apare. În unele cazuri, acest lucru ar putea duce la segmentul exportat care conține de fapt mai multe profiluri de clienți decât acceptă sistemul țintă. Depășirea limitelor rezultatelor sistemelor țintă va sări peste export. 

## <a name="set-up-a-new-export"></a>Configurați un nou export  
Pentru a configura sau edita un export, trebuie să existe conexiuni disponibile pentru dvs. Conexiunile depind de [rolul dvs. de utilizator](permissions.md):
- **Administratorii** au acces la toate conexiunile. De asemenea, pot crea conexiuni noi atunci când configurează un export.
- **Contributorii** pot avea acces la conexiuni specifice. Acestea depind de administratori pentru a configura și partaja conexiuni. Lista exporturilor afișează contribuabili dacă pot edita sau vizualiza doar un export în coloana **Permisiuni**. Pentru mai multe informații, accesați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Vizualizatori** pot vizualiza doar exporturile existente - nu le poate crea.

### <a name="define-a-new-export"></a>Definiți un nou export

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare export**.

1. În panoul **Configurați exportul**, selectați ce conexiune să utilizați. [Conexiunile](connections.md) sunt gestionate de administratori. 

1. Furnizați detaliile necesare și selectați **Salvare** pentru a crea exportul.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Definiți un nou export pe baza unui export existent

1. Faceți salt la **Date** > **Exporturi**.

1. În lista de exporturi, selectați exportul pe care doriți să îl duplicați.

1. Selectați **Creați duplicat** în bara de comandă pentru a deschide panoul **Configurați exportul** cu detaliile exportului selectat.

1. Examinați și adaptați exportul și selectați **Salvați** pentru a crea un nou export.

### <a name="edit-an-export"></a>Editarea unui export

1. Faceți salt la **Date** > **Exporturi**.

1. În lista de exporturi, selectați exportul pe care doriți să îl editați.

1. Pe bara de comenzi, selectați **Editare**.

1. Schimbați valorile pe care doriți să le actualizați și selectați **Salvați**.

## <a name="view-exports-and-export-details"></a>Vizualizați exporturi și detalii despre export

După crearea destinațiilor de export, acestea sunt listate pe **Date** > **Exporturi**. Toți utilizatorii pot vedea ce date sunt partajate și starea cea mai recentă a acestora.

1. Faceți salt la **Date** > **Exporturi**.

1. Utilizatorii fără permisiuni de editare selectează **Vizualizare** în loc de **Editați** pentru a vedea detaliile exportului.

1. Panoul lateral arată configurația unui export. Fără permisiuni de editare, nu puteți modifica valorile. Selectați **Închidere** pentru a reveni la pagina de exporturi.

## <a name="schedule-and-run-exports"></a>Planificați și rulați exporturile

Fiecare export pe care îl configurați are o planificare de reîmprospătare. În timpul unei reîmprospătări, sistemul caută date noi sau actualizate pentru a le include într-un export. În mod implicit, exporturile sunt executate ca parte a fiecărui [reîmprospătare planificată a sistemului](system.md#schedule-tab). Puteți particulariza planificarea de reîmprospătare sau îl puteți dezactiva pentru a rula manual exporturile.

Planificările de export depind de starea mediului dvs. Dacă există actualizări în curs pe [dependențe](system.md#refresh-policies) când ar trebui să înceapă un export planificat, sistemul va finaliza mai întâi actualizările și apoi va rula exportul. Puteți vedea când a fost actualizat ultima oară exportul în coloana **Reîmprospătat**.

### <a name="schedule-exports"></a>Planificare export

Puteți defini planificări de reîmprospătare particularizate pentru exporturi individuale sau mai multe exporturi simultan. Planificarea definită în prezent este listată în coloana listei de export **Planificare**. Permisiunea de a schimba planificarea este aceeași ca și pentru [editarea și definirea exporturilor](export-destinations.md#set-up-a-new-export). 

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați exportul pe care doriți să-l planificați.

1. Pe bara de comenzi, selectați **Planificare**.

1. În **Planificarea exportului**, setați **Planificarea executării** la **Pornit** pentru a rula automat exportul. Setați-l la **Dezactivat** pentru a-l reîmprospăta manual.

1. Pentru exporturile actualizate automat, alegeți o valoare **Recurență** și specificați detaliile pentru aceasta. Timpul definit se aplică tuturor cazurilor de recurență. Este momentul în care un export ar trebui să înceapă reîmprospătarea.

1. Aplicați și activați modificările selectând **Salvați**.

Când editați planificarea pentru mai multe exporturi, trebuie să faceți o selecție în **Păstrați sau înlocuiți planificările**:
- **Păstrați planificările individuale**: Persistați planificarea definită anterior pentru exporturile selectate și dezactivați-le sau numai activați-le.
- **Definiți o planificare nouă pentru toate exporturile selectate**: Înlocuiți planificările existente ale exporturilor selectate.

### <a name="run-exports-on-demand"></a>Executați exporturi la cerere

Pentru a exporta date fără a aștepta o reîmprospătare programată, accesați **Date** > **Exporturi**.

- Pentru a rula toate exporturile, selectați **Executare totală** în bara de comandă. Această acțiune va executa numai exporturi care au o planificare activă.
- Pentru a rula un singur export, selectați-l în listă și selectați **Executare** în bara de comandă. Așa executați exporturile fără planificare activă. 

## <a name="remove-an-export"></a>Eliminați un export

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați exportul de eliminat.

1. Pe bara de comenzi, selectați **Eliminare**.

1. Confirmați eliminarea selectând **Eliminare** pe ecranul de confirmare.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
