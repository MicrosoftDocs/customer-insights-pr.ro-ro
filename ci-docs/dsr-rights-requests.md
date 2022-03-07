---
title: Solicitări de drepturi privind datele subiecților sub RGPD | Microsoft Docs
description: Răspundeți la solicitările persoanei vizate pentru capabilitatea de detalii despre public din Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350284"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Solicitări de drepturi privin datele subiecților sub RGPD

Regulamentul general de protecție a datelor (RGPD) al Uniunii Europene este în vigoare din 25 mai 2018. Oferă drepturi semnificative persoanelor cu privire la datele lor. RGPD se referă la protejarea și activarea drepturilor de confidențialitate ale persoanelor fizice. Puteți citi mai multe despre angajamentul Microsoft față de securitate și conformitate în [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Ne-am angajat să ne ajutăm clienții să își îndeplinească cerințele RGPD. Include dreptul de a șterge și exporta date care includ informații personale, cum ar fi ID-uri de utilizator, numere de telefon și adrese de e-mail. Administratorii pot implementa cererile utilizatorilor de a șterge sau exporta date cu caracter personal.

## <a name="audience-insights"></a>Detalii despre public

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Răspundeți la solicitările RGPD ale persoanei vizate pentru capabilitatea de detalii despre public din Dynamics 365 Customer Insights

„Dreptul la eliminare” prin înlăturarea datelor cu caracter personal din datele clienților unei organizații reprezintă o protecție-cheie în Regulamentul general privind protecția datelor (RGPD). Îndepărtarea datelor personale include eliminarea tuturor datelor personale și a jurnalelor generate de sistem, cu excepția informațiilor din jurnalul de audit.

#### <a name="manage-data-subject-delete-requests"></a>Gestionați solicitările de ștergere a subiectului de date

Detaliile despre public oferă următoarele experiențe în cadrul produsului pentru a șterge datele cu caracter personal pentru un anumit client sau utilizator:

- **Gestionați ștergerea cererilor datelor clienților**: Datele clienților din Customer Insights sunt ingerate din surse de date originale externe pentru Customer Insights. Toate cererile de ștergere a RGPD trebuie să fie efectuate în sursă originală de date.
- **Gestionați solicitările de ștergere pentru datele de utilizator Customer Insights** : Datele pentru utilizatori sunt create de Customer Insights. Toate cererile de ștergere a RGPD trebuie să fie efectuate în Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Gestionați solicitări pentru a șterge datele clienților

Un administrator al Customer Insights poate urma acești pași pentru a elimina datele despre clienți care au fost șterse în sursa de date:

1. Conectați-vă la Dynamics 365 Customer Insights.
2. În Detalii despre audiență, accesați **Date** > **Surse de date**
3. Pentru fiecare sursă de date din listă care conține datele șterse ale clienților:
   1. Selectați (...) și apoi selectați **Reîmprospătare**.
   2. Verificați starea sursei de date din **Stare**. O bifă înseamnă că actualizarea a reușit. Un triunghi de avertizare înseamnă că a apărut o problemă. Dacă este afișat un triunghi de avertizare, contactați D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Manipularea RGPD de ștergere a cererilor pentru datele clienților.](audience-insights/media/gdpr-data-sources.png "Manipularea RGPD de ștergere a cererilor pentru datele clienților")

##### <a name="manage-delete-requests-for-user-data"></a>Gestionați ștergerea cererilor pentru datele utilizatorilor

Un administrator al Customer Insights poate urma acești pași pentru ștergerea datelor de utilizator Customer Insights:

1. Conectați-vă la Dynamics 365 Customer Insights.
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


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]