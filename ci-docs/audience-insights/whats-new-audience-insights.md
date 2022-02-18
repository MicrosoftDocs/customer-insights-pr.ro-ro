---
title: Caracteristici noi și viitoare
description: Informații despre funcții noi, îmbunătățiri și remedieri de erori.
ms.date: 03/02/2022
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 0e25ed4e4e25b130fda410d4ba1c78caded7f0f9
ms.sourcegitcommit: b7189b8621e66ee738e4164d4b3ce2af0def3f51
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/03/2022
ms.locfileid: "8088300"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Noutățile din capacitatea de detalii despre public din Dynamics 365 Customer Insights



Suntem încântați să anunțăm cele mai noi actualizări! Acest articol rezumă caracteristicile de previzualizare publică, caracteristicile de previzualizare, îmbunătățirile generale de disponibilitate și actualizări ale caracteristicilor. Pentru a vedea planurile de caracteristici pe termen lung, consultați [planurile de lansare Dynamics 365 și Power Platform](/dynamics365/release-plans/).

Lansăm actualizări pentru fiecare regiune în parte. Prin urmare, anumite regiuni pot vedea caracteristici înaintea altora. Cu excepția cazului în care se specifică altfel, nu trebuie să luați nicio acțiune și vom actualiza automat aplicația fără întreruperi.

> [!TIP]
> Pentru a remite și vota pentru solicitări de caracteristici și sugestii de produs, accesați [portalul Dynamics 365 Application Ideas](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="january-2022-updates"></a>Actualizări din ianuarie 2022

Actualizările din ianuarie 2022 includ noi funcții, îmbunătățiri de performanță și remedieri de erori.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Analiza sentimentelor feedback-ului clientului dvs

Customer Insights oferă o nouă funcție bazată pe inteligență artificială pentru a sintetiza sentimentul clienților și pentru a identifica aspecte specifice de afaceri ca oportunități pentru îmbunătățiri specifice. Analizând feedback-ul scris al clienților dvs., puteți obține informații precise la costuri reduse. Analiza sentimentelor bazată pe modele de procesare a limbajului natural (NLP) care generează două perspective derivate pentru fiecare ID de client. Un scor de sentiment (de la –5 la 5) și o listă a aspectelor de afaceri aplicabile. 

Pentru mai multe informații, vezi [Analizați sentimentul în feedbackul clienților (Previzualizare)](sentiment-analysis.md).


## <a name="december-2021-updates"></a>Actualizările din decembrie 2021

Actualizările din decembrie 2021 includ noi funcții, îmbunătățiri de performanță și remedieri de erori.

### <a name="forward-customer-insights-logs-to-azure-monitor"></a>Redirecționați jurnalele Customer Insights către Azure Monitor

Customer Insights oferă o integrare directă cu Azure Monitor. Această caracteristică include evenimente de audit și evenimente operaționale. Jurnalele de resurse Azure Monitor vă permit să monitorizați și să trimiteți jurnalele către Azure Storage, Azure Log Analytics sau să le transmiteți în flux către Azure Event Hubs.

Pentru mai multe informații, vezi [Redirecționarea conectării Dynamics 365 Customer Insights cu Azure Monitor (Previzualizare)](diagnostics.md).

### <a name="enrich-customer-profiles-with-engagement-data"></a>Îmbogățiți profilurile clienților cu date de implicare

Utilizați datele de la Microsoft Office 365 pentru a vă îmbogăți profilurile contului de client cu informații despre angajamente prin intermediul Office 365 aplicații. Datele de implicare constau în e-mail și activitate de întâlnire, care este agregată la nivel de cont. De exemplu, numărul de e-mailuri dintr-un cont de afaceri sau numărul de întâlniri cu contul. Nu sunt partajate date despre utilizatorii individuali. Această îmbogățire este disponibilă în următoarele regiuni: Regatul Unit, Europa, America de Nord.

Pentru mai multe informații, vezi [Îmbogățiți profilurile clienților cu date de implicare (Previzualizare)](enrichment-office.md).

### <a name="advanced-data-unification-features"></a>Funcții avansate de unificare a datelor

#### <a name="enable-conflict-resolution-policies-at-the-individual-attribute-level"></a>Activați politicile de soluționare a conflictelor la nivel de atribut individual

Când deduplicați înregistrările clienților dintr-o entitate, este posibil să nu doriți să alegeți o înregistrare completă ca câștigător. Acum vă permitem să îmbinați cele mai bune câmpuri din diferite înregistrări pe baza regulilor pentru fiecare atribut. De exemplu, puteți alege să păstrați cel mai recent e-mail ȘI cea mai completă adresă din diferite înregistrări. 

Acum puteți defini reguli de îmbinare separate pentru atribute individuale în timp ce deduplicați și îmbinați înregistrările într-o singură entitate. Anterior, vă permiteam să selectați o singură regulă de îmbinare (păstrarea înregistrărilor pe baza caracterului complet al datelor recente) și acea regulă a fost aplicată la nivel de înregistrare tuturor atributelor. Acest lucru nu este ideal atunci când unele dintre datele pe care doriți să le păstrați sunt găsite în înregistrarea A și alte date bune găsite în înregistrarea B.

Pentru mai multe informații, consultați [Definiți eliminarea informațiilor duplicate pentru o entitate de potrivire](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="custom-rules-for-matching"></a>Reguli personalizate pentru potrivire

Există momente când trebuie să specificați o excepție de la regulile generale pentru a NU potrivi înregistrările. Acest lucru se poate întâmpla atunci când mai multe persoane partajează suficiente informații, astfel încât sistemul să le potrivească ca un singur individ. De exemplu, gemeni cu același nume de familie, care locuiesc în același oraș și împărtășesc data nașterii.

Excepțiile asigură că unificarea incorectă a datelor poate fi abordată în regulile de unificare. Puteți adăuga mai multe excepții la o regulă.

Pentru mai multe informații, vezi [Adăugați excepții la o regulă](match-entities.md#add-exceptions-to-a-rule).

#### <a name="provide-additional-conflict-resolution-policies-and-enable-grouping-of-attributes"></a>Furnizați politici suplimentare de rezolvare a conflictelor și permiteți gruparea atributelor

Această caracteristică vă permite să tratați un grup de câmpuri ca o singură unitate. De exemplu, dacă înregistrările noastre conțin câmpurile Adresa1, Adresa2, Orașul, Statul și Zip. Probabil că nu dorim să îmbinăm Adresa2 a unei alte înregistrări, crezând că ne-ar face datele mai complete.

Acum puteți combina un grup de câmpuri înrudite și să aplicați grupului o singură politică de îmbinare. 

Pentru mai multe informații, vezi [Combinați un grup de câmpuri](merge-entities.md#combine-a-group-of-fields).


## <a name="november-2021-updates"></a>Actualizări din noiembrie 2021

Actualizările din noiembrie 2021 includ noi funcții, îmbunătățiri de performanță și remedieri de erori.

### <a name="segment-membership-now-available-in-dataverse"></a>Calitatea de membru al segmentului este acum disponibilă în Dataverse

Informațiile privind apartenența la segmente pentru profilurile clienților sunt acum disponibile în Dataverse împreună cu profilurile și perspectivele clienților. Aplicațiile de acțiune Dynamics 365 și aplicațiile bazate pe model pot utiliza aceste date pentru a căuta detaliile de apartenență la segment pentru un anumit client.

### <a name="activities-support-contact-level-details-for-business-accounts"></a>Activitățile acceptă detalii la nivel de contact pentru conturile de afaceri

Acum puteți configura, afișa și filtra activități pentru persoanele de contact din cronologia activității contului dvs. de afaceri pentru a înțelege mai bine care persoane de contact din cont au luat parte la anumite activități.

## <a name="october-2021-updates"></a>Actualizări din octombrie 2021

Actualizările din octombrie 2021 includ funcții noi, îmbunătățiri de performanță și remedieri de erori.

### <a name="b-to-b"></a>B-la-B

Începând din octombrie 2021, puteți lucra cu conturile de afaceri și persoanele de contact aferente acestora în Customer Insights. Înainte, aplicația era în mare parte adaptată consumatorilor individuali. Mai multe zone de caracteristici au fost actualizate pentru a suporta scenarii B-to-B pe lângă un nou tip de mediu. Pentru o prezentare generală a funcțiilor B-to-B acceptate, consultați [Lucrați cu conturi de afaceri în statistici privind publicul](work-with-business-accounts.md).

Următoarele secțiuni evidențiază unele dintre domeniile cheie care au fost adaptate pentru a sprijini conturile de afaceri și consumatorii individuali.

#### <a name="export-segments-based-on-business-accounts"></a>Segmente de export pe baza conturilor de afaceri

Toate exporturile de segmente în statistici privind publicul sunt disponibile în contextul conturilor de afaceri. Majoritatea exporturilor de segment necesită o configurare suplimentară și [informațiile de contact proiectate](segment-builder.md#create-a-new-segment) în segmentele de bază să fie valabile pentru conturile de afaceri. Pentru mai multe informații, vezi [Segmente de export](export-destinations.md#export-segments).

#### <a name="use-the-linkedin-ads-export-with-business-accounts"></a>Utilizați exportul LinkedIn Ads cu conturi de afaceri

Exportul LinkedIn Ads este acum disponibil pentru contact și direcționarea companiei în contextul conturilor de afaceri. Când selectați direcționarea companiei ca obiectiv principal al exportului LinkedIn, puteți exporta segmente construite pe conturi de afaceri fără a fi nevoie să proiectați informații de contact. Pentru mai multe informații, accesați documentele despre [Export de reclame LinkedIn](export-linkedin-ads.md) si diferenta dintre [direcționarea contactelor](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) și [țintirea companiei](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting). 

#### <a name="create-measures-based-on-business-accounts-and-their-hierarchy"></a>Creați măsuri bazate pe conturile de afaceri și pe ierarhia acestora

Generatorul de măsuri vă permite să creați măsuri în jurul conturilor de afaceri și, opțional, să utilizați informațiile ierarhice. Informațiile ierarhice sunt utilizate pentru a cumula un calcul de măsură într-un cont și în toate subconturile asociate acestuia. De exemplu, puteți crea măsuri precum venitul total pentru fiecare grup de conturi de afaceri identificate prin ierarhia lor. Pentru mai multe informații, consultați [Definire și gestionare măsuri](measures.md).

#### <a name="create-segments-based-on-business-accounts-and-their-hierarchy"></a>Creați segmente bazate pe conturile de afaceri și pe ierarhia acestora

Generatorul de segmente vă permite să creați segmente de conturi de afaceri care includ opțional informații de contact pentru fiecare cont dintr-un segment. Dacă ați configurat ierarhia contului, puteți utiliza informațiile despre ierarhia contului la crearea segmentului. Pentru mai multe informații, vezi [Creați un nou segment](segment-builder.md#create-a-new-segment).

#### <a name="retain-your-business-accounts-with-deep-insights-to-their-churn-tendency"></a>Păstrați-vă conturile de afaceri cu informații profunde despre tendința lor de abandon

Modelul de abandon de clienți predicție acceptă acum și conturile de afaceri. Puteți evalua riscul de pierdere nu doar pentru un cont, ci și pentru o combinație între un cont și o categorie de produse sau servicii pe care aceștia le cumpără de la dvs. Această adăugare vă ajută să înțelegeți dacă este mai probabil ca un cont să nu mai cumpere de la dvs. în general sau doar pentru o anumită categorie de bunuri sau servicii. Pentru a vă ajuta în continuare să utilizați acest model AI, acesta enumeră, de asemenea, motivele pentru care este probabil ca un cont să se retragă. Pentru mai multe informații, vezi [Schimbarea tranzacției predicție (previzualizare)](predict-transactional-churn.md).

#### <a name="see-contacts-of-a-business-account-in-customer-view"></a>Vedeți contactele unui cont de afaceri în vizualizarea Client

Dacă conturile de afaceri sunt mapate la conturi asociate, aplicația Customer Insights afișează aceste persoane de contact asociate ca parte a vizualizării detaliilor clienților. Pentru mai multe informații, vezi [Profilele clienților](customer-profiles.md).


## <a name="september-2021-updates"></a>Actualizări din septembrie 2021

Actualizările din septembrie 2021 includ noi caracteristici, actualizări de performanță și remedieri de erori.

### <a name="activities"></a>Activități

- **Îmbunătățiri ale cronologiei activității** Am extins filtrele pentru cronologia activității pe profilurile clienților. În plus, puteți utiliza noua pană de filtrare pentru a filtra după tipul de activitate și după dată. Datele pot fi filtrate în condiții diferite. Pentru mai multe informații, consultați [Vizualizați cronologiile activității în profilurile clienților](activities.md#view-activity-timelines-on-customer-profiles).

### <a name="relationships"></a>Relații

- **Suport pentru relații multi-hop** Utilizați relații multi-hop atunci când configurați activități și definiți relații între entități. Relațiile multi-hop folosesc o entitate intermediară pentru a conecta două entități. Când configurați o activitate, puteți utiliza o relație multi-hop pentru a vă conecta entitatea de activitate la o entitate intermediară și apoi la o entitate client. Puteți combina relații multi-hop cu relații cu mai multe căi. Pentru mai multe informații, consultați [Relație multi-hop](relationships.md#multi-hop-relationship).

- **Suport pentru relații cu mai multe căi** Utilizați relații multi-cale atunci când configurați activități și definiți relații între entități. Relațiile cu mai multe căi relaționează o entitate sursă cu mai multe entități. Când configurați o activitate, puteți utiliza o relație cu mai multe căi pentru a vă conecta entitatea de activitate la mai mult de o entitate client. Puteți combina relații cu mai multe căi cu relații multi-hop. Pentru mai multe informații, consultați [Relație cu mai multe căi](relationships.md#multi-path-relationship).

## <a name="august-2021-updates"></a>Actualizări august 2021

Actualizările din iulie și august 2021 includ o nouă caracteristică, upgrade-uri de performanță și remedieri de erori.

### <a name="extensibility"></a>Extensibilitate

- **Exportați segmente în Klaviyo** Am extins [destinațiile noastre de export pentru a include Klaviyo](export-klaviyo.md). Acum puteți exporta segmente pentru a crea campanii, face marketing prin e-mail și utiliza cu grupuri specifice de clienți în Klaviyo. 


## <a name="june-2021-updates"></a>Actualizări iunie 2021

Actualizările din iunie 2021 includ mai multe caracteristici, actualizări de performanță și remedieri de erori.

### <a name="data-ingestion"></a>Ingestie date

- **Actualizări îmbunătățite ale progresului unificării datelor** Acum puteți vizualiza actualizări de stare dinamică mai granulare și îmbunătățite pe pașii [procesul de unificare a datelor](data-unification.md). Această caracteristică vă permite să urmăriți progresul detaliat pentru a înțelege fluxul procesului și să luați măsuri dacă vreun pas necesită atenție.

### <a name="extensibility"></a>Extensibilitate

- **Exportați segmente și alte date în Salesforce Marketing Cloud** Am extins destinațiile noastre de export pentru a include [Salesforce Marketing Cloud](export-salesforce.md). Acum puteți exporta segmente și alte tipuri de date în Salesforce Marketing Cloud printr-un export SFTP de brand. Importul de date poate fi complet automatizat în Salesforce și utilizat pentru a crea campanii de marketing mai eficiente.  
 
- **Exportați segmente în ActiveCampaign** Am extins destinațiile noastre de export pentru a include [Campanie activă](export-active-campaign.md). Acum puteți exporta segmente pentru a genera campanii, rula marketing prin e-mail și lucra cu grupuri specifice de clienți în ActiveCampaign.
 
- **Exportați segmente în Sendinblue** Am extins destinațiile noastre de export pentru a include [Sendinblue](export-sendinblue.md). Acum puteți exporta segmente pentru a genera campanii, rula marketing prin e-mail și lucra cu grupuri specifice de clienți în Sendinblue.
 
### <a name="ux-updates"></a>Actualizări UX 

- **Pagina de clienți noi și îmbunătățite și pagina de detalii a profilului** Am reproiectat pagina Clienți și paginile de detalii ale profilului pentru o experiență îmbunătățită a utilizatorului și o performanță mai bună. Aceste modificări vă permit să vizualizați, să sortați, să căutați și să filtrați clienții. Filtrele sunt acum reprezentate în adresa URL pentru a partaja rezultatele căutării cu alți utilizatori fără probleme. Rezultatele căutării pot fi salvate și ca segment.    
  Pagina de detalii pentru profilurile clienților acum grupează date în diferite subsecțiuni, cum ar fi date demografice, ID-uri și alte atribute de profil pentru o mai bună lizibilitate. Alte secțiuni de pe pagina cu detalii despre profil sunt acum mai interactive. De exemplu, secțiunea de activități permite acum filtrarea și sortarea.


## <a name="may-2021-updates"></a>Actualizări mai 2021

Actualizările din mai 2021 includ mai multe funcții, actualizări de performanță și remedieri de erori.

### <a name="data-ingestion"></a>Ingestie date

- **Vizualizați sau modificați metadatele sau definiția entității atunci când atașați date de pe Azure Data Lake Storage** Acum puteți vizualiza și edita metadatele sau definiția entității în detaliile despre public atunci când atașați date dintr-un dosar Common Data Model în Azure Data Lake Storage. Această capacitate oferă feedback în timp real, validarea modelului și verificarea erorilor. Aceasta vă permite să editați fără probleme atât model.json cât și manifest.json.

### <a name="extensibility"></a>Extensibilitate

- **Exporturi de segmente îmbunătățite, programare personalizată și duplicare** Acuma puteți [vizualiza toate exporturile pentru un anumit segment](export-destinations.md#view-exports-and-export-details) într-o listă. Această vizualizare nouă ajută la gestionarea modului în care este utilizat un anumit segment și la adaptarea de exporturi existente sau la crearea de noi exporturi.    
  Puteți [defini programe de reîmprospătare personalizate](export-destinations.md#schedule-and-run-exports) pentru exporturi individuale sau mai multe exporturi simultan. Până în prezent, toate exporturile erau efectuate cu fiecare reîmprospătare a sistemului.    
  În loc să creați un nou export de la zero, puteți începe bazându-vă pe unul existent pentru a economisi ceva timp.

- **Exportați segmente în Microsoft Advertising** Am extins destinațiile noastre de export pentru a include Microsoft Advertising. Creați audiențe Customer Match în Microsoft Advertising cu datele de profil unificate ale clienților dvs. și să utilizați aceste audiențe pentru campanii de publicitate. Pentru mai multe informații, consultați [Exportați segmente în Microsoft Advertising](export-microsoft-advertising.md).

- **Exportați segmente în anunțuri LinkedIn** Am extins destinațiile noastre de export pentru a include anunțuri LinkedIn și pentru a vă permite să deblocați direcționarea prin contact, precum și direcționarea către companii prin LinkedIn, exportând datele unificate ale profilului dvs. de client. Pentru mai multe informații, consultați [Exportați segmente în Anunțuri LinkedIn](export-linkedin-ads.md).


- **Exportați segmente în Omnisend** Am extins destinațiile noastre de export pentru a include Omnisend. Utilizați segmentele create în detaliile despre public pentru a genera campanii, a oferi marketing prin e-mail și a utiliza anumite grupuri de clienți cu Omnisend. Pentru mai multe informații, consultați [Exportați segmente în Omnisend](export-omnisend.md)

### <a name="predictions"></a>Predicții

- **Raport de utilizare a datelor de intrare** Raportul de utilizare a datelor de intrare oferă o imagine consolidată a erorilor și avertismentelor pe care le pot genera predicțiile dvs. predefinite. De asemenea, oferă recomandări despre cum să îmbunătățim performanța modelului.    
  Raportul este disponibil după ce un model a finalizat procesul de instruire. Este creat pentru fiecare model separat, indiferent dacă s-a finalizat cu succes sau nu.
  În prezent, această caracteristică este disponibilă numai pentru modelul Transaction Churn. Pentru mai multe informații, consultați [Raport de utilizare a datelor de intrare](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Relații

- **Vizualizator de relații** Vizualizarea vizualizatorului de relații vă permite să vedeți toate relațiile existente între entități și cardinalitatea acestora. Relațiile sunt acum organizate în grupuri: creat de utilizator, sistem și relații moștenite. De asemenea, puteți exporta o vizualizare ca imagine. Pentru mai multe informații, consultați [Vizualizați relațiile](relationships.md#view-relationships). 

## <a name="april-2021-updates"></a>Actualizări aprilie 2021

Actualizările din aprilie 2021 includ mai multe funcții, actualizări de performanță și remedieri de erori.

### <a name="data-unification"></a>Unificarea datelor
 
- **Experiență îmbunătățită de îmbinare pentru unificarea datelor**    
  
   Acum avem o experiență îmbunătățită a utilizatorului în configurația de îmbinare a procesului de unificare a datelor. Modificările includ ordonarea intuitivă a câmpurilor combinate și statistici detaliate despre câmpurile combinate și singleton.

- **Reordonarea entitățlori și configurarea tuturor înregistrărilor sursă în entitatea Client**  
      
   Acum puteți reordona și elimina entități dintr-un plan de combinare existent în procesul de unificare a datelor. Oferă flexibilitate de a reordona entitățile în procesul de potrivire în funcție de nevoile afacerii. În plus, activăm includerea tuturor înregistrărilor care nu se potrivesc în entitatea finală *Client*, care le permite să își definească definiția setului de date ale profilului clientului.

### <a name="enrichments"></a>Îmbogățiri

 - **Îmbogățire nouă îmbunătățirea adreselor**    
  
   Suntem încântați să introducem o nouă îmbogățire pentru a îmbunătăți adresele în datele clienților dvs. Adresele din datele dvs. pot fi nestructurate, incomplete sau incorecte. Această caractreristică folosește modelele Microsoft pentru a vă normaliza și îmbogăți adresele în Formatul Common Data Model pentru o mai bună acuratețe și informații.
 
   Pentru mai multe informații, consultați [Îmbogățirea profilurilor clienților cu adrese îmbunătățite](enrichment-enhanced-addresses.md).

- **Experiență de configurare ghidată pentru îmbogățiri**    
  
   Am revizuit experiența de configurare pentru îmbogățiri cu o experiență simplă și ghidată. Aveți acum un proces clar pas cu pas pentru crearea și editarea îmbogățirilor.
 
   În plus, am separat configurația conexiunilor pentru îmbogățiri terțe pentru a permite ca aceeași conexiune să fie utilizată de îmbogățiri multiple. Numai administratorii pot configura conexiuni noi, dar conexiunile create sunt disponibile atât pentru administratori, cât și pentru contribuitori.    

   Pentru mai multe informații, consultați [Prezentare conexiuni=](connections.md).

- **Îmbogățiri multiple de același tip**    
  
   Acum permitem utilizatorilor să creeze și să gestioneze mai multe îmbogățiri de același tip de îmbogățire. De exemplu, puteți crea acum două îmbogățiri de adrese separate pentru a îmbogăți două segmente de clienți diferite. Limitele se aplică numărului de îmbogățiri de același tip care pot fi create și variază în funcție de tipul de îmbogățire.
  
   Pentru mai multe informații, consultați [Îmbogățire pentru profiluri de clienți](enrichment-hub.md).

## <a name="march-2021-updates"></a>Actualizări martie 2021

Actualizările din martie 2021 includ mai multe funcții, actualizări de performanță și remedieri de erori.

### <a name="activities"></a>Activități

- **Expert activitate și tipuri semantice**

   Am îmbunătățit și am actualizat experiența noastră de cartografiere a activității pentru a ghida și simplifica crearea cartografierii activității. În această nouă experiență, utilizatorii obțin o experiență ghidată pentru a ajuta la finalizarea fiecărui pas al procesului. La etapa de mapare a activității, pe lângă alegerea dintre mai multe tipuri de activități, utilizatorul poate alege să mapeze semantic datele pentru *Abonament* și/sau *SalesOrderLine* la schemele standard din industrie, care pot fi utilizate pentru consumul din aval.   

   Pentru mai multe informații, consultați [Activități Client](activities.md).

### <a name="data-ingestion"></a>Ingestie date

- **Conectați-vă la sursele de date local folosind fluxuri de date Power Platform și gateway-uri** Suntem încântați să anunțăm previzualizarea fluxurilor de date Power Platform și conectivitate local folosind gateway-uri în Customer Insights cu o Power Platform asociată sau un mediu Dataverse. Orice sursă de date nouă creată într-un mediu Customer Insights cu un mediu Dataverse legat va fi implicit la fluxuri de date Power Platform care aduc conectivitatea de date local și un set bogat de conectori și capabilități de transformare.

### <a name="extensibility"></a>Extensibilitate

- **Exporturi organizate în conexiuni și exporturi** Am schimbat numele paginii **Exportați destinațiile** în **Conexiuni** și am adăugat o pagină separată pentru **Exporturi**. Ca parte a acestei actualizări, vom transforma exporturile existente în perechi de conexiuni și exporturi utilizând conexiunea respectivă. Administratorii au acum mai multă claritate asupra datelor de ieșire din pagina **Conexiuni**. Toate rolurile utilizatorilor au acces la pagina **Exporturi**, dar numai administratorii pot alege să permită contribuitorilor să editeze anumite exporturi cu conexiuni partajate.     
  Pentru mai multe informații, consultați [Prezentare generală a conexiunilor](connections.md) și [Prezentare generală a exporturilor](export-destinations.md).

- **Exportați segmente în Campaign Monitor** Am extins destinațiile noastre de export pentru a include Campaign Monitor. Acum puteți exporta segmente din Customer Insights în listele Campaign Monitor și le puteți folosi ca bază pentru campaniile dvs. de marketing.    
   Pentru informații suplimentare, consultați [Exportați în Campaign Monitorl](export-campaign-monitor.md).

- **Exportați segmente în Persoană de contact constantă** Am extins destinațiile noastre de export pentru a include Persoană de contact constantă. Acum puteți exporta segmente din Customer Insights în listele Persoană de contact constantă și le puteți folosi ca bază pentru campaniile dvs. de marketing.   
   Pentru informații suplimentare, consultați [Exportați în Persoană de contact constantă](export-constant-contact.md).

- **Exportați segmente în RollWorks** Am extins destinațiile noastre de export pentru a include RollWorks. Acum puteți exporta segmente din Customer Insights către publicuri RollWorks și să le utilizați ca bază pentru publicitatea dvs. B-la-B.    
   Pentru informații suplimentare, consultați [Exportați în RollWorks ](export-rollworks.md).

- **Exportați segmente în Snapchat** Am extins destinațiile noastre de export pentru a include Snapchat. Acum puteți exporta segmente din Customer Insights în publicurile Snapchat și le puteți folosi ca bază pentru publicitatea dvs.     
   Pentru informații suplimentare, consultați [Exportați în Snapchat](export-snapchat.md).

### <a name="predictions"></a>Predicții

- **Utilizați filtre de produse în recomandările predictive de produse** Am adăugat capacitatea de a utiliza filtre de produse în modelul nostru de recomandare a produselor. Acum puteți crea un predicție care utilizează doar un subset de produse.    
   Pentru mai multe informații, consultați [Configurați filtrele de produse](predict-product-recommendation.md#configure-product-filters).

- **Creați segmente din predicțiile modelului** Am adăugat o modalitate rapidă de a crea segmente folosind rezultatele unui model predicție. Din pagina de rezultate a modelului, puteți crea cu ușurință un segment nou selectând noua opțiune **Creați un segment**.    
  Pentru mai multe informații, consultați [Creați un segment bazat pe un model predicție](prediction-based-segment.md).

- **Explicații pentru recomandările produsului** Am adăugat informații care explică factorii cheie învățați de modelul AI pentru a genera recomandări de produs și gradul în care acești factori contribuie la recomandările de produs. Aceste informații sunt adăugate la ecranul rezultatelor modelului.    
   Pentru mai multe informații, consultați [Examinați starea și rezultatele unei predicții](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Actualizări februarie 2021

Actualizările din februarie 2021 includ mai multe caracteristici, actualizări de performanță și remedieri de erori.

#### <a name="extensibility"></a>Extensibilitate

- **Exportare segmente în AdRoll**

  Am extins destinațiile noastre de export pentru a include AdRoll. Acum puteți exporta segmente din Customer Insights către segmentele de public AdRoll și le puteți folosi ca bază pentru publicitatea dvs. Pentru informații suplimentare, consultați [Conector pentru AdRoll](export-adroll.md).

#### <a name="segments"></a>Segmente
 
- **Dublați un segment**
  
  Pentru a crea un segment nou bazat pe unul existent, acum puteți duplica un segment și edita segmentul duplicat pentru a-l rafina în continuare. 

- **Adăugați atribute suplimentare unui segment**

  Acum puteți include atribute în rezultatul segmentului dvs., chiar dacă aceste atribute nu fac parte din profilul clientului. De exemplu, includeți ID-urile de abonament într-un segment, chiar dacă face parte din entitatea de abonament care are o relație M: 1 cu entitatea client. Atâta timp cât atributul aparține unei entități legate de entitatea client, puteți include acum aceste atribute.  

#### <a name="predictions"></a>Predicții

- **Creați recomandări predictive de produs**

  Înțelegerea a ceea ce clienții sunt interesați să cumpere este unul dintre primii pași necesari pentru a îmbunătăți veniturile din afaceri și pentru a fideliza clienții prin personalizare și implicare. Furnizarea de recomandări pentru produse care nu sunt aliniate la interesele clientului dvs. poate crea un sentiment de deconectare între client și afacerea dvs. și, în cele din urmă, poate limita veniturile potențiale și experiența generală pentru un client. 

  Folosind propriile date, puteți crea acum predicții pentru produsele pe care clienții dvs. le-ar putea achiziționa în viitor. Pentru mai multe informații, consultați [Recomandarea produsului predicție](predict-product-recommendation.md).

#### <a name="system-administration"></a>Administrare de sistem

- **Mediul de copiere acceptă mai multe tipuri de surse de date**

  Administratorii pot copia configurațiile de mediu într-un mediu nou din aceeași organizație. Această caracteristică extinde funcționalitatea mediului de copiere pentru cazurile în care sursele de date bazate pe un data lake gestionat Microsoft Dataverse sau un folder Common Data Model.

## <a name="january-2021-updates"></a>Actualizări din ianuarie 2021

Actualizările din ianuarie 2021 includ mai multe caracteristici, actualizări de performanță și remedieri de erori.

#### <a name="extensibility"></a>Extensibilitate

- **Funcționalitate extinsă și performanță îmbunătățită pentru exportul SFTP** Acum puteți exporta toate entitățile de ieșire din Customer Insights către o gazdă SFTP. Anterior, exportul era limitat la entități din segment. În plus, performanța exportului SFTP permite mai mult volum de date în mai puțin timp, în funcție de performanța gazdei dvs. SFTP.    
  Pentru informații suplimentare, consultați [Conector pentru SFTP (previzualizare)](export-sftp.md).  

#### <a name="segments"></a>Segmente

- **Segmente sugerate alimentate de învățarea programată pentru a îmbunătăți valorile** Există un mod nou de a descoperi și de a crea segmente. Sistemul folosește un model AI pentru a sugera segmente care pot ajuta la îmbunătățirea unui KPI (măsură) pe care îl urmăriți deja. Afișăm gradul de influență al atributelor pe care le selectați pe o măsură sau un alt atribut principal. Aceste informații vă ajută să găsiți segmente potențiale care prezintă oportunități.    
  Pentru informații suplimentare, consultați [Segmente sugerate (previzualizare)](suggested-segments.md).

#### <a name="data-unification"></a>Unificarea datelor

- **Experiență de potrivire îmbunătățită** În zona de unificare a datelor, experiența de potrivire a fost actualizată. Vă permite să configurați și să vizualizați regulile de potrivire, inclusiv statistici detaliate pentru a explica în continuare cum funcționează potrivirea. Există opțiuni pentru a dezactiva o regulă de potrivire, astfel încât să nu mai fie activă în timp ce păstrează configurația, trageți și fixați regulile de potrivire și multe altele.
  Pentru informații suplimentare, consultați [Potriviți entități](match-entities.md).

- **Ieșirea deduplicării din procesul de potrivire este disponibilă ca entitate** Rezultatul procesului de deduplicare din procesul de potrivire este acum scris într-o entitate separată pentru analiză ulterioară. Această entitate constă din câmpurile utilizate în procesul de deduplicare și înregistrarea câștigătorului și înregistrările alternative corespunzătoare care se îmbină cu înregistrarea câștigătorului.
  Pentru mai multe informații, consultați [Ieșirea deduplicată ca o entitate](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Administrare de sistem

- **Partajați fără probleme datele către Microsoft Dataverse** Acum puteți partaja rezultatele Customer Insights cu aplicații Microsoft Dataverse care utilizează Microsoft Dataverse Data Lake gestionat. Odată ce asociați un mediu Dataverse cu Customer Insights, aveți opțiunea de a activa partajarea datelor.
  Pentru informații suplimentare, consultați [Gestionare medii](manage-environments.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]