---
title: Segmente sugerate pe baza măsurilor (previzualizare)
description: Lăsați învățare programată să vă ajute să găsiți segmente noi și interesante pe baza atributelor clienților.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170972"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Segmente sugerate pe baza măsurilor (previzualizare)

Descoperiți segmente interesante ale clienților dvs. cu ajutorul unui model AI. Această caracteristică alimentată de învățarea programată sugerează segmente bazate pe măsuri sau atribute ale clientului. Vă poate ajuta să vă îmbunătățiți indicatorii cheie de performanță (KPI) sau să înțelegeți mai bine influența atributelor în contextul altor atribute.

> [!NOTE]
> Funcția de segmente sugerate folosește mijloace automate pentru a evalua datele și a face predicții pe baza acestor date. Prin urmare, are capacitatea de a fi utilizat ca metodă de profilare, așa cum termenul respectiv este definit de Regulamentul general privind protecția datelor („GDPR”). Utilizarea acestei funcții pentru prelucrarea datelor poate face obiectul GDPR sau altor legi sau reglementări. Sunteți responsabil pentru a vă asigura că utilizarea de către dvs. a Dynamics 365 Customer Insights, inclusiv această caracteristică, respectă toate legile și reglementările aplicabile, inclusiv legile legate de confidențialitate, date cu caracter personal, date biometrice, protecția datelor și confidențialitatea comunicărilor.

:::image type="content" source="media/suggested-segments.png" alt-text="Pagină cu segmente sugerate care afișează detaliile unei sugestii într-un panou lateral.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Segmente sugerate pentru a vă îmbunătăți indicatorii de performanță

Dacă utilizați [măsuri create](measures.md) pentru a vă ajuta să urmăriți KPI-urile, creați segmente pentru a vedea influențele asupra KPI-ului. Puteți utiliza aceste informații pentru a derula o campanie foarte bine direcționată.

De exemplu, urmăriți o măsură numită *TotalSpendPerCustomer*. Ca afacere, ați dori să vedeți acest număr crescând. Alegând o măsură ca atribut principal, selectați atributele pe care doriți să le evaluați pentru influență. Sa spunem *nivelul de membru*, *perioada de membru* și *ocupaţie*. Customer Insights vă poate sugera apoi un segment care vă spune cine este cea mai mare influență a măsurii respective. De exemplu, *Contabili* care sunt membri *Aur* și care au fost alături de afacerea dvs. de *cel puțin cinci ani* sunt cel mai mare factor de influență al *TotalSpendPerCustomer*. Veți obține o dimensiune estimată a segmentului pentru fiecare sugestie. Puteți utiliza aceste informații pentru a crea campanii pentru publicul vizat.

## <a name="understand-what-influences-a-customer-attribute"></a>Înțelegeți ce influențează atributul unui client

Puteți alege un atribut client în loc de o măsură ca atribut principal. Pe baza alegerii dvs. de a influența atributele, modelul AI creează o serie de sugestii care arată modul în care atributele selectate influențează atributul principal.

De exemplu, alegeți *Membru Recompense (Da/Nu)* ca atribut principal. *Vechime*, *Ocupaţie*, și *Numărul de tichete de asistență* sunt stabilite ca alte atribute care influențează. Modelul AI ar putea sugera că segmentele care indică în mare parte profesioniștii IT cu un mandat de peste doi ani sunt membri recompensați. O altă sugestie ar putea evidenția faptul că contabilii cu un mandat de peste un an și mai puțin de trei bilete de asistență sunt membri recompensați.

## <a name="artificial-intelligence-usage"></a>Utilizarea inteligenței artificiale

Folosind atributul principal și atributele de influențare, un algoritm al arborelui decizional sugerează segmente interesante. Sugestiile se bazează pe reguli sau modele care au fost preluate de algoritmul AI. Doar segmentele care diferă semnificativ de populația medie sunt prezentate ca sugestii. Comparația cu populația medie se bazează pe măsura selectată sau atributul principal.

### <a name="responsible-ai"></a>AI responsabil

Cu segmentele sugerate, selectați atribute pentru a crea segmente noi și pentru a procesa datele pe care le selectați. Atunci când alegeți atribute, inclusiv atribute sensibile precum rasa, orientarea sexuală sau sexul, trebuie să vă asigurați că puteți și ar trebui să procesați aceste date. Sunteți responsabil să respectați orice legi aplicabile organizației dvs. și să respectați principiile și politicile de confidențialitate ale organizației dvs.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Rezultate diferite pentru atributele primare cu valori categorice și numerice

Sugestiile de segmente sunt diferite dacă alegeți un atribut numeric sau un atribut categoric ca atribut principal. Valorile dintr-un atribut categoric conțin două sau mai multe categorii sau tipuri. Un atribut numeric conține date cantitative și are un sentiment de măsurare asociat cu acesta.

Cu un atribut numeric precum *venit anual* sau *perioada de membru* ca atribut principal, sistemul sugerează segmente care au o valoare medie mai mare sau mai mică a atributului numeric în comparație cu toți clienții.

Un atribut categoric precum *satisfacția clientului* deoarece atributul principal are ca rezultat segmente sugerate care au un procent mai mare sau mai mic de clienți care aparțin unei anumite categorii în comparație cu procentul tuturor clienților care aparțin aceleiași categorii. De exemplu, *satisfacția clientului* este ales ca atribut principal și constă din trei categorii (*Scăzut*, *Mediu* și *Înalt*). Pentru fiecare categorie, vor fi sugerate segmente care au un procent mai mare sau mai mic de clienți aparținând acelei categorii în comparație cu proporția tuturor clienților din aceeași categorie. Dacă 22% dintre toți clienții au un nivel de satisfacție *Înalt*, atunci numai segmentele care au o proporție mai mare sau mai mică de clienți cu un nivel de satisfacție *Înalt* în comparație cu 22% vor fi sugerate pentru acea categorie. În mod similar, vor fi sugerate segmente pentru fiecare dintre celelalte categorii (*Scăzut* și *Mediu*) dacă sunt semnificative statistic.

> [!NOTE]
> În prezent, acceptăm numai atribute categorice primare care au până la 10 categorii. Dacă doriți să vedeți sugestii de segmente bazate pe un atribut principal cu mai mult de 10 categorii, vă recomandăm să grupați unele dintre categorii pentru a reduce numărul de categorii la 10 sau mai puțin. Această limitare se aplică numai atributelor principale. Pentru influențarea atributelor categorice, în prezent acceptăm maximum 100 de categorii.

## <a name="generate-suggested-segments"></a>Generați segmente sugerate

1. Mergi la **Segmente** și selectați **Sugestii (previzualizare)** fila.

1. Selectați **Găsiți noi sugestii** și alegeți **Îmbunătățiți o măsură/metrică**. Selectați **Start**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Alegerea măsurii de îmbunătățire pe segmentele sugerate.":::

1. Alegeți un atribut sau o măsură de client ca atribut principal și selectați **Următorul**.

1. Selectați atributele de influență și selectați **Alerga**.

   > [!TIP]
   > Selectarea atributelor de influențare multiple îmbunătățește șansele de a evalua modul în care acestea influențează atributul principal. Nu includeți atribute care nu au nicio influență asupra atributului principal. De exemplu, dacă toți clienții dvs. provin dintr-o anumită țară, nu includeți atributul *țară* deoarece nu va avea niciun impact asupra rezultatului.

În funcție de numărul de profiluri ale clienților și de atributele selectate, procesarea atributelor selectate poate dura câteva minute.

## <a name="manage-suggested-segments"></a>Gestionați segmentele sugerate

Mergi la **Segmente** și selectați **Sugestii (previzualizare)** fila. În **Sugestii de segmente bazate pe atribute** secțiune, selectați un segment sugerat pentru a vedea acțiunile disponibile.

- **Vedere** detaliile de segment sugerate și valorile atributelor sau regulile pe care modelul AI le-a învățat.
- **Salvați ca segment** sugestia ca segment. Se afișează pe **Toate segmentele** filă și poate fi [reîmprospătat, editat sau șters](segments.md).
- **Editați atributele** și modificați atributele configurate care vor înlocui sugestiile curente.
- **Actualizează sugestiile** pentru a reîmprospăta sugestiile păstrând în același timp atributele configurate.

## <a name="limitations"></a>Limitări

1. Nepotrivire estimată a dimensiunii segmentului: dacă alegeți un atribut principal care conține valori goale, acesta poate afecta dimensiunea estimată a segmentului în sugestiile de segment. La salvarea unui astfel de segment, dimensiunea reală a segmentului poate fi diferită de estimarea inițială.

2. Atributele primare de tip boolean nu funcționează: în prezent, acceptăm doar tipurile de date șir și numerice ca atribut principal.

3. Segmentele sugerate nu sunt suficient de distincte: rețineți că atributele selectate și distribuția valorilor acestor atribute influențează rezultatele. Puteți schimba atributele de influență sau chiar atributul principal pentru a obține rezultate diferite.

[!INCLUDE [footer-include](includes/footer-banner.md)]