---
title: Prezentare generală a exporturilor (previzualizare)
description: Gestionați exporturile către partajare date.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: 44f58d694b9bd35a8d8c04d487d40743291e0566
ms.sourcegitcommit: ef3e17134d44d2731605381ea0385dbc5aef6120
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460205"
---
# <a name="exports-preview-overview"></a>Prezentare generală a exporturilor (previzualizare)

 Exporturile vă permit să partajați date specifice cu diverse aplicații. Acestea pot include profiluri de clienți, entități, scheme și detalii de mapare. Fiecare export necesită o [conexiune, configurată de un administrator, pentru a gestiona autentificarea și accesul](connections.md). Pagina **Exporturi** vă arată toate exporturile configurate.

## <a name="export-types"></a>Tipuri de export

Există două tipuri principale de exporturi:  

- **Exporturi de date** vă permit să exportați orice tip de entitate disponibil în Customer Insights. Entitățile pe care le selectați pentru export sunt exportate cu toate câmpurile de date, metadate, scheme și detalii de mapare.
- **Segmentează exporturile** vă permit să exportați entități segmentate din Customer Insights. Pentru consumatorii individuali (B-to-C), segmentele reprezintă o listă de profiluri de clienți. Pentru companii (B-to-B), [segmentele pot reprezenta o listă de conturi sau persoane de contact](segment-builder.md#create-a-new-segment-with-segment-builder). Când configurați exportul, selectați câmpurile de date incluse, în funcție de sistemul țintă către care exportați datele.

### <a name="export-segments"></a>Export segmente

**Exportul segmentelor în medii pentru conturi de business (B la B) sau consumatori individuali (B la C)**  
Majoritatea opțiunilor de export acceptă ambele tipuri de medii. Exportarea segmentelor către diferite sisteme țintă are cerințe specifice. 

**Exporturile de segmente în medii pentru consumatori individuali (B la C)**  
- Segmentele din contextul mediilor pentru clienții individuali sunt construite pe baza entității *profil client unificat*. Fiecare segment care îndeplinește cerințele sistemelor țintă (de exemplu, o adresă de e-mail) poate fi exportat.

**Segmentați exporturile în medii pentru conturi de afaceri (B-to-B)**  
- Segmentele în contextul mediilor pentru conturile de afaceri sunt construite pe *cont* entitatea sau *a lua legatura* entitate. Pentru a exporta segmente de cont așa cum este, sistemul țintă trebuie să accepte segmente de cont pure. Acesta este cazul pentru [LinkedIn](export-linkedin-ads.md) când alegeți opțiunea **companie** la definirea exportului.
- Toate celelalte sisteme țintă necesită câmpuri de la entitatea de contact.
- Cu două tipuri de segmente (contacte și conturi), Customer Insights identifică automat ce tip de segmente sunt eligibile pentru export pe baza sistemului țintă. De exemplu, pentru un sistem țintă axat pe contacte, cum ar fi Mailchimp, Customer Insights vă permite doar să alegeți segmente de contact de exportat.

**Limite la exporturile pe segmente**  
- Sistemele țintă terțe pot limita numărul de profiluri de clienți pe care le puteți exporta. 
- Pentru clienții individuali, veți vedea numărul real de membri ai segmentului atunci când selectați un segment pentru export. Veți primi un avertisment dacă un segment este prea mare. 
- Pentru conturile de afaceri, veți vedea numărul de conturi sau persoane de contact în funcție de segment. Veți primi un avertisment dacă segmentul este prea mare. Depășirea limitelor rezultatelor sistemelor țintă va sări peste export.

## <a name="set-up-a-new-export"></a>Configurați un nou export

Pentru a configura sau edita un export, aveți nevoie de conexiunile potrivite disponibile pentru dvs. Conexiunile depind de [rolul dvs. de utilizator](permissions.md):
- **Administratorii** au acces la toate conexiunile. De asemenea, pot crea conexiuni noi atunci când configurează un export.
- **Contributorii** pot avea acces la conexiuni specifice. Acestea depind de administratori pentru a configura și partaja conexiuni. Lista exporturilor afișează contribuabili dacă pot edita sau vizualiza doar un export în coloana **Permisiuni**. Pentru mai multe informații, accesați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Vizualizatori** pot vizualiza doar exporturile existente - nu le poate crea.

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare export**.

1. În **Configurați exportul** panoul, selectați care [conexiune](connections.md) a folosi.

1. Furnizați detaliile necesare și selectați **Salvare** pentru a crea exportul. Pentru detaliile necesare, consultați documentația Customer Insights pentru exportul specific.

## <a name="manage-existing-exports"></a>Gestionați exporturile existente

Mergi la **Date** > **Exporturi** pentru a vedea exporturile, numele conexiunii, tipul conexiunii și starea acestora. Toate rolurile de utilizatori pot vizualiza exporturile configurate. Puteți sorta lista de exporturi după orice coloană sau puteți utiliza caseta de căutare pentru a găsi exportul pe care doriți să îl gestionați.

Selectați un export pentru a vedea acțiunile disponibile.

:::image type="content" source="media/exports_showmore.png" alt-text="Pagina de exporturi.":::

- **Vedere** sau **Editați | ×** exportul. Utilizatorii fără permisiuni de editare selectează **Vizualizare** în loc de **Editați** pentru a vedea detaliile exportului.
- **Alerga** exportul pentru a exporta cele mai recente date.
- **Creați duplicat** a unui export.
- **[Programa](#schedule-and-run-exports)** exportul.
- **Detașează conexiunea** pentru a elimina conexiunea pentru acest export. Detach nu elimină conexiunea, dar dezactivează exportul. The **Conexiune utilizată** coloana afișează Nicio conexiune.
- **Elimina** exportul.

## <a name="schedule-and-run-exports"></a>Planificați și rulați exporturile

Fiecare export pe care îl configurați are o planificare de reîmprospătare. În timpul unei reîmprospătări, sistemul caută date noi sau actualizate pentru a le include într-un export. În mod implicit, exporturile sunt executate ca parte a fiecărui [reîmprospătare planificată a sistemului](schedule-refresh.md). Puteți particulariza planificarea de reîmprospătare sau îl puteți dezactiva pentru a rula manual exporturile.

> [!TIP]
> Minimizați timpul de procesare al exporturilor de segmente cu următoarele bune practici:
> - Distribuiți entitățile de segment în mai multe exporturi.
> - Evitați programarea tuturor exporturilor în același timp. Lăsați 30 de minute sau o oră între ora programată pentru fiecare export.

Planificările de export depind de starea mediului dvs. Dacă există actualizări în curs pe [dependențe](system.md#refresh-processes) când ar trebui să înceapă un export planificat, sistemul va finaliza mai întâi actualizările și apoi va rula exportul. The **Odihnit** coloana arată când a fost actualizat ultima dată un export.

### <a name="schedule-exports"></a>Planificare export

Definiți programe personalizate de reîmprospătare pentru exporturi individuale sau mai multe exporturi simultan. Planificarea definită în prezent este listată în coloana listei de export **Planificare**. Permisiunea de a schimba programul este aceeași ca [editarea și definirea exporturilor](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați exportul pe care doriți să-l planificați.

1. Selectați **Planificare**.

1. În **Planificarea exportului**, setați **Planificarea executării** la **Pornit** pentru a rula automat exportul. Setați-l la **Dezactivat** pentru a-l reîmprospăta manual.

1. Pentru exporturile actualizate automat, alegeți o valoare **Recurență** și specificați detaliile pentru aceasta. Timpul definit se aplică tuturor cazurilor de recurență. Este momentul în care un export ar trebui să înceapă reîmprospătarea.

1. Selectați **Salvare**.

Când editați programul pentru mai multe exporturi, faceți o selecție sub **Păstrați sau anulați programele**:

- **Păstrați programe individuale** : Păstrați programul definit anterior pentru exporturile selectate și dezactivați sau activați-le doar.
- **Definiți o planificare nouă pentru toate exporturile selectate**: Înlocuiți planificările existente ale exporturilor selectate.

### <a name="run-exports-on-demand"></a>Executați exporturi la cerere

Pentru a exporta date fără a aștepta o reîmprospătare programată, accesați **Date** > **Exporturi**.

- Pentru a rula toate exporturile, selectați **Executare totală** în bara de comandă. Sunt executate numai exporturile care au o programare activă. Pentru a rula un export care nu este activ, executați un singur export.
- Pentru a rula un singur export, selectați-l în listă și selectați **Executare** în bara de comandă.

## <a name="troubleshooting"></a>Depanare

### <a name="segment-not-eligible-for-export"></a>Segmentul nu este eligibil pentru export

**Problemă** Într-un mediu de conturi de afaceri, exporturile dvs. eșuează cu mesajul de eroare: „Următorul segment nu este eligibil pentru această destinație de export: '{ numele segmentului} '. Alegeți numai segmente de tip ContactProfile și încercați din nou."

**Rezoluţie** Mediile Customer Insights pentru conturile de afaceri au fost actualizate pentru a suporta segmente de contact pe lângă segmentele de cont. Datorită acestei modificări, exporturile care necesită detalii de contact funcționează numai cu segmente bazate pe contacte.

1. [Creați un segment bazat pe contacte](segment-builder.md) care se potrivește cu segmentul utilizat anterior.

1. Odată ce segmentul de contact este rulat, editați exportul respectiv și selectați noul segment.

1. Selectați **Salvați** pentru a salva configurația sau **Salvați și rulați** pentru a testa acest export imediat.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
