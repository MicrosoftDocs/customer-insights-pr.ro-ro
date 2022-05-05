---
title: Îmbogățiți profilurile clienților cu date de la Microsoft Office 365
description: Utilizați date proprietare de la Microsoft Office pentru a vă îmbogăți profilurile clienților cu date de implicare.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 782042ff643bd0cc70ac53e5680bfd0c68944d84
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643460"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Îmbogățiți profilurile clienților cu date de implicare (previzualizare)

Utilizați datele de la Microsoft Office 365 pentru a vă îmbogăți profilurile contului de client cu informații despre angajamente prin intermediul Office 365 aplicații. Datele de implicare constau în e-mail și activitate de întâlnire, care este agregată la nivel de cont. De exemplu, numărul de e-mailuri dintr-un cont de afaceri sau numărul de întâlniri cu contul. Nu sunt disponibile date despre utilizatorii individuali. 

Această îmbogățire este disponibilă în următoarele regiuni: Regatul Unit, Europa, America de Nord.

## <a name="prerequisites"></a>Cerințe preliminare

Pentru a configura îmbogățirea, trebuie îndeplinite următoarele cerințe preliminare:

- Ai un activ Office 365 licență cloud.
- Tu ai [profiluri unificate ale clienților](customer-profiles.md) bazat pe [conturi de afaceri](work-with-business-accounts.md).
- Mediul dumneavoastră Customer Insights trebuie să aibă un [Microsoft Dataverse organizatie atasata](create-environment.md#step-3-connect-to-microsoft-dataverse).
- Tu ai [administrator](permissions.md#admin) permisiuni.
- Aveți sau puteți obține consimțământul dvs Office 365 administratorul locatarului de utilizat Office 365 date de furnizat **Perspective pentru organizație** în cadrul aplicațiilor Dynamics 365.

## <a name="configure-the-enrichment"></a>Configurați îmbogățirea

1. Accesați **Date** > **Îmbogățire**.

1. Du-te la **Descoperi** filă și selectați **Îmbogățiți-mi datele** pe **Implicarea contului** ţiglă.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Dală de implicare a contului.":::
   
1. Selectați **Următorul** în **Prezentare generală** pas și introduceți adrese de e-mail de la organizația dvs. pentru care datele Office vor fi agregate. Numai datele de la adresele de e-mail enumerate sunt procesate pentru comunicare relevantă. O bună practică este să utilizați grupuri de e-mail, de exemplu, *Echipa de vânzări din SUA*, care sunt ușor de gestionat în Office 365. Numărul de adrese de e-mail din grupuri sunt rezolvate și afișate. Numărul total de adrese de e-mail trebuie să fie de cel puțin 2 și nu poate depăși 2.500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Adresele de e-mail pentru implicarea contului.":::

1. Examinați declarația de consimțământ, selectați **Sunt de acord** casetă de selectare și selectați **Următorul**.

1. Selectați setul de date despre clienți și selectați **Următorul**.

1. Hartați câmpul adresei de e-mail de contact și selectați **Următorul**.

1. Examinați configurația îmbogățirii, dați un nume îmbogățirii și selectați **Economisiți îmbogățirea** pentru a salva îmbogățirea.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 acordul administratorului locatarului

Consimțământul unui Office 365 administratorul locatarului este necesar pentru a activa îmbogățirea. Se trimite un e-mail către Office 365 administratorilor locatarii atunci când îmbogățirea este salvată, ceea ce le cere să revizuiască și să își dea acordul pentru a permite aplicațiilor Dynamics 365 să utilizeze întreprinderile dvs.Office 365 date de furnizat **Perspective pentru organizație**. The Office 365 administratorul chiriașului poate, de asemenea, să își dea consimțământul direct în lor Office 365 consola de administrare, prin selectare **Perspective pentru organizație**.

## <a name="running-the-enrichment-for-the-first-time"></a>Rularea îmbogățirii pentru prima dată

Când îmbogățirea este începută pentru prima dată, după Office 365 administratorul locatarului și-a dat consimțământul, descărcarea datelor de la Office 365 începe. Acest proces durează ceva timp. Prima rundă de îmbogățire va fi programată să aibă loc cu o întârziere de șase ore. Puteți vedea numărul de zile pe care le acoperă datele pe pagina de prezentare generală a implicării contului după ce se termină îmbogățirea. Cu un volum mare de date, rulați din nou îmbogățirea după câteva zile. Se asigură că datele sunt complete pentru întreaga fereastră de timp, care este de un an.

Pentru a începe procesul, selectați **Alerga** pe pagina de configurare a implicării contului. În plus, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unui [reîmprospătare programată](system.md#schedule-tab). În mod implicit, îmbogățirea rulează o dată pe săptămână.

În funcție de dimensiunea datelor Office, poate dura câteva ore până la finalizarea unei execuții de îmbogățire.

Când executați o îmbogățire, Microsoft va procesa datele din Office 365 limită de conformitate pentru a crea informații agregate, care sunt apoi adăugate în mediul dvs. Customer Insights. Nicio dată la nivel individual (de exemplu, corpul oricărui e-mail sau invitație din calendar) nu devine disponibilă pentru utilizatorii Customer Insights. 

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Rezultate de îmbogățire

După rularea procesului de îmbogățire, accesați **Îmbogățirile mele** pentru a revizui rezultatele îmbogățirii. Veți găsi numărul total de clienți îmbogățiți și o prezentare generală a rezultatelor îmbogățirii. Include numărul de e-mailuri și întâlniri procesate, numărul de zile pentru care datele au fost agregate și multe altele.

Veți găsi, de asemenea, o diagramă cu numărul de clienți îmbogățiți de-a lungul timpului și o previzualizare a datelor de îmbogățire.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Previzualizarea rezultatelor după executarea procesului de îmbogățire":::

Toate datele sunt agregate până la nivel de cont. Sistemul calculează un scor de implicare, care variază de la 0 la 100, pentru fiecare cont. Scorul de implicare oferă o măsură compozită a angajării contului prin e-mailuri și întâlniri în raport cu celelalte conturi ale dvs. Următoarea listă conține datele agregate pe care le oferă îmbogățirea angajării contului:



| Date                                                                              | Nume coloană                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Scor angajament                                                                  |  EngagementScore                         |
| Numărul de e-mailuri către cont                                                       |  NoOfEmails_ToAccount                    |
| Numărul de e-mailuri din cont                                                     |  NoOfEmails_FromAccount                  | 
| Numărul de întâlniri inițiate de cont                                           |  NoOfMeetings_FromAccount                | 
| Numărul de întâlniri inițiate de organizația dvs                                 |  NoOfMeetings_ToAccount                  | 
| Numărul de persoane din organizația dvs. în întâlniri cu cont                  |  NoOfContactsInvolved_Meetings           | 
| Numărul de persoane din organizația dvs. în conversații prin e-mail cu contul       |  NoOfContactsInvolved_E-mails             | 
| Numărul de persoane din cont în întâlniri cu organizația dvs                  |  NoOfAccountContactsInvolved_Meetings    | 
| Numărul de persoane din cont în conversații prin e-mail cu organizația dvs       |  NoOfAccountContactsInvolved_E-mails      | 
| Data de începere a implicării (primul e-mail sau întâlnire din date)                        |  EngagementStartDate                     | 
| Zile de la ultimul e-mail                                                             |  DaysSinceLastEmail                      | 
| Zile de la ultima întâlnire                                                           |  DaysDeLastMeeting                    | 
| Durata medie a întâlnirilor                                                      |  AverageDuration_Of_Meetings             | 
| Durata medie a răspunsurilor la e-mail din cont                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Data de începere a agregarii                                                            |  AggregationStartDate                    | 
| Nivel de agregare (an, lună sau săptămână)                                          |  Nivel de agregare                        | 


Examinați datele îmbogățite selectând **Vezi mai mult** în secțiunea de previzualizare. Se deschide *Birou* entitate. Puteți găsi, de asemenea, entitatea listată în **Îmbogăţire** grup in **Date** > **Entități**. Veți găsi, de asemenea, *Office_UserEntity*, care conține ID-urile Active Directory pentru adresele de e-mail care au fost alese în timpul configurării îmbogățirii 

## <a name="see-enrichment-data-on-the-customer-card"></a>Consultați datele de îmbogățire de pe cardul clientului

Implicarea contului poate fi vizualizată și pe cardurile individuale ale clienților. Accesați **Clienți** și selectați un profil de client. În cardul de client, veți găsi scorul de implicare al contului, numărul total de e-mailuri și numărul total de întâlniri agregate în ultimul an. De asemenea, găsiți diagrame care arată e-mailul și istoricul întâlnirilor.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Card de client cu date îmbogățite.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Creați segmente și măsuri pe baza datelor îmbogățite

Datele îmbogățite pot fi folosite pentru a crea segmente și măsuri, așa cum este detaliat mai jos. De exemplu, un segment care conține toți clienții care au o valoare peste 60 pentru *zile de la ultimul e-mail* și *zile de la ultima întâlnire*. Segmentul respectiv conține conturi învechite pe care le puteți încerca să le reactivați. 

## <a name="next-steps"></a>Pașii următori

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
