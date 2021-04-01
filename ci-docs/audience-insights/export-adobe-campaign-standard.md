---
title: Exportați datele Customer Insights în Adobe Campaign Standard
description: Aflați cum utilizați segmentele de statistici privind publicul în Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596330"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Utilizați segmentele de Customer Insights în Adobe Campaign Standard (previzualizare)

Ca utilizator al statisticilor publicului pentru Dynamics 365 Customer Insights, este posibil să fi creat segmente pentru a vă face campaniile de marketing mai eficiente, vizând publicuri relevante. Pentru a utiliza un segment din statisticile publicului în Adobe Experience Platform și aplicații precum Adobe Campaign Standard, trebuie să urmați câțiva pași descriși în acest articol.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de proces a pașilor descriși în acest articol.":::

## <a name="prerequisites"></a>Cerințe preliminare

-   Licență Dynamics 365 Customer Insights
-   Licență Adobe Campaign Standard
-   Cont Azure Blob Storage

## <a name="campaign-overview"></a>Prezentare generală campanie

Pentru a înțelege mai bine modul în care puteți utiliza segmente din statisticile publicului în platforma Adobe Experience, haideți să analizăm un exemplu de campanie fictivă.

Să presupunem că compania dvs. oferă clienților dvs. din Statele Unite un serviciu lunar, bazat pe abonament. Doriți să identificați clienții ale căror abonamente trebuie reînnoite în următoarele opt zile, dar nu și-au reînnoit abonamentul. Pentru a păstra acești clienți, doriți să le trimiteți o ofertă promoțională prin e-mail, utilizând Adobe Campaign Standard.

În acest exemplu, dorim să derulăm o dată campania de e-mail promoțională. Acest articol nu acoperă cazul de utilizare al desfășurării campaniei de mai multe ori. Cu toate acestea, statisticile publicului și Adobe Campaign Standard pot fi configurate pentru a funcționa și pentru un scenariu de campanie recurentă.

## <a name="identify-your-target-audience"></a>Identificați-vă publicul țintă

În scenariul nostru, presupunem că adresele de e-mail ale clienților sunt disponibile în statisticile publicului, iar preferințele lor promoționale au fost analizate pentru a identifica membrii segmentului.

[Segmentul pe care l-ați definit în statistici privind publicul](segments.md) se numește **ChurnProneCustomers** și intenționați să trimiteți acestor clienți promoția prin e-mail.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captură de ecran a paginii segmente cu segmentul ChurnProneCustomers creat.":::

E-mailul de ofertă pe care doriți să îl trimiteți va conține prenume, nume de familie, și data de încheiere a abonamentului clientului. Acesta informează clienții despre reducerea pe care o vor primi dacă își reînnoiesc abonamentul înainte de a se încheia.

## <a name="export-your-target-audience"></a>Expportați-vă publicul țintă

Odată cu publicul țintă identificat, putem configura exportul din statistici privind publicul către un cont de stocare Blob Azure.

1. În Detalii despre audiență, accesați **Administrator** > **Destinații export**.

1. În dala **Campanie Adobe**, selectați **Configurare**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Placă de configurare pentru Adobe Campaign Standard.":::

1. Furnizează un **Nume afișat** pentru această nouă destinație de export și apoi introduceți **Nume de cont**, **Cheia contului** și **Recipient** din contul Azure Blob Storage în care doriți să exportați segmentul.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captură de ecran a configurării contului de stocare. "::: 

   - Pentru a afla mai multe despre cum puteți găsi numele contului Stocarea de bloburi Azure și cheia contului, consultați [Gestionați setările contului de stocare în portalul Azure](/azure/storage/common/storage-account-manage).

   - Pentru a afla cum să creați un container, consultați [Creați un container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Selectați **Următorul**.

1. Alegeți segmentul pe care doriți să îl exportați. În acest exemplu, este **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captură de ecran a interfeței de selectare a segmentului cu segmentul ChurnProneCustomers selectat.":::

1. Selectați **Următorul**.

1. Acum mapăm câmpurile **Sursă** de la segmentul de statistici al publicului la numele câmpurilor **Ţintă** din schema de profil Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Cartarea câmpului pentru conectorul Adobe Campaign Standard.":::

   Dacă doriți să adăugați mai multe atribute, selectați **Adăugați un atribut**. Numele țintă poate fi diferit de numele câmpului sursă, astfel încât să puteți mapa în continuare rezultatele segmentelor din statistici privind publicul către Adobe Campaign Standard dacă câmpurile nu au același nume în cele două sisteme.

   > [!NOTE]
   > Adresa de e-mail este utilizată ca un câmp de identitate, dar puteți utiliza orice alt identificator din profilul de client al informațiilor despre public pentru a mapa datele la Adobe Campaign Standard.

1. Selectați **Salvare**.

După salvarea destinației de export, o găsiți pe **Administrator** > **Exporturi** > **Destinațiile mele de export**.

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Captură de ecran cu lista exporturilor și segmentul eșantion evidențiat.":::

Acum puteți [exporta segmentul la cerere](export-destinations.md#export-data-on-demand). Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md).

> [!NOTE]
> Asigurați-vă că numărul de înregistrări din segmentul exportat se încadrează în limita permisă a licenței dvs. Adobe Campaign Standard.

Datele exportate sunt stocate în containerul de stocare Azure Blob pe care l-ați configurat mai sus. Următoarea cale a folderului este creată automat în container:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Configurați Adobe Campaign Standard

Atunci când un segment din statistici privind publicul este exportat, acesta conține coloanele pe care le-ați selectat în timp ce definiți destinația de export în pasul anterior. Aceste date pot fi utilizate pentru [crearea profilurilor în Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Pentru a utiliza segmentul în Adobe Campaign Standard, trebuie să extindem schema de profil în Adobe Campaign Standard pentru a include două câmpuri suplimentare. Aflați cum să [extindeți resursa profilului](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) cu câmpuri noi în Adobe Campaign Standard.

În exemplul nostru, aceste câmpuri sunt *Numele segmentului și data segmentului (opțional).*

Vom folosi aceste câmpuri pentru a identifica profilurile din Adobe Campaign Standard pe care dorim să le vizăm pentru această campanie.

Dacă nu există alte înregistrări în Adobe Campaign Standard, în afară de ceea ce urmează să importați, puteți sări peste acest pas.

## <a name="import-data-into-adobe-campaign-standard"></a>Importați date în Adobe Campaign Standard

Acum că totul este la locul său, trebuie să importăm datele pregătite despre audiență din statistici despre audiență în Adobe Campaign Standard pentru a crea profiluri. Învățați [cum să importați profiluri în Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) folosind un flux de lucru.

Fluxul de lucru de import din imaginea de mai jos a fost configurat să ruleze la fiecare 8 ore și caută segmente de informații despre publicul exportat (fișier .csv în Azure Blob Storage). Fluxul de lucru extrage conținutul fișierului .csv într-o ordine de coloane specificată. Acest flux de lucru a fost creat pentru a efectua tratarea erorilor de bază și pentru a se asigura că fiecare înregistrare are o adresă de e-mail înainte de a hidrata datele în Adobe Campaign Standard. Fluxul de lucru extrage, de asemenea, numele segmentului din numele fișierului înainte de a fi introdus în datele profilului ACS.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captură de ecran a unui flux de lucru de import în interfața cu utilizatorul Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Regăsiți publicul în Adobe Campaign Standard

Odată ce datele sunt importate în Adobe Campaign Standard, dvs. [poate crea un flux de lucru](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) și [interogare](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) clienții pe baza *Nume segment* și *Data segmentului* pentru a selecta profilurile care au fost identificate pentru campania noastră eșantion.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Creați și trimiteți e-mailul utilizând Adobe Campaign Standard

Creați conținutul e-mailului și apoi [testați și trimiteți](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email-ul dvs.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Eșantion de e-mail cu ofertă de reînnoire de la Adobe Campaign Standard.":::