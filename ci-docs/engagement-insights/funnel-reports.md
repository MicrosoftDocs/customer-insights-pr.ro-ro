---
title: Rapoarte de pâlnie
description: Cum să utilizați rapoartele de pâlnie pentru a înțelege modul în care publicul ia decizii.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 09/21/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: efb10f2664630a5851d9582ff09c378c01777b96
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558957"
---
# <a name="create-and-manage-funnel-reports"></a>Creați și gestionați rapoarte de pâlnie

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un raport pâlnie colectează informații despre pașii care apar în timpul unui călătoria clientului prin site-ul dvs. web sau aplicația mobilă. Vă ajută să înțelegeți cum progresează publicul printr-un proces și să identifice punctele de abandon. De exemplu, puteți utiliza un raport de pâlnie pentru a identifica căile pe care le iau clienții dvs. înainte de a face o achiziție. Un raport de pâlnie oferă date pentru a informa deciziile și a identifica domeniile de optimizare și îmbunătățiri ale procesului.

## <a name="create-a-funnel-report"></a>Creați un raport de pâlnie

Pentru a crea raportul de pâlnie, specificați pașii pe care doriți să îi includeți și activitatea pentru fiecare pas. O activitate este un [eveniment](glossary.md) care reprezintă comportamentul utilizatorului. Raportul de pâlnie afișează numărul de utilizatori care au finalizat fiecare pas definit. 

1. Accesați **Pâlnii** și selectați **+Pâlnie nouă** pentru a începe un raport de pâlnie.

1. În **Editor de pâlnie**, sub **Pași** selectați **+Adaugă pas.** 

1. Introduceți un nume în  **Titlul pasului**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Raport nou pâlnie.":::

1. Selectați o **Activitate**. O activitate înregistrează când un utilizator vizualizează o pagină (**Vizualizare** activitate) sau interacționează cu conținutul (**Acțiune** activitate).

1. Utilizați **Criteriile pașilor** pentru a specifica dimensiunea activității. [Dimensiunile](dimensions.md) sunt atribute care pot descrie, filtra sau grupa date.

1. Opțional, puteți configura pași de pâlnie cu mai multe condiții. Selectați **Adăugați o condiție** pentru a specifica mai multe dimensiuni într-un pas. Criteriile suplimentare trebuie să utilizeze același tip de activitate. Puteți alege dacă mai multe condiții sunt conectate cu un operator AND sau cu un operator OR.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Editor de pâlnie care arată configurația pasului cu pași cu mai multe condiții.":::

1. Selectați **Adăugare pas** până când parcurgeți toți pașii pe care îi doriți în raport.

1. Selectați **Salvați**, denumiți raportul și **Salvați** din nou. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Exemplu: raport de pâlnie al companiei Fourth Coffee

Următorul scenariu demonstrează o modalitate de utilizare a unui raport de pâlnie. Un analist al companiei Fourth Coffee dorește să înțeleagă predicția unei promoții recente asupra tarifelor de abonament. Analistul creează un raport de pâlnie pentru a identifica activitatea clientului. Raportul începe când clienții ajung pe pagina principală a companiei până când utilizează codul de promovare al abonamentului. Analistul creează un raport de pâlnie cu următorii pași:

Pasul 1: Clienții care ajung la pagina principală   
Pasul 2: Clienții care fac o achiziție   
Pasul 3: Clienții care folosesc codul promoțional pentru a obține o reducere de abonament   
Pasul 4: Înregistrarea la abonament   

:::image type="content" source="media/funnel-report-example.png" alt-text="exemplu de raport de pâlnie.":::
  
Această pâlnie vă permite să vedeți numărul de utilizatori care au folosit codul promoțional după o achiziție unică pentru a se înscrie la programul de abonamente.

### <a name="configure-advanced-settings"></a>Configurați setările complexe 

Rapoartele privind pâlnie vă permit să definiți o limită a timpului necesar pentru a finaliza o pâlnie. De exemplu, puteți seta timpul pentru finalizarea pâlniei la patru zile. Această setare va contoriza abonamentele înregistrate cu succes care au avut loc în termen de patru zile de la accesarea de către utilizator a paginii de pornire.

1. Accesați **Pâlnii** pentru a deschide **Biblioteca de pâlnii**.

1. Selectați un nume pentru a deschide raportul. 

1. În **Editor de pâlnie**, selectați **Setări avansate**. 

1. Setați Limita timpului de finalizare a pâlniei la **Pornit**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Editorul de pâlnie afișează setări și opțiuni avansate pentru a limita timpul pentru a finaliza o pâlnie.":::

1. Alegeți momentul în care pâlnia trebuie să fi fost finalizată în lista verticală **Setați limita la**.

1. Selectați **Salvare** pentru a vă aplica modificările.


## <a name="cross-channel-funnel-reports"></a>Rapoarte pâlnie pe mai multe canale 

Statisticile de implicare pot, de asemenea, să colecteze date comportamentale ale clienților pe aplicația dvs. mobilă. Odată ce ați instrumentat aplicația mobilă cu ajutorul detaliilor de implicare [Android SDK](get-started-android.md) sau [SDK iOS](get-started-ios.md), puteți crea rapoarte de canal pe mai multe canale. 

### <a name="create-a-cross-channel-funnel-report"></a>Creați un raport pâlnie pe mai multe canale 

1. Urmați pașii pentru a [crea un raport pâlnie](#create-a-funnel-report).    

1. Pentru a urmări modul în care clienții dvs. interacționează cu marca dvs. atât pe site-ul dvs. web, cât și în aplicația mobilă sau pe mai multe site-uri web, utilizați comutatorul spațiului de lucru pentru a crea pași de canal cu date din alte spații de lucru. În **Editor de pâlnie**, sub **Pași** selectați din ce spațiu de lucru ar trebui să provină datele pentru pasul pâlniei dvs.

## <a name="manage-funnel-reports"></a>Gestionați rapoartele de canal

Puteți examina rapoartele de pâlnie pentru a analiza datele, pentru a urmări performanța și pentru a aduna informații.

> [!NOTE]
> - Rapoartele de pâlnie Detalii despre angajamente acceptă în prezent scenarii în care toți utilizatorii din pâlnie sunt anonimi sau toți utilizatorii sunt autentificați. 
> - Datele istorice din rapoartele de pâlnie sunt disponibile pentru ultimele 30 de zile.

### <a name="view-funnel-reports"></a>Vizualizați rapoarte de pâlnie

1. Accesați **Pâlnii** pentru a deschide **Biblioteca de pâlnii**.
1. Selectați un nume pentru a deschide raportul.    

### <a name="see-the-data-collected-for-a-report"></a>Consultați datele colectate pentru un raport   

Pentru a vedea informații despre o fază

- Arată un pas în raport.

:::image type="content" source="media/funnel-step-data.png" alt-text="date de pâlnie.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Modificați intervalul de date pentru raportul de pâlnie

1. Accesați **Pâlnii** pentru a deschide **Biblioteca de pâlnii**.

1. Selectați un nume pentru a deschide raportul.

1. Deschideți **interval de timp** și selectați o nouă perioadă de timp din listă sau **Interval de date fix** pentru a specifica un interval de date.

## <a name="edit-or-delete-funnel-reports"></a>Editați sau ștergeți rapoartele de pâlnie

Puteți schimba numele unui raport de pâlnie, îl puteți șterge sau modifica pașii din raport.

### <a name="rename-or-delete-a-funnel-report"></a>Redenumiți sau ștergeți un raport de pâlnie

1. Accesați **Pâlnii** pentru a deschide **Biblioteca de pâlnii**. 

1. Selectați **Mai mult** lângă raportul pe care doriți să-l modificați și alegeți **Editați numele** sau **Ștergeți**.

### <a name="edit-a-funnel-step"></a>Editați un pas de pâlnie  

1. Accesați **Pâlnii** pentru a deschide **Biblioteca de pâlnii**. 

1. Selectați un nume pentru a deschide raportul.

1. Selectați pasul pe care doriți să-l editați.

1. Selectați **Editare**.

1. În **Editor de pâlnie** actualizați informațiile pe care doriți să le modificați.  

1. Selectați **Salvare**.

### <a name="reorder-a-funnel-step"></a>Reordonați un pas de pâlnie

1. Accesați **Pâlnii** pentru a deschide **Biblioteca de pâlnii**. 

1. Selectați un nume pentru a deschide raportul.

1. Selectați pasul pe care doriți să-l reordonați.

1. Selectați **Mutați** și apoi **Sus**, **Jos**, **În sus** sau **În jos**, pentru a muta pasul.

### <a name="delete-a-funnel-step"></a>Ștergeți un pas de pâlnie

1. Accesați **Pâlnii** pentru a deschide **Biblioteca de pâlnii**. 

1. Selectați un nume pentru a deschide raportul.

1. Selectați pașii pe care doriți să-i eliminați și selectați **Ștergeți**.

## <a name="funnel-insights"></a>Informații despre pâlnie 

Statisticile despre implicare oferă acum informații despre canal pentru clienți. Utilizați informații despre canal pentru a obține o perspectivă mai profundă asupra comportamentului clienților cu privire la pașii din raportul dvs. privind canalele. Când creați și salvați un nou raport de canal, statistici despre canal sunt generate automat pentru raportul dvs. 

:::image type="content" source="media/funnel-insights.png" alt-text="Detalii despre pâlnie.":::

> [!NOTE]
> Detaliile de pâlnie pot fi generate numai pentru pașii canalului care **nu** includ dimensiuni personalizate. Pentru a genera detalii de pâlnie pentru toți pașii din pâlnia dvs., utilizați dimensiuni de livrare pentru statistici de implicare pentru a crea pașii pâlniei. 

Puteți vizualiza statistici privind canalele din următoarele categorii, atât la nivel principal, cât și la nivel de pas: 

 - Rata de conversie
 -    Rata conversiei dintre Checkout și Buy este de 22%.
 - Timp de tranziție 
 -    Timpul mediu de tranziție dintre Cart și Checkout este de 23 minute. 
 - Timpul de finalizare 
 -    Timpul mediu necesar clienților pentru a finaliza pâlnia este de 47 de minute. 

Utilizați aceste informații pentru a explora mai adânc comportamentul clienților și pentru a înțelege mai bine punctele de renunțare și conversiile pentru raportul dvs. de canal. 

Pentru a compara statistici în diferiți pași, selectați **A se vedea defalcarea pasului** sau **Comparați cu alți pași** din cardurile de informații. Acestea vor afișa un grafic cu bare comparând valori pentru fiecare pas al pâlniei. 

Statisticile despre pâlnie sunt recalculate la fiecare 24 de ore sau când **Salvați** raportul dvs. de pâlnie. 

> [!NOTE]
> Pentru a vizualiza statistici pentru canalul dvs., trebuie să salvați raportul de fiecare dată când efectuați modificări. 

