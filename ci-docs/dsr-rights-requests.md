---
title: Solicitări de drepturi privind datele subiecților sub RGPD | Microsoft Docs
description: Răspundeți la solicitările subiectului de date pentru Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: af2583295627f98e980adbca4f216b9c34c3cad8
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808576"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Solicitări de drepturi privin datele subiecților sub RGPD

Regulamentul general de protecție a datelor (RGPD) al Uniunii Europene este în vigoare din 25 mai 2018. Oferă drepturi semnificative persoanelor cu privire la datele lor. RGPD se referă la protejarea și activarea drepturilor de confidențialitate ale persoanelor fizice. Puteți citi mai multe despre angajamentul Microsoft față de securitate și conformitate în [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Ne-am angajat să ne ajutăm clienții să își îndeplinească cerințele RGPD. Include dreptul de a șterge și exporta date care includ informații personale, cum ar fi ID-uri de utilizator, numere de telefon și adrese de e-mail. Administratorii pot implementa cererile utilizatorilor de a șterge sau exporta date cu caracter personal.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Răspundeți la solicitările de eliminare a subiectului de date RGPD pentru Dynamics 365 Customer Insights

„Dreptul la eliminare” prin înlăturarea datelor cu caracter personal din datele clienților unei organizații reprezintă o protecție-cheie în Regulamentul general privind protecția datelor (RGPD). Îndepărtarea datelor personale include eliminarea tuturor datelor personale și a jurnalelor generate de sistem, cu excepția informațiilor din jurnalul de audit.

#### <a name="manage-data-subject-delete-requests"></a>Gestionați solicitările de ștergere a subiectului de date

Customer Insights oferă următoarele experiențe în produs pentru a șterge datele personale pentru un anumit client sau utilizator:

- **Gestionați ștergerea cererilor datelor clienților**: Datele clienților din Customer Insights sunt ingerate din surse de date originale externe pentru Customer Insights. Toate cererile de ștergere a RGPD trebuie să fie efectuate în sursă originală de date.
- **Gestionați solicitările de ștergere pentru datele de utilizator Customer Insights** : Datele pentru utilizatori sunt create de Customer Insights. Toate cererile de ștergere a RGPD trebuie să fie efectuate în Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Gestionați solicitări pentru a șterge datele clienților

Un administrator al Customer Insights poate urma acești pași pentru a elimina datele despre clienți care au fost șterse în sursa de date:

1. Conectați-vă la Dynamics 365 Customer Insights.
2. Mergi la **Date** > **Surse de date**
3. Pentru fiecare sursă de date din listă care conține datele șterse ale clienților:
   1. Selectați elipsa verticală (&vellip;) și apoi selectați **Reîmprospăta**.
   2. Verificați starea sursei de date din **Stare**. O bifă înseamnă că actualizarea a reușit. Un triunghi de avertizare înseamnă că a apărut o problemă. Dacă este afișat un triunghi de avertizare, contactați D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Manipularea RGPD de ștergere a cererilor pentru datele clienților.](media/gdpr-data-sources.png "Manipularea RGPD de ștergere a cererilor pentru datele clienților")

##### <a name="manage-delete-requests-for-user-data"></a>Gestionați ștergerea cererilor pentru datele utilizatorilor

Un administrator al Customer Insights poate urma acești pași pentru ștergerea datelor de utilizator Customer Insights:

1. Conectați-vă la Dynamics 365 Customer Insights.
2. Mergi la **Admin** > **Securitate** > **Permisiuni**.
3. Bifați caseta de selectare pentru utilizatorul pe care doriți să-l eliminați.
4. Selectați **Eliminare**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Răspunsul la cererile de export al datelor persoanei vizate în temeiul RGPD

Ca parte a angajamentului nostru de a colabora cu dvs. în călătoria dvs. către Regulamentul general privind protecția datelor (GDPR), am dezvoltat documentație care să vă ajute să răspundeți la solicitările persoanelor vizate.

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

Pentru a elimina datele privind consimțământul despre anumiți utilizatori, eliminați-le din sursele de date ingerate pentru capacitatea de gestionare a consimțământului. După reîmprospătarea sursă de date, datele eliminate vor fi șterse și din Centrul de consimțământ. Aplicațiile care utilizează entitatea de consimțământ vor șterge și datele care au fost eliminate de pe sursă după a [reîmprospăta](system.md#refresh-processes). Vă recomandăm să reîmprospătați sursele de date rapid după ce răspundeți la o solicitare a persoanei vizate pentru a elimina datele utilizatorului din toate celelalte procese și aplicații.

[!INCLUDE [footer-include](includes/footer-banner.md)]