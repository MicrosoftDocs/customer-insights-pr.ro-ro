---
title: Lucrul cu Customer Insights în Microsoft Dataverse
description: Aflați cum să conectați Customer Insights și Microsoft Dataverse și înțelegeți entitățile de ieșire care sunt exportate în Dataverse.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 0d536259f310b41fe12922baeebdc4569937db08
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303844"
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

1. Dacă utilizați propriul cont Data Lake Storage:
   1. Selectați **Activați partajarea datelor** cu Dataverse.
   1. Introduceți **Identificator de permisiuni**. Pentru a obține identificatorul de permisiune, [activați partajarea datelor cu Dataverse din a ta Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Activați partajarea datelor cu Dataverse din a ta Azure Data Lake Storage (previzualizare)

În [al tau Azure Data Lake Storage cont](own-data-lake-storage.md), verificați dacă utilizatorul care configurează mediul Customer Insights are cel puțin **Cititor de date Blob de stocare** permisiuni pe`customerinsights` container în contul de depozitare.

### <a name="limitations"></a>Limitări

- Doar mapare unu-la-unu între a Dataverse organizaţie şi an Azure Data Lake Storage cont. Odata Dataverse organizația este conectată la un cont de stocare, nu se poate conecta la un alt cont de stocare. Această limitare împiedică Dataverse de la popularea mai multor conturi de stocare.
- Partajarea datelor nu va funcționa dacă este necesară o configurare Azure Private Link pentru a vă accesa Azure Data Lake Storage cont pentru că se află în spatele unui firewall. Dataverse momentan nu acceptă conexiunea la punctele finale private prin Private Link.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Configurați singur grupuri de securitate Azure Data Lake Storage

1. Creați două grupuri de securitate pe abonamentul dvs. Azure - unul **Cititor** grup de securitate și unul **Colaborator** grup de securitate și setați Microsoft Dataverse serviciu ca proprietar pentru ambele grupuri de securitate.

1. Gestionați Lista de control al accesului (ACL) pe`customerinsights` container în contul dvs. de stocare prin aceste grupuri de securitate.
   1. Adaugă Microsoft Dataverse serviciu și orice Dataverse aplicații de afaceri bazate pe Dynamics 365 Marketing la **Cititor** grup de securitate cu **numai pentru citire** permisiuni.
   1. Adăuga *numai* aplicația Customers Insights la **Colaborator** grupului de securitate să le acorde pe ambele **Citeste si scrie** permisiuni de a scrie profiluri și informații.

### <a name="set-up-powershell"></a>Configurați PowerShell

Configurați PowerShell pentru a executa scripturi PowerShell.

1. Instalați cea mai recentă versiune a [Azure Active Directory PowerShell pentru Graph](/powershell/azure/active-directory/install-adv2).
   1. Pe computer, selectați tasta Windows de pe tastatură și căutați **Windows PowerShell** și selectați **Rulat ca administrator**.
   1. În fereastra PowerShell care se deschide, introduceți `Install-Module AzureAD`.

1. Importă trei module.
   1. În fereastra PowerShell, introduceți`Install-Module -Name Az.Accounts` și urmați pașii.
   1. Repetați pentru`Install-Module -Name Az.Resources` și `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Executați scripturi PowerShell și obțineți identificatorul de permisiune

1. Descărcați cele două scripturi PowerShell de care aveți nevoie pentru a rula de la inginerul nostru [Repoziție GitHub](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: Necesită permisiuni de administrator al locatarului.
   - `ByolSetup.ps1`: necesită permisiuni de proprietar de date blob de stocare la nivel de cont/container de stocare. Acest script va crea permisiunea pentru dvs. Atribuirea rolului dvs. poate fi eliminată manual după rularea cu succes a scriptului.

1. A executa`CreateSecurityGroups.ps1` în Windows PowerShell, furnizând ID-ul de abonament Azure care conține dvs Azure Data Lake Storage. Deschideți scriptul PowerShell într-un editor pentru a examina informații suplimentare și logica implementată.

   Acest script creează două grupuri de securitate în abonamentul Azure: unul pentru grupul Reader și altul pentru grupul Contributor. Microsoft Dataverse service este proprietarul pentru ambele grupuri de securitate.

1. Salvați ambele valori ale ID-urilor grupului de securitate generate de acest script pentru a le utiliza în`ByolSetup.ps1` scenariu.

   > [!NOTE]
   > Crearea grupului de securitate poate fi dezactivată pentru chiriașul dvs. În acest caz, ar fi necesară o configurare manuală, iar dvs Azure AD administratorul ar trebui [activați crearea grupului de securitate](/azure/active-directory/enterprise-users/groups-self-service-management).

1. A executa`ByolSetup.ps1` în Windows PowerShell, furnizând ID-ul abonamentului Azure care conține dvs Azure Data Lake Storage, numele contului de stocare, numele grupului de resurse și valorile ID-ului grupului de securitate Reader și Contributor. Deschideți scriptul PowerShell într-un editor pentru a examina informații suplimentare și logica implementată.

   Acest script adaugă controlul de acces bazat pe roluri necesar pentru Microsoft Dataverse serviciu și orice Dataverse aplicații de afaceri bazate pe De asemenea, actualizează Lista de control al accesului (ACL) pe`customerinsights` container pentru grupurile de securitate create cu`CreateSecurityGroups.ps1` scenariu. Se oferă grupul de colaboratori *rwx* se acordă permisiunea și grupul de cititori *rx* numai permisiunea.

1. Copiați șirul de ieșire care arată astfel:`https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Introduceți șirul de ieșire copiat în fișierul **Identificator de permisiuni** câmpul pasului de configurare a mediului pentru Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opțiuni de configurare pentru a activa partajarea datelor de la dvs Azure Data Lake Storage cu Microsoft Dataverse .":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Eliminați o conexiune existentă la a Dataverse mediu inconjurator

Când vă conectați la a Dataverse mediu, mesajul de eroare **Această organizație CDS este deja atașată la o altă instanță Customer Insights** înseamnă că Dataverse mediu este deja utilizat într-un mediu Customer Insights. Puteți elimina conexiunea existentă ca administrator global pe Dataverse mediu inconjurator. Pot dura câteva ore pentru a completa modificările.

1. Salt la [Power Apps](https://make.powerapps.com).
1. Selectați mediul din selectorul de mediu.
1. Mergi la **Soluții**.
1. Dezinstalați sau ștergeți soluția numită **Dynamics 365 Customer Insights Supliment pentru cardul de client (previzualizare)**.

SAU

1. Deschide-ți Dataverse mediu inconjurator.
1. Mergi la **Setari avansate** > **Soluții**.
1. Dezinstalați **CustomerInsightsCustomerCard** soluţie.

Dacă eliminarea conexiunii eșuează din cauza dependențelor, trebuie să eliminați și dependențele. Pentru mai multe informații, vezi [Eliminarea dependențelor](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Entități de ieșire

Unele entități de ieșire din Customer Insights sunt disponibile ca tabele în Dataverse. Secțiunile de mai jos descriu schema așteptată a acestor tabele.

- [Profil client](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Îmbogățire](#enrichment)
- [Predicția](#prediction)
- [Segmentul de membru](#segment-membership)

### <a name="customerprofile"></a>Profil client

Acest tabel conține profilul de client unificat de la Customer Insights. Schema pentru un profil de client unificat depinde de entitățile și atributele utilizate în procesul de unificare a datelor. O schemă de profil client conține de obicei un subset de atribute din [Definiția Common Data Model a CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tabelul AlternateKey conține chei ale entităților, care au participat la procesul de unificare.

|Column  |Tip  |Descriere  |
|---------|---------|---------|
|DataSourceName    |Șir         | Numele pentru sursa de date. De exemplu: `datasource5`        |
|EntityName        | Șir        | Numele entității în Customer Insights. De exemplu: `contact1`        |
|AlternateValue    |Șir         |ID alternativ care este mapat la ID-ul clientului. Exemplu: `cntid_1078`         |
|KeyRing           | Text multilinie        | Valoare JSON  </br> Eșantion: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | Șir        | ID-ul profilului de client unificat.         |
|AlternateKeyId     | GUID         |  GUID determinist AlternateKey bazat pe msdynci_identifier       |
|msdynci_identifier |   Șir      |   `DataSourceName|EntityName|AlternateValue`  </br> Eșantion: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Acest tabel conține activități ale utilizatorilor care sunt disponibile în Customer Insights.

| Column            | Tipul        | Descriere                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Șir      | ID de profil client                                                                      |
| ActivityId        | Șir      | ID-ul intern al activității clienților (cheie primară)                                       |
| SourceEntityName  | Șir      | Nume al entității sursă                                                                |
| SourceActivityId  | Șir      | Cheie primară de la entitatea sursă                                                       |
| ActivityType      | Șir      | Tipul activității semantice sau numele activității particularizate                                        |
| ActivityTimeStamp | DATETIME    | Marca temporală a activității                                                                      |
| Funcție             | Șir      | Titlul sau numele activității                                                               |
| Descriere       | Șir      | Descrierea activității                                                                     |
| URL               | Șir      | Link către o adresă URL externă specifică activității                                         |
| SemanticData      | Șir JSON | Include o listă de perechi de valori cheie pentru câmpurile de mapare semantică specifice tipului de activitate |
| RangeIndex        | Șir      | Marca de timp Unix utilizată pentru sortarea cronologiei activității și a interogărilor eficiente asupra intervalului |
| mydynci_unifiedactivityid   | GUID | ID-ul intern al activității clienților (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Acest tabel conține datele de ieșire ale măsurilor bazate pe atribute ale clienților.

| Column             | Tip             | Descriere                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | Șir           | ID de profil client        |
| Măsuri           | Șir JSON      | Include o listă de perechi de valori cheie pentru numele măsurii și valorile pentru clientul dat | 
| msdynci_identifier | Șir           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ID de profil client |


### <a name="enrichment"></a>Îmbogățire

Acest tabel conține rezultatul procesului de îmbogățire.

| Column               | Tip             |  Descriere                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | Șir           | ID de profil client                                 |
| EnrichmentProvider   | Șir           | Numele furnizorului pentru îmbogățire                                  |
| EnrichmentType       | Șir           | Tipul de îmbogățire                                      |
| Valori               | Șir JSON      | Lista atributelor produse de procesul de îmbogățire |
| msdynci_enrichmentid | GUID             | GUID determinist generat de msdynci_identifier |
| msdynci_identifier   | Șir           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predicția

Acest tabel conține rezultatul predicțiilor modelelor.

| Column               | Tipul        | Descriere                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Șir      | ID de profil client                                  |
| ModelProvider        | Șir      | Numele furnizorului modelului                                      |
| Model                | Șir      | Nume model                                                |
| Valori               | Șir JSON | Lista atributelor produse de model |
| msdynci_predictionid | GUID        | GUID determinist generat de msdynci_identifier | 
| msdynci_identifier   | Șir      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Segmentul de membru

Acest tabel conține informații despre apartenența la segmente ale profilurilor clienților.

| Column        | Tipul | Descriere                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | Șir       | ID de profil client        |
| SegmentProvider      | Șir       | Aplicație care publică segmentele.      |
| SegmentMembershipType | Șir       | Tipul de client pentru înregistrarea de membru al acestui segment. Acceptă mai multe tipuri, cum ar fi Client, Contact sau Cont. Implicit: Client  |
| Segmente       | Șir JSON  | Lista segmentelor unice la care este membru profilul clientului      |
| msdynci_identifier  | Șir   | Identificatorul unic al înregistrării de membru al segmentului. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID determinist generat din`msdynci_identifier`          |


[!INCLUDE [footer-include](includes/footer-banner.md)]
