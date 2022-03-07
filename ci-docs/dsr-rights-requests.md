---
title: Solicitări de drepturi privind datele subiecților sub RGPD | Microsoft Docs
description: Răspundeți la solicitările subiectului de date pentru capacitatea Dynamics 365 Customer Insights de informații despre public.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c116f7ce208c0288851a4b2230e27784ba3a5337
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732695"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Solicitări de drepturi privin datele subiecților sub RGPD

Regulamentul general de protecție a datelor (RGPD) al Uniunii Europene este în vigoare din 25 mai 2018. Oferă drepturi semnificative persoanelor cu privire la datele lor. RGPD se referă la protejarea și activarea drepturilor de confidențialitate ale persoanelor fizice. Puteți citi mai multe despre angajamentul Microsoft față de securitate și conformitate în [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Ne-am angajat să ne ajutăm clienții să își îndeplinească cerințele RGPD. Include dreptul de a șterge și exporta date care includ informații personale, cum ar fi ID-uri de utilizator, numere de telefon și adrese de e-mail. Administratorii pot implementa cererile utilizatorilor de a șterge sau exporta date cu caracter personal.

## <a name="audience-insights"></a>Detalii despre public

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Răspunsul la solicitările de ștergere a subiectului de date din GDPR pentru capacitatea Dynamics 365 Customer Insights de informații despre public

„Dreptul la eliminare” prin înlăturarea datelor cu caracter personal din datele clienților unei organizații reprezintă o protecție-cheie în Regulamentul general privind protecția datelor (RGPD). Îndepărtarea datelor personale include eliminarea tuturor datelor personale și a jurnalelor generate de sistem, cu excepția informațiilor din jurnalul de audit.

#### <a name="manage-data-subject-delete-requests"></a>Gestionați solicitările de ștergere a subiectului de date

Detaliile despre public oferă următoarele experiențe în cadrul produsului pentru a șterge datele cu caracter personal pentru un anumit client sau utilizator:

- **Gestionați ștergerea cererilor datelor clienților**: Datele clienților din Customer Insights sunt ingerate din surse de date originale externe pentru Customer Insights. Toate cererile de ștergere a RGPD trebuie să fie efectuate în sursă originală de date.
- **Gestionați solicitările de ștergere pentru datele de utilizator Customer Insights** : Datele pentru utilizatori sunt create de Customer Insights. Toate cererile de ștergere a RGPD trebuie să fie efectuate în Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Gestionați solicitări pentru a șterge datele clienților

Un administrator al Customer Insights poate urma acești pași pentru a elimina datele despre clienți care au fost șterse în sursa de date:

1. conectați-vă la Dynamics 365 Customer Insights.
2. În Detalii despre audiență, accesați **Date** > **Surse de date**
3. Pentru fiecare sursă de date din listă care conține datele șterse ale clienților:
   1. Selectați (...) și apoi selectați **Reîmprospătare**.
   2. Verificați starea sursei de date din **Stare**. O bifă înseamnă că actualizarea a reușit. Un triunghi de avertizare înseamnă că a apărut o problemă. Dacă este afișat un triunghi de avertizare, contactați D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Manipularea RGPD de ștergere a cererilor pentru datele clienților.](audience-insights/media/gdpr-data-sources.png "Manipularea RGPD de ștergere a cererilor pentru datele clienților")

##### <a name="manage-delete-requests-for-user-data"></a>Gestionați ștergerea cererilor pentru datele utilizatorilor

Un administrator al Customer Insights poate urma acești pași pentru ștergerea datelor de utilizator Customer Insights:

1. conectați-vă la Dynamics 365 Customer Insights.
2. În detalii despre public, accesați **Admin** > **Permisiuni**.
3. Bifați caseta de selectare pentru utilizatorul pe care doriți să-l eliminați.
4. Selectați **Eliminare**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Răspunsul la cererile de export al datelor persoanei vizate în temeiul RGPD

Ca parte a angajamentului nostru de a ne asocia cu dvs. în călătoria dvs. către Regulamentul general privind protecția datelor (RGPD), am dezvoltat o documentație care vă va ajuta să vă pregătiți. Această documentație descrie pașii pe care îi puteți face astăzi pentru a sprijini respectarea RGPD atunci când utilizați detalii privind publicul.

#### <a name="manage-export-and-view-requests"></a>Gestionați solicitările de export și vizualizare

Dreptul de portabilitate a datelor permite persoanelor vizate să solicite o copie a datelor cu caracter personal într-un format electronic (definit ca „format structurat, utilizat în mod obișnuit, în format electronic și format interoperabil”) care poate fi transmis unui alt operator de date.

##### <a name="export-customer-data-tenant-admin"></a>Exportați date despre clienți (administratorul entității găzduite)

Un administrator de entitate găzduită poate urma acești pași pentru a exporta date:

1. Trimiteți un e-mail la D365CI@microsoft.com specificând adresa de e-mail a clientului în cerere. Echipa Customer Insights va trimite un e-mail la adresa de e-mail înregistrată a administratorului entității găzduite înregistrate, solicitând confirmarea exportului de date.
2. Aprobați confirmarea de a exporta datele pentru client solicitate.
3. Primiți datele exportate prin intermediul adresei de e-mail de administrator de entitate găzduită.

##### <a name="export-user-data-tenant-admin"></a>Exportați date de utilizatori (administratorul entității găzduite)

1. Trimiteți un e-mail la D365CI@microsoft.com specificând adresa de e-mail a utilizatorului în cerere. Echipa Customer Insights va trimite un e-mail la adresa de e-mail înregistrată a administratorului entității găzduite înregistrate, solicitând confirmarea exportului de date.
2. Aprobați confirmarea de a exporta datele pentru utilizator solicitate.
3. Primiți datele exportate prin intermediul adresei de e-mail de administrator de entitate găzduită.

## <a name="consent-management-preview"></a>Gestionarea consimțământului (previzualizare)

Capacitatea de gestionare a consimțământului nu colectează în mod direct datele utilizatorului. Importă și prelucrează doar datele de consimțământ furnizate de utilizatori în alte aplicații.

Pentru a elimina datele privind consimțământul despre anumiți utilizatori, eliminați-le din sursele de date ingerate pentru capacitatea de gestionare a consimțământului. După reîmprospătarea sursă de date, datele eliminate vor fi șterse și din Centrul de consimțământ. Aplicațiile care utilizează entitatea de consimțământ vor șterge și datele care au fost eliminate de pe sursă după a [reîmprospăta](audience-insights/system.md#refresh-processes). Vă recomandăm să reîmprospătați sursele de date rapid după ce răspundeți la o solicitare a persoanei vizate pentru a elimina datele utilizatorului din toate celelalte procese și aplicații.


## <a name="engagement-insights-preview"></a>Detalii despre angajamente (versiune preliminară)

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Ștergerea și exportarea datelor despre evenimente care conțin informații de identificare ale utilizatorului final

Următoarele secțiuni descriu cum să ștergeți și să exportați date despre evenimente care ar putea conține date cu caracter personal.

Pentru a șterge sau exporta date:

1. Etichetați proprietățile evenimentului care conțin date cu informații personale.
2. Ștergeți sau exportați datele asociate cu anumite valori (de exemplu: un ID de utilizator specificat).

#### <a name="tag-and-update-event-properties"></a>Etichetați și actualizați proprietățile evenimentului

Datele personale sunt etichetate la nivel de proprietate a evenimentului. Mai întâi, etichetați proprietățile luate în considerare pentru ștergere sau export.

Pentru a eticheta o proprietate a evenimentului ca având informații personale, urmați acești pași:

1. Deschideți spațiul de lucru care conține evenimentul.

1. Accesați **Date** > **Evenimente** pentru a vedea lista evenimentelor din spațiul de lucru selectat.
  
1. Selectați evenimentul pe care doriți să îl etichetați.

1. Selectați **Editați proprietățile** pentru a deschide panoul listând toate proprietățile evenimentului selectat.
     
1. Selectați **...** și apoi alegeți **Editați** pentru a ajunge la caseta de dialog **Actualizați proprietatea**.

   ![Editați evenimentul.](engagement-insights/media/edit-event.png "Editați evenimentul")

1. În fereastra **Actualizați proprietatea**, alegeți **...** în colțul din dreapta sus, apoi alegeți caseta **Conține EUII**. Alegeți **Actualizare** pentru a vă salva modificările.

   ![Salvați modificările.](engagement-insights/media/update-property.png "Salvați modificările")

   > [!NOTE]
   > De fiecare dată când schema evenimentului se modifică sau creați un eveniment nou, este recomandat să evaluați proprietățile asociate evenimentului și să le etichetați sau să le etichetați ca conținând date personale, dacă este necesar.

#### <a name="delete-or-export-tagged-event-data"></a>Ștergeți sau exportați datele de eveniment etichetate

Dacă toate proprietățile evenimentului au fost etichetate în mod corespunzător, așa cum este descris în pasul anterior, un administrator de mediu poate emite o cerere de ștergere a datelor evenimentului etichetat.

Pentru a gestiona ștergerea EUII sau solicitările de export

1. Accesați **Administrator** > **Mediu** > **Setări**.

1. În secțiunea **Gestionați informațiile de identificare ale utilizatorului final (EUII)**, selectați **Gestionați EUII**.

##### <a name="deletion"></a>Ștergere

Pentru ștergere, puteți introduce o listă de ID-uri de utilizator separate prin virgulă în secțiunea **Ștergeți informațiile de identificare ale utilizatorului final (EUII)**. Aceste ID-uri vor fi apoi comparate cu toate proprietățile de evenimente etichetate ale tuturor proiectelor din mediul curent prin potrivirea exactă a șirurilor. 

Dacă o valoare a proprietății se potrivește cu unul dintre ID-urile furnizate, evenimentul asociat va fi șters definitiv. Datorită ireversibilității acestei acțiuni, trebuie să confirmați ștergerea după selectarea **Șterge**.

##### <a name="export"></a>Export

Procesul de export este identic cu procesul de ștergere atunci când vine vorba de definirea valorilor proprietății evenimentului în secțiunea **Exportați informații de identificare ale utilizatorului final (EUII)**. În plus, va trebui să furnizați un **URL de stocare blob Azure** pentru a specifica destinația de export. Adresa URL Blob Azure trebuie să includă o [Semnătură de acces partajată (SAS)](/azure/storage/common/storage-sas-overview).

După selectarea **Export**, toate evenimentele echipei actuale care conțin proprietăți etichetate potrivite vor fi exportate în format CSV la destinația de export.

### <a name="good-practices"></a>Bune practici

* Încercați să evitați trimiterea evenimentelor care conțin date personale.
* Dacă trebuie să trimiteți evenimente care conțin date EUII, limitați numărul de evenimente și proprietăți de eveniment care conțin date EUII. În mod ideal, limitați-vă la un astfel de eveniment.
* Asigurați-vă că cât mai puține persoane au acces la datele personale trimise.
* Pentru evenimentele care conțin date personale, asigurați-vă că setați o proprietate pentru a emite un identificator unic care poate fi ușor legat de un anumit utilizator (de exemplu, un ID de utilizator). Acest lucru facilitează separarea datelor și exportul sau ștergerea datelor corecte.
* Etichetați o singură proprietate pentru fiecare eveniment ca conținând date personale. În mod ideal unul care conține doar un identificator unic.
* Nu etichetați proprietăți care conțin valori detaliate (de exemplu, un întreg corp de solicitare). Funcția de statistici de implicare folosește potrivirea exactă a șirurilor atunci când decide ce evenimente trebuie șterse sau exportate.

[!INCLUDE[footer-include](includes/footer-banner.md)]