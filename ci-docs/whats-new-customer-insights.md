---
title: Caracteristici noi și viitoare
description: Informații despre funcții noi, îmbunătățiri și remedieri de erori.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 25c6e2897d836854408871b2c74afa16ecba7435
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643726"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Ce este nou în Dynamics 365 Customer Insights

Suntem încântați să anunțăm cele mai noi actualizări! Acest articol rezumă caracteristicile de previzualizare publică, caracteristicile de previzualizare, îmbunătățirile generale de disponibilitate și actualizări ale caracteristicilor. Pentru a vedea planurile de caracteristici pe termen lung, consultați [planurile de lansare Dynamics 365 și Power Platform](/dynamics365/release-plans/).

Lansăm actualizări pentru fiecare regiune în parte. Prin urmare, anumite regiuni pot vedea caracteristici înaintea altora. Cu excepția cazului în care se specifică altfel, nu trebuie să luați nicio acțiune și vom actualiza automat aplicația fără întreruperi.

> [!TIP]
> Pentru a remite și vota pentru solicitări de caracteristici și sugestii de produs, accesați [portalul Dynamics 365 Application Ideas](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="march-2022-updates"></a>Actualizări martie 2022

Actualizările din martie 2022 includ noi funcții, îmbunătățiri de performanță și remedieri de erori.

### <a name="liveramp-abilitec-enrichment-preview"></a>Îmbogățirea LiveRamp AbiliTec (Previzualizare)

LiveRamp oferă rezoluția identității și consolidarea datelor clienților. Puteți mapa identificatorii personali din datele clienților dvs. la graficul de identitate AbiliTec și puteți primi ID-uri AbiliTec. Apoi puteți utiliza aceste ID-uri pentru o mai bună unificare a datelor clienților dvs.

Pentru mai multe informații, vezi [Îmbogățiți profilurile clienților cu date de identitate din LiveRamp (Previzualizare)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Organizați segmente și măsuri cu etichete și filtre
Dacă organizația dvs. menține o mulțime de segmente sau măsuri, găsirea celui potrivit poate fi uneori o provocare. Această nouă funcție vă permite să organizați liste folosind etichete și coloane. Vă ajută să găsiți date rapid și ușor și să personalizați vizualizările.

Pentru mai multe informații, vezi [Lucrați cu etichete și coloane](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Activați partajarea datelor cu Dataverse atunci când utilizați propriul cont de stocare

Dacă mediul dumneavoastră folosește Azure Data Lake Storage pentru a stoca date despre Customer Insights, cu care partajarea datelor Microsoft Dataverse necesită o configurație suplimentară.
Anterior, puteai activa doar partajarea datelor cu Dataverse când datele dumneavoastră au fost stocate în lacul nostru de date gestionat. 

Pentru mai multe informații, vezi [Activați partajarea datelor cu Dataverse din a ta Azure Data Lake Storage (Previzualizare)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Noi destinații de export: Iterable și Braze

Continuăm să ne extindem ecosistemul de destinații de export cu noi conexiuni. Acum puteți exporta segmente în Iterable și Braze pentru a le folosi serviciile de activare.

Pentru mai multe informații, vezi [Exportați segmente în Iterable (previzualizare)](export-iterable.md) și [Exportați segmente în Braze (previzualizare)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Îmbunătățiri ale exportului Marketo și Google Ads

Schimbarea API-urilor în serviciile conectate duce la actualizări pentru ca conectorii să ruleze în mod fiabil și fără probleme. Am lansat câteva actualizări pentru exporturile către serviciile Marketo și Google Ads:

- Google Ads: noua versiune a conectorului de export Google Ads simplifică experiența de autentificare și acum vă permite să creați automat noi segmente de public Google Ads. 
- Marketo: noua versiune a conectorului de export Marketo oferă suport pentru ID-ul Marketo, permițându-vă să evitați duplicarea datelor, să actualizați înregistrările existente și să creați noi înregistrări în Marketo. 


## <a name="february-2022-updates"></a>Actualizări februarie 2022

Actualizările din februarie 2022 includ noi funcții, îmbunătățiri de performanță și remedieri de erori.

### <a name="general-availability-for-prediction-models"></a>Disponibilitate generală pentru modelele predicție

Modele ieșite din cutie predicție, inclusiv **pierderea abonamentului**, **tranzacțional**, și **valoarea de viață a clientului (CLV)** devin disponibile în general ca parte a Customer Insights. 

Pentru mai multe informații, vezi [Prezentare generală a predicțiilor](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Nou sursă de date: Integrare cu Azure Synapse Analytics (Previzualizare)

Azure Synapse Analytics este un serviciu de analiză pentru întreprinderi care accelerează timpul de a obține informații în depozitele de date și sistemele de date mari.

Organizații care folosesc deja Azure Synapse Analytics poate ingera acele date în Customer Insights. 

Pentru mai multe informații, vezi [Conectați un Azure Synapse sursă de date (Previzualizare)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>Îmbogățirea LiveRamp (Previzualizare)

LiveRamp oferă rezoluția identității și consolidarea datelor clienților. Puteți mapa identificatorii personali din datele clienților dvs. la graficul de identitate AbiliTec și puteți primi ID-uri AbiliTec. Apoi puteți utiliza aceste ID-uri pentru o mai bună unificare a datelor clienților dvs.

Pentru mai multe informații, vezi [Îmbogățiți profilurile clienților cu date de identitate din LiveRamp (Previzualizare)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Îmbogățirea surselor de date (Previzualizare)

Utilizați date din surse precum Microsoft și alți parteneri pentru a vă îmbogăți datele clienților înainte de unificarea datelor. Îmbogățirile sursă de date ajută la obținerea unei complete și a unei calități mai mari a datelor, care pot ajuta la obținerea unor rezultate mai bune odată ce vă unificați datele.

Pentru mai multe informații, vezi [Îmbogățirea surselor de date (Previzualizare)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Schimbați proprietarul mediului

În timp ce mai mulți utilizatori pot avea permisiuni de administrator în Customer Insights, doar un utilizator este proprietarul unui mediu. O experiență îmbunătățită vă permite să schimbați proprietarii unui mediu și să revendicați dreptul de proprietate dacă un fost proprietar a părăsit organizația. 

Pentru mai multe informații, vezi [Schimbați proprietarul unui mediu](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Procesul de pregătire a datelor listează motivele corupției pentru înregistrările corupte

Pregătirea datelor arată acum motivul corupției pentru toate câmpurile cu date corupte. Informațiile sunt furnizate la nivel de înregistrare individuală pentru o identificare ușoară. 

Pentru mai multe informații, vezi [Surse de date corupte](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Sfârșitul previzualizării pentru funcțiile de raportare din capacitatea de statistici privind implicarea

The Dynamics 365 Customer Insights Previzualizarea capacității de statistici privind implicarea s-a încheiat pe 15 februarie 2022.  
Această modificare înseamnă că experiența de încercare a Customer Insights nu mai include capacitatea de a crea canale sau alte funcționalități de raportare.

Vă invităm să explorați și să evaluați multe alte caracteristici ale [Informații despre clienți](https://dynamics.microsoft.com/ai/customer-insights/), platforma Microsoft de date pentru clienți (CDP).    
 
Pentru o perioadă de tranziție, participanții existenți la previzualizare încă au acces la unele capacități și funcționalități de previzualizare:

- Obțineți codul pentru a instrumenta un site web sau o aplicație mobilă 
- Vedeți evenimentele și proprietățile evenimentului 
- Îmbunătățiți profilurile unificate cu evenimente ingerate și rafinate pentru a beneficia de întreaga valoare a datelor clienților lor
  
În perioada de tranziție, evenimentele capturate sunt încă transmise în flux către lacul de date conectat. Odată ce această funcționalitate este dezactivată, partajarea datelor se va opri și nu sunt trimise evenimente noi la stocarea conectată.
Contactați direct echipa de cont Microsoft dacă aveți întrebări despre sfârșitul previzualizării capacității. Echipa de cont vă va ține la curent cu lansările viitoare. 

## <a name="january-2022-updates"></a>Actualizări din ianuarie 2022

Actualizările din ianuarie 2022 includ noi funcții, îmbunătățiri de performanță și remedieri de erori.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Analiza sentimentelor feedback-ului clientului dvs

Customer Insights oferă o nouă funcție bazată pe inteligență artificială pentru a sintetiza sentimentul clienților și pentru a identifica aspecte specifice de afaceri ca oportunități pentru îmbunătățiri specifice. Analizând feedback-ul scris al clienților dvs., puteți obține informații precise la costuri reduse. Analiza sentimentelor alimentată de modele de procesare a limbajului natural (NLP) care generează două perspective derivate pentru fiecare ID de client. Un scor de sentiment (de la –5 la 5) și o listă a aspectelor de afaceri aplicabile. 

Pentru mai multe informații, vezi [Analizați sentimentul în feedbackul clienților (Previzualizare)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]