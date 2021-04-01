---
title: Solicitări de drepturi privind datele subiecților sub RGPD | Microsoft Docs
description: Răspundeți la solicitările persoanei vizate pentru capabilitatea de detalii despre public din Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9c453c9b416bff0e6362a8ccf7ff534f4efa1e00
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597526"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Solicitări de drepturi privin datele subiecților sub RGPD

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Răspundeți la solicitările RGPD ale persoanei vizate pentru capabilitatea de detalii despre public din Dynamics 365 Customer Insights

„Dreptul la eliminare” prin înlăturarea datelor cu caracter personal din datele clienților unei organizații reprezintă o protecție-cheie în Regulamentul general privind protecția datelor (RGPD). Îndepărtarea datelor personale include eliminarea tuturor datelor personale și a jurnalelor generate de sistem, cu excepția informațiilor din jurnalul de audit.

### <a name="manage-data-subject-delete-requests"></a>Gestionați solicitările de ștergere a subiectului de date

Detaliile despre public oferă următoarele experiențe în cadrul produsului pentru a șterge datele cu caracter personal pentru un anumit client sau utilizator:

- **Gestionați ștergerea cererilor datelor clienților**: Datele clienților din Customer Insights sunt ingerate din surse de date originale externe pentru Customer Insights. Toate cererile de ștergere a RGPD trebuie să fie efectuate în sursă originală de date.
- **Gestionați solicitările de ștergere pentru datele de utilizator Customer Insights** : Datele pentru utilizatori sunt create de Customer Insights. Toate cererile de ștergere a RGPD trebuie să fie efectuate în Customer Insights.

#### <a name="manage-delete-requests-for-customer-data"></a>Gestionați ștergerea cererilor pentru datele clienților

Un administrator al Customer Insights poate urma acești pași pentru a elimina datele despre clienți care au fost șterse în sursa de date:

1. Conectați-vă la Dynamics 365 Customer Insights.
2. În Detalii despre audiență, accesați **Date** > **Surse de date**
3. Pentru fiecare sursă de date din listă care conține datele șterse ale clienților:
   1. Selectați (...) și apoi selectați **Reîmprospătare**.
   2. Verificați starea sursei de date din **Stare**. O bifă înseamnă că actualizarea a reușit. Un triunghi de avertizare înseamnă că a apărut o problemă. Dacă este afișat un triunghi de avertizare, contactați D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Manipularea RGPD de ștergere a cererilor pentru datele clienților](media/gdpr-data-sources.png "Manipularea RGPD de ștergere a cererilor pentru datele clienților")

#### <a name="manage-delete-requests-for-user-data"></a>Gestionați ștergerea cererilor pentru datele utilizatorilor

Un administrator al Customer Insights poate urma acești pași pentru ștergerea datelor de utilizator Customer Insights:

1. Conectați-vă la Dynamics 365 Customer Insights.
2. În detalii despre public, accesați **Admin** > **Permisiuni**.
3. Bifați caseta de selectare pentru utilizatorul pe care doriți să-l eliminați.
4. Selectați **Eliminare**.

> [!div class="mx-imgBorder"]
> ![Gestionarea cererilor de ștergere conform RGPD a datelor utilizatorilor](media/gdpr-permissions.png "Gestionarea cererilor de ștergere conform RGPD a datelor utilizatorilor")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Răspunsul la cererile de export al datelor persoanei vizate în temeiul RGPD

Ca parte a angajamentului nostru de a ne asocia cu dvs. în călătoria dvs. către Regulamentul general privind protecția datelor (RGPD), am dezvoltat o documentație care vă va ajuta să vă pregătiți. Această documentație descrie pașii pe care îi puteți face astăzi pentru a sprijini respectarea RGPD atunci când utilizați detalii privind publicul.

### <a name="manage-export-and-view-requests"></a>Gestionați solicitările de export și vizualizare

Dreptul de portabilitate a datelor permite persoanelor vizate să solicite o copie a datelor cu caracter personal într-un format electronic (definit ca „format structurat, utilizat în mod obișnuit, în format electronic și format interoperabil”) care poate fi transmis unui alt operator de date.

#### <a name="export-customer-data-tenant-admin"></a>Exportați date despre clienți (administratorul entității găzduite)

Un administrator de entitate găzduită poate urma acești pași pentru a exporta date:

1. Trimiteți un e-mail la D365CI@microsoft.com specificând adresa de e-mail a clientului în cerere. Echipa Customer Insights va trimite un e-mail la adresa de e-mail înregistrată a administratorului entității găzduite înregistrate, solicitând confirmarea exportului de date.
2. Aprobați confirmarea de a exporta datele pentru client solicitate.
3. Primiți datele exportate prin intermediul adresei de e-mail de administrator de entitate găzduită.

#### <a name="export-user-data-tenant-admin"></a>Exportați date de utilizatori (administratorul entității găzduite)

1. Trimiteți un e-mail la D365CI@microsoft.com specificând adresa de e-mail a utilizatorului în cerere. Echipa Customer Insights va trimite un e-mail la adresa de e-mail înregistrată a administratorului entității găzduite înregistrate, solicitând confirmarea exportului de date.
2. Aprobați confirmarea de a exporta datele pentru utilizator solicitate.
3. Primiți datele exportate prin intermediul adresei de e-mail de administrator de entitate găzduită.


[!INCLUDE[footer-include](../includes/footer-banner.md)]