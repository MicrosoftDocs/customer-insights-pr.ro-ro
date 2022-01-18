---
title: Analiza semantică pentru feedback-ul clienților
description: Aflați cum să utilizați un model de analiză a sentimentelor pentru feedback-ul clienților în Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 05e530a1bc96c5fd9c7a3bc0197563d8fe330387
ms.sourcegitcommit: cb71e39de9b891c24bd5cd9c014eb3eeb537ac24
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 01/10/2022
ms.locfileid: "7951115"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analizați sentimentul în feedbackul clienților (Previzualizare)

Clienții se așteaptă la produse, servicii și experiențe de înaltă calitate în zilele noastre. În special clienții care își împărtășesc feedback-ul. Este foarte dificil pentru organizații să analizeze un volum din ce în ce mai mare de date fără a reduce acuratețea și costul forței de muncă mai mare. Dynamics 365 Customer Insights oferă un model de analiză a sentimentelor pentru feedback-ul clienților, care permite organizațiilor să își analizeze datele mai precis și la un cost mai mic.

Analiza sentimentelor vă permite să sintetizați sentimentul clienților și să identificați aspectele de afaceri ca oportunități de îmbunătățire. Această funcție Customer Insights vă ajută să înțelegeți ce funcționează bine și ce trebuie să abordați. Concentrați-vă pe domeniile cele mai relevante și de impact ale afacerii pentru a îmbunătăți experiența pentru clienții dvs. În cele din urmă, vă poate ajuta să conduceți acțiuni de afaceri care să permită experiențe care au ca rezultat satisfacția și loialitatea clienților.

## <a name="overview"></a>Prezentare generală

Funcția de analiză a sentimentelor generează două informații derivate pentru fiecare ID de client. Un scor de sentiment (de la -5 la 5) și o listă a aspectelor de afaceri aplicabile (domenii de activitate) împreună vă ajută să înțelegeți mai bine feedback-ul clienților. 

Aceste informații vă pot ajuta să obțineți următoarele rezultate: 
- Obțineți o imagine de ansamblu asupra sentimentelor clienților față de o marcă sau organizație
- Identificați clienții cu sentimente negative pentru a vă concentra campaniile și angajamentele și pentru a optimiza pentru o rentabilitate mai mare  
- Identificați aspectele de afaceri cu problemele semnalate de clienți  
- Segmentați clienții în funcție de sentimentul lor de a desfășura campanii personalizate cu eforturi de vânzări, marketing și asistență direcționate
- Optimizați operațiunile de afaceri abordând domeniile de îngrijorare sau oportunități care au fost menționate de clienți
- Recunoașteți aspectele de afaceri care merg bine și recompensați clienții fericiți prin programe de loialitate și promovare

Pentru a ne asigura că puteți avea încredere în rezultatele modelelor, oferim informații transparente despre modul în care modelele iau decizii. Veți primi o listă de cuvinte care au afectat decizia modelelor de a atribui un anumit scor de sentiment sau un aspect de afaceri comentariilor de feedback.  

Folosim două **Modele de procesare a limbajului natural (NLP).** : primul atribuie fiecărui comentariu de feedback un scor de sentiment. Al doilea model asociază fiecare feedback cu toate aspectele de afaceri aplicabile. Modelele sunt instruite pe date publice din surse din rețelele de socializare, retail, restaurante, produse de larg consum și industriile auto.    
  
- Aspectele de afaceri predefinite pentru ca modelul să fie asociate cu datele de feedback includ:
-   Gestionarea conturilor
-   Finalizarea comenzii și plata
-   Asistență pentru clienți
-   Preluare din depozit
-   Expedierea și recuperarea ambalajelor
-   Precomandă
-   Preț
-   Confidențialitate și securitate
-   Promoții și recompense
-   Recepție și garanție
-   Schimb retururi și anulare
-   Acuratețea procesării
-   Calitate site web/aplicație

> [!NOTE]
> În prezent, acceptăm doar analiza sentimentelor pentru feedback-ul clienților în limba engleză. Mai multe limbi vor fi acceptate în viitor. Dacă se încarcă feedback în alte limbi, modelul va returna în continuare rezultate. Cu toate acestea, aceste rezultate nu vor fi exacte. 

## <a name="prerequisites"></a>Cerințe preliminare

Analiza sentimentelor se bazează pe datele de feedback text care au trecut prin [procesul de unificare a datelor](data-unification.md). Vă recomandăm cu căldură [configurați-vă entitățile de date de feedback ca entități de activitate de tip semantic](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (Tip de feedback) în prealabil. 

Pentru a configura un model de analiză a sentimentelor, aveți nevoie de cel puțin [Permisiuni de colaborator](permissions.md).

Customer Insights poate procesa până la 10 milioane de înregistrări de feedback pentru un singur model. Modelul poate analiza comentariile de feedback până la 128 de cuvinte. Dacă un comentariu de feedback este mai lung, analiza ia în considerare doar primele 128 de cuvinte.

### <a name="data-requirements"></a>Cerinţe de date
  
Următoarele atribute de date sunt necesare:
- ID unificat de client (UCID) pentru a potrivi înregistrările de date de feedback text cu un client individual. Acest ID este rezultatul [procesul de unificare a datelor](data-unification.md).
- ID feedback
- Timp de feedback
- Text de feedback   

> [!TIP]
> Analiza sentimentelor necesită feedback-ul text al clienților dvs. În prezent, poate fi configurată o singură entitate de feedback. Dacă există mai multe entități de feedback, le puteți uni Power Query înainte de a începe absorbția de date.

## <a name="configure-a-sentiment-analysis"></a>Configurați o analiză a sentimentelor 

1. În Customer Insights, accesați secțiunea **Informații** > **Predicții**.

1. Pe **Analiza sentimentelor clienților** țiglă, selectați **Utilizați modelul**.

1. În **Analiza sentimentelor clienților (previzualizare)** panou, selectați **Incepe**.

1. În **Numele modelului** pas, furnizați a **Nume** pentru analiza dvs. 

1. Furnizați **Numele entității de ieșire pentru aspectul afacerii** si **Numele entității de ieșire a scorului de sentiment**, apoi selectați **Următorul**.

1. În **Date obligatorii** pas, selectați **Adăugați date**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Adăugați flux de date în modelul de analiză a sentimentelor.":::

1. În **Adăugați date** panoul, alegeți tipul semantic **Părere** din lista.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Pas de configurare pentru a selecta activitățile de feedback pentru analiza sentimentelor.":::

1. Selectați activitățile de utilizat pentru această analiză a sentimentelor, apoi selectați **Următorul**.
 
1. Mapați atributele din datele dvs. la atributele modelului. Selectați **salva** pentru a aplica selecțiile dvs. 

1. Vedeți starea mapării datelor. Selectați **Următorul** pentru a continua. 

1. În **Examinați detaliile modelului dvs** pas, validați configurația analizei sentimentelor dvs. Puteți reveni la orice parte a configurației predicție. Selectați **Salvați și rulați** pentru a începe analiza. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Examinați pasul pentru modelul de sentiment care arată toate elementele configurate.":::

1. Selectați **Terminat** pentru a părăsi experiența de configurare. Procesul poate dura câteva ore, în funcție de cantitatea de date utilizată. 

## <a name="review-analysis-status"></a>Examinați starea analizei

1.  Mergeți la **Informații** > **Predicții** și selectați fila **Previziunile mele**.
2.  Selectați predicția pe care doriți să o revizuiți.
- **Nume predicție**: Numele predicției furnizat la crearea acesteia.
- **tipul predicție** : Tipul de model utilizat pentru predicție.
- **Entitate de ieșire**: Numele entității care va stoca rezultatul predicției. Accesați **Date** > **Entități** pentru a găsi entitatea cu acest nume.
- **Câmp estimat**: Acest câmp este populat numai pentru anumite tipuri de predicții și nu este utilizat în predicția valorii ciclului de viață a clientului.
- **Stare**: Starea rulării predicției.
  - **În așteptare**: Predicția așteaptă să se finalizeze alte procese.
  - **Reîmprospătare**: Predicția rulează în prezent pentru a crea rezultate care vor curge în entitatea de ieșire.
  - **Eșuat**: Rularea predicției a eșuat. Pentru mai multe detalii, consultați fișierele-jurnal.
  - **Reușit**: Predicția a reușit. Selectați Vizualizare sub elipsele verticale pentru a examina rezultatele predicției.
- **Editat**: Data la care configurația predicției a fost modificată.
- **Ultima reîmprospătare** : data la care predicție a reîmprospătat rezultă în entitatea de ieșire.

## <a name="manage-sentiment-analysis"></a>Gestionați analiza sentimentelor

Puteți optimiza, depana, reîmprospăta sau șterge predicțiile. Examinați un raport de utilizare a datelor de intrare pentru a afla cum să faceți o predicție mai rapid și mai fiabil. Pentru mai multe informații, consultați [Gestionați o predicție](manage-predictions.md).

## <a name="review-analysis-results"></a>Examinați rezultatele analizei
 
1. Mergeți la **Informații** > **Predicții** și selectați fila **Previziunile mele**. 
1. Selectați numele predicție pentru care doriți să examinați rezultatele. În acest caz, selectați analiza de sentiment pe care doriți să o examinați. 

### <a name="summary-tab"></a>Filă rezumat

Există patru secțiuni principale de date în pagina de rezultate. 

- **Scorul mediu de sentiment** : vă ajută să înțelegeți sentimentul general al tuturor clienților. Scorurile de sentimente sunt grupate în trei categorii: 
  1.    Negativ (-5 > 2)
  2.    Neutru (-1 > 1)
  3.    Pozitiv (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Reprezentare vizuală a sentimentului general al clienților.":::

- **Distribuția clienților în funcție de scorul de sentiment** : Clienții sunt clasificați în grupuri negative, neutre și pozitive în funcție de scorurile lor de sentiment. Plasați cursorul peste barele din histogramă pentru a vedea numărul de clienți și scorul mediu de sentiment din fiecare grup. Aceste date vă pot ajuta [creați segmente de clienți](segments.md) pe baza scorurilor lor de sentimente.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Diagramă cu bare care arată sentimentul clienților din cele trei grupuri de sentimente.":::

- **Scorul mediu de sentiment în timp** : sentimentul clienților se poate schimba în timp. Oferim tendințe ale sentimentelor clienților dvs. pentru intervalul de timp al datelor dvs. Această vizualizare vă poate ajuta să evaluați efectul promoțiilor sezoniere, al lansărilor de produse sau al altor intervenții limitate în timp asupra sentimentului clienților. Vedeți graficul selectând anul de interes din meniul drop-down. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Diagramă istoric cu scorul de sentiment de-a lungul timpului reprezentat ca o linie.":::
 
- **Sentiment asupra aspectelor de afaceri** : Acest tabel afișează sentimentul mediu pe diferite aspecte ale afacerii. Vă poate ajuta să evaluați ce aspecte ale afacerii dvs. satisfac deja clienții sau aspectele care necesită mai multă atenție. Înregistrările de feedback care nu se aliniază la niciunul dintre aspectele de afaceri acceptate sunt clasificate în categoria **Alte**. Tabelul este sortat alfabetic în mod implicit. Puteți modifica sortarea selectând un antet de tabel.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Lista aspectelor de afaceri cu valoarea sentimentului asociată și numărul de clienți care o menționează.":::
 
  Selectați numele unui aspect de afaceri pentru a vedea informații suplimentare despre modul în care un aspect de afaceri este identificat de model. Există două părți în acest panou: 

  - **Cuvinte influente** : Afișează cuvintele de top care au influențat identificarea de către modelul AI a unui aspect de afaceri în feedback-ul clienților. 
    **Arată cuvinte jignitoare** : Vă permite să includeți cuvinte jignitoare în listă din datele originale de feedback ale clienților. În mod implicit, este dezactivat.  Mascarea cuvintelor ofensatoare este alimentată de un model AI și este posibil să nu detecteze toate cuvintele ofensatoare. Continuăm să iterăm și să antrenăm clasificatorul pentru performanțe optime. Dacă detectați un cuvânt jignitor care nu a fost filtrat conform așteptărilor, anunțați-ne. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Listă de cuvinte influente cu comutatorul pentru a afișa sau a ascunde cuvintele jignitoare.":::
 
  - **Mostre de feedback** : afișează înregistrările reale de feedback în datele dvs. Cuvintele sunt codificate pe culori în funcție de influența lor asupra identificării unui aspect de afaceri. 


### <a name="influential-words-analysis-tab"></a>Fila de analiză a cuvintelor influente

Există trei secțiuni de informații suplimentare care explică cum funcționează modelul de sentiment.
  
1. **Cuvinte de top care contribuie la sentimentul pozitiv** : Afișează cuvintele de top care au influențat identificarea de către modelul AI a sentimentelor pozitive în feedback-ul clienților.  
2. **Cuvinte de top care contribuie la sentimentul negativ** : Afișează cuvintele de top care au influențat identificarea de către modelul AI a sentimentelor negative în feedback-ul clienților.  
3. **Mostre de feedback** : Afișează înregistrările reale de feedback, una cu un sentiment negativ și una cu un sentiment pozitiv. Cuvintele din înregistrările de feedback sunt evidențiate în funcție de contribuția lor la scorul de sentiment atribuit. Cuvintele care contribuie la un scor pozitiv de sentiment sunt evidențiate cu verde. Cuvintele care contribuie la un scor negativ sunt evidențiate cu roșu.
   Selectați **Vezi mai mult** pentru a încărca mai multe mostre de feedback care oferă mai multe informații și context despre modul în care funcționează modelul de sentiment.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Exemple de analiză a sentimentelor privind feedback-ul clienților.":::
 
**Arată cuvinte jignitoare** : Vă permite să includeți cuvinte jignitoare în listă din datele originale de feedback ale clienților. În mod implicit, este dezactivat.  Mascarea cuvintelor ofensatoare este alimentată de un model AI și este posibil să nu detecteze toate cuvintele ofensatoare. Continuăm să iterăm și să antrenăm clasificatorul pentru performanțe optime. Dacă detectați un cuvânt jignitor care nu a fost filtrat conform așteptărilor, anunțați-ne. 

## <a name="act-on-analysis-results"></a>Acționați asupra rezultatelor analizei

Puteți începe cu ușurință să creați noi segmente de clienți din pagina cu rezultatele analizei sentimentelor selectând **Creați segmente** în partea de sus a paginii cu rezultatele modelului.

:::image type="content" source="media/create-segment-model.png" alt-text="Bară de comandă cu opțiuni pentru modelele predicție.":::
 
## <a name="potential-bias"></a>Potențial părtinire

Ca și în cazul oricărei funcții care utilizează inteligența artificială predictivă, ar trebui să fiți conștient de potențiala părtinire a datelor pe care le utilizați pentru a prezice sentimentul clienților. De exemplu, dacă colectați feedback doar digital, puteți pierde feedback de la clienții care desfășoară în principal afaceri cu dvs. în persoană, ceea ce ar putea afecta rezultatul funcției.

Deoarece această caracteristică folosește mijloace automate pentru a evalua datele și a face predicții pe baza acestor date, are, prin urmare, capacitatea de a fi utilizată ca metodă de profilare, așa cum termenul respectiv este definit de Regulamentul general privind protecția datelor („GDPR”). Utilizarea acestei funcții pentru prelucrarea datelor poate face obiectul GDPR sau altor legi sau reglementări. Sunteți responsabil pentru a vă asigura că folosiți Dynamics 365 Customer Insights, inclusiv analiza sentimentelor, respectă toate legile și reglementările aplicabile, inclusiv legile referitoare la confidențialitate, datele personale, datele biometrice, protecția datelor și confidențialitatea comunicațiilor.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

