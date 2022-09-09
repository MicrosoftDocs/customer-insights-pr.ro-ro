---
title: Lucrul cu Customer Insights în Microsoft Dataverse
description: Aflați cum să conectați Customer Insights și Microsoft Dataverse și înțelegeți entitățile de ieșire care sunt exportate în Dataverse.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: dfa63110fc5291f2b63aebf588d6fdd20ed4ab67
ms.sourcegitcommit: 134aac66e3e0b77b2e96a595d6acbb91bf9afda2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/07/2022
ms.locfileid: "9424324"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Lucrul cu Customer Insights în Microsoft Dataverse

Customer Insights oferă opțiunea de a face entitățile de ieșire disponibile în [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Această integrare permite partajarea ușoară a datelor și dezvoltarea personalizată printr-o abordare cu cod redus/fără cod. The [entități de ieșire](#output-entities) sunt disponibile ca tabele în a Dataverse mediu inconjurator. Puteți utiliza datele pentru orice altă aplicație bazată pe Dataverse Mese. Aceste tabele permit scenarii precum fluxuri de lucru automate Power Automate sau construirea de aplicații cu Power Apps.

Conectarea la dvs Dataverse mediul vă permite de asemenea [ingerați date din sursele de date local folosind Power Platform fluxuri de date și gateway-uri](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Cerințe preliminare

- Informații despre clienți și Dataverse mediile trebuie să fie găzduite în aceeași regiune.
- Un rol de administrator global configurat în Dataverse mediu inconjurator. Verificați dacă acest lucru [Dataverse mediu este asociat](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) la anumite grupuri de securitate și asigurați-vă că sunteți adăugat la acele grupuri de securitate.
- Niciun alt mediu Customer Insights nu este deja asociat cu Dataverse mediul pe care doriți să îl conectați. Învață cum să [eliminați o conexiune existentă la a Dataverse mediu inconjurator](#remove-an-existing-connection-to-a-dataverse-environment).
- A Microsoft Dataverse mediu conectat la un singur cont de stocare dacă configurați mediul pentru [foloseste-ti Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse dreptul la capacitate de stocare

Un abonament Customer Insights vă dă dreptul la capacitate suplimentară pentru organizația dvs. existentă [Dataverse Capacitate de stocare](/power-platform/admin/capacity-storage). Capacitatea adăugată depinde de numărul de profiluri pe care le folosește abonamentul.

**Exemplu:**

Presupunând că obțineți 15 GB de stocare a bazei de date și 20 GB de stocare a fișierelor la 100.000 de profiluri de clienți. Dacă abonamentul include 300.000 de profiluri de clienți, capacitatea de stocare totală este de 45 GB (3 x 15 GB) de stocare a bazei de date și 60 GB de stocare a fișierelor (3 x 20 GB). În mod similar, dacă aveți un abonament B-to-B cu 30K conturi, capacitatea dvs. totală de stocare este de 45 GB (3 x 15 GB) de stocare a bazei de date și 60 GB de stocare a fișierelor (3 x 20 GB).

Capacitatea de jurnal nu este incrementală și fixă pentru organizația dvs.

Pentru mai multe informații despre drepturile detaliate privind capacitatea, consultați [Ghid de licențiere Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Conectați a Dataverse mediu pentru Customer Insights

The **Microsoft Dataverse** pasul vă permite să conectați Customer Insights cu dvs Dataverse mediu în timp ce [crearea unui mediu Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="partajarea datelor cu Microsoft Dataverse activat automat pentru medii noi.":::

1. Furnizați adresa URL a dvs Dataverse mediu sau lăsați necompletat pentru a avea unul creat pentru dvs.

   > [!NOTE]
   > După stabilirea conexiunii dintre Customer Insights și Dataverse, nu schimbați numele organizației pentru Dataverse mediu inconjurator. Numele organizației este folosit în Dataverse Adresa URL și un nume schimbat întrerup conexiunea cu Customer Insights.

   [Power Platform administratorii pot controla cine poate crea un nou Dataverse medii](/power-platform/admin/control-environment-creation). Dacă încercați să configurați un nou mediu Customer Insights și nu puteți, este posibil ca administratorul să fi dezactivat crearea de Dataverse medii pentru toată lumea, cu excepția administratorilor.

1. Dacă utilizați propriul cont data lake storage:
   1. Selectați **Activați partajarea** datelor cu Dataverse.
   1. Introduceți identificatorul **permisiunilor**. Pentru a obține identificatorul de permisiune, [activați partajarea datelor cu Dataverse de la propriul dvs Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Activați partajarea datelor cu Dataverse de pe cont propriu Azure Data Lake Storage (previzualizare)

În [propriul Azure Data Lake Storage cont](own-data-lake-storage.md), verificați dacă utilizatorul care configurează mediul Customer Insights are cel puțin **permisiuni de stocare Blob Data Reader** pe containerul din `customerinsights` contul de stocare.

### <a name="limitations"></a>Limitări

- Doar maparea unu-la-unu între o Dataverse organizație și un Azure Data Lake Storage cont. Odată ce o Dataverse organizație este conectată la un cont de stocare, aceasta nu se poate conecta la un alt cont de stocare. Această limitare Dataverse împiedică popularea mai multor conturi de stocare.
- Partajarea datelor nu va funcționa dacă este necesară o configurare Azure Private Link pentru a vă Azure Data Lake Storage accesa contul, deoarece se află în spatele unui paravan de protecție. Dataverse în prezent, nu acceptă conexiunea la puncte finale private prin Private Link.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Configurarea grupurilor de securitate pe cont propriu Azure Data Lake Storage

1. Creați două grupuri de securitate pe abonamentul Azure - un **grup de securitate Reader** și un **grup de securitate Contributor** și setați Microsoft Dataverse serviciul ca proprietar pentru ambele grupuri de securitate.

1. Gestionați lista de control al accesului (ACL) din containerul din `customerinsights` contul de stocare prin aceste grupuri de securitate.
   1. Microsoft Dataverse Adăugați serviciul și orice Dataverse aplicații de business bazate pe, cum ar fi Dynamics 365 Marketing, la **grupul de securitate Reader** cu **permisiuni doar în** citire.
   1. Adăugați *numai* aplicația Customer Insights la **grupul de securitate Contributor** pentru a acorda atât permisiuni de citire, cât **și de scriere** pentru a scrie profiluri și detalii.

### <a name="set-up-powershell"></a>Configurarea PowerShell

Configurați PowerShell pentru a executa scripturi PowerShell.

1. Instalați cea mai recentă versiune de [Azure Active Directory PowerShell pentru Graph](/powershell/azure/active-directory/install-adv2).
   1. Pe computer, selectați tasta Windows de pe tastatură și căutați **Windows PowerShell** și selectați **Rulat ca administrator**.
   1. În fereastra PowerShell care se deschide, introduceți `Install-Module AzureAD`.

1. Importați trei module.
   1. În fereastra PowerShell, introduceți `Install-Module -Name Az.Accounts` și urmați pașii.
   1. Repetați pentru `Install-Module -Name Az.Resources` și `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Executarea scripturilor PowerShell și obținerea identificatorului de permisiune

1. Descărcați cele două scripturi PowerShell de care aveți nevoie pentru a rula de la repo-ul [GitHub al inginerului](https://github.com/trin-msft/byol) nostru.
   - `CreateSecurityGroups.ps1`: Necesită permisiuni de administrator de entitate găzduită.
   - `ByolSetup.ps1`: Necesită permisiuni de stocare Blob data owner la nivel de cont de stocare / container. Acest script va crea permisiunea pentru tine. Atribuirea rolurilor poate fi eliminată manual după executarea cu succes a scriptului.

1. Executați `CreateSecurityGroups.ps1` în Windows PowerShell furnizând ID-ul de abonament Azure care conține .Azure Data Lake Storage Deschideți scriptul PowerShell într-un editor pentru a revizui informațiile suplimentare și logica implementată.

   Acest script creează două grupuri de securitate pentru abonamentul Azure: unul pentru grupul Reader și altul pentru grupul Contribuitor. Microsoft Dataverse serviciul este proprietarul pentru ambele aceste grupuri de securitate.

1. Salvați ambele valori ID de grup de securitate generate de acest script pentru a utiliza în script-ul `ByolSetup.ps1`.

   > [!NOTE]
   > Crearea grupului de securitate poate fi dezactivată pe entitatea găzduită. În acest caz, ar fi necesară o configurare manuală și Azure AD administratorul ar trebui să [activeze crearea](/azure/active-directory/enterprise-users/groups-self-service-management) grupului de securitate.

1. Executați `ByolSetup.ps1` în Windows PowerShell furnizând ID-ul de abonament Azure care conține numele contului de Azure Data Lake Storage stocare, numele grupului de resurse și valorile ID-ului de grup de securitate Reader și Contributor. Deschideți scriptul PowerShell într-un editor pentru a revizui informațiile suplimentare și logica implementată.

   Acest script adaugă controlul de acces bazat pe roluri necesar pentru Microsoft Dataverse serviciu și orice Dataverse aplicații de afaceri bazate pe. De asemenea, actualizează lista de control al accesului (ACL) din `customerinsights` container pentru grupurile de securitate create cu scriptul `CreateSecurityGroups.ps1`. Grupului Contributor i se acordă *permisiunea rwx*, iar grupului Cititori i se acordă *numai permisiunea r-x*.

1. Copiați șirul de ieșire care arată astfel: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Introduceți șirul de ieșire copiat în **câmpul Identificator** de permisiuni al pasului de configurare a mediului pentru Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opțiuni de configurare pentru a permite partajarea datelor de pe cont propriu Azure Data Lake Storage cu Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Eliminarea unei conexiuni existente la un Dataverse mediu

Atunci când vă conectați la un Dataverse mediu, mesajul **de eroare Această organizație CDS este deja atașată la o altă instanță** Customer Insights înseamnă că Dataverse mediul este deja utilizat într-un mediu Customer Insights. Aveți posibilitatea să eliminați conexiunea existentă ca administrator global pe Dataverse mediu. Poate dura câteva ore pentru a popula modificările.

1. Salt la [Power Apps](https://make.powerapps.com).
1. Selectați mediul din selectorul de mediu.
1. Accesați **Soluții**.
1. Dezinstalați sau ștergeți soluția numită **Dynamics 365 Customer Insights Program de completare card client (Previzualizare)**.

SAU

1. Deschideți mediul Dataverse.
1. Accesați **Soluții** > **de setări** avansate.
1. Dezinstalați soluția **CustomerInsightsCustomerCard**.

Dacă eliminarea conexiunii nu reușește din cauza dependențelor, trebuie să eliminați și dependențele. Pentru mai multe informații, consultați [Eliminarea dependențelor](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Entități de ieșire

Unele entități de ieșire din Customer Insights sunt disponibile ca tabele în Dataverse. Secțiunile de mai jos descriu schema așteptată a acestor tabele.

- [Profil client](#customerprofile)
- [Profil contact](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Îmbogățire](#enrichment)
- [Predicția](#prediction)
- [Apartenența la segment](#segment-membership)

### <a name="customerprofile"></a>Profil client

Acest tabel conține profilul de client unificat de la Customer Insights. Schema pentru un profil de client unificat depinde de entitățile și atributele utilizate în procesul de unificare a datelor. O schemă de profil client conține de obicei un subset de atribute din [Definiția Common Data Model a CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). Pentru scenariul B-la-B, profilul de client conține conturi unificate și schema conține, de obicei, un subset de atribute din [definiția common data model de cont](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account).

### <a name="contactprofile"></a>Profil contact

Un ContactProfile conține informații unificate despre o persoană de contact. Persoanele de contact sunt [persoane care sunt mapate la un cont](data-unification-contacts.md) într-un scenariu B-la-B.

| Column                       | Tipul                | Descriere     |
| ---------------------------- | ------------------- | --------------- |
|  Data nașterii            | DateTime       |  Data nașterii persoanei de contact               |
|  Oraș                 | SMS |  Orașul adresei de contact               |
|  ContactId            | SMS |  ID-ul profilului de contact               |
|  ContactProfileId     | Identificator unic   |  GUID pentru persoana de contact               |
|  ȚarăOrRegiune      | SMS |  Țara/Regiunea adresei de contact               |
|  CustomerId           | SMS |  ID-ul contului la care este mapată persoana de contact               |
|  EntityName           | SMS |  Entitatea de la care provin datele                |
|  FirstName            | SMS |  Prenume contactului               |
|  Gen               | SMS |  Sexul contactului               |
|  Id                   | SMS |  GUID determinist bazat pe`Identifier`               |
|  Identifier           | SMS |  ID-ul intern al profilului de contact: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | SMS |  Titlul postului persoanei de contact               |
|  LastName             | SMS |  Nume de familie persoanei de contact               |
|  PostalCode           | SMS |  Codul poștal al adresei de contact               |
|  PrimaryEmail         | SMS |  Adresa de e-mail a persoanei de contact               |
|  PrimaryPhone         | SMS |  Numărul de telefon al persoanei de contact               |
|  JudețSauProvincie      | SMS |  Statul sau provincia adresei de contact               |
|  StreetAddress        | SMS |  Strada adresei de contact               |

### <a name="alternatekey"></a>AlternateKey

Tabelul AlternateKey conține chei ale entităților, care au participat la procesul de unificare.

|Column  |Tipul  |Descriere  |
|---------|---------|---------|
|DataSourceName    |SMS         | Numele pentru sursa de date. De exemplu: `datasource5`        |
|EntityName        | SMS        | Numele entității în Customer Insights. De exemplu: `contact1`        |
|AlternateValue    |SMS         |ID alternativ care este mapat la ID-ul clientului. Exemplu: `cntid_1078`         |
|KeyRing           | SMS        | Valoare JSON  </br> Eșantion: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | SMS        | ID-ul profilului de client unificat.         |
|AlternateKeyId     | Identificator unic        |  AlternateKey GUID determinist bazat pe`Identifier`      |
|Identifier |   SMS      |   `DataSourceName|EntityName|AlternateValue`  </br> Eșantion: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Acest tabel conține activități ale utilizatorilor care sunt disponibile în Customer Insights.

| Column            | Tipul        | Descriere                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | SMS      | ID de profil client                                                                      |
| ActivityId        | SMS      | ID-ul intern al activității clienților (cheie primară)                                       |
| SourceEntityName  | SMS      | Nume al entității sursă                                                                |
| SourceActivityId  | SMS      | Cheie primară de la entitatea sursă                                                       |
| ActivityType      | SMS      | Tipul activității semantice sau numele activității particularizate                                        |
| ActivityTimeStamp | DateTime    | Marca timpului de activitate                                                                      |
| Funcție             | SMS      | Titlul sau numele activității                                                               |
| Descriere       | SMS      | Descrierea activității                                                                     |
| Adresă URL               | SMS      | Link către o adresă URL externă specifică activității                                         |
| SemanticData      | SMS | Include o listă de perechi de valori cheie pentru câmpurile de mapare semantică specifice tipului de activitate |
| RangeIndex        | SMS      | Marca de timp Unix utilizată pentru sortarea cronologiei activității și a interogărilor eficiente asupra intervalului |
| UnifiedActivityId   | Identificator unic | ID-ul intern al activității clienților (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Acest tabel conține datele de ieșire ale măsurilor bazate pe atribute ale clienților.

| Column             | Tipul             | Descriere                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | SMS           | ID de profil client        |
| Măsuri           | SMS      | Include o listă de perechi de valori cheie pentru numele măsurii și valorile pentru clientul dat |
| Identifier | SMS           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | Identificator unic     | ID de profil client |

### <a name="enrichment"></a>Îmbogățire

Acest tabel conține rezultatul procesului de îmbogățire.

| Column               | Tipul             |  Descriere                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | SMS           | ID de profil client                                 |
| EnrichmentProvider   | SMS           | Numele furnizorului pentru îmbogățire                                  |
| EnrichmentType       | SMS           | Tipul de îmbogățire                                      |
| Valori               | SMS      | Lista atributelor produse de procesul de îmbogățire |
| EnrichmentId | Identificator unic            | GUID determinist generat de la`Identifier` |
| Identifier   | SMS           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predicția

Acest tabel conține rezultatul predicțiilor modelelor.

| Column               | Tipul        | Descriere                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | SMS      | ID de profil client                                  |
| ModelProvider        | SMS      | Numele furnizorului modelului                                      |
| Model                | SMS      | Nume model                                                |
| Valori               | SMS | Lista atributelor produse de model |
| PredictionId | Identificator unic       | GUID determinist generat de la`Identifier` |
| Identifier   | SMS      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Apartenența la segment

Acest tabel conține informații despre apartenența la segment a profilurilor de client.

| Column        | Tipul | Descriere                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | SMS       | ID de profil client        |
| SegmentProvider      | SMS       | Aplicație care publică segmentele.      |
| SegmentMembershipType | SMS       | Tipul de client pentru această înregistrare de membru segment. Acceptă mai multe tipuri, cum ar fi Client, Persoană de contact sau Cont. Implicit: Client  |
| Segmente       | SMS  | Lista segmentelor unice din care face parte profilul clientului      |
| Identifier  | SMS   | Identificator unic al înregistrării apartenenței la segment. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | Identificator unic      | GUID determinist generat de la`Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
