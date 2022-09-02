---
title: Solicitări de drepturi privind datele subiecților sub RGPD | Microsoft Docs
description: Răspundeți la solicitările subiectului de date pentru Dynamics 365 Customer Insights.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387126"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Solicitări de drepturi privin datele subiecților sub RGPD

Regulamentul general de protecție a datelor (RGPD) al Uniunii Europene este în vigoare din 25 mai 2018. Oferă drepturi semnificative persoanelor cu privire la datele lor. RGPD se referă la protejarea și activarea drepturilor de confidențialitate ale persoanelor fizice. Citiți mai multe despre angajamentul Microsoft față de securitate și conformitate la adresa [Centrul de încredere Microsoft](https://www.microsoft.com/trust-center).

Ne-am angajat să ne ajutăm clienții să își îndeplinească cerințele RGPD. Include dreptul de a șterge sau exporta date care includ informații personale, cum ar fi ID-uri de utilizator, numere de telefon și adrese de e-mail. Administratorii pot implementa cererile utilizatorilor de a șterge sau exporta date cu caracter personal.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Răspunzând la solicitările de ștergere a persoanelor vizate din GDPR pentru Customer Insights

„Dreptul la eliminare” prin înlăturarea datelor cu caracter personal din datele clienților unei organizații reprezintă o protecție-cheie în Regulamentul general privind protecția datelor (RGPD). Îndepărtarea datelor personale include eliminarea tuturor datelor personale și a jurnalelor generate de sistem, cu excepția informațiilor din jurnalul de audit.

### <a name="manage-data-subject-delete-requests"></a>Gestionați solicitările de ștergere a subiectului de date

Customer Insights oferă următoarele experiențe în produs pentru a șterge datele personale pentru un anumit client sau utilizator:

- **Gestionați ștergerea cererilor datelor clienților**: Datele clienților din Customer Insights sunt ingerate din surse de date originale externe pentru Customer Insights. Efectuați mai întâi solicitările de ștergere GDPR în sursă de date original.
- **Gestionați solicitările de ștergere pentru datele de utilizator Customer Insights** : Datele pentru utilizatori sunt create de Customer Insights. Efectuați toate solicitările de ștergere din GDPR în Customer Insights.

#### <a name="manage-requests-to-delete-customer-data"></a>Gestionați solicitări pentru a șterge datele clienților

În calitate de administrator Customer Insights, eliminați datele clienților Customer Insights care au fost șterse din sursă de date. Verificați că solicitările de ștergere din GDPR au fost efectuate în sursă de date original.

1. Conectați-vă la Dynamics 365 Customer Insights.

1. Accesați **Date** > **Surse de date**.

1. Pentru fiecare sursă de date din listă care conține datele șterse ale clienților:
   1. Selectați sursă de date și apoi selectați **Reîmprospăta**.
   1. Verificați starea sursei de date din **Stare**. O bifă înseamnă că actualizarea a reușit. Un triunghi de avertizare înseamnă că a apărut o problemă. Dacă este afișat un triunghi de avertizare, contactați D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Manipularea RGPD de ștergere a cererilor pentru datele clienților.":::

1. După o reîmprospătare reușită a surselor de date, executați și reîmprospătările din aval. Mai ales, dacă nu aveți programată o reîmprospătare completă recurentă a Customer Insights.

   > [!IMPORTANT]
   > Segmentele statice nu sunt incluse într-o reîmprospătare completă sau în executarea reîmprospătărilor în aval după o solicitare de ștergere. Pentru a vă asigura că și datele despre clienți sunt eliminate din segmentele statice, recreați segmentele statice cu datele sursă reîmprospătate.

#### <a name="manage-delete-requests-for-user-data"></a>Gestionați ștergerea cererilor pentru datele utilizatorilor

În calitate de administrator Customer Insights, ștergeți datele utilizatorului Customer Insights.

1. Conectați-vă la Dynamics 365 Customer Insights.

1. Mergi la **Admin** > **Securitate** > și selectați **Utilizatori** fila.

1. Bifați caseta de selectare pentru utilizatorii pe care doriți să-i ștergeți.

1. Selectați **Eliminare**.

1. Confirmați ștergerea.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Răspunsul la cererile de export al datelor persoanei vizate în temeiul RGPD

Dreptul de portabilitate a datelor permite persoanelor vizate să solicite o copie a datelor cu caracter personal într-un format electronic (definit ca „format structurat, utilizat în mod obișnuit, în format electronic și format interoperabil”) care poate fi transmis unui alt operator de date.

### <a name="manage-export-and-view-requests"></a>Gestionați solicitările de export și vizualizare

Gestionați cererile de export de date despre clienți sau utilizatori.

#### <a name="export-customer-data-tenant-admin"></a>Exportați date despre clienți (administratorul entității găzduite)

În calitate de administrator de locatar, exportați datele clienților.

1. Trimiteți un e-mail la D365CI@microsoft.com specificând adresa de e-mail a clientului în cerere. Echipa Customer Insights va trimite un e-mail la adresa de e-mail înregistrată a administratorului entității găzduite înregistrate, solicitând confirmarea exportului de date.
2. Aprobați confirmarea de a exporta datele pentru client solicitate.
3. Primiți datele exportate prin intermediul adresei de e-mail de administrator de entitate găzduită.

#### <a name="export-user-data-tenant-admin"></a>Exportați date de utilizatori (administratorul entității găzduite)

În calitate de administrator de locatar, exportați datele utilizatorului.

1. Trimiteți un e-mail la D365CI@microsoft.com specificând adresa de e-mail a utilizatorului în cerere. Echipa Customer Insights trimite un e-mail la adresa de e-mail a administratorului locatarului înregistrat, solicitând confirmarea exportului datelor.
1. Aprobați confirmarea de a exporta datele pentru utilizator solicitate.
1. Primiți datele exportate prin intermediul adresei de e-mail de administrator de entitate găzduită.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Gestionarea ștergerii datelor în Dynamics 365 Customer Insights

Datele sunt șterse (partiții de date și instantanee de date) dacă partițiile de date și instantaneele de date sunt inactive mai mult de 30 de zile, ceea ce înseamnă că au fost înlocuite cu o nouă partiție de date și instantanee printr-o reîmprospătare a surselor de date.

Nu toate datele și instantaneele sunt șterse. Cea mai recentă partiție de date și instantanee de date sunt active deoarece sunt utilizate în Customer Insights. Pentru cele mai recente date, nu contează dacă sursele de date nu au fost reîmprospătate în ultimele 30 de zile.

[!INCLUDE [footer-include](includes/footer-banner.md)]
