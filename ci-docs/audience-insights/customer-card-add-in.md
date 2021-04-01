---
title: Instalați și configurați Programul de completare card client
description: Instalarea și configurarea programului de completare card client pentru Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f3c4a01f9ce7749eeee72f7901620dae7cb9b8d3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597342"
---
# <a name="customer-card-add-in-preview"></a>Program de completare card client (previzualizare)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Obțineți o vizualizare la 360 de grade a clienților dvs. direct în aplicațiile Dynamics 365. Vizualizați datele demografice, informațiile și cronologiile de activitate cu ajutorul programului de completare card client.

## <a name="prerequisites"></a>Cerințe preliminare

- Aplicația Dynamics 365 (cum ar fi Hub de vânzări sau Hub de servicii pentru clienți), versiunea 9.0 și ulterior cu Interfață unificată activată.
- Profilurile clienților [ingerate din aplicația Dynamics 365 folosind Common Data Service](connect-power-query.md).
- Utilizatorii programului de completare card client trebuie să fie [adăugați ca utilizatori](permissions.md) în Detalii despre audiență.
- [Capabilități de căutare și filtrare configurate](search-filter-index.md).
- Control demografic: câmpurile demografice (cum ar fi vârsta sau sexul), sunt disponibile în profilul de client unificat.
- Controlul îmbogățirii: necesită [îmbogățiri](enrichment-hub.md) active aplicate profilurilor clienților.
- Control inteligent: Necesită date generate în Azure Machine Learning ([Predicții](predictions.md) sau [Modele particularizate](custom-models.md))
- Controlul măsurii: Necesită [măsuri configurate](measures.md).
- Controlul cronologiei: Necesită [activități configurate](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instalați suplimentul cardului client

Adăugarea programului de completare Card client este o soluție pentru aplicațiile de implicare a clienților din Dynamics 365. Pentru a instala soluția, accesați AppSource și căutați **Card de client Dynamics**. Selectați [Programul de completare card de client AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) și selectați **Obțineți acum**.

Este posibil să fie nevoie să vă autentificați cu datele dvs. de acreditare pentru aplicația Dynamics 365 pentru a instala soluția.

Poate dura ceva timp pentru ca soluția să fie instalată în mediul dvs.

## <a name="configure-the-customer-card-add-in"></a>Configurați programul de completare pentru card client

1. În calitate de administrator, accesați secțiunea **Setări** din Dynamics 365 și selectați **Soluții**.

1. Selectați legătura **Nume afișat** pentru soluția **Dynamics 365 Customer Insights Program de completare card client (Previzualizare)**.

   > [!div class="mx-imgBorder"]
   > ![Selectați numele afișat](media/select-display-name.png "Selectați numele afișat")

1. Selectați **Conectare** și introduceți acreditările pentru contul de administrator pe care îl utilizați pentru a configura Customer Insights.

   > [!NOTE]
   > Verificați dacă funcția de blocare a ferestrelor pop-up a browserului nu blochează fereastra de autentificare atunci când selectați butonul **Conectare**.

1. Selectați mediul de la care doriți să preluați date.

1. Definiți maparea câmpului către înregistrări în aplicația Dynamics 365.
   - Pentru a mapa un contact, selectați câmpul din entitatea Client care se potrivește cu ID-ul entității dvs. de contact.
   - Pentru a mapa un cont, selectați câmpul din entitatea Client care se potrivește cu ID-ul entității dvs. de cont.

   > [!div class="mx-imgBorder"]
   > ![Câmpul ID persoană de contact](media/contact-id-field.png "Câmpul ID persoană de contact")

1. Selectați **Salvare configurație** pentru a salva setările.

1. În continuare, trebuie să atribuiți roluri de securitate în Dynamics 365, astfel încât utilizatorii să poată personaliza și vedea cardul de client. În Dynamics 365, accesați **Setări** > **Securitate** > **Utilizatori**. Selectați utilizatorii pentru a edita rolurile utilizatorului și selectați **Gestionați roluri**.

1. Atribuiți rolul **Utilizator standard card Customer Insights** pentru utilizatorii care vor personaliza conținutul afișat pe card pentru întreaga organizație.

## <a name="add-customer-card-controls-to-forms"></a>Adăugare controale Card client la formulare
  
1. Pentru a adăuga controale pentru cardul clientului în formularul dvs. de contact, accesați secțiunea **Setări** > **Particularizări** în Dynamics 365.

1. Selectați **Particularizați sistemul**.

1. Navigați la entitatea **Persoană de contact**, extindeți-o și selectați **Formulare**.

1. Selectați formularul de contact la care doriți să adăugați controalele Card client.

    > [!div class="mx-imgBorder"]
    > ![Selectați formularul de contact](media/contact-active-forms.png "Selectați formularul de contact")

1. Pentru a adăuga un control, în editorul de formulare, trageți orice câmp din **Exploratorul de câmp** în locul în care doriți să apară controlul.

1. Selectați câmpul pe formularul pe care tocmai l-ați adăugat și selectați **Modificare proprietăți**.

1. Accesați fila **Controale** și selectați **Adăugare control**. Alegeți unul dintre controalele particularizate disponibile și selectați **Adăugați**.

1. În caseta de dialog **Proprietăți câmp**, debifați caseta de selectare **Afișare etichetă pe formular**.

1. Selectați opțiunea **Web** pentru control. Pentru controlul Îmbogățire, selectați tipul de îmbogățire pe care doriți să-l afișați configurand câmpul **enrichmentType**. Adăugați un control separat de îmbogățire pentru fiecare tip de îmbogățire.

1. Selectați **Salvați** și **Publicați** pentru a publica formularul de contact actualizat.

1. Accesați formularul de contact publicat. Veți vedea controlul nou adăugat. Este posibil să fie nevoie să vă conectați, prima dată când îl utilizați.

1. Pentru a particulariza ceea ce doriți să afișați în controlul particularizat, selectați butonul de editare din colțul din dreapta sus.

## <a name="upgrade-customer-card-add-in"></a>Faceți upgrade la programul de completare Customer Card
Programul de completare pentru Customer Card nu se actualizează automat. Pentru a face upgrade la cea mai recentă versiune, urmați această procedură în aplicația Dynamics 365 care are instalat programul de completare.

1. În aplicația Dynamics 365, accesați **Setări** > **Particularizare** și selectați **Soluții**.

1. În tabelul cu programe de completare căutați **CustomerInsightsCustomerCard** și selectați rândul.

1. Selectați **Aplicați actualizarea soluției** în bara de acțiune.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Actualizați soluția în zona de particularizare a aplicațiilor Dynamics 365":::

1. După ce începeți procesul de actualizare, veți vedea un indicator de încărcare până la finalizarea actualizării. Dacă nu există o versiune mai nouă, actualizarea va afișa un mesaj de eroare.


[!INCLUDE[footer-include](../includes/footer-banner.md)]