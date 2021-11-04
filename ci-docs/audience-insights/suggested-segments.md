---
title: Segmente sugerate alimentate de învățare programată
description: Lăsați învățare programată să vă ajute să găsiți segmente noi și interesante pe baza atributelor clienților.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 44e46bb650b6f090afcab3bc940d03a304e9c375
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673198"
---
# <a name="suggested-segments-preview"></a>Segmente sugerate (previzualizare)

Descoperiți segmente interesante ale clienților dvs. cu ajutorul unui model AI. Această caracteristică alimentată de învățarea programată sugerează segmente bazate pe măsuri sau atribute ale clientului. Vă poate ajuta să vă îmbunătățiți indicatorii de performanță sau să înțelegeți mai bine influența atributelor în contextul altor atribute. 

> [!NOTE]
> Funcția de segmente sugerate utilizează mijloace automate pentru a evalua datele și a face predicții pe baza acestor date și, prin urmare, are capacitatea de a fi utilizată ca metodă de profilare, deoarece acest termen este definit de Regulamentul general privind protecția datelor („GDPR”). Utilizarea acestei funcții pentru prelucrarea datelor poate face obiectul GDPR sau altor legi sau reglementări. Sunteți responsabil pentru a vă asigura că utilizarea de către dvs. a Dynamics 365 Customer Insights, inclusiv această caracteristică, respectă toate legile și reglementările aplicabile, inclusiv legile legate de confidențialitate, date cu caracter personal, date biometrice, protecția datelor și confidențialitatea comunicărilor.

:::image type="content" source="media/suggested-segments.png" alt-text="Pagină cu segmente sugerate care afișează detaliile unei sugestii într-un panou lateral.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Segmente sugerate pentru a vă îmbunătăți indicatorii de performanță

Ca utilizator al statisticilor privind publicul, probabil că aveți o serie de [măsuri create](measures.md) care vă ajută să vă urmăriți indicatorii cheie de performanță (KPIs). Este important să înțelegeți cum anumite atribute influențează acest KPI pentru a crea segmente și pentru a rula o campanie foarte vizată.   
De exemplu, urmăriți o măsură numită *TotalSpendPerCustomer*. Ca afacere, ați dori să vedeți acest număr crescând. Alegând o măsură ca atribut principal, vă permite să selectați atributele pe care doriți să le evaluați pentru influență. Sa spunem *nivelul de membru*, *perioada de membru* și *ocupaţie*. Customer Insights vă poate sugera apoi un segment care vă spune cine este cea mai mare influență a măsurii respective. De exemplu, *Contabili* care sunt membri *Aur* și care au fost alături de afacerea dvs. de *cel puțin cinci ani* sunt cel mai mare factor de influență al *TotalSpendPerCustomer*. Veți obține o dimensiune estimată a segmentului pentru fiecare sugestie. Puteți utiliza aceste informații pentru a crea campanii pentru publicul vizat.

## <a name="understand-what-influences-a-customer-attribute"></a>Înțelegeți ce influențează atributul unui client

Puteți alege un atribut client în loc de o măsură ca atribut principal. Pe baza alegerii dvs. de a influența atributele, modelul AI creează o serie de sugestii care arată modul în care atributele selectate influențează atributul principal.   
De exemplu, alegeți *Membru Recompense (Da/Nu)* ca atribut principal. *Vechime*, *Ocupaţie*, și *Numărul de tichete de asistență* sunt stabilite ca alte atribute care influențează. Modelul AI ar putea sugera că segmentele care indică în mare parte profesioniștii IT cu un mandat de peste doi ani sunt membri recompensați. O altă sugestie ar putea evidenția faptul că contabilii cu un mandat de peste un an și mai puțin de trei bilete de asistență sunt membri recompensați. 

## <a name="artificial-intelligence-usage"></a>Utilizarea inteligenței artificiale

Folosind atributul principal și atributele de influențare, un algoritm al arborelui decizional sugerează segmente interesante. Sugestiile se bazează pe reguli sau modele care au fost preluate de algoritmul AI. Doar segmentele care diferă semnificativ de populația medie sunt prezentate ca sugestii. Comparația cu populația medie se bazează pe măsura selectată sau atributul principal.

### <a name="responsible-ai"></a>AI responsabil

Segmentele sugerate vă permit să selectați atribute pentru a crea segmente noi și pentru a procesa datele selectate. Atunci când alegeți atribute, inclusiv atribute sensibile precum rasa, orientarea sexuală sau sexul, trebuie să vă asigurați că puteți și ar trebui să procesați aceste date. Sunteți responsabil să respectați orice legi aplicabile organizației dvs. și să respectați principiile și politicile de confidențialitate ale organizației dvs.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Rezultate diferite pentru atributele primare cu valori categorice și numerice

Sugestiile de segmente sunt diferite dacă alegeți un atribut numeric sau un atribut categoric ca atribut principal. Valorile dintr-un atribut categoric conțin două sau mai multe categorii sau tipuri. Un atribut numeric conține date cantitative și are un sentiment de măsurare asociat cu acesta.

Cu un atribut numeric precum *venit anual* sau *perioada de membru* ca atribut principal, sistemul sugerează segmente care au o valoare medie mai mare sau mai mică a atributului numeric în comparație cu toți clienții.

Un atribut categoric precum *satisfacția clientului* deoarece atributul principal are ca rezultat segmente sugerate care au un procent mai mare sau mai mic de clienți care aparțin unei anumite categorii în comparație cu procentul tuturor clienților care aparțin aceleiași categorii. De exemplu, *satisfacția clientului* este ales ca atribut principal și constă din trei categorii (*Scăzut*, *Mediu* și *Înalt*). Pentru fiecare categorie, vor fi sugerate segmente care au un procent mai mare sau mai mic de clienți aparținând respectivei categorii, în comparație cu proporția tuturor clienților din aceeași categorie. Dacă 22% dintre toți clienții au un nivel de satisfacție *Înalt*, atunci numai segmentele care au o proporție mai mare sau mai mică de clienți cu un nivel de satisfacție *Înalt* în comparație cu 22% vor fi sugerate pentru acea categorie. În mod similar, vor fi sugerate segmente pentru fiecare dintre celelalte categorii (*Scăzut* și *Mediu*) dacă sunt semnificative statistic.

> [!NOTE]
> În prezent, acceptăm numai atribute categorice primare care au până la 10 categorii. Dacă doriți să vedeți sugestii de segmente bazate pe un atribut principal cu mai mult de 10 categorii, vă recomandăm să grupați unele dintre categorii pentru a reduce numărul de categorii la 10 sau mai puțin. Această limitare se aplică numai atributelor principale. Pentru influențarea atributelor categorice, în prezent acceptăm maximum 100 de categorii.

## <a name="generate-suggested-segments"></a>Generați segmente sugerate

1. Mergeți la **Segmente**.

1. Selectați fila **Sugestii (previzualizare)**.

1. Selectați **Obțineți noi sugestii** pentru a începe experiența ghidată.

1. Alegeți o măsură sau un atribut de client drept atributul primar și selectați **Următorul**.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Alegerea atributului principal pentru sugestii pe segmentele sugerate.":::

1. Selectați atributele de influență și selectați **Salvați**.
   
   > [!TIP]
   > Selectarea atributelor de influențare multiple îmbunătățește șansele de a evalua modul în care acestea influențează atributul principal. Nu includeți atribute care nu influențează atributul principal. De exemplu, dacă toți clienții dvs. provin dintr-o anumită țară, nu includeți atributul *țară* deoarece nu va avea niciun impact asupra rezultatului.

1. În funcție de numărul de profiluri ale clienților și de atributele selectate, procesarea atributelor selectate poate dura câteva minute. 

## <a name="view-details-of-a-suggested-segment"></a>Vizualizați detaliile unui segment sugerat

Odată ce modelul AI a generat sugestiile, le veți găsi în listă **Segmente** > **Sugestii (previzualizare)**.
 
Selectați un segment sugerat pentru a revizui detaliile sugestiei respective. De asemenea, puteți revizui valorile atributelor sau regulile pe care modelul AI le-a învățat pentru a sugera segmentul selectat.

## <a name="save-a-suggestion-as-a-segment"></a>Salvați o sugestie ca segment

1. Accesați **Segmente** > **Sugestii (previzualizare)**.

1. Selectați segmentul pe care doriți să-l salvați. 

1. În panoul lateral, selectați **Salvați ca segment**. 

1. După salvarea segmentului, acesta se va afișa în lista de segmente de pe fila **Toate segmentele**. Acum poate fi [reîmprospătat, editat sau șters ca orice alt segment](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Reîmprospătați sau editați un set de sugestii

1. Accesați **Segmente** > **Sugestii (previzualizare)**.

1. Selectați **Reîmprospătați sugestiile** pentru a reîmprospăta sugestiile păstrând în același timp atributele configurate. Sau selectați **Editați atributele** pentru a modifica atributele configurate. Sistemul va rula din nou modelul AI, va genera sugestii de segmente pe baza celor mai recente date și va înlocui sugestiile actuale.

## <a name="limitations"></a>Limitări

1. Nepotrivire estimată a dimensiunii segmentului: dacă alegeți un atribut principal care conține valori goale, acesta poate afecta dimensiunea estimată a segmentului în sugestiile de segment. La salvarea unui astfel de segment, dimensiunea reală a segmentului poate fi diferită de estimarea inițială.
 
2. Atributele primare de tip boolean nu funcționează: în prezent, acceptăm doar tipurile de date șir și numerice ca atribut principal.

3. Segmentele sugerate nu sunt suficient de distincte: rețineți că atributele selectate și distribuția valorilor acestor atribute influențează rezultatele. Puteți schimba atributele de influență sau chiar atributul principal pentru a obține rezultate diferite.



[!INCLUDE[footer-include](../includes/footer-banner.md)]