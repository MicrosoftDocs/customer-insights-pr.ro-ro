---
title: Creați segmente complexe cu generatorul de segmente
description: Utilizați generatorul de segmente pentru a crea segmente complexe de clienți, grupându-le pe baza diferitelor atribute.
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
ms.openlocfilehash: cde373cd65e296675e1b3c92f3024e1093853842
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170650"
---
# <a name="create-complex-segments-with-segment-builder"></a>Creați segmente complexe cu generatorul de segmente

Definiți filtre complexe pe baza entității client unificate și a entităților conexe. Fiecare segment, după procesare, creează un set de înregistrări ale clienților pe care le puteți exporta și pe care puteți acționa.

> [!TIP]
> Segmente bazate pe **clienți individuali** includ automat informațiile de contact disponibile pentru membrii segmentului. În medii pentru **conturi de business**, segmentele se bazează pe conturi (companii sau filiale). Pentru a include informații de contact într-un segment, utilizați funcționalitatea **Atributele proiectului** în generatorul de segmente. Asigurați-vă că sursele de date de contact sunt [mapate semantic la ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping) pentru entitate.

## <a name="segment-builder"></a>Constructor de segmente

Următoarea imagine ilustrează diferitele aspecte ale constructorului de segmente. Afișează un segment care are ca rezultat un grup de clienți. Clienții au comandat bunuri într-un anumit interval de timp și au adunat puncte de recompensă sau au cheltuit o anumită sumă de bani.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elemente ale constructorului de segmente." lightbox="media/segment-builder-overview.png":::

1. Organizați-vă segmentul cu reguli și subreguli. Fiecare regulă sau subregulă constă din condiții. Combinați condițiile cu operatori logici.

1. Alegeți [calea relației](relationships.md) între entități care se aplică unei reguli. Calea relației determină ce atribute pot fi utilizate într-o condiție.

1. Gestionați regulile și subregulile. Schimbați poziția unei reguli sau ștergeți-o.

1. Adăugați condiții și construiți nivelul potrivit de cuibărire folosind subreguli.

1. Aplicați operațiile de setare la regulile conectate.

1. Utilizați panoul de atribute pentru a adăuga atribute de entitate disponibile sau pentru a crea condiții pe baza atributelor. Panoul afișează lista entităților și atributelor, bazate pe calea relației selectate, care sunt disponibile pentru regula selectată.

1. Adăugați condiții bazate pe atribute regulilor și subregulilor existente sau adăugați-o la o nouă regulă.

1. Anulați și refaceți modificările în timp ce construiți segmentul.

Exemplul de mai sus ilustrează capacitatea de segmentare. Am definit un segment pentru clienții care au cumpărat cel puțin $500 de bunuri online *și* au un interes în dezvoltarea de software.

## <a name="create-a-new-segment-with-segment-builder"></a>Creați un nou segment cu generatorul de segmente

1. Mergeți la **Segmente**.

1. Selectați **Nou** > **Construiește-ți propriul**. În pagina generator de segmente, definiți sau compuneți reguli. O regulă constă din una sau mai multe condiții care definesc un set de clienți.

1. Selectați **Editează detaliile** lângă segmentul fără titlu. Furnizați un nume pentru segmentul dvs. și actualizați **Numele entității de ieșire** sugerat pentru segment. Opțional, adăugați o descriere și [Etichete](work-with-tags-columns.md#manage-tags) la segment.

   :::image type="content" source="media/segments_edit_details.png" alt-text="caseta de dialog Editare detalii.":::

1. În **Regula 1** secțiunea, alegeți un atribut al unei entități după care doriți să filtrați clienții. Există două moduri de a alege atribute:
   - Consultați lista entităților și atributelor disponibile în panoul **Adăugați la regulă** și selectați pictograma **+** pictogramă de lângă atributul de adăugat. Alegeți dacă doriți să adăugați atributul la o regulă existentă sau utilizați-l pentru a crea o nouă regulă.
   - Tastați numele atributului în secțiunea regulii pentru a vedea sugestiile potrivite.

1. Alegeți operatorii pentru a specifica valorile potrivite ale condiției. Atributul poate avea unul dintre cele patru tipuri de date ca valoare: numeric, șir, dată sau boolean. În funcție de tipul de date al atributului, sunt disponibili diferiți operatori pentru a specifica condiția. Pentru segmente cu conturi de afaceri, sunt disponibili doi operatori speciali pentru a include ierarhii potențiale între conturile ingerate. Utilizați operatorii *copil al* și *parinte a* pentru a include conturi conexe.

1. Selectați **Adăugați o condiție** pentru a adăuga mai multe condiții unei reguli. Pentru a crea o regulă sub regula curentă, selectați **Adăugați o subregulă**.

1. Dacă o regulă folosește alte entități decât cele *Client* entitate, selectați **Stabiliți calea relației** pentru a mapa entitatea selectată la entitatea client unificat. Dacă există o singură cale de relație posibilă, sistemul o selectează automat. Diferit [căi de relație](relationships.md#relationship-paths) poate da rezultate diferite. Fiecare regulă poate avea propria cale de relaționare.

   :::image type="content" source="media/relationship-path.png" alt-text="Calea relației potențiale la crearea unei reguli bazate pe o entitate mapată la entitatea client unificată.":::

1. Dacă aveți mai multe condiții într-o regulă, alegeți ce operator logic le conectează.  
   - Operator **ȘI**: trebuie îndeplinite toate condițiile pentru a include o înregistrare în segment. Utilizați această opțiune când definiți condiții pentru diferite entități.
   - Operator **SAU**: trebuie îndeplinite oricare dintre condiții pentru a include o înregistrare în segment. Utilizați această opțiune când definiți mai multe condiții pentru aceeași entitate.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Rregulă cu două condiții ȘI.":::

   Atunci când utilizați operatorul SAU, toate condițiile trebuie să se bazeze pe entități incluse în calea relației.

1. Pentru a crea seturi diferite de înregistrări ale clienților, creați mai multe reguli. Pentru a include clienții necesari pentru cazul dvs. de afaceri, combinați grupuri. Mai exact, dacă nu puteți include o entitate într-o regulă din cauza căii de relație specificate, creați o nouă regulă pentru a alege atributele din aceasta.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Adăugați o nouă regulă la un segment și alegeți operatorul setat.":::

   1. Selectați **Adăugați o regulă**.
   1. Selectați unul dintre operatorii de mulțimi: **Reuniune**, **Intersecție** sau **Cu excepția**.

      - **Uniune** unește cele două grupuri.
      - **Intersectare** suprapune cele două grupuri. Numai datele ce *sunt comune* pentru ambele grupuri vor rămâne în grupul unificat.
      - **Excepție** combină cele două grupuri. Se păstrează numai datele din grupul A care *nu sunt comune* cu datele din grupa B.

1. În mod implicit, entitatea de ieșire va conține automat toate atributele profilurilor clienților care se potrivesc cu filtrele definite. Dacă un segment se bazează pe alte entități decât cele *Client* entitate, selectați **Atributele proiectului** pentru a adăuga mai multe atribute de la aceste entități la entitatea de ieșire.

   > [!IMPORTANT]
   > Pentru segmentele bazate pe conturi de afaceri, detalii despre una sau mai multe persoane de contact ale fiecărui cont din *Profil de contact* entitatea trebuie inclusă în segment pentru a permite ca acel segment să fie activat sau exportat către destinații care necesită informații de contact. Pentru mai multe informații despre entitatea *ContactProfile*, vedeți [Mapări semantice](semantic-mappings.md).
   > Un exemplu de ieșire pentru un segment bazat pe conturi de business cu atributele proiectate ale persoanelor de contact ar putea arăta astfel:
   >
   > |ID  |Nume cont  |Venituri  |Nume persoană de contact  | Rol persoană de contact|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100K | [Abbie Moss, Ruth Soto]  | [CEO, manager achiziții]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Exemplu de atribute proiectate selectate în panoul lateral pentru a fi adăugate la entitatea de ieșire.":::
  
   De exemplu: un segment se bazează pe o entitate care conține date de achiziție, care sunt legate de entitatea *Client*. Segmentul caută toți clienții din Spania care au achiziționat bunuri în anul curent. Puteți alege să adăugați atribute precum prețul mărfurilor sau data achiziției la toate înregistrările clienților care se potrivesc din entitatea de ieșire. Aceste informații ar putea fi utile pentru a analiza corelațiile sezoniere cu cheltuielile totale.

   > [!NOTE]
   > - **Atributele proiectului** funcționează numai pentru entitățile care au o relație de la unu la mai mulți cu entitatea client. De exemplu, un client poate avea mai multe abonamente.
   > - Dacă atributul pe care doriți să îl proiectați este la mai mult de un salt de entitatea *Client*, așa cum este definită de relație, acel atribut ar trebui să fie utilizat în fiecare regulă a interogării de segment pe care o construiți.
   > - Dacă atributul pe care doriți să îl proiectați este la doar un salt de entitatea *Client*, acel atribut nu trebuie să fie prezent în fiecare regulă a interogării de segment pe care o construiți.
   > - **Atributele proiectate** sunt luate în calcul atunci când se utilizează operatori de mulțimi.

1. Selectați **Alerga** pentru a crea segmentul. Selectați **Salvați** dacă doriți să păstrați configurația curentă și să rulați segmentul mai târziu. The **Segmente** afișează pagina.

### <a name="segment-builder-tips"></a>Sfaturi pentru constructorul de segmente

Când creați un segment utilizând generatorul de segmente, țineți cont de următoarele sfaturi:

- Generatorul de segmente nu va sugera valori valide de la entități atunci când setează operatorii pentru condiții. Puteți accesa **Date** > **Entități** și descărcați datele entității pentru a vedea ce valori sunt disponibile.
- Condițiile bazate pe date vă permit să comutați între date fixe și un interval de date flotant.
- Dacă aveți mai multe reguli pentru segmentul dvs., regula pe care o modificați are o linie albastră verticală lângă ea.
- Puteți muta reguli și condiții în alte locuri din definiția segmentului. Selectați elipsa verticală (&vellip;) lângă o regulă sau o condiție și alegeți cum și unde să o mutați.
- Controalele **Anulare** și **Refacere** din bara de comenzi vă permit să reveniți la modificări.
- După crearea unui segment, unele segmente vă permit [urmăriți utilizarea segmentului](segments.md#track-usage-of-a-segment).

## <a name="next-steps"></a>Pașii următori

[Exportați un segment](export-destinations.md) și explorați [Integrarea Cardului Clientului](customer-card-add-in.md) pentru a utiliza segmente în alte aplicații.

[!INCLUDE [footer-include](includes/footer-banner.md)]
