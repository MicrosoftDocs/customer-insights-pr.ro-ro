---
title: Caracteristici noi și viitoare
description: Informații despre funcții noi, îmbunătățiri și remedieri de erori.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 2159481f9355de738a7b457dcf0849a45c3e08db
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896250"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Noutățile din capacitatea de detalii despre public din Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Suntem încântați să anunțăm cele mai noi actualizări! Acest articol rezumă caracteristicile de previzualizare publică, caracteristicile de previzualizare, îmbunătățirile generale de disponibilitate și actualizări ale caracteristicilor. Pentru a vedea planurile de caracteristici pe termen lung, consultați [planurile de lansare Dynamics 365 și Power Platform](/dynamics365/release-plans/).

Lansăm actualizări pentru fiecare regiune în parte. Prin urmare, anumite regiuni pot vedea caracteristici înaintea altora. Cu excepția cazului în care se specifică altfel, nu trebuie să luați nicio acțiune și vom actualiza automat aplicația fără întreruperi.

> [!TIP]
> Pentru a remite și vota pentru solicitări de caracteristici și sugestii de produs, accesați [portalul Dynamics 365 Application Ideas](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="march-2021-updates"></a>Actualizări martie 2021

Actualizările din martie 2021 includ mai multe funcții, actualizări de performanță și remedieri de erori.

### <a name="activities"></a>Activități

- **Expert de activitate și tipuri semantice** Am îmbunătățit și am actualizat experiența noastră de cartografiere a activității pentru a ghida și simplifica crearea cartografierii activității. În această nouă experiență, utilizatorii obțin o experiență ghidată pentru a ajuta la finalizarea fiecărui pas al procesului. La etapa de mapare a activității, pe lângă alegerea dintre mai multe tipuri de activități, utilizatorul poate alege să mapeze semantic datele pentru *Abonament* și/sau *SalesOrderLine* la schemele standard din industrie, care pot fi utilizate pentru consumul din aval.    
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

- **Exportați segmente în RollWorks** Am extins destinațiile noastre de export pentru a include RollWorks. Acum puteți exporta segmente din Customer Insights în publicurile RollWorks și le puteți folosi ca bază pentru publicitatea dvs. B2B.    
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

  Administratorii pot copia configurațiile de mediu într-un mediu nou din aceeași organizație. Această caracteristică extinde funcționalitatea mediului de copiere pentru cazurile în care sursele de date se bazează pe un data lake Common Data Service sau se utilzează un folder Common Data Model.

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


## <a name="december-2020-updates"></a>Actualizările din decembrie 2020

Actualizările din decembrie 2020 includ mai multe funcții, actualizări de performanță și remedieri de erori.

### <a name="new-and-updated-features-in-december-2020"></a>Caracteristici noi și actualizate în decembrie 2020

#### <a name="data-enrichment"></a>Îmbogățire date

- **Îmbunătățirea îmbogățirii afinității mărcii și intereselor**
  
  Ne-am simplificat scorurile de afinitate pentru a le face mai ușor de înțeles și de utilizat. Acum puteți identifica rapid clienții în funcție de cât de multă afinitate au pentru un anumit brand sau interes.

  În plus, am adăugat noi opțiuni de configurare pentru a controla mai bine modul în care doriți ca profilurile dvs. de clienți să fie îmbogățite. 

  Pentru mai multe informații, consultați [Îmbogățiți profilurile clienților cu afinități de brand și interes](enrichment-microsoft.md).

- **Controlați ce profiluri să îmbogățiți**

  Acum puteți îmbogăți doar un subset de profiluri de clienți cu opțiunea de a selecta o entitate de segment în loc de entitatea de client implicită. Creați un segment cu profilurile clienților pe care doriți să îl îmbogățiți și selectați-l în configurația de îmbogățire pentru setul de date despre clienți.
  Această caracteristică este disponibilă în prezent numai pentru îmbogățiri oferite de Experian și HERE Technologies. Vom activa această capacitate în mai multe îmbogățiri în curând.

  Pentru mai multe informații, consultați [Îmbogățiți profilurile clienților cu date demografice de la Experian](enrichment-experian.md) sau [Îmbogățirea profilurilor clienților cu tehnologiile HERE](enrichment-here.md).

#### <a name="extensibility"></a>Extensibilitate

- **Activați-vă segmentele prin Autopilot**

  Exportați segmente către Autopilot și folosiți-le în scopuri de marketing. Pentru informații suplimentare, consultați [Conector pentru Autopilot (previzualizare)](export-autopilot.md).

- **Activați-vă segmentele prin SendGrid**

  Exportați segmente către SendGrid și folosiți-le în scopuri de marketing. Pentru informații suplimentare, consultați [Conector pentru SendGrid](export-sendgrid.md).

#### <a name="system-administration"></a>Administrare de sistem

- **Experiență actualizată în managementul mediului**
  
  Acum puteți crea, edita, șterge și reseta medii direct din selectorul de mediu din antetul aplicației. 
  
  În plus, mediul pe care îl utilizați va fi fixat în partea de sus a panoului de mediu, astfel încât să nu mai aveți nevoie să îl căutați.

  Pentru informații suplimentare, consultați [Gestionare medii](manage-environments.md).

## <a name="november-2020-updates"></a>Actualizări din noiembrie 2020

Actualizările din noiembrie 2020 includ mai multe funcții, upgrade-uri de performanță și remedieri de erori.

### <a name="new-and-updated-features-in-november-2020"></a>Funcții noi și actualizate în noiembrie 2020

#### <a name="data-enrichment"></a>Îmbogățire date

- **Aduceți propriile date de îmbogățire prin import personalizat Secure File Transfer Protocol (SFTP)**
  
  Importul particularizat SFTP vă permite să importați de îmbogățire date care nu trebuie să treacă prin procesul de unificare a datelor. Aflați mai multe informații despre importul particularizat SFTP.

  Pentru mai multe informații, consultați [Îmbogățiți profilurile clienților cu date personalizate (previzualizare)](enrichment-SFTP-custom-import.md).
 
- **Îmbogățiți-vă datele despre clienți cu date de localizare de la HERE Technologies**

  Cu serviciile de îmbogățire a datelor de la HERE Technologies, puteți construi o înțelegere mai precisă a locației clienților dvs. cu normalizarea adreselor, extragerea latitudinii și longitudinii și multe altele. Aflați mai multe despre îmbogățire cu HERE Technologies.

  Pentru mai multe informații, consultați [Îmbogățirea profilurilor clienților cu HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Unificarea datelor

- **Flexibilitate pentru activarea profilării datelor pentru entitățile și câmpurile selectate din contul dvs. de stocare**

  Puteți indica ce entități de date și câmpuri dintr-un folder Model de date comune din contul dvs. Azure Data Lake Storage doriți să activați profilarea datelor ca parte a procesului de ingestie de date.

  Pentru mai multe informații, consultați [Conectați-vă la un folder Common Data Model](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Extensibilitate

- **Activați-vă segmentele prin Google Ads**

  Exportați segmente din în liste de audiență Google Ads și folosiți-le pentru publicitate în Căutarea Google, Rețeaua de vizualizare Google, YouTube și Gmail. Aflați mai multe despre activarea segmentelor dvs. prin Google Ads.

  Pentru informații suplimentare, consultați [Conector pentru Google Ads](export-google-ads.md).

- **Activați-vă segmentele prin Marketo**

  Exportați segmente către segmente de public Marketo și utilizați aceste segmente de public pentru automatizarea marketingului. Aflați mai multe despre activarea segmentelor dvs. prin Marketo. 

  Pentru informații suplimentare, consultați [Conector pentru Marketo](export-marketo.md).

- **Activați-vă segmentele prin DotDigital**

  Exportați segmente către DotDigital și folosiți-le în scopuri de marketing. Aflați mai multe despre activarea segmentelor dvs. prin DotDigital. 

  Pentru informații suplimentare, consultați [Conector pentru DotDigital](export-dotdigital.md).

#### <a name="predictions"></a>Predicții

- **Preziceți retragerea tranzacțională**

  Funcția de predicție a retragerii tranzacționale vă permite, fără ajutorul unui om specialist în știința datelor, să preziceți probabilitatea ca un client să nu mai cumpere produse sau servicii.  Folosind scorul de predicție, puteți combina alte informații despre clienții dvs., cum ar fi valoarea clientului, pentru a crea segmente cu risc ridicat de retragere sau clienți cu valoare ridicată. Utilizați acest segment pentru a viza direct clienții prin activități de marketing, asistență pentru clienți și alte scenarii pentru a reduce riscul de retragere.
 
  Configurați definiția retragerii ca o fereastră bazată pe timp specifică afacerii dvs. și definiți când clienții sunt considerați retrași. De exemplu, un magazin alimentar ar putea dori să considere un client ca retras dacă nu a cumpărat nimic în ultimele 30 de zile.
 
  Pe măsură ce continuați să creați predicția, vă vom ghida cu datele necesare și vă vom permite să mapați datele despre afacerea dvs. în câmpurile necesare pentru a prezice retragerea pentru clienții dvs. De asemenea, puteți planifica un program de reinstruire a modelului pe baza informațiilor noi din sistemul dvs. pentru a se adapta la circumstanțele comerciale în schimbare.
 
  Pentru mai multe informații, consultați [Predicția retragerii tranzacționale (previzualizare)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Administrare de sistem

- **Resetați mediul**

  Resetați totul într-un mediu al unei instanțe selectate pentru a începe din nou.

  Pentru mai multe informații, consultați [Resetarea unui mediu existent](manage-environments.md#reset-an-existing-environment).


- **Conectați-vă la contul Azure Data Lake Storage utilizând un director de serviciu**

  Scrieți date de ieșire și citiți date din contul dvs. de stocare utilizând un director de serviciu Azure. Conexiunile de cont de stocare existente pot continua să utilizeze cheia de cont. De asemenea, oferă o opțiune de actualizare pentru a utiliza principalul de serviciu în continuare. Conexiunile noi se vor baza pe metoda de autentificare a principalului de serviciu pentru contul dvs. de stocare.

  Pentru mai multe informații, consultați [Conectarea la un cont Azure Data Lake Storage Gen2 cu o entitate principală de serviciu Azure pentru detalii privind publicul](connect-service-principal.md).

## <a name="october-2020-updates"></a>Actualizări din octombrie 2020

Actualizările din octombrie 2020 includ mai multe funcții, upgrade-uri de performanță și remedieri de erori.

### <a name="new-and-updated-features-in-october-2020"></a>Funcții noi și actualizate în octombrie 2020

#### <a name="extensibility"></a>Extensibilitate

- **Exportare în Mailchimp**

Exportați segmente în listele de public existente în Mailchimp pentru le a oferi clienților dvs. o experiență de e-mail personalizată.

Pentru informații suplimentare, consultați [Conector pentru Mailchimp](export-mailchimp.md).

#### <a name="data-enrichment"></a>Îmbogățire date

- **Duplicați înregistrările sursă într-o entitate Match**

Specificați regulile de eliminare a informațiilor duplicate pentru entitățile utilizate în procesul de potrivire pentru a identifica înregistrările duplicate. Îmbinați-le într-o singură înregistrare și conectați toate înregistrările sursă la această înregistrare combinată. Această înregistrare cu eliminarea informațiilor duplicate va fi apoi utilizată în procesul de potrivire între entități.

Pentru mai multe informații, consultați [Definiți eliminarea informațiilor duplicate pentru o entitate de potrivire](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Administrare de sistem

- **Orchestrare: opțiune nouă de reîmprospătare în Îmbinare**

Până astăzi, când executați procesul de îmbinare, sistemul rula toate procesele din aval care depindeau de îmbinare și procesele ulterioare. Acum puteți verifica rezultatul procesului de îmbinare (entitatea client unificată) înainte de a-l utiliza în procesarea din aval, cum ar fi segmente sau măsuri.
Pe pagina de îmbinare, puteți alege acum să rulați doar pasul de îmbinare și să rulați doar acest proces. Pentru a reîmprospăta și toate procesele din aval, puteți alege să executați procesele de îmbinare și aval. 

## <a name="september-2020-updates"></a>Actualizări din septembrie 2020

Actualizările din septembrie 2020 includ mai multe funcții, actualizări de performanță și remedieri de erori.

### <a name="new-and-updated-features-in-september-2020"></a>Funcții noi și actualizate în septembrie 2020

#### <a name="activities"></a>Activități

- **Predicție inteligentă a semanticii atributelor**

Această nouă caracteristică prezice tipurile semantice de atribute de intrare care sunt transmise procesului de unificare a datelor. Folosește modele învățare programată care îmbunătățesc precizia și economisesc timp.

#### <a name="enrichments"></a>Îmbogățiri

- **Îmbogățirea cu date demografice de la Experian**

Îmbogățirea cu date demografice de la Experian este acum disponibilă în previzualizare. Experian este lider global în raportarea creditelor pentru consumatori și afaceri și servicii de marketing. Cu [Serviciile de îmbogățire a datelor Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage), puteți construi o înțelegere mai profundă a clienților dvs. îmbogățind profilurile clienților cu date demografice, cum ar fi dimensiunea gospodăriei, veniturile și multe altele.

Pentru a utiliza această caracteristică, trebuie să aveți un abonament Experian activ.

Pentru mai multe informații, consultați [Îmbogățirea profilurilor clienților cu date demografice de la Experian](enrichment-experian.md)


#### <a name="system-administration"></a>Administrare de sistem

- **Panoul cu detaliile unei activități**

Panoul cu detalii despre activitate vă permite să vedeți detalii despre activitățile pe care le rulează sistemul. Este un mod la îndemână de a identifica problemele legate de configurație și de a găsi soluții.
Examinați mesajele de eroare pentru a vedea cum să abordați eventualele probleme.
 
- **Informații de procesare adăugate la mai multe pagini**

Această îmbunătățire adaugă informații despre starea entităților dvs. pe pagina **Entități** și **Clienți**.
 
În plus, puteți găsi detalii despre progresul proceselor, împreună cu detaliile activității, pe ambele pagini.

- **Îmbunătățiri la pagina de stare a sistemului**

Am îmbunătățit structura tabelului cu detalii de stare în **Sistem** > **Stare** la examinarea exporturilor de date.
 
În plus, erorile în **Detalii** sunt acum mai detaliate și mai acționabile. 
 
- **Anularea readuce operațiunea la starea anterioară**

Când anulați o sarcină, de exemplu, în procesul de potrivire, aceasta va reveni la ultima sa stare. De exemplu, dacă procesul de potrivire s-a încheiat ieri și îl anulați astăzi, acesta va reveni la starea de succes de ieri.


## <a name="august-2020-updates"></a>Actualizări august 2020

Actualizările din august 2020 includ mai multe funcții, actualizări de performanță și remedieri de erori.

### <a name="new-and-updated-features-in-august-2020"></a>Funcții noi și actualizate în august 2020

#### <a name="data-unification"></a>Unificarea datelor

- **Experiență îmbunătățită pentru etapa hărții în timpul unificării datelor**

  Experiența la etapa hărții în procesul de unificare a datelor vă permite să selectați entități, atribute și să definiți semantica într-un mod mai transparent.

  Modificările includ:
  
  - mai puține interacțiuni necesare pentru a adăuga entități și câmpuri;
  - capacități de căutare îmbunătățite pe pagina hărții;
  - identificarea vizuală și ușoară a tipului de câmp sugerat

#### <a name="enrichment"></a>Îmbogățire

- **Îmbogățirea afinităților de interes disponibile pe mai multe piețe**

  Extindem disponibilitatea îmbogățirii afinităților de interes dincolo de Statele Unite la alte cinci piețe: Canada, Australia, Regatul Unit, Franța și Germania. Cu această extensie, vă puteți îmbogăți datele despre clienți cu mai multe interese aplicabile acestor piețe. De asemenea, vă vom îmbogăți profilurile de clienți care se află pe aceste piețe utilizând date proprietare locale de la Microsoft.
  Pentru mai multe informații, consultați [Îmbogățiți profilurile clienților cu afinități de brand și interes](enrichment-microsoft.md)


## <a name="july-2020-updates"></a>Actualizări iulie 2020

Actualizările din iulie 2020 includ mai multe caracteristici, actualizări de performanță și remedieri de erori.

### <a name="new-and-updated-features-in-july-2020"></a>Caracteristici noi și actualizate în iulie 2020

#### <a name="extensibility"></a>Extensibilitate

- **Declanșator Power Automate pentru procesul de unificare finalizat**

  Ne-am extins declanșatoarele pentru Power Automate și vă permit să creați o notificare sau o acțiune atunci când este finalizată o actualizare a procesului de unificare (mapare, potrivire, îmbinare).    
  Pentru mai multe informații, consultați [Conectorul Power Automate](export-power-automate.md)

#### <a name="enrichment"></a>Îmbogățire

- **Îmbogățirea afinităților de marcă disponibile pe mai multe piețe**

  Extindem disponibilitatea îmbogățirii afinităților de marcă dincolo de Statele Unite la alte cinci piețe: Canada, Australia, Regatul Unit, Franța și Germania. Cu această extensie, vă puteți îmbogăți datele clienților dvs. cu mărci locale de pe aceste piețe. De asemenea, vă vom îmbogăți profilurile de clienți care se află pe aceste piețe utilizând date proprietare locale de la Microsoft.
  Pentru mai multe informații, consultați [Îmbogățiți profilurile clienților cu afinități de brand și interes](enrichment-microsoft.md)

## <a name="june-2020-updates"></a>Actualizări iunie 2020

Actualizările din iunie 2020 includ mai multe caracteristici, actualizări de performanță și remedieri de erori.

### <a name="new-and-updated-features-in-june-2020"></a>Caracteristici noi și actualizate în iunie 2020

#### <a name="enrichment"></a>Îmbogățire

- **Îmbogățirea cu datele companiei din Leadspace**
  
  Definiți câmpurile din profilurile de clienți unificate, care sunt utilizate pentru a căuta datele companiei aferente din Leadspace. După executarea procesului de îmbogățire, profilurile B2B sunt îmbogățite cu mai multe atribute, inclusiv dimensiunea companiei, locația, industria și multe altele.    
  Această colaborare vă permite să îmbunătățiți calitatea datelor dvs. cu aportul de la servicii terțe. Pentru a utiliza această îmbogățire, veți avea nevoie de o licență de la Leadspace pentru a accesa datele companiei sale B2B. Sistemul va folosi acea licență pentru a vă menține datele îmbogățite continuu.    
  Pentru mai multe informații, consultați [Îmbogățirea profilurilor companiei cu Leadspace](enrichment-leadspace.md).

- **Pagină hub de îmbogățire**

  Toate îmbogățirile datelor de la furnizori primari și terți de îmbogățire sunt configurate în același loc. Configurarea îmbogățirii datelor este o experiență perfectă care este gestionată dintr-un loc comun.    
  Pentru mai multe informații, consultați [Îmbogățire pentru profiluri de clienți](enrichment-hub.md).

- **Îmbogățirea separată a mărcii și a interesului**

  Afinitățile de mărci și interese sunt acum disponibile ca două îmbogățiri independente. Îmbogățirile separate vă oferă flexibilitatea de a le configura și gestiona individual, în funcție de cerințele sau nevoile dvs. de afaceri.    
  Pentru mai multe informații, consultați [Îmbogățiți profilurile clienților cu afinități de brand și interes](enrichment-microsoft.md).

#### <a name="extensibility"></a>Extensibilitate

- **Adrese URL clicabile pentru activități unificate în Program de completare Card client Dynamics 365**

  Activitățile unificate din programul de completare a cardului pentru clienți afișează acum adrese URL pe care se poate face clic dacă aceste adrese URL au fost definite în timpul configurării activităților.    
  Pentru mai multe informații, consultați [Programul de completare Card client](customer-card-add-in.md).

- **Afinități de marcă și de interes disponibile în Program de completare Card client Dynamics 365**

  Un nou control asupra suplimentului pentru programul de completare Card client Dynamics 365 vă permite să arătați îmbogățirile de marcă și de interes pentru contactele dvs. în aplicațiile de implicare a clienților din Dynamics 365.    
  Pentru mai multe informații, consultați [Programul de completare Card client](customer-card-add-in.md).

- **Mai multe declanșatoare Power Automate**

  Ne-am extins declanșatoarele pentru Power Automate și a adăugat următoarele declanșatoare:
  - Obțineți o notificare sau efectuați o acțiune când se finalizează o actualizare completă automată (surse de date, unificare, segmente, măsuri, exporturi)
  - Definiți un prag pentru o măsură de afaceri. De exemplu, aveți posibilitatea să creați o notificare care este trimisă atunci când pragul definit este trecut. În plus, declanșatorul aduce informații care vă permit să construiți fluxuri de lucru mai complexe în Power Automate.    
  Pentru mai multe informații, consultați [Conectorul Power Automate](export-power-automate.md)

- **Exportați către Facebook Ads Manager**
  
  Această funcție vă permite să exportați segmente către Managerul de anunțuri Facebook. Segmentele sunt exportate ca segmente de public personalizate pentru a utiliza profiluri de clienți unificate în campanii de marketing și reclame Facebook. Publicul personalizat este, de asemenea, utilizabil pentru a crea campanii pe Instagram prin Facebook Ads Manager.    
  Pentru mai multe informații, consultați [Conector pentru Facebook Ads Manager](export-facebook.md).

#### <a name="predictions"></a>Predicții

- **Predicție retragere abonament**

  Urmați o experiență ghidată pentru a crea predicție în zonele de abonament precum serviciile cloud, apartenența clienților și alte sectoare. 

  Funcția de abonament predicție vă permite să prezicem probabilitatea ca un client să oprească utilizarea de produse sau servicii bazate pe abonament fără a angaja un om de știință de date. Folosind scorul predicție, puteți combina alte informații despre clienții dvs. pentru a crea segmente cu risc ridicat de forfecare. Cu ajutorul acestui segment, puteți viza direct clienții în marketing, asistență pentru clienți și alte scenarii pentru a reduce riscul de retragere pentru clienți specifici pentru a îmbunătăți veniturile și a reduce costurile.

  În cadrul experienței, puteți configura definiția churn ca o fereastră bazată pe timp specifică afacerii dvs. De exemplu, o afacere de streaming video care are un proces de abonament lunar ar putea dori să considere un client că s-a oprit după 15 zile de la expirarea abonamentului.

  Pe măsură ce continuați prin predicție, vă vom îndruma prin ce date este necesar și vă vom permite să mapăm datele despre afacerea dvs. în câmpurile necesare pentru a prezice retragerea pentru clienții dvs. Pe măsură ce informațiile despre afaceri se schimbă, puteți, de asemenea, să setați o programare pentru a reda informațiile noi din sistemul dvs. pentru a vă adapta circumstanțelor de schimbare ale afacerii.    
  Pentru mai multe informații, consultați [Predicție retragere abonament (previzualizare)](predict-subscription-churn.md).

#### <a name="segments"></a>Segmente

- **Găsiți clienți similari**
  
  Găsiți clienți similari în baza de clienți utilizând informații artificiale. Un model de clasificare binară învățare programată atribuie un scor de similitudine clienților din segmentul extins. Scorul se bazează pe similaritatea cu clienții din segmentul sursă. În funcție de scorul de similaritate, profilurile clienților sunt adăugate unui segment nou creat.

  Uneori denumit modelare similară în marketingul digital, folosește un model AI pentru a găsi clienți care sunt similari cu un alt segment al clienților dvs., luând în considerare mai multe atribute. Acesta nu numai că vă permite să alegeți atributele, dar vă permite, de asemenea, să specificați numărul maxim de clienți care ar trebui să se afle în acest nou segment. Modelul de inteligență artificială va calcula apoi scoruri de similitudine pentru fiecare client pe baza atributelor selectate și va găsi clienți cu un scor similar de medie mai mare. Segmentul rezultat va include clienți care arată similar cu clientul din segmentul inițial.    
  Pentru informaţii suplimentare, consultaţi [Clienți similari](find-similar-customer-segments.md).

- **Suprapunerea și diferențierea segmentelor**

  Suprapunerea segmentelor vă permite să vedeți câți și care clienți sunt comune pentru două sau mai multe segmente. De exemplu, modul în care un segment cu cheltuieli mari se suprapune cu un segment de clienți cu satisfacții ridicate sau cum se suprapune un segment de clienți care se suprapune cu un segment de clienți cu satisfacție scăzută. În plus, puteți analiza modul în care se suprapune modificările pe baza unui atribut suplimentar la alegere.

  Diferențiatori de segmente dezvăluie ceea ce diferențiază un segment de restul clienților sau de un alt segment. Tot ce trebuie să faceți este să identificați un segment, iar sistemul va identifica atributele de profil și măsurile care disting segmentul sub forma unei liste clasificate de diferențiatori - de la cel mai puternic diferențiator la cel mai slab.    
  Pentru informații suplimentare, consultați [Detalii de segment (previzualizare)](segment-insights.md).

- **Durata de viață a segmentului**
  
  Definiți o planificare pentru a activa sau dezactiva un segment.    
  Pentru informații suplimentare, consultați [Gestionați segmente existente](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Actualizări mai 2020

Actualizările din mai 2020 includ mai multe caracteristici, upgrade-uri de performanță și remedieri de erori.

### <a name="new-and-updated-features-in-may-2020"></a>Caracteristici noi și actualizate în mai 2020

#### <a name="data-ingestion"></a>Ingestie date

- **Ingestia de date în timp real: vizualizări de istoric**

  Atunci când utilizați API-ul nostru pentru a ingera actualizări în timp real, puteți vedea până la 30 de zile de istoric agregat pentru aceste actualizări. Aveți acces la agregatele tuturor apelurilor API reușite sau nereușite, inclusiv rezultatul acestora, sistemul sursă și alte metadate utile.    
  Pentru mai multe informații, consultați [Ingestie date în timp real](real-time-data-ingestion.md).

- **Ingestia de date în timp real: actualizări de profil**

  Această extensie a ingerării datelor în timp real vă permite să vedeți, în câteva secunde, modificările la anumite câmpuri de profil de utilizator.    
  În plus față de funcționalitatea în timp real pentru activități, sistemul acceptă actualizări cu latență redusă a câmpurilor de profil. Actualizările în timp real pentru câmpurile de profil au un timp de expirare și, prin urmare, nu sunt un înlocuitor pentru reîmprospătări programate.    
  Pentru mai multe informații, consultați [Ingestie date în timp real](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Extensibilitate

- **Cronologie actualizată și paginare în programul de completare Card client**

  Cronologia soluției de completare a cardului client se potrivește cu cronologia activității. Paginarea cronologiei s-a îmbunătățit, afișând până la 50 de activități simultan. De asemenea, permite încărcarea mai multor activități în cronologie.    
  Pentru mai multe informații, consultați [Programul de completare Card client](customer-card-add-in.md).

- Declanșator **Power Automate pentru modificările segmentului**

  Declanșatoare pentru ca Power Automate să definează de la ce puteți construi un flux. Declanșatorul nou adăugat vă permite să definiți un prag pentru un segment. De exemplu, aveți posibilitatea să creați o notificare care este trimisă atunci când pragul definit este trecut.    
  Pentru mai multe informații, consultați [Conectorul Power Automate](export-power-automate.md).

- **Suport de tip multitenant pentru modele personalizate**

  Configurați fluxurile de lucru pentru modele particularizate cu un serviciu web al unei entități găzduite diferite de Invățare programată Azure. Vă puteți conecta la entitatea găzduită Azure Machine Learning atunci când creați un nou flux de lucru pentru modele personalizate. Această capacitate este un plus față de capacitatea existentă de integrare cu propriul serviciu web personalizat de Învățare programată Azure.    
  Pentru mai multe informații, consultați [Modelele de învățare programată particularizate](custom-models.md).

#### <a name="segments"></a>Segmente

- **Automatizarea căii entității**

  Atunci când creează un segment, utilizatorii trebuie să definească calea entității. Această capacitate face un prim pas la automatizarea definiției căii entității, astfel încât să vă puteți concentra asupra criteriilor de segmentare pe care le aveți în minte.    
  Dacă entitatea prin care doriți să segmentați clienții este direct legată de entitatea client unificată, nu va mai fi necesar să definiți calea entității. Cu toate acestea, dacă există mai multe căi de entitate posibile, tot trebuie să o definiți manual.

- **Acțiuni pe mai multe segmente**
  
  Utilizatorii pot selecta mai multe segmente și pot lua măsuri asupra lor, ar fi reîmprospătarea segmentelor, cu un singur clic.    

- **Se reîmprospătează segmentele**

  Utilizatorii pot reîmprospăta un singur segment sau pot selecta numai segmentele pe care doresc să le reîmprospăteze.    

  
- **Îmbunătățiri ale segmentelor compuse**

  Utilizatorii pot crea, edita și șterge segmente bazate pe alte segmente. De exemplu, un segment construit pe un alt segment care a fost construit pe un al treilea segment.    

- **Pagina cu lista de segmente**

  Noul design al paginii de segmente utilizează un format de listă care vă permite să vedeți mai multe segmente simultan. Se adaugă un câmp de căutare pentru a găsi rapid segmente. Utilizatorii pot aplica acum acțiuni precum descărcarea sau ștergerea pe mai multe segmente simultan. O nouă experiență de tendință este introdusă pentru a identifica rapid modificările semnificative pe segmente.    
  Pentru mai multe informații, consultați [Creați și gestionați segmente](segments.md).

#### <a name="system-administration"></a>Administrare de sistem

- **Customer Insights disponibil în Microsoft Dynamics 365 Online Government**

  Având din ce în ce mai multe canale pentru interacțiuni, datele cetățenilor sunt răspândite în nenumărate sisteme, ceea ce duce la date silozate și la o vizualizare fragmentată a informațiilor despre interacțiunile cu cetățenii. Fără o vizualizare completă a interacțiunilor fiecărui cetățean pe canale, este imposibil pentru guverne să se modernizeze la scară largă. Microsoft se angajează să sprijine nevoile tehnologice ale guvernului pentru a ține pasul cu așteptările cetățenilor pentru experiențe consecvente și receptive.    
  Odată cu lansarea valului 1 din 2020, Dynamics 365 Customer Insights va fi disponibil pentru Government Community Cloud (GCC), un mediu construit pentru a satisface nevoile mai mari de conformitate ale agențiilor guvernamentale ale Statelor Unite. Agențiile obțin o viziune unificată asupra cetățenilor și utilizează IA predefinită pentru a obține informații care îmbunătățesc interacțiunile, împuternicesc angajații și transformă comunitățile, reducând în același timp complexitatea IT și îndeplinind standardele de conformitate și securitate ale Statelor Unite. Dynamics 365 Government îndeplinește cerințele exigente ale Programului Federal de Gestionare a Riscurilor și Autorizațiilor din SUA (FedRAMP), permițând agențiilor federale din Statele Unite să beneficieze de economiile de costuri și de securitatea riguroasă a Microsoft Cloud.

## <a name="april-2020-updates"></a>Actualizări aprilie 2020

Actualizările din aprilie 2020 includ mai multe caracteristici, upgrade-uri de performanță și remedieri de erori.

### <a name="new-and-updated-features-in-april-2020"></a>Caracteristici noi și actualizate în aprilie 2020

#### <a name="activities"></a>Activități

- **Maparea entității de activitate la tipul de activitate standard**
  
  Configurația și stocarea activității se bazează în prezent pe un design static pentru a le vizualiza într-o cronologie. Semnificația semantică a activităților, care are potențial pentru mai multe cazuri de utilizare în modelele AI, nu este utilizată pe deplin în acest moment. Intenționăm să facem cronologia activității mai dinamică, în funcție de tipul de activitate și de o mai bună înțelegere semantică a activităților. Această caracteristică are ca scop identificarea tipului de activitate definit în Common Data Model pentru orice activitate ingerată.
  Pentru mai multe informații, consultați [Activități Client](activities.md).

#### <a name="data-ingestion"></a>Ingestie date

- **Ingestia de date în timp real: activități**
  
  Ingerarea datelor în timp real oferă date imediat pentru consum, până când actualizarea planificată ulterioară extrage aceste date din sursa de date.    
  Pentru mai multe informații, consultați [Ingestie date în timp real](real-time-data-ingestion.md).

- **Îmbunătățiri ale pregătirii datelor**
  
  Aflați mai multe despre datele ingerate într-o entitate. Cu rezumatul datelor, puteți înțelege caracteristicile de calitate a datelor care vă pot ajuta să luați măsurile corespunzătoare.    
  Pentru informaţii suplimentare, consultaţi [Explorați date de entitate](entities.md#exploring-a-specific-entitys-data).

- **Ingerați date analitice din Dynamics 365 cu Common Data Service**
  
  Common Data Service este disponibil ca o modalitate de a crea surse de date. Clienții Dynamics 365 existenți pot ingera entități analitice de la Common Data Service la Customer Insights. O singură sursă de date poate folosi simultan același lac administrat de Common Data Service într-un mediu Customer Insights.    
  Pentru mai multe informații, consultați [Conectarea la date într-un Common Data Service data lake gestionat](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Extensibilitate

- **Exportați în LiveRamp**

  Activați-vă datele în LiveRamp® pentru a vă conecta cu peste 500 de platforme pe ecosistemele digitale, sociale și TV. Utilizați datele din LiveRamp pentru direcționarea, suprimarea și personalizarea campaniilor publicitare.    
  Pentru mai multe informații, consultați [conectorul LiveRamp&reg;](export-liveramp.md).

- **Programul de completare Customer Insights Teams**
  
  Robotul oferă funcții de căutare pentru profiluri de clienți unificate. Acesta va afișa o fișă cu până la 15 câmpuri din profilul clientului rezultat. Mai multe potriviri returnează o listă de rezultate în care puteți selecta un profil.    
  Pentru mai multe informații, consultați [Robot Teams pentru Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Măsuri

- **Măsurați pagina de listă**
  
  Printre îmbunătățirile aduse paginii de măsuri se numără sprijinirea acțiunilor privind o singură măsură și pentru mai multe măsuri simultan. În plus, veți găsi un câmp de căutare pentru a găsi și urmări rapid măsurile.    
  Pentru mai multe informații, consultați [Creați și gestionați segmente](segments.md).

- **Îmbunătățiri ale măsurilor compuse**
  
  Utilizatorii pot crea, edita și șterge măsuri bazate pe alte măsuri. De exemplu, o măsură construită pe un altă măsură care a fost construită pe o a treia măsură.

#### <a name="segments"></a>Segmente

- **Un alt operator**
  
  Operatorul in-set permite segmentarea pentru clienți după mai multe valori posibile de șir. Înainte ca acest operator să fie adăugat, trebuia să construiți astfel de segmente cu mai multe condiții OR. Operatorul In-set vă permite să faceți acest lucru cu o singură condiție.    
  Pentru mai multe informații, consultați [Creați și gestionați segmente](segments.md).

#### <a name="system-administration"></a>Administrare de sistem

- **Copierea setărilor de configurare într-un mediu nou**
  
  Copiați configurația dintr-un mediu în altul. În timp ce creați un mediu nou, aveți posibilitatea să selectați un mediu existent din care doriți să copiați configurația. În prezent, sprijinim sursele de date, unificarea datelor, relațiile, măsurile și segmentele care urmează să fie copiate. Acreditările sursă de date și datele reale nu sunt copiate.    
  Pentru informații suplimentare, consultați [Gestionare medii](manage-environments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]