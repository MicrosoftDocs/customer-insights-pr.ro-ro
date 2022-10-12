---
title: Analizați sentimentul pentru feedback-ul clienților (previzualizare)
description: Aflați cum să utilizați un model de analiză a sentimentelor pentru feedback-ul clienților în Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610481"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analizați sentimentul în feedbackul clienților (previzualizare)

Analiza sentimentelor vă permite să sintetizați sentimentul clienților și să identificați aspectele de afaceri ca oportunități de îmbunătățire. Această funcție Customer Insights vă ajută să înțelegeți ce funcționează bine și ce trebuie să abordați. Vă poate ajuta să conduceți acțiuni de afaceri care permit experiențe care au ca rezultat o satisfacție și loialitate ridicate ale clienților.

## <a name="overview"></a>Prezentare generală

Funcția de analiză a sentimentelor generează două informații derivate pentru fiecare ID de client. Un scor de sentiment (de la -5 la 5) și o listă de aspecte de afaceri aplicabile (domenii de activitate) care împreună vă ajută să înțelegeți mai bine feedback-ul clienților.

Această analiză vă ajută:
- Obțineți o imagine de ansamblu asupra sentimentelor clienților față de o marcă sau organizație
- Identificați clienții cu sentimente negative pentru a vă concentra campaniile și angajamentele și pentru a optimiza pentru o rentabilitate mai mare  
- Identificați aspectele de afaceri cu problemele semnalate de clienți  
- Segmentați clienții în funcție de sentimentul lor de a desfășura campanii personalizate cu eforturi de vânzări, marketing și asistență direcționate
- Optimizați operațiunile de afaceri abordând domeniile de îngrijorare sau oportunități care au fost menționate de clienți
- Recunoașteți aspectele de afaceri care merg bine și recompensați clienții fericiți prin programe de loialitate și promovare

Modelul oferă o listă de cuvinte care au afectat decizia modelului de a atribui un anumit scor de sentiment sau un aspect de afaceri comentariilor de feedback.  

Folosim două **Modele de procesare a limbajului natural (NLP).** : primul atribuie fiecărui comentariu de feedback un scor de sentiment. Al doilea model asociază fiecare feedback cu toate aspectele de afaceri aplicabile. Modelele sunt instruite pe date publice din surse din rețelele sociale, comerțul cu amănuntul, restaurantele, produsele de consum și industriile auto.
  
Aspectele de afaceri predefinite pentru ca modelul să fie asociate cu datele de feedback includ:
- Gestionarea conturilor
- Finalizarea comenzii și plata
- Asistență pentru clienți
- Preluare din depozit
- Expedierea și recuperarea ambalajelor
- Precomandă
- Preț
- Confidențialitate și securitate
- Promoții și recompense
- Recepție și garanție
- Schimb retururi și anulare
- Acuratețea procesării
- Calitate site web/aplicație

> [!NOTE]
> În prezent, acceptăm doar analiza sentimentelor pentru feedback-ul clienților în limba engleză. Mai multe limbi vor fi acceptate în viitor. Dacă se încarcă feedback în alte limbi, modelul va returna în continuare rezultate. Cu toate acestea, aceste rezultate nu vor fi exacte.

## <a name="prerequisites"></a>Cerințe preliminare

- Macar [Permisiuni de colaborator](permissions.md)
- [Unificat](data-unification.md) date de feedback text. Vă recomandăm cu căldură [configurați-vă entitățile de date de feedback ca entități de activitate de tip semantic](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (Tipul de feedback).
- ID unificat de client (UCID) de la unificarea datelor pentru a potrivi înregistrările de date de feedback text cu un client individual.
- ID feedback
- Timp de feedback
- Text de feedback

Customer Insights poate procesa până la 10 milioane de înregistrări de feedback pentru un singur model. Modelul poate analiza comentariile de feedback până la 128 de cuvinte. Dacă un comentariu de feedback este mai lung, analiza ia în considerare doar primele 128 de cuvinte.

> [!NOTE]
> Poate fi configurată o singură entitate de feedback. Dacă există mai multe entități de feedback, combinați-le Power Query înainte de ingerarea datelor.

## <a name="configure-a-sentiment-analysis"></a>Configurați o analiză a sentimentelor

1. Mergi la **Inteligența** > **Previziuni**.

1. Pe **Crea** filă, selectați **Utilizați modelul** pe **Analiza sentimentelor clienților (previzualizare)** ţiglă.

1. Selectați **Începeți**.

1. **Nume** analiza și furnizați **Numele entității de ieșire pentru aspectul afacerii** si **Numele entității de ieșire a scorului de sentiment**.

1. Selectați **Următorul**.

1. Selectați **Adăugați date** pentru **Feedback-ul clienților**.

1. Selectați tipul de activitate semantică **Părere** care conține datele de feedback. Dacă activitatea nu a fost configurată, selectați **Aici** și creează-l.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Pasul de configurare pentru a selecta activitățile de feedback pentru analiza sentimentelor.":::

1. Selectați activitățile de utilizat pentru această analiză a sentimentelor, apoi selectați **Următorul**.

1. Mapați atributele din datele dvs. la atributele modelului. 

1. Selectați **Salvare**.

1. Selectați **Următorul**. The **Examinați și alergați** pasul arată un rezumat al configurației și oferă șansa de a face modificări înainte de a crea analiza.

1. Selectați **Editați | ×** pe oricare dintre pașii pentru a revizui și a face orice modificări.

1. Dacă sunteți mulțumit de selecțiile dvs., selectați **Salvați și rulați** pentru a începe rularea modelului. Selectați **Terminat**. The **Previziunile mele** se afișează fila în timp ce predicție este creată. Procesul poate dura câteva ore până la finalizare, în funcție de cantitatea de date utilizate în predicție.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Vedeți rezultatele analizei

1. Mergi la **Inteligența** > **Previziuni**.

1. În **Previziunile mele** fila, selectați predicție pe care doriți să-l vizualizați.

Există două file de rezultate.

### <a name="sumary-tab"></a>Fila Rezumat

Există patru secțiuni principale de date în pagina de rezultate.

- **Scorul mediu de sentiment** : scorurile de sentimente vă ajută să înțelegeți sentimentul general al tuturor clienților.
  - **Negativ** (-5 > 2)
  - **Neutru** (-1 > 1)
  - **Pozitiv** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Reprezentare vizuală a sentimentului general al clienților.":::

- **Distribuția clienților în funcție de scorul de sentiment** : Clienții sunt clasificați în grupuri negative, neutre și pozitive în funcție de scorurile lor de sentiment. Plasați cursorul peste barele din histogramă pentru a vedea numărul de clienți și scorul mediu de sentiment din fiecare grup. Aceste date vă pot ajuta [creați segmente de clienți](prediction-based-segment.md) pe baza scorurilor lor de sentimente.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Diagramă cu bare care arată sentimentul clienților din cele trei grupuri de sentimente.":::

- **Scorul mediu de sentiment în timp** : sentimentul clienților se poate schimba în timp. Oferim tendințe ale sentimentelor clienților dvs. pentru intervalul de timp al datelor dvs. Această vizualizare vă ajută să evaluați efectul promoțiilor sezoniere, al lansărilor de produse sau al altor intervenții limitate în timp asupra sentimentului clienților. Vedeți graficul selectând anul de interes din meniul drop-down.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Diagramă istoric cu scorul de sentiment de-a lungul timpului reprezentat ca o linie.":::

- **Sentiment asupra aspectelor de afaceri** : Sentimentul mediu pe diferite aspecte ale afacerii vă ajută să evaluați ce aspecte ale afacerii dvs. satisfac deja clienții sau necesită mai multă atenție. Înregistrările de feedback care nu se aliniază la niciunul dintre aspectele de afaceri acceptate sunt clasificate în categoria **Alte**. Sortați datele selectând orice coloană.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Lista aspectelor de afaceri cu valoarea sentimentului asociată și numărul de clienți care o menționează.":::

  Selectați numele unui aspect al afacerii pentru a vedea cum este identificat un aspect al afacerii de către model:

  - **Cuvinte influente** : Cuvinte de top care au influențat identificarea de către modelul AI a unui aspect de afaceri în feedback-ul clienților.
    **Arată cuvinte jignitoare** : Vă permite să includeți cuvinte jignitoare în listă din datele originale de feedback ale clienților. În mod implicit, este dezactivat.  Mascarea cuvintelor ofensatoare este alimentată de un model AI și este posibil să nu detecteze toate cuvintele ofensatoare. Dacă detectați un cuvânt jignitor care nu a fost filtrat conform așteptărilor, anunțați-ne.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Listă de cuvinte influente cu comutatorul pentru a afișa sau a ascunde cuvintele jignitoare.":::

  - **Mostre de feedback** : Înregistrările reale de feedback în datele dvs. Cuvintele sunt codificate pe culori în funcție de influența lor asupra identificării unui aspect de afaceri.

### <a name="influential-words-analysis-tab"></a>Fila de analiză a cuvintelor influente

Există trei secțiuni de informații suplimentare care explică modul în care funcționează modelul de sentiment.
  
- **Cuvinte de top care contribuie la sentimentul pozitiv** : Cuvinte de top care au influențat identificarea de către modelul AI a sentimentelor pozitive în feedback-ul clienților.  

- **Cuvinte de top care contribuie la sentimentul negativ** : Cuvinte de top care au influențat identificarea de către modelul AI a sentimentelor negative în feedback-ul clienților.

- **Mostre de feedback** : Înregistrări reale de feedback, una cu un sentiment negativ și una cu un sentiment pozitiv. Cuvintele din înregistrările de feedback sunt evidențiate în funcție de contribuția lor la scorul de sentiment atribuit. Cuvintele care contribuie la un scor pozitiv de sentiment sunt evidențiate cu verde. Cuvintele care contribuie la un scor negativ sunt evidențiate cu roșu.
   Selectați **Vezi mai mult** pentru a încărca mai multe mostre de feedback.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Exemple de analiză a sentimentelor privind feedback-ul clienților.":::

**Arată cuvinte jignitoare** : Vă permite să includeți cuvinte jignitoare în listă din datele originale de feedback ale clienților. În mod implicit, este dezactivat.  Mascarea cuvintelor ofensatoare este alimentată de un model AI și este posibil să nu detecteze toate cuvintele ofensatoare. Dacă detectați un cuvânt jignitor care nu a fost filtrat conform așteptărilor, anunțați-ne.

## <a name="act-on-analysis-results"></a>Acționați asupra rezultatelor analizei

Pentru a crea noi segmente de clienți din rezultatele analizei sentimentelor, selectați **Creați segmente** în partea de sus a paginii cu rezultatele modelului.

## <a name="potential-bias"></a>Prejudecată potențială

Ca și în cazul oricărei funcții care utilizează inteligența artificială predictivă, ar putea exista o potențială părtinire în datele pe care le utilizați pentru a prezice sentimentul clienților. De exemplu, dacă colectați feedback doar digital, este posibil să pierdeți feedback de la clienții care desfășoară în principal afaceri cu dvs. în persoană, ceea ce afectează rezultatul caracteristicii.

Deoarece această caracteristică folosește mijloace automate pentru a evalua datele și a face predicții pe baza acestor date, are, prin urmare, capacitatea de a fi utilizată ca metodă de profilare, așa cum termenul respectiv este definit de Regulamentul general privind protecția datelor („GDPR”). Utilizarea acestei funcții pentru prelucrarea datelor poate face obiectul GDPR sau altor legi sau reglementări. Sunteți responsabil pentru a vă asigura că folosiți Dynamics 365 Customer Insights, inclusiv analiza sentimentelor, respectă toate legile și reglementările aplicabile, inclusiv legile referitoare la confidențialitate, datele personale, datele biometrice, protecția datelor și confidențialitatea comunicațiilor.

[!INCLUDE [footer-include](includes/footer-banner.md)]

