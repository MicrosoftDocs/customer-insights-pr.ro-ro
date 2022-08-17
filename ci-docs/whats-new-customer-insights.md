---
title: Ce este nou în Dynamics 365 Customer Insights
description: Informații despre funcții noi, îmbunătățiri și remedieri de erori.
ms.date: 08/03/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: a9bb254736ae70589afb267bf0a60206a18a3385
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246026"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Ce este nou în Dynamics 365 Customer Insights

Suntem încântați să anunțăm cele mai noi actualizări! Acest articol rezumă caracteristicile de previzualizare publică, caracteristicile de previzualizare, îmbunătățirile generale de disponibilitate și actualizări ale caracteristicilor. Pentru a vedea planurile de caracteristici pe termen lung, consultați [planurile de lansare Dynamics 365 și Power Platform](/dynamics365/release-plans/).

Lansăm actualizări pentru fiecare regiune în parte. Prin urmare, anumite regiuni pot vedea caracteristici înaintea altora. Cu excepția cazului în care se specifică altfel, nu trebuie să luați nicio măsură, vom actualiza aplicația automat, fără timp de nefuncționare.

> [!TIP]
> Pentru a remite și vota pentru solicitări de caracteristici și sugestii de produs, accesați [portalul Dynamics 365 Application Ideas](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="july-2022-updates"></a>Actualizări iulie 2022

Actualizările din iulie 2022 includ noi funcții, îmbunătățiri de performanță și remedieri de erori.

### <a name="export-to-moengage"></a>Exportați în MoEngage

Exportați segmente de profiluri de clienți unificate în MoEngage și utilizați-le pentru marketing prin e-mail în MoEngage.

Pentru mai multe informații, vezi [Exportați segmente în MoEngage](export-moengage.md).

### <a name="ssh-support-for-sftp-based-exports"></a>Suport SSH pentru exporturi bazate pe SFTP

Alegeți dacă doriți să vă autentificați prin SSH sau nume de utilizator/parolă pentru conexiunile la destinațiile de export SFTP.

Pentru mai multe informații, vezi [Exportați date pe gazde SFTP](export-sftp.md).

### <a name="personalize-experiences-with-data-about-known-and-unknown-users"></a>Personalizați experiențele cu date despre utilizatori cunoscuți și necunoscuți

Gestionarea datelor despre clienți nu este o provocare nouă, dar devine din ce în ce mai dificilă pe măsură ce utilizatorii navighează pe diferitele canale digitale oferite de mărci. Un utilizator care este cunoscut (autentificat) pe un canal devine necunoscut (neautentificat) pe altul dacă nu este autentificat. Problema este adesea că utilizatorii neautentificați (necunoscuti) nu au un ID comun. Ar putea fi folosit pentru a asocia atribute semnificative ale profilurilor și pentru a genera profiluri unificate pentru clienți. Customer Insights ajută la rezolvarea acestei probleme prin ingerarea datelor din metodele de urmărire pe sistemele dumneavoastră sursă.

Pentru mai multe informații, vezi [Personalizați-vă experiențele cu date despre utilizatori cunoscuți și necunoscuți](unknown-to-known.md).

## <a name="june-2022-updates"></a>Actualizări iunie 2022

Actualizările din iunie 2022 includ noi funcții, îmbunătățiri de performanță și remedieri de erori.

### <a name="updated-user-experience-for-data-sources-and-data-ingestion"></a>Experiență de utilizator actualizată pentru sursele de date și asimilarea datelor

Importarea datelor dintr-o gamă largă de surse de date este baza pentru consolidarea datelor clienților dvs. în Dynamics 365 Customer Insights. Am revizuit experiența utilizatorului pentru importul și conectarea surselor de date. Această actualizare are scopul de a vă facilita asimilarea datelor în Customer Insights.

Pentru mai multe informații, vezi [Prezentare generală a surselor de date](data-sources.md).

### <a name="export-to-inmobi"></a>Exportați în InMobi

InMobi ajută mărcile să înțeleagă, să identifice, să se implice și să atragă consumatori. Puteți exporta segmente și alte date în serviciul InMobi prin conturile Azure Blob Storage.

Pentru mai multe informații, vezi [Exportați în InMobi (previzualizare)](export-inmobi.md)

### <a name="lockbox-support-in-customer-insights"></a>Asistență pentru Lockbox în Customer Insights

Customer Lockbox oferă o interfață pentru a revizui și a aproba (sau respinge) solicitările de acces la date. Aceste solicitări apar atunci când accesul la date la datele clienților este necesar pentru a rezolva un caz de asistență.

Pentru mai multe informații, vezi [Accesați în siguranță datele clienților cu Customer Lockbox (Previzualizare)](security-overview.md#securely-access-customer-data-with-customer-lockbox-preview).

### <a name="connect-to-your-data-using-azure-private-link"></a>Conectați-vă la datele dvs. utilizând Azure Private Link

Azure Private Link să ne conectăm Customer Insights la dvs Azure Data Lake Storage cont printr-un punct final privat din rețeaua virtuală. Pentru datele dintr-un cont de stocare, care nu este expus la internetul public, Private Link permite conectarea la acea rețea restricționată.

Pentru mai multe informații, vezi [Utilizați linkul privat în Informații despre clienți](security-overview.md#set-up-an-azure-private-link).

## <a name="may-2022-updates"></a>Actualizări mai 2022

Actualizările din mai 2022 includ noi funcții, îmbunătățiri de performanță și remedieri de erori.

### <a name="updated-data-unification-experience"></a>Experiență actualizată de unificare a datelor

 Unificarea datelor vă permite să unificați sursele de date odată diferite într-un singur set de date principal care oferă o vizualizare unificată a datelor respective. Datele pot fi unificate pe o singură entitate sau pe mai multe entități. Tu primul [selectați entitățile și câmpurile sursă](map-entities.md),[eliminați înregistrările duplicate](remove-duplicates.md), specificați regulile pentru [condiţii de potrivire](match-entities.md) și definiți care [câmpuri de inclus în profilurile unificate ale clienților](merge-entities.md).

Pentru mai multe informații, vezi [Prezentare generală a unificării datelor](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Pagina de pornire reîmprospătată în Customer Insights

**Acasă** vă ghidează prin procesul de configurare pentru caracteristicile cheie și oferă o privire de ansamblu asupra segmentelor, măsurilor și datelor de îmbogățire. Am reîmprospătat experiența pentru a oferi informații mai relevante dintr-o privire.

Pentru mai multe informații, vezi [Explorați statisticile clienților](home.md).

### <a name="track-usage-of-a-segment"></a>Urmăriți utilizarea unui segment

Acuma poți [urmăriți utilizarea unui segment](segments.md#track-usage-of-a-segment) în aplicații, care se bazează pe Dataverse organizație care este conectată cu Customer Insights. Pentru [Segmentele Customer Insights utilizate în călătoriile clienților din Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), sistemul vă informează despre utilizarea segmentului respectiv.

### <a name="export-to-criteo"></a>Exportați în Criteo

Criteo este o platformă online care ajută utilizatorii să gestioneze publicitatea digitală. Acum puteți exporta segmente de profiluri de clienți unificate pentru a genera campanii, a oferi marketing prin e-mail și a utiliza anumite grupuri de clienți cu Criteo.

Pentru mai multe informații, vezi [Exportați segmente în Criteo (previzualizare)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Structură rafinată a documentației pentru crearea mediului

Am revizuit documentele de ajutor legate de crearea și gestionarea mediilor în Customer Insights. Articolele sunt acum grupate sub nodul Medii din cuprins. Articolele restructurate oferă mai multe îndrumări pentru diferitele modalități de a configura medii și au o structură mai clară. Dacă aveți feedback de împărtășit, anunțați-ne prin intermediul comenzilor către sfârșitul articolelor de ajutor.

Pentru mai multe informații, vezi [Cum să: creați un mediu nou](create-environment.md).

## <a name="april-2022-updates"></a>Actualizări aprilie 2022

Actualizările din aprilie 2022 includ noi funcții, îmbunătățiri de performanță și remedieri de erori.

### <a name="dun--bradstreet-enrichment-preview"></a>Îmbogățirea Dun & Bradstreet (Previzualizare)

Dun & Bradstreet oferă date comerciale, analize și perspective pentru companii. Aceasta permite clienților cu profiluri de clienți unificate pentru companii să-și îmbogățească datele. Îmbogățirile includ atribute precum numărul DUNS, dimensiunea companiei, locația, industria și multe altele.

Pentru mai multe informații, vezi [Îmbogățirea profilurilor companiei cu Dun & Bradstreet (Previzualizare)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Definiți tipul de măsură atunci când creați o măsură nouă

Acum puteți face distincția între măsurile pentru profiluri individuale și măsurile din întreaga afacere. În timp ce măsurile de afaceri apar pe pagina de pornire a Customer Insights, măsurile pentru clienți sunt expuse în vizualizările detaliate ale clienților.

Pentru mai multe informații, vezi [Utilizați generatorul de măsuri pentru a crea măsuri de la zero](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Consolidarea documentației Customer Insights

Ne-am revizuit articolele de documentație și am eliminat mențiunile despre statisticile de implicare și capabilitățile de statistici ale publicului. În continuare, ne vom referi în mod constant la numele produsului Customer Insights atunci când vom scrie despre caracteristicile de bază ale aplicației. Această modificare duce, de asemenea, la o restructurare semnificativă a cuprinsului, a structurii URL și a căilor fișierelor din depozitul de documentație de bază. Toate marcajele sau linkurile existente continuă să funcționeze și să redirecționeze către adresele URL actualizate.

Dacă doriți să ne anunțați cum percepeți acea schimbare sau observați că ceva nu funcționează conform așteptărilor, spuneți-ne prin [trimiterea de feedback pentru această pagină](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

## <a name="march-2022-updates"></a>Actualizări martie 2022

Actualizările din martie 2022 includ noi funcții, îmbunătățiri de performanță și remedieri de erori.

### <a name="liveramp-abilitec-enrichment-preview"></a>Îmbogățirea LiveRamp AbiliTec (Previzualizare)

LiveRamp oferă rezoluția identității și consolidarea datelor clienților. Puteți mapa identificatorii personali din datele clienților dvs. la graficul de identitate AbiliTec și puteți primi ID-uri AbiliTec. Puteți utiliza apoi aceste ID-uri pentru o mai bună unificare a datelor clienților dvs.

Pentru mai multe informații, vezi [Îmbogățiți profilurile clienților cu date de identitate din LiveRamp (Previzualizare)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Organizați segmente și măsuri cu etichete și filtre

Dacă organizația dvs. menține o mulțime de segmente sau măsuri, găsirea celui potrivit poate fi uneori o provocare. Această nouă funcție vă permite să organizați liste folosind etichete și coloane. Vă ajută să găsiți date rapid și ușor și să personalizați vizualizările.

Pentru mai multe informații, vezi [Lucrați cu etichete și coloane](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Activați partajarea datelor cu Dataverse atunci când utilizați propriul cont de stocare

Dacă mediul dumneavoastră folosește Azure Data Lake Storage pentru a stoca datele Customer Insights, cu care partajarea datelor Microsoft Dataverse necesită o configurație suplimentară.
Anterior, puteai activa doar partajarea datelor cu Dataverse când datele dumneavoastră au fost stocate în lacul nostru de date gestionat.

Pentru mai multe informații, vezi [Activați partajarea datelor cu Dataverse din a ta Azure Data Lake Storage (Previzualizare)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

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

Azure Synapse Analytics este un serviciu de analiză a întreprinderii care accelerează timpul de a obține informații în depozitele de date și sistemele de date mari.

Organizații care folosesc deja Azure Synapse Analytics poate ingera acele date în Customer Insights. 

Pentru mai multe informații, vezi [Conectați un Azure Synapse sursă de date (Previzualizare)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>Îmbogățirea LiveRamp (Previzualizare)

LiveRamp oferă rezoluția identității și consolidarea datelor clienților. Puteți mapa identificatorii personali din datele clienților dvs. la graficul de identitate AbiliTec și puteți primi ID-uri AbiliTec. Puteți utiliza apoi aceste ID-uri pentru o mai bună unificare a datelor clienților dvs.

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

The Dynamics 365 Customer Insights Previzualizarea capacității privind statisticile de implicare s-a încheiat pe 15 februarie 2022.  
Această modificare înseamnă că experiența de încercare a Customer Insights nu mai include capacitatea de a crea canale sau alte funcționalități de raportare.

Vă invităm să explorați și să evaluați multe alte caracteristici ale [Informații despre clienți](https://dynamics.microsoft.com/ai/customer-insights/), platforma Microsoft de date pentru clienți (CDP).    
 
Pentru o perioadă de tranziție, participanții existenți de previzualizare au în continuare acces la unele capacități și funcționalități de previzualizare:

- Obțineți codul pentru a instrumenta un site web sau o aplicație mobilă 
- Vedeți evenimentele și proprietățile evenimentului 
- Îmbunătățiți profilurile unificate cu evenimente ingerate și rafinate pentru a beneficia de întreaga valoare a datelor clienților lor
  
În perioada de tranziție, evenimentele capturate sunt încă transmise în flux către lacul de date conectat. Odată ce această funcționalitate este dezactivată, partajarea datelor se va opri și nu sunt trimise evenimente noi la stocarea conectată.
Contactați direct echipa de cont Microsoft dacă aveți întrebări despre sfârșitul previzualizării capacității. Echipa de cont vă va ține la curent cu lansările viitoare. 

## <a name="january-2022-updates"></a>Actualizări din ianuarie 2022

Actualizările din ianuarie 2022 includ noi funcții, îmbunătățiri de performanță și remedieri de erori.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Analiza sentimentelor feedback-ului clientului dvs

Customer Insights oferă o nouă funcție bazată pe inteligență artificială pentru a sintetiza sentimentul clienților și pentru a identifica aspecte specifice de afaceri ca oportunități pentru îmbunătățiri specifice. Analizând feedback-ul scris al clienților dvs., puteți obține informații precise la costuri reduse. Analiza sentimentelor alimentată de modele de procesare a limbajului natural (NLP) care generează două perspective derivate pentru fiecare ID de client. Un scor de sentiment (de la –5 la 5) și o listă a aspectelor de afaceri aplicabile. 

Pentru mai multe informații, consultați [Analizați sentimentul în feedbackul clienților (Previzualizare)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]