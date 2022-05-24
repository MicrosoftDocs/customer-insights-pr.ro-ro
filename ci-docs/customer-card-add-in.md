---
title: Supliment pentru cardul de client pentru aplicațiile Dynamics 365 (conține videoclip)
description: Afișați datele despre profilul clientului din Customer Insights în aplicațiile Dynamics 365 cu acest program de completare.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 8508880bb3274bb491a314a043a5222d4d381073
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755651"
---
# <a name="customer-card-add-in-preview"></a>Program de completare card client (previzualizare)

Obțineți o vizualizare la 360 de grade a clienților dvs. direct în aplicațiile Dynamics 365. Cu programul de completare a cardului pentru clienți instalat într-o aplicație Dynamics 365 acceptată, puteți alege să afișați câmpurile de profil ale clienților, informații și cronologia activității. Programul de completare va prelua date din Customer Insights fără a afecta datele din aplicația Dynamics 365 conectată.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Cerințe preliminare

- Programul de completare funcționează numai cu aplicații bazate pe model Dynamics 365, cum ar fi Sales sau Customer Service, versiunea 9.0 și versiunile ulterioare.
- Pentru ca datele dvs. Dynamics 365 să fie mapate la profilurile clienților Customer Insights, vă recomandăm [ingerat din aplicația Dynamics 365 folosind Microsoft Dataverse conector](connect-power-query.md). Dacă utilizați o metodă diferită pentru a asimila contacte (sau conturi) Dynamics 365, trebuie să vă asigurați că`contactid` (sau`accountid`) câmpul este setat ca [cheia primară pentru acel sursă de date în pasul de hartă a procesului de unificare a datelor](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- Toți utilizatorii Dynamics 365 ai suplimentului pentru cardul de client trebuie să fie [adăugat ca utilizatori](permissions.md) în Customer Insights pentru a vedea datele.
- [Capacități de căutare și filtrare configurate](search-filter-index.md) în Customer Insights sunt necesare pentru ca căutarea datelor să funcționeze.
- Fiecare control de supliment se bazează pe date specifice din Customer Insights. Unele date și controale sunt disponibile numai în medii de tipuri specifice. Configurația add-in vă va informa dacă un control nu este disponibil din cauza tipului de mediu selectat. Aflați mai multe despre [cazuri de utilizare a mediului](work-with-business-accounts.md).
  - **Măsurați controlul**: Necesită [măsuri configurate](measures.md) de tipul atributelor clientului.
  - **Controlul inteligenței** : Necesită date generate folosind [predicții sau modele personalizate](predictions-overview.md).
  - **Controlul detaliilor clientului**: Toate câmpurile din profil sunt disponibile în profilul de client unificat.
  - **Control îmbogățire**: solicită [îmbogățiri](enrichment-hub.md) active aplicate profilelor de client. Suplimentul de card acceptă aceste îmbogățiri: [Mărci](enrichment-microsoft.md) furnizat de Microsoft, [Interese](enrichment-microsoft.md) furnizate de Microsoft și [Date despre implicarea biroului](enrichment-office.md) furnizate de Microsoft.
  - **Controlul contactelor**: Necesită definirea entității semantice a contactelor de tip.
  - **Control cronologie**: necesită [activități configurate](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instalați suplimentul cardului client

Adăugarea programului de completare Card client este o soluție pentru aplicațiile de implicare a clienților din Dynamics 365. Pentru a instala soluția, accesați AppSource și căutați **Card de client Dynamics**. Selectați [Programul de completare card de client AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) și selectați **Obțineți acum**.

Este posibil să fie nevoie să vă autentificați cu datele dvs. de acreditare pentru aplicația Dynamics 365 pentru a instala soluția. Poate dura ceva timp pentru ca soluția să fie instalată în mediul dvs.

## <a name="configure-the-customer-card-add-in"></a>Configurați programul de completare pentru card client

1. În calitate de administrator, accesați secțiunea **Setări** din Dynamics 365 și selectați **Soluții**.

1. Selectați legătura **Nume afișat** pentru soluția **Dynamics 365 Customer Insights Program de completare card client (Previzualizare)**.

   > [!div class="mx-imgBorder"]
   > ![Selectați numele afișat.](media/select-display-name.png "Selectați numele afișat.")

1. Selectați **Conectare** și introduceți acreditările pentru contul de administrator pe care îl utilizați pentru a configura Customer Insights.

   > [!NOTE]
   > Verificați dacă funcția de blocare a ferestrelor pop-up a browserului nu blochează fereastra de autentificare atunci când selectați butonul **Conectare**.

1. Selectați mediul Customer Insights de la care doriți să preluați date.

1. Definiți maparea de la câmp la înregistrări în aplicația Dynamics 365. În funcție de datele din Customer Insights, puteți alege să mapați următoarele opțiuni:
   - Pentru a mapa un contact, selectați câmpul din entitatea Client care se potrivește cu ID-ul entității dvs. de contact.
   - Pentru a mapa un cont, selectați câmpul din entitatea Client care se potrivește cu ID-ul entității dvs. de cont.

   > [!div class="mx-imgBorder"]
   > ![Câmpul ID persoană de contact.](media/contact-id-field.png "Câmpul ID persoană de contact.")

1. Selectați **Salvare configurație** pentru a salva setările.

1. În continuare, trebuie să atribuiți roluri de securitate în Dynamics 365, astfel încât utilizatorii să poată personaliza și vedea cardul de client. În Dynamics 365, accesați **Setări** > **Securitate** > **Utilizatori**. Selectați utilizatorii pentru a edita rolurile utilizatorului și selectați **Gestionați roluri**.

1. Atribuiți rolul **Utilizator standard card Customer Insights** pentru utilizatorii care vor personaliza conținutul afișat pe card pentru întreaga organizație.

## <a name="add-customer-card-controls-to-forms"></a>Adăugare controale Card client la formulare

În funcție de scenariul dvs., puteți alege să adăugați controale fie la formularul **Persoană de contact** sau formularul **Cont**. Dacă mediul dvs. Customer Insights este pentru conturi de afaceri, vă recomandăm să adăugați controalele în formularul de cont. În acest caz, înlocuiți „contact” în pașii de mai jos cu „cont”.

1. Pentru a adăuga controale pentru cardul clientului în formularul dvs. de contact, accesați secțiunea **Setări** > **Particularizări** în Dynamics 365.

1. Selectați **Particularizați sistemul**.

1. Navigați la entitatea **Persoană de contact** și extindeți-o și selectați **Formulare**.

1. Selectați formularul de contact la care doriți să adăugați controalele Card client.

    > [!div class="mx-imgBorder"]
    > ![Selectați formularul de contact.](media/contact-active-forms.png "Selectați formularul de contact.")

1. Pentru a adăuga un control, în editorul de formulare, trageți orice câmp din **Exploratorul de câmp** în locul în care doriți să apară controlul.

1. Selectați câmpul pe formularul pe care tocmai l-ați adăugat și selectați **Modificare proprietăți**.

1. Accesați fila **Controale** și selectați **Adăugare control**. Alegeți unul dintre controalele particularizate disponibile și selectați **Adăugați**.

1. În caseta de dialog **Proprietăți câmp**, debifați caseta de selectare **Afișare etichetă pe formular**.

1. Selectați opțiunea **Web** pentru control. Pentru controlul Îmbogățire, selectați tipul de îmbogățire pe care doriți să-l afișați configurand câmpul **enrichmentType**. Adăugați un control separat de îmbogățire pentru fiecare tip de îmbogățire.

1. Selectați **Salvați** și **Publicați** pentru a publica formularul de contact actualizat.

1. Accesați formularul de contact publicat. Veți vedea controlul nou adăugat. Este posibil să fie nevoie să vă conectați, prima dată când îl utilizați.

1. Pentru a particulariza ceea ce doriți să afișați în controlul particularizat, selectați butonul de editare din colțul din dreapta sus.

## <a name="upgrade-customer-card-add-in"></a>Faceți upgrade la programul de completare Customer Card

Programul de completare pentru Customer Card nu se actualizează automat. Pentru a trece la cea mai recentă versiune, urmați acești pași în aplicația Dynamics 365 care are instalat programul de completare.

1. În aplicația Dynamics 365, accesați **Setări** > **Particularizare** și selectați **Soluții**.

1. În tabelul cu programe de completare căutați **CustomerInsightsCustomerCard** și selectați rândul.

1. Selectați **Aplicați actualizarea soluției** în bara de acțiune.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Actualizați soluția în zona de particularizare a aplicațiilor Dynamics 365.":::

1. După ce începeți procesul de actualizare, veți vedea un indicator de încărcare până la finalizarea actualizării. Dacă nu există o versiune mai nouă, actualizarea va afișa un mesaj de eroare.

## <a name="troubleshooting"></a>Depanare

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Comenzile din Add-in-ul pentru cardul de client nu găsesc date

**Problemă:**

Chiar și cu câmpurile de ID configurate corect, controalele nu pot găsi date pentru niciun client.  

**Rezolvare:**

1. Asigurați-vă că ați configurat suplimentul pentru card conform instrucțiunilor: [Configurați suplimentul pentru cardul de client](#configure-the-customer-card-add-in)

1. Examinați configurația pentru absorbția datelor. Editați sursă de date pentru sistemul Dynamics 365 care conține ID-ul de contact GUID. Dacă ID-ul contactului GUID este afișat cu caractere majuscule în Power Query editor, încercați următorii pași:
    1. Editați sursă de date pentru a deschide sursă de date în Power Query Editor.
    1. Selectați coloana ID de contact.
    1. Selectați **Transforma** în bara de antet pentru a vedea acțiunile disponibile.
    1. Selectați **litere mici**. Validați dacă GUID-urile din tabel sunt acum litere mici.
    1. Salvați sursa de date.
    1. Rulați procesele de asimilare, unificare și în aval de date pentru a propaga modificările la GUID.

După ce sistemul a finalizat reîmprospătarea completă, comenzile Add-in pentru cardul de client ar trebui să arate datele așteptate.

[!INCLUDE [footer-include](includes/footer-banner.md)]
