---
title: Lucrul cu Customer Insights în Microsoft Dataverse
description: Aflați cum să conectați Customer Insights și Microsoft Dataverse și înțelegeți entitățile de ieșire care sunt exportate în Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 3848e143bc7cb2f345bc698a274b92148ef00669
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833691"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Lucrul cu Customer Insights în Microsoft Dataverse

Customer Insights oferă opțiunea de a face disponibile entități de ieșire ca [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Această integrare permite partajarea ușoară a datelor și dezvoltarea personalizată printr-o abordare cu cod redus/fără cod. The [entități de ieșire](#output-entities) sunt disponibile ca tabele în a Dataverse mediu inconjurator. Puteți utiliza datele pentru orice altă aplicație bazată pe Dataverse Mese. Aceste tabele permit scenarii precum fluxuri de lucru automate Power Automate sau construirea de aplicații cu Power Apps.

Conectarea la dvs Dataverse mediul vă permite de asemenea [ingerați date din sursele de date local folosind Power Platform fluxuri de date și gateway-uri](data-sources.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Cerințe preliminare

- Informații despre clienți și Dataverse mediile trebuie să fie găzduite în aceeași regiune.
- Trebuie să aveți un rol de administrator global în Dataverse mediu inconjurator. Verificați dacă acest lucru [Dataverse mediu este asociat](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) la anumite grupuri de securitate și asigurați-vă că sunteți adăugat la acele grupuri de securitate.
- Niciun alt mediu Customer Insights nu este deja asociat cu Dataverse mediul pe care doriți să îl conectați. Învață cum să [eliminați o conexiune existentă la a Dataverse mediu inconjurator](#remove-an-existing-connection-to-a-dataverse-environment).
- A Microsoft Dataverse mediul se poate conecta doar la un singur cont de stocare. Se aplică numai dacă configurați mediul la [foloseste-ti Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Conectați a Dataverse mediu pentru Customer Insights

The **Microsoft Dataverse** pasul vă permite să conectați Customer Insights cu dvs Dataverse mediu în timp ce [crearea unui mediu Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="partajarea datelor cu Microsoft Dataverse activat automat pentru medii net noi.":::

Administratorii pot configura Customer Insights pentru a conecta un existent Dataverse mediu inconjurator. Prin furnizarea URL-ului către Dataverse mediu, se atașează noului lor mediu Customer Insights.

Dacă nu doriți să utilizați unul existent Dataverse mediu, sistemul creează un nou mediu pentru datele Customer Insights din chiriașul dvs. [Power Platform administratorii pot controla cine poate crea medii](/power-platform/admin/control-environment-creation). Când configurați un nou mediu Customer Insights și administratorul a dezactivat crearea de Dataverse medii pentru toată lumea, cu excepția administratorilor, este posibil să nu puteți crea un mediu nou.

**Activați partajarea datelor** cu Dataverse bifând caseta de selectare a partajării datelor.

Dacă utilizați propriul cont Data Lake Storage, aveți nevoie și de **Identificator de permisiuni**. Pentru mai multe informații despre cum să obțineți identificatorul de permisiune, consultați secțiunea următoare.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Activați partajarea datelor cu Dataverse din a ta Azure Data Lake Storage (Previzualizare)

Activarea partajării datelor cu Microsoft Dataverse când mediul tău [folosește propriul tău Azure Data Lake Storage cont](own-data-lake-storage.md) necesită o configurație suplimentară. Utilizatorul care configurează mediul Customer Insights trebuie să aibă cel puțin **Cititor de date Blob de stocare** permisiuni pe *CustomerInsights* recipient în Azure Data Lake Storage cont.

1. Creați două grupuri de securitate pe abonamentul Azure - unul **Cititor** grup de securitate și unul **Colaborator** grup de securitate și setați Microsoft Dataverse serviciu ca proprietar pentru ambele grupuri de securitate.
2. Gestionați Lista de control al accesului (ACL) din containerul CustomerInsights din contul dvs. de stocare prin intermediul acestor grupuri de securitate. Adaugă Microsoft Dataverse serviciu și orice Dataverse aplicații de afaceri bazate pe Dynamics 365 Marketing la **Cititor** grup de securitate cu **numai pentru citire** permisiuni. Adăuga *numai* aplicația Customers Insights la **Colaborator** grupului de securitate să le acorde pe ambele **Citeste si scrie** permisiuni de a scrie profiluri și informații.

### <a name="limitations"></a>Limitări

Există două limitări la utilizare Dataverse cu a ta Azure Data Lake Storage cont:

- Există o mapare unu-la-unu între a Dataverse organizaţie şi an Azure Data Lake Storage cont. Odata Dataverse organizația este conectată la un cont de stocare, nu se poate conecta la un alt cont de stocare. Această limitare împiedică ca a Dataverse nu populează mai multe conturi de stocare.
- Partajarea datelor nu va funcționa dacă este necesară o configurare Azure Private Link pentru a vă accesa contul de stocare Azure Data Lake, deoarece se află în spatele unui firewall. Dataverse momentan nu acceptă conexiunea la punctele finale private prin Private Link.

### <a name="set-up-powershell"></a>Configurați PowerShell

Pentru a executa scripturile PowerShell, mai întâi trebuie să configurați PowerShell în consecință.

1. Instalați cea mai recentă versiune a [Azure Active Directory PowerShell pentru Graph](/powershell/azure/active-directory/install-adv2).
   1. Pe computer, selectați tasta Windows de pe tastatură și căutați **Windows PowerShell** și selectați **Rulat ca administrator**.
   1. În fereastra PowerShell care se deschide, introduceți `Install-Module AzureAD`.
2. Importă trei module.
    1. În fereastra PowerShell, introduceți`Install-Module -Name Az.Accounts` și urmați pașii.
    1. Repetați pentru`Install-Module -Name Az.Resources` și `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Pași configurare

1. Descărcați cele două scripturi PowerShell de care aveți nevoie pentru a rula de la inginerul nostru [Repoziție GitHub](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Ai nevoie *administratorul chiriașului* permisiuni pentru a rula acest script PowerShell.
       - Acest script PowerShell creează două grupuri de securitate în abonamentul Azure. Unul pentru grupul Reader și altul pentru grupul Contributor și va face Microsoft Dataverse serviciu ca proprietar pentru ambele grupuri de securitate.
       - Executați acest script PowerShell în Windows PowerShell furnizând ID-ul abonamentului Azure care conține dvs Azure Data Lake Storage. Deschideți scriptul PowerShell într-un editor pentru a examina informații suplimentare și logica implementată.
       - Salvați ambele valori ale ID-urilor grupului de securitate generate de acest script, deoarece le vom folosi în`ByolSetup.ps1` scenariu.

        > [!NOTE]
        > Crearea grupului de securitate poate fi dezactivată pentru chiriașul dvs. În acest caz, ar fi necesară o configurare manuală, iar dvs Azure AD administratorul ar trebui [activați crearea grupului de securitate](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Ai nevoie *Proprietar de date Blob de stocare* permisiuni la nivelul contului de stocare/container pentru a rula acest script sau acest script va crea unul pentru dvs. Atribuirea rolului dvs. poate fi eliminată manual după rularea cu succes a scriptului.
        - Acest script PowerShell adaugă controlul de acces bazat pe tole (RBAC) necesar pentru Microsoft Dataverse serviciu și orice Dataverse aplicații de afaceri bazate pe De asemenea, actualizează Lista de control al accesului (ACL) din containerul CustomerInsights pentru grupurile de securitate create cu`CreateSecurityGroups.ps1` scenariu. Grupul de colaboratori va avea *rwx* permisiunea și grupul de cititori va avea *rx* numai permisiunea.
        - Executați acest script PowerShell în Windows PowerShell furnizând ID-ul abonamentului Azure care conține dvs Azure Data Lake Storage, numele contului de stocare, numele grupului de resurse și valorile ID-ului grupului de securitate Reader și Contributor. Deschideți scriptul PowerShell într-un editor pentru a examina informații suplimentare și logica implementată.
        - Copiați șirul de ieșire după rularea cu succes a scriptului. Șirul de ieșire arată astfel:`https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Introduceți șirul de ieșire copiat de sus în **Identificator de permisiuni** câmpul pasului de configurare a mediului pentru Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opțiuni de configurare pentru a activa partajarea datelor de la dvs Azure Data Lake Storage cu Microsoft Dataverse .":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Eliminați o conexiune existentă la a Dataverse mediu inconjurator

Când vă conectați la a Dataverse mediu, mesajul de eroare **Această organizație CDS este deja atașată la o altă instanță Customer Insights** înseamnă că Dataverse mediu este deja utilizat într-un mediu Customer Insights. Puteți elimina conexiunea existentă ca administrator global pe Dataverse mediu inconjurator. Pot dura câteva ore pentru a completa modificările.

1. Salt la [Power Apps](https://make.powerapps.com).
1. Selectați mediul din selectorul de mediu.
1. Mergi la **Soluții**
1. Dezinstalați sau ștergeți soluția numită **Dynamics 365 Customer Insights Supliment pentru cardul de client (previzualizare)**.

SAU

1. Deschide-ți Dataverse mediu inconjurator.
1. Mergi la **Setari avansate** > **Soluții**.
1. Dezinstalează **CustomerInsightsCustomerCard** soluţie.

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

| Column            | Tip        | Descriere                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Șir      | ID de profil client                                                                      |
| ActivityId        | Șir      | ID-ul intern al activității clienților (cheie primară)                                       |
| SourceEntityName  | Șir      | Nume al entității sursă                                                                |
| SourceActivityId  | Șir      | Cheie primară de la entitatea sursă                                                       |
| ActivityType      | Șir      | Tipul activității semantice sau numele activității particularizate                                        |
| ActivityTimeStamp | DATETIME    | Marca de timp a activității                                                                      |
| Funcția             | Șir      | Titlul sau numele activității                                                               |
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

| Column               | Tip        | Descriere                                          |
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
| SegmentMembershipType | Șir       | Tipul de client acest segment înregistrează apartenența. Acceptă mai multe tipuri, cum ar fi Client, Contact sau Cont. Implicit: Client  |
| Segmente       | Șir JSON  | Lista segmentelor unice la care este membru profilul clientului      |
| msdynci_identifier  | Șir   | Identificatorul unic al înregistrării de membru al segmentului. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID determinist generat din`msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
