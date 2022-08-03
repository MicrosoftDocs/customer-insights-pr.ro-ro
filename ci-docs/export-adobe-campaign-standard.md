---
title: Exportați segmentele Customer Insights către Adobe Standard de campanie (previzualizare)
description: Aflați cum utilizați segmentele Customer Insights în Adobe Standard de campanie.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195535"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Exportați segmentele Customer Insights către Adobe Standard de campanie (previzualizare)

Exportați segmente care vizează publicurile relevante către Adobe Standard de campanie.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de proces a pașilor descriși în acest articol.":::

## <a name="prerequisites"></a>Cerințe preliminare

- Un Adobe Licență standard pentru campanie.
- Un [Cont Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) nume și cheie de cont. Pentru a găsi numele și cheia, consultați [Gestionați setările contului de stocare în portalul Azure](/azure/storage/common/storage-account-manage).
- Un [Container Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Prezentare generală de campanie

Pentru a înțelege mai bine cum puteți utiliza segmente din Customer Insights în Adobe Experience Platform, să ne uităm la un exemplu de campanie fictiv.

Să presupunem că compania dvs. oferă clienților dvs. din Statele Unite un serviciu lunar, bazat pe abonament. Doriți să identificați clienții ale căror abonamente trebuie reînnoite în următoarele opt zile, dar nu și-au reînnoit abonamentul. Pentru a păstra acești clienți, doriți să le trimiteți o ofertă promoțională prin e-mail, folosind Adobe Campaign Standard.

În acest exemplu, dorim să derulăm o dată campania de e-mail promoțională. Acest articol nu acoperă cazul de utilizare al desfășurării campaniei de mai multe ori. Cu toate acestea, Customer Insights și Adobe Campaign Standard poate fi configurat să funcționeze și pentru un scenariu de campanie recurentă.

## <a name="identify-your-target-audience"></a>Identificați-vă publicul țintă

În scenariul nostru, presupunem că adresele de e-mail ale clienților sunt disponibile în Customer Insights și preferințele lor promoționale au fost analizate pentru a identifica membrii segmentului.

The [segment pe care l-ați definit în Customer Insights](segments.md) se numește **ChurnProneCustomers** și intenționați să trimiteți acestor clienți promoția prin e-mail.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captură de ecran a paginii segmente cu segmentul ChurnProneCustomers creat.":::

E-mailul de ofertă pe care doriți să îl trimiteți va conține prenume, nume de familie, și data de încheiere a abonamentului clientului. Acesta informează clienții despre reducerea pe care o vor primi dacă își reînnoiesc abonamentul înainte de a se încheia.

## <a name="export-your-target-audience"></a>Expportați-vă publicul țintă

### <a name="set-up-connection-to-adobe-campaign"></a>Configurați conexiunea la Adobe Campanie

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Adobe Campanie**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți **Nume de cont**, **de cont**, și **Container** pentru contul dvs. de stocare blob.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captură de ecran a configurării contului de stocare. ":::

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Salvare** pentru a finaliza conexiunea.

### <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea Adobe Campaign. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. Alegeți segmentul pe care doriți să îl exportați. În acest exemplu, este **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captură de ecran a interfeței de selectare a segmentului cu segmentul ChurnProneCustomers selectat.":::

1. Selectați **Următorul**.

1. Harta **Sursă** câmpuri de la segmentul Customer Insights la **Ţintă** numele câmpurilor în Adobe Schema profilului standard al campaniei.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Maparea câmpului pentru conectorul Adobe Campaign Standard.":::

   Dacă doriți să adăugați mai multe atribute, selectați **Adăugați un atribut**. Numele țintă poate fi diferit de numele câmpului sursă, astfel încât să puteți mapa în continuare ieșirea segmentului din Customer Insights către Adobe Standard de campanie dacă câmpurile nu au același nume în cele două sisteme.

   > [!NOTE]
   > Adresa de e-mail este folosită ca câmp de identitate, dar puteți utiliza orice alt identificator din profilul clientului pentru a mapa datele Adobe Standard de campanie.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Asigurați-vă că numărul de înregistrări din segmentul exportat se încadrează în limita permisă a licenței dvs. Adobe Campaign Standard.

Datele exportate sunt stocate în containerul de Stocare bloburi Azure pe care l-ați configurat mai sus. Următoarea cale de folder este creată automat în containerul dvs.:*%ContainerName% /CustomerInsights_%instanceID% /% exportdestination-name%_%segmentname%_%timestamp% .csv*

Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Configurați Adobe Campaign Standard

Segmentele exportate conțin coloanele pe care le-ați selectat la configurarea exportului. Aceste date pot fi utilizate pentru a [crea profiluri în Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Pentru a utiliza segmentul în Adobe Standard de campanie, [extinde schema profilului](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) în Adobe Standardul campaniei să includă două câmpuri suplimentare.

În exemplul nostru, aceste câmpuri sunt Numele segmentului și Data segmentului. Vom folosi aceste câmpuri pentru a identifica profilurile din Adobe Campaign Standard pe care dorim să o vizăm pentru această campanie.

Dacă nu există alte înregistrări în Adobe Standardul campaniei, în afară de ceea ce urmează să importați, săriți peste acest pas.

## <a name="import-data-into-adobe-campaign-standard"></a>Importați date în Adobe Campaign Standard

Importați datele de audiență pregătite din Customer Insights în Adobe Standard de campanie la [creați profiluri folosind un flux de lucru](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Fluxul de lucru de import din imaginea de mai jos a fost configurat să ruleze la fiecare opt ore și să caute segmente de Customer Insights exportate (fișier .csv în Azure Blob Storage). Fluxul de lucru extrage conținutul fișierului .csv într-o ordine de coloane specificată. Acest flux de lucru a fost creat pentru a efectua tratarea erorilor de bază și pentru a se asigura că fiecare înregistrare are o adresă de e-mail înainte de a hidrata datele în Adobe Campaign Standard. Fluxul de lucru extrage și numele segmentului din numele fișierului înainte de a fi introdus în datele de profil Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captură de ecran a unui flux de lucru de import în interfața de utilizator Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Recuperați publicul în Adobe Campaign Standard

Odată ce datele sunt importate în Adobe Standard de campanie, [creați un flux de lucru](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) și [interogare](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) clienții pe baza numelui segmentului și a datei segmentului pentru a selecta profilurile care au fost identificate pentru campania noastră eșantion.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Creați și trimiteți e-mailul utilizând Adobe Campaign Standard

Creați conținutul e-mailului și apoi [testați și trimiteți](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email-ul dvs.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exemplu de e-mail cu ofertă de reînnoire de la Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
