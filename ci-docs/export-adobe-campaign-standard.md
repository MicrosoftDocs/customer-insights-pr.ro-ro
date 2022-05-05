---
title: Exportați datele Customer Insights la Adobe Campaign Standard
description: Aflați cum utilizați segmentele Customer Insights în Adobe Standard de campanie.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 2a62d2f889f199222eeb8cc969fce62fa89fa6f0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643451"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Utilizați segmentele Customer Insights în Adobe Campaign Standard (previzualizare)

Ca utilizator Dynamics 365 Customer Insights, este posibil să fi creat segmente pentru a vă eficientiza campaniile de marketing prin țintirea unor publicuri relevante. Pentru a utiliza un segment din Customer Insights în Adobe Experience Platform și aplicații precum Adobe Standard de campanie, trebuie să urmați câțiva pași descriși în acest articol.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de proces a pașilor descriși în acest articol.":::

## <a name="prerequisites"></a>Cerințe preliminare

-   Licență Dynamics 365 Customer Insights
-   Licență Adobe Campaign Standard
-   Cont Azure Blob Storage

## <a name="campaign-overview"></a>Prezentare generală de campanie

Pentru a înțelege mai bine cum puteți utiliza segmente din Customer Insights în Adobe Experience Platform, să ne uităm la un exemplu de campanie fictiv.

Să presupunem că compania dvs. oferă clienților dvs. din Statele Unite un serviciu lunar, bazat pe abonament. Doriți să identificați clienții ale căror abonamente trebuie reînnoite în următoarele opt zile, dar nu și-au reînnoit abonamentul. Pentru a păstra acești clienți, doriți să le trimiteți o ofertă promoțională prin e-mail, folosind Adobe Campaign Standard.

În acest exemplu, dorim să derulăm o dată campania de e-mail promoțională. Acest articol nu acoperă cazul de utilizare al desfășurării campaniei de mai multe ori. Cu toate acestea, Customer Insights și Adobe Campaign Standard poate fi configurat să funcționeze și pentru un scenariu de campanie recurentă.

## <a name="identify-your-target-audience"></a>Identificați-vă publicul țintă

În scenariul nostru, presupunem că adresele de e-mail ale clienților sunt disponibile în și preferințele lor promoționale au fost analizate pentru a identifica membrii segmentului.

The [segment pe care l-ați definit în Customer Insights](segments.md) se numește **ChurnProneCustomers** și intenționați să trimiteți acestor clienți promoția prin e-mail.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captură de ecran a paginii segmente cu segmentul ChurnProneCustomers creat.":::

E-mailul de ofertă pe care doriți să îl trimiteți va conține prenume, nume de familie, și data de încheiere a abonamentului clientului. Acesta informează clienții despre reducerea pe care o vor primi dacă își reînnoiesc abonamentul înainte de a se încheia.

## <a name="export-your-target-audience"></a>Expportați-vă publicul țintă

### <a name="configure-a-connection"></a>Configurați o conexiune

Cu publicul nostru țintă identificat, putem configura exportul într-un cont Azure Blob Storage.

1. În Customer Insights, accesați **Admin** > **Conexiuni**.

1. Selectați **Adăugați conectare** și alegeți **Adobe Campaign** pentru a configura conexiunea sau selectați **Configurat** în dala **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Dală de configurare pentru Adobe Campaign Standard.":::

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Introduceți **Nume de cont**, **Cheia de cont** și **Recipient** pentru contul Azure Blob Storage în care doriți să exportați segmentul.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captură de ecran a configurării contului de stocare. "::: 

   - Pentru a afla mai multe despre cum puteți găsi numele contului de Stocare bloburi Azure și cheia contului, consultați [Gestionați setările contului de stocare în portalul Azure](/azure/storage/common/storage-account-manage).

   - Pentru a afla cum să creați un container, consultați [Creați un container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Selectați **Salvare** pentru a finaliza conexiunea.

### <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Adobe Campaign. Dacă nu vedeți numele acestei secțiuni, atunci nu aveți la dispoziție conexiuni de acest tip.

1. Alegeți segmentul pe care doriți să îl exportați. În acest exemplu, este **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captură de ecran a interfeței de selectare a segmentului cu segmentul ChurnProneCustomers selectat.":::

1. Selectați **Următorul**.

1. Acum mapăm **Sursă** câmpurile de la segmentul Customer Insights la **Ţintă** numele câmpurilor în Adobe Schema profilului standard al campaniei.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Maparea câmpului pentru conectorul Adobe Campaign Standard.":::

   Dacă doriți să adăugați mai multe atribute, selectați **Adăugați un atribut**. Numele țintă poate fi diferit de numele câmpului sursă, astfel încât să puteți mapa în continuare ieșirea segmentului din Customer Insights către Adobe Standard de campanie dacă câmpurile nu au același nume în cele două sisteme.

   > [!NOTE]
   > Adresa de e-mail este folosită ca câmp de identitate, dar puteți utiliza orice alt identificator din profilul clientului pentru a mapa datele Adobe Standard de campanie.

1. Selectați **Salvare**.

După salvarea destinației de export, o veți găsi pe **Date** > **Exporturi**.

Acum puteți [exporta segmentul la cerere](export-destinations.md#run-exports-on-demand). Exportul va rula, de asemenea, cu fiecare [actualizare programată](system.md).

> [!NOTE]
> Asigurați-vă că numărul de înregistrări din segmentul exportat se încadrează în limita permisă a licenței dvs. Adobe Campaign Standard.

Datele exportate sunt stocate în containerul de Stocare bloburi Azure pe care l-ați configurat mai sus. Următoarea cale a folderului este creată automat în container:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Configurați Adobe Campaign Standard

Segmentele exportate conțin coloanele pe care le-ați selectat în timp ce definiți destinația de export la pasul anterior. Aceste date pot fi utilizate pentru a [crea profiluri în Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Pentru a utiliza segmentul în Adobe Campaign Standard, trebuie să extindem schema de profil în Adobe Campaign Standard pentru a include două câmpuri suplimentare. Aflați cum să [extindeți resursa profilului](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) cu câmpuri noi în Adobe Campaign Standard.

În exemplul nostru, aceste câmpuri sunt *Numele segmentului și data segmentului (opțional)*.

Vom folosi aceste câmpuri pentru a identifica profilurile din Adobe Campaign Standard pe care dorim să o vizăm pentru această campanie.

Dacă nu există alte înregistrări în Adobe Campaign Standard, în afară de ceea ce urmează să importați, puteți sări peste acest pas.

## <a name="import-data-into-adobe-campaign-standard"></a>Importați date în Adobe Campaign Standard

Acum că totul este la locul său, trebuie să importăm datele de audiență pregătite din Customer Insights în Adobe Standard de campanie pentru a crea profiluri. Învățați [cum să importați profiluri în Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) folosind un flux de lucru.

Fluxul de lucru de import din imaginea de mai jos a fost configurat să ruleze la fiecare opt ore și să caute segmente de Customer Insights exportate (fișier .csv în Azure Blob Storage). Fluxul de lucru extrage conținutul fișierului .csv într-o ordine de coloane specificată. Acest flux de lucru a fost creat pentru a efectua tratarea erorilor de bază și pentru a se asigura că fiecare înregistrare are o adresă de e-mail înainte de a hidrata datele în Adobe Campaign Standard. Fluxul de lucru extrage și numele segmentului din numele fișierului înainte de a fi introdus în datele de profil Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captură de ecran a unui flux de lucru de import în interfața de utilizator Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Recuperați publicul în Adobe Campaign Standard

Odată ce datele sunt importate în Adobe Campaign Standard, [puteți crea un flux de lucru](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) și [interoga](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) clienții pe baza *Nume segment* și *Data segmentului* pentru a selecta profilurile care au fost identificate pentru eșantionul nostru de campanie.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Creați și trimiteți e-mailul utilizând Adobe Campaign Standard

Creați conținutul e-mailului și apoi [testați și trimiteți](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email-ul dvs.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exemplu de e-mail cu ofertă de reînnoire de la Adobe Campaign Standard.":::
