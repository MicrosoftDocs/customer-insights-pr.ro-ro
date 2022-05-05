---
title: Creați segmente cu generatorul de segmente
description: Creați segmente de clienți pentru a îi grupa pe baza diferitelor atribute.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: c8e9e4976ade36c1c3c4f688a667b329bfde6e3e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643555"
---
# <a name="create-segments"></a>Creare segmente

Definiți filtre complexe pe baza entității client unificate și a entităților conexe. Fiecare segment, după procesare, creează un set de înregistrări ale clienților pe care le puteți exporta și pe care puteți acționa. Segmentele sunt gestionate pe pagina **Segmente**. Puteți [crea segmente noi](#create-a-new-segment) utilizând creatorul de segmente sau [creați segmente rapide](#quick-segments) din alte zone ale aplicații.

> [!TIP]
> - Segmentele rapide sunt acceptate numai în medii pentru **clienți individuali**.
> - Segmente bazate pe **clienți individuali** includ automat informațiile de contact disponibile pentru membrii segmentului. În medii pentru **conturi de business**, segmentele se bazează pe conturi (companii sau filiale). Pentru a include informații de contact într-un segment, utilizați funcționalitatea **Atributele proiectului** în generatorul de segmente. Asigurați-vă că sursele de date de contact sunt [mapate semantic la ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping) pentru entitate.

## <a name="segment-builder"></a>Constructor de segmente

Următoarea imagine ilustrează diferitele aspecte ale constructorului de segmente. Afișează un segment care are ca rezultat un grup de clienți. Clienții au comandat bunuri într-un anumit interval de timp și au adunat puncte de recompensă sau au cheltuit o anumită sumă de bani.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elemente ale constructorului de segmente." lightbox="media/segment-builder-overview.png":::

1. Organizați-vă segmentul cu reguli și subreguli. Fiecare regulă sau subregulă constă din condiții. Combinați condițiile cu operatorii logici

1. Alegeți [calea relației](relationships.md) între entități care se aplică unei reguli. Calea relației determină ce atribute pot fi utilizate într-o condiție.

1. Gestionați regulile și subregulile. Schimbați poziția unei reguli sau ștergeți-o.

1. Adăugați condiții și construiți nivelul potrivit de cuibărire folosind subreguli.

1. Aplicați operațiile de setare la regulile conectate.

1. Utilizați panoul de atribute pentru a adăuga atribute de entitate disponibile sau pentru a crea condiții pe baza atributelor. Panoul afișează lista entităților și atributelor, bazate pe calea relației selectate, care sunt disponibile pentru regula selectată.

1. Adăugați condiții bazate pe atribute regulilor și subregulilor existente sau adăugați-o la o nouă regulă.

1. Anulați și refaceți modificările în timp ce construiți segmentul.

Exemplul de mai sus ilustrează capacitatea de segmentare. Am definit un segment pentru clienții care au cumpărat cel puțin $500 de bunuri online *și* au un interes în dezvoltarea de software.

## <a name="create-a-new-segment"></a>Crearea unui nou segment

Sunt mai multe moduri de a crea un segment nou. Această secțiune descrie cum să-ți construiești propriul segment de la zero. De asemenea, puteți să creați un *segment rapid* pe baza entităților existente sau să valorificați modelele de învățare programată pentru a obține *segmente sugerate*. Pentru informații suplimentare, accesați [Prezentare generală segmente](segments.md).

Când creați un segment, puteți salva o schiță. În etapa de schiță, un segment este salvat ca segment inactiv. Când finalizați configurația segmentului, rulați-o pentru a activa segmentul. De asemenea, puteți **Activa** un segment din pagina **Toate segmentele**.

1. Salt la pagina **Segmente**.

1. Selectați **Nou** > **Construiește-ți propriul**.

1. În pagina generator de segmente, definiți sau compuneți reguli. O regulă constă din una sau mai multe condiții care definesc un set de clienți.

1. În **Regula 1** secțiunea, alegeți un atribut al unei entități după care doriți să filtrați clienții. Există două moduri de a alege atribute:
   - Consultați lista entităților și atributelor disponibile în panoul **Adăugați la regulă** și selectați pictograma **+** pictogramă de lângă atributul de adăugat. Alegeți dacă doriți să adăugați atributul la o regulă existentă sau utilizați-l pentru a crea o nouă regulă.
   - Tastați numele atributului în secțiunea regulii pentru a vedea sugestiile potrivite.

1. Alegeți operatorii pentru a specifica valorile potrivite ale condiției. Atributul poate avea unul dintre cele patru tipuri de date ca valoare: numeric, șir, dată sau boolean. În funcție de tipul de date al atributului, sunt disponibili diferiți operatori pentru a specifica condiția. Pentru segmente cu conturi de afaceri, sunt disponibili doi operatori speciali pentru a include ierarhii potențiale între conturile ingerate. Utilizați operatorii *copil al* și *parinte a* pentru a include conturi conexe.

1. Selectați **Adăugați o condiție** pentru a adăuga mai multe condiții unei reguli. Pentru a crea o regulă sub regula curentă, selectați **Adăugați o subregulă**.

1. Dacă o regulă folosește alte entități decât entitatea *Client*, trebuie să setați calea relației. Calea relației este necesară pentru a informa sistemul despre pe care relații doriți să le accesați în entitatea unificată de client. Selectați **Setați calea relației** să mapeze entitatea selectată la entitatea client unificată. Dacă există o singură cale de relație posibilă, sistemul o va selecta automat. Căile de relație diferite pot produce rezultate diferite. Fiecare regulă poate avea propria cale de relaționare.

   :::image type="content" source="media/relationship-path.png" alt-text="Calea relației potențiale la crearea unei reguli bazate pe o entitate mapată la entitatea client unificată.":::

   De exemplu, entitatea *eCommerce_eCommercePurchases* în captura de ecran are patru opțiuni de a mapa la entitatea *Client*:
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Client
   - eCommerce_eCommercePurchases > Client
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Client
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Client Când alegem ultima opțiune putem include atribute de la toate entitățile listate în condițiile regulii. Probabil vom obține mai puține rezultate, deoarece înregistrările clientului potrivite trebuie să facă parte din toate entitățile. În acest exemplu, au achiziționat bunuri prin e-commerce(*eCommerce_eCommercePurchases*) la un punct de vânzare(*POS_posPurchases*) și participă în programul nostru de loialitate (*loyaltyScheme_loyCustomers*). Atunci când alegem a doua opțiune, putem alege doar atribute din entitatea *eCommerce_eCommercePurchases* și *Client*. Acest lucru duce probabil la obținerea mai multor profiluri ale clienților.

1. Dacă aveți mai multe condiții într-o regulă, puteți alege ce operator logic le conectează.  
   - Operator **ȘI**: trebuie îndeplinite toate condițiile pentru a include o înregistrare în segment. Această opțiune este cea mai utilă atunci când definiți condiții pentru diferite entități.
   - Operator **SAU**: trebuie îndeplinite oricare dintre condiții pentru a include o înregistrare în segment. Această opțiune este cea mai utilă atunci când definiți condiții multiple pentru aceeași entitate.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Rregulă cu două condiții ȘI.":::

   Atunci când utilizați operatorul SAU, toate condițiile trebuie să se bazeze pe entități incluse în calea relației.

   - Puteți crea mai multe reguli pentru a crea seturi diferite de înregistrări ale clienților. Puteți combina mai multe grupuri pentru a include clienții necesari pentru cazul dvs. de afaceri. Pentru a crea o nouă regulă, selectați **Adăugați regulă**. Mai exact, dacă nu puteți include o entitate într-o regulă din cauza traseului de relație specificat, trebuie să creați o nouă regulă pentru a alege atributele din aceasta.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Adăugați o nouă regulă la un segment și alegeți operatorul setat.":::

   - Selectați unul dintre operatorii de mulțimi: **Reuniune**, **Intersecție** sau **Cu excepția**.

      - **Uniune** unește cele două grupuri.
      - **Intersectare** suprapune cele două grupuri. Numai datele ce *sunt comune* pentru ambele grupuri vor rămâne în grupul unificat.
      - **Excepție** combină cele două grupuri. Se păstrează numai datele din grupul A care *nu sunt comune* cu datele din grupa B.

1. În mod implicit, segmentele generează entitatea de ieșire care conține toate atributele profilurilor clienților care se potrivesc cu filtrele definite. Dacă un segment se bazează pe alte entități decât entitatea *Client*, puteți adăuga mai multe atribute de la aceste entități la entitatea de ieșire. Selectați **Atributele proiectului** pentru a alege atributele care vor fi anexate entității de ieșire.

   > [!IMPORTANT]
   > Pentru segmentele bazate pe conturi comerciale, detaliile unuia sau mai multor contacte ale fiecărui cont din entitatea *ContactProfile* trebuie incluse în segment pentru a permite activarea sau exportarea segmentului respectiv către destinații care necesită informații de contact. Pentru mai multe informații despre entitatea *ContactProfile*, vedeți [Mapări semantice](semantic-mappings.md).
   > Un exemplu de ieșire pentru un segment bazat pe conturi de business cu atributele proiectate ale persoanelor de contact ar putea arăta astfel:
   >
   > |ID  |Nume cont  |Venituri  |Nume persoană de contact  | Rol persoană de contact|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100K | [Abbie Moss, Ruth Soto]  | [CEO, manager achiziții]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Exemplu de atribute proiectate selectate în panoul lateral pentru a fi adăugate la entitatea de ieșire.":::
  
   De exemplu: un segment se bazează pe o entitate care conține date de achiziție, care sunt legate de entitatea *Client*. Segmentul caută toți clienții din Spania care au achiziționat bunuri în anul curent. Puteți alege să atașați atribute precum prețul mărfurilor sau data achiziției la toate înregistrările clientului corespunzătoare din entitatea de ieșire. Aceste informații ar putea fi utile pentru a analiza corelațiile sezoniere cu cheltuielile totale.

   > [!NOTE]
   > - **Atributele proiectului** funcționează numai pentru entitățile care au o relație de la unu la mai mulți cu entitatea client. De exemplu, un client poate avea mai multe abonamente.
   > - Dacă atributul pe care doriți să îl proiectați este la mai mult de un salt de entitatea *Client*, așa cum este definită de relație, acel atribut ar trebui să fie utilizat în fiecare regulă a interogării de segment pe care o construiți.
   > - Dacă atributul pe care doriți să îl proiectați este la doar un salt de entitatea *Client*, acel atribut nu trebuie să fie prezent în fiecare regulă a interogării de segment pe care o construiți.
   > - **Atributele proiectate** sunt luate în calcul atunci când se utilizează operatori de mulțimi.

1. Selectați **Editează detaliile** lângă segmentul fără titlu. Furnizați un nume pentru segmentul dvs. și actualizați **Numele entității de ieșire** sugerat pentru segment. Opțional, adăugați o descriere și [Etichete](work-with-tags-columns.md#manage-tags) la segment.

   :::image type="content" source="media/segments_edit_details.png" alt-text="caseta de dialog Editare detalii.":::

1. Selectați **Rulare** pentru a salva segmentul, activați-l și începeți să procesați segmentul pe baza tuturor regulilor și condițiilor. În caz contrar, va fi salvat ca segment inactiv.

1. Selectați **Înapoi la segmente** pentru a reveni la pagina **Segmente**.

1. În mod implicit, segmentul este creat drept segment dinamic. Asta înseamnă că segmentul este reîmprospătat în timpul reîmprospătărilor sistemului. Pentru a [opri reîmprospătarea automată](segments.md#manage-existing-segments), selectați segmentul și alegeți opțiunea **Faceți static**. Segmentele statice pot fi [reîmprospătate manual](segments.md#refresh-segments) oricând.

> [!TIP]
> - Generatorul de segmente nu va sugera valori valide de la entități atunci când setează operatorii pentru condiții. Puteți accesa **Date** > **Entități** și descărcați datele entității pentru a vedea ce valori sunt disponibile.
> - Condițiile bazate pe date vă permit să comutați între datele fixe și un interval de date flotant.
> - Dacă aveți mai multe reguli pentru segmentul dvs., regula pe care o modificați are o linie albastră verticală lângă ea.
> - Puteți muta reguli și condiții în alte locuri din definiția segmentului. Selectați [...] lângă o regulă sau condiție și alegeți cum și unde să o mutați.
> - Controalele **Anulare** și **Refacere** din bara de comenzi vă permit să reveniți la modificări.

## <a name="quick-segments"></a>Segmente rapide

Segmentele rapide permit crearea de segmente simple cu un singur operator rapid pentru informații mai rapide.

1. Pe pagina **Segmente**, selectați **Nou** > **Creare din**.
   - Selectați opțiunea **Profiluri** pentru a construi un segment care se bazează pe entitatea *Client unificat*.
   - Selectați opțiunea **Măsuri** pentru a construi un segment în jurul măsurilor pe care le-ați creat înainte.
   - Selectați opțiunea **Inteligență** pentru a construi un segment în jurul uneia dintre entitățile de ieșire pe care le-ați generat folosind fie capabilități **Predicții** sau **Modele particularizate**.

2. În caseta de dialog **Segment rapid nou**, selectați un atribut din lista verticală **Câmp**.

3. Sistemul vă va oferi mai multe informații care vă vor ajuta să creați segmente mai bune ale clienților dvs.
   - Pentru câmpurile categorice, vom afișa 10 numere de clienți de top. Alegeți o **Valoare** și selectați **Revizuire**.
   - Pentru un atribut numeric, sistemul va arăta ce valoare a atributului se încadrează sub percentila fiecărui client. Alegeți un **Operator** și o **Valoare**, apoi selectați **Revizuire**.

4. Sistemul vă va oferi o **Dimensiunea estimată segment**. Puteți alege dacă vreți să generați segmentul pe care l-ați definit sau să îl revizuiți mai întâi pentru a obține o dimensiune diferită a segmentului.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Numele și estimarea pentru un segment rapid.":::

5. Furnizeaza un **Nume** și **Numele entității de ieșire** pentru segmentul dvs. Opțional, adăugați [Etichete](work-with-tags-columns.md#manage-tags).

6. Selectați **Salvare** pentru a crea segmentul.

7. După ce segmentul a terminat procesarea, îl puteți vizualiza ca orice alt segment creat.

## <a name="next-steps"></a>Pașii următori

[Exportați un segment](export-destinations.md) și explorați [Integrarea Cardului Clientului](customer-card-add-in.md) pentru a utiliza segmente în alte aplicații.

[!INCLUDE [footer-include](includes/footer-banner.md)]
