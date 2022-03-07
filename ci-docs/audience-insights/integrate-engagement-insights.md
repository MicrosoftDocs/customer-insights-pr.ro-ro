---
title: Integrați date web din statistici despre implicare cu statistici despre public
description: Aduceți informații web despre clienți, de la statistici despre implicare la informații despre public.
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 76a53a897e90152707a7c1255ed5ed93a5f3b5a0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305033"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Integrați date web din statistici despre implicare cu statistici despre public

Clienții își fac adesea tranzacțiile zilnice online folosind site-uri web. Capacitatea de prezentare a implicării (previzualizare) în Dynamics 365 Customer Insights este o soluție la îndemână pentru a integra datele web ca sursă. Pe lângă datele tranzacționale, demografice sau comportamentale, putem vedea activități pe web în profiluri unificate ale clienților. Putem folosi aceste profiluri pentru a obține informații suplimentare, cum ar fi segmente, măsuri sau predicții pentru activarea publicului.

Acest articol descrie pașii pentru a aduce datele despre activitatea web a clienților dvs. din statistici de implicare în mediul dvs. de informații despre publicul existent.

În acest exemplu, presupunem un mediu care conține profiluri unificate ale clienților. Profilurile au fost unificate cu surse din sondaje, vânzări cu amănuntul și un sistem de ticketing. De asemenea, arată activitățile conexe ale clienților. 

Acum vrem să știm dacă un client ne vizitează proprietățile web și îi înțelegem activitățile. Activitățile includ, de exemplu, site-uri web vizitate sau pagini de produse vizualizate dintr-un link primit într-un e-mail.

## <a name="prerequisites"></a>Cerințe preliminare

Pentru a integra datele din statistici despre implicare, trebuie îndeplinite câteva cerințe preliminare: 

- Integrați SDK-urile de implicare cu site-ul dvs. web. Pentru mai multe informații, consultați [Prezentare generală resurse pentru dezvoltator](../engagement-insights/developer-resources.md).
- Exportul de evenimente web din statistici despre implicare necesită acces la un cont Azure Data Lake Storage care va fi folosit pentru a ingera datele despre evenimentele web în perspectivele publicului. Pentru informații suplimentare, consultaț [Exportați evenimente](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Configurați evenimente rafinate în statistici despre implicare

După ce un administrator a instrumentat un site web cu SDK-ul Insights Insights, *evenimente de bază* sunt adunate atunci când un utilizator vizualizează o pagină web sau face clic undeva. Evenimentele de bază tind să conțină numeroase detalii. În funcție de cazul dvs. de utilizare, aveți nevoie doar de un subset de date într-un eveniment de bază. Statisticile despre implicare vă permit să creați *evenimente rafinate* care conțin doar proprietățile unui eveniment de bază pe care îl selectați.     

Pentru mai multe informații, consultați [Creați și modificați evenimente rafinate](../engagement-insights/refined-events.md).

Considerații la crearea evenimentelor rafinate: 

- Oferiți un nume semnificativ pentru evenimentul rafinat. Acesta va fi folosit ca nume de activitate în statisticile publicului.
- Selectați cel puțin următoarele proprietăți pentru a crea o activitate în statistici privind publicul: 
    - Signal.Action.Name - indică detaliile activității.
    - Signal.User.Id - folosit pentru cartografierea cu ID-ul clientului.
    - Signal.View.Uri - utilizat ca adresă web ca bază pentru segmente sau măsuri.
    - Signal.Export.Id - folosit ca cheie principală pentru evenimente.
    - Signal.Timestamp – determină data și ora pentru activitate.

Selectați filtrele pentru a vă concentra pe evenimentele și paginile care contează pentru cazul dvs. de utilizare. În acest exemplu, vom folosi numele acțiunii „Promovare prin e-mail”.

## <a name="export-the-refined-web-events"></a>Exportați evenimentele web rafinate 

După definirea evenimentului rafinat, trebuie să configurați exportul datelor evenimentului către Azure Data Lake Storage, care poate fi setat ca un sursă de date pentru ingestie în statisticile publicului. Exporturile au loc în mod constant pe măsură ce evenimentele curg din proprietatea web.

Pentru informații suplimentare, consultaț [Exportați evenimente](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Ingerează date despre evenimente în statisticile publicului

Acum, după ce ați definit evenimentul rafinat și ați configurat exportul, trecem la ingerarea datelor în perspectivele publicului. Trebuie să creați o nouă sursă de date bazată pe un folder Common Data Model. Introduceți detaliile pentru contul de stocare în care exportați evenimentele. În fișierul *default.cdm.json*, selectați evenimentul rafinat pentru a ingera și a crea entitatea în statistici despre public.

Pentru mai multe informații, consultați [Conectați-vă la un folder Common Data Model utilizând un cont Azure Data Lake](connect-common-data-model.md).


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Relaționați datele de eveniment rafinate ca activitate a profilului unui client

După finalizarea ingestiei entității, puteți configura activitatea pentru profilul clientului.

Pentru mai multe informații, consultați [Activități Client](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Pagina cu activități cu panoul de activități Editare extins și câmpuri completate.":::

Configurați noua activitate cu următoarea mapare: 

- **Cheia principală**: Signal.Export.Id, un ID unic care este disponibil pentru fiecare înregistrare a evenimentelor în detaliile de implicare. Această proprietate este generată automat.

- **Marcaj temporal** Signal.Timestamp în proprietatea evenimentului.

- **Eveniment**: Signal.Name, numele evenimentului pe care doriți să îl urmăriți.

- **Adresa web**: Signal.View.Uri referindu-se la URI-ul paginii care a creat evenimentul.

- **Detalii**: Signal.Action.Name pentru a reprezenta informațiile de asociat evenimentului. Proprietatea selectată în acest caz indică faptul că evenimentul este destinat promovării prin e-mail.

- **Tipul activității**: În acest exemplu, alegem tipul de activitate existent WebLog. Această selecție este o opțiune de filtrare utilă pentru a rula modele predicție sau pentru a crea segmente pe baza acestui tip de activitate.

- **Configurați relația**: Această setare importantă leagă activitatea de profilurile de clienți existente. **Signal.User.Id** este identificatorul configurat în SDK pentru a fi colectat și care se referă la ID-ul utilizatorului în alte surse de date care sunt configurate în statistici privind publicul. În acest exemplu, configurăm relația dintre Signal.User.Id și RetailCustomers: CustomerRetailId, care este cheia principală care a fost identificată în etapa de hartă a procesului de unificare a datelor.

După procesarea activităților, puteți examina înregistrările clienților și puteți deschide un card de client pentru a vedea activitățile din perspectivele implicării în cronologie. 

> [!TIP]
> Pentru a găsi un ID de client care are o activitate de detalii de implicare, accesați **Entități** și previzualizați datele pentru entitatea UnifiedActivity. ActivityTypeDisplay = WebLog conține activitatea de detalii despre implicare configurată în exemplul de mai sus. Copiați ID-ul clientului pentru una dintre aceste înregistrări și pentru ID-ul respectiv pe pagina **Clienți**.

## <a name="next-steps"></a>Pașii următori

Acum puteți crea [segmente](segments.md), [măsuri](measures.md) și [predicții](predictions.md) pentru a stabili o conexiune semnificativă cu clienții dvs.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
