---
title: Crearea și gestionarea mediilor
description: Aflați cum să vă înscrieți pentru serviciu și cum să gestionați mediile.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: ba29bcd173e615e544bd10e69043f310c009eb47
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/29/2022
ms.locfileid: "8492019"
---
# <a name="manage-environments"></a>Gestionați mediile

## <a name="switch-environments"></a>Comutați medii

Selectați controlul **Mediu** din colțul din dreapta sus al paginii pentru a modifica mediile.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Captură de ecran a comenzii pentru a schimba mediul.":::

Administratorii pot [crea](create-environment.md) și gestiona medii.

## <a name="edit-an-existing-environment"></a>Editați un mediu existent

Puteți edita câteva dintre detaliile mediilor existente.

1.  Selectați selectorul **Mediu** în antetul aplicației.

2.  Selectați pictograma **Editare**.

3. În caseta **Editați mediul**, puteți actualiza setările de mediu.

Pentru informații suplimentare despre setările de mediu, consultați [Creați un mediu nou](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Conectare la Microsoft Dataverse
   
Pasul **Microsoft Dataverse** vă permite să conectați Customer Insights cu mediul Dataverse. 

Furnizați-vă propriul dvs Microsoft Dataverse mediu pentru a partaja date (profiluri și perspective) cu aplicațiile de afaceri bazate pe Dataverse, cum ar fi Dynamics 365 Marketing sau aplicațiile bazate pe model în Power Apps.

Pentru a utiliza [modele predicție predefinite](predictions-overview.md#out-of-box-models), configurați partajarea datelor cu Dataverse. Sau puteți activa ingestia de date din sursele de date local, furnizând URL de mediu Microsoft Dataverse administrat de organizația dvs.

Activarea partajării datelor cu Microsoft Dataverse prin selectarea casetei de selectare pentru partajarea datelor, se va declanșa o reîmprospătare completă o singură dată a surselor de date și a tuturor celorlalte procese.

> [!IMPORTANT]
> 1. Informații despre clienți și Dataverse trebuie să fie în aceeași regiune pentru a permite partajarea datelor.
> 1. Trebuie să aveți un rol de administrator global în Dataverse mediu inconjurator. Verificați dacă acest lucru [Dataverse mediu este asociat](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) la anumite grupuri de securitate și asigurați-vă că sunteți adăugat la acele grupuri de securitate.
> 1. Niciun mediu existent Customer Insights nu este deja asociat cu asta Dataverse mediu inconjurator. Învață cum să [eliminați o conexiune existentă la a Dataverse mediu inconjurator](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Opțiuni de configurare pentru a permite partajarea datelor cu Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Activați partajarea datelor cu Dataverse din a ta Azure Data Lake Storage (Previzualizare)

Dacă mediul dvs. este configurat pentru a utiliza propriul dvs Azure Data Lake Storage pentru a stoca datele Customer Insights, permițând partajarea datelor cu acestea Microsoft Dataverse necesită o configurație suplimentară.

1. Creați două grupuri de securitate pe abonamentul Azure - unul **Cititor** grup de securitate și unul **Colaborator** grup de securitate și setați Microsoft Dataverse serviciu ca proprietar pentru ambele grupuri de securitate.
2. Gestionați Lista de control al accesului (ACL) din containerul CustomerInsights din contul dvs. de stocare prin intermediul acestor grupuri de securitate. Adaugă Microsoft Dataverse serviciu și orice Dataverse aplicații de afaceri bazate pe Dynamics 365 Marketing la **Cititor** grup de securitate cu **numai pentru citire** permisiuni. Adăuga *numai* aplicația Customers Insights la **Colaborator** grupului de securitate să le acorde pe ambele **Citeste si scrie** permisiuni de a scrie profiluri și informații.
   
#### <a name="prerequisites"></a>Cerințe preliminare

Pentru a executa scripturile PowerShell, trebuie să aveți următoarele trei module importate. 

1. Instalați cea mai recentă versiune a [Azure Active Directory PowerShell pentru Graph](/powershell/azure/active-directory/install-adv2).
   1. Pe computer, selectați tasta Windows de pe tastatură și căutați **Windows PowerShell** și selectați **Rulat ca administrator**.
   1. În fereastra PowerShell care se deschide, introduceți `Install-Module AzureAD`.
2. Importă trei module.
    1. În fereastra PowerShell, introduceți`Install-Module -Name Az.Accounts` și urmați pașii. 
    1. Repetați pentru`Install-Module -Name Az.Resources` și `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Pași configurare

1. Descărcați cele două scripturi PowerShell de care aveți nevoie pentru a rula de la inginerul nostru [Repoziție GitHub](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Ai nevoie *administratorul chiriașului* permisiuni pentru a rula acest script PowerShell. 
       - Acest script PowerShell creează două grupuri de securitate în abonamentul Azure. Unul pentru grupul Reader și altul pentru grupul Contributor și va face Microsoft Dataverse serviciu ca proprietar pentru ambele grupuri de securitate.
       - Executați acest script PowerShell în Windows PowerShell furnizând ID-ul abonamentului Azure care conține Azure Data Lake Storage. Deschideți scriptul PowerShell într-un editor pentru a examina informații suplimentare și logica implementată.
       - Salvați ambele valori ale ID-urilor grupului de securitate generate de acest script, deoarece le vom folosi în`ByolSetup.ps1` scenariu.
       
        > [!NOTE]
        > Crearea grupului de securitate poate fi dezactivată pentru chiriașul dvs. În acest caz, ar fi necesară o configurare manuală, iar dvs Azure AD administratorul ar trebui [activați crearea grupului de securitate](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Ai nevoie *Proprietar de date Blob de stocare* permisiuni la nivelul contului de stocare/container pentru a rula acest script sau acest script va crea unul pentru dvs. Atribuirea rolului dvs. poate fi eliminată manual după rularea cu succes a scriptului.
        - Acest script PowerShell adaugă controlul de acces bazat pe tole (RBAC) necesar pentru Microsoft Dataverse serviciu și orice Dataverse aplicații de afaceri bazate pe De asemenea, actualizează Lista de control al accesului (ACL) din containerul CustomerInsights pentru grupurile de securitate create cu`CreateSecurityGroups.ps1` scenariu. Grupul de colaboratori va avea *rwx* permisiunea și grupul de cititori va avea *rx* numai permisiunea.
        - Executați acest script PowerShell în Windows PowerShell furnizând ID-ul abonamentului Azure care conține Azure Data Lake Storage, numele contului de stocare, numele grupului de resurse și valorile ID-ului grupului de securitate Reader și Contributor. Deschideți scriptul PowerShell într-un editor pentru a examina informații suplimentare și logica implementată.
        - Copiați șirul de ieșire după rularea cu succes a scriptului. Șirul de ieșire arată astfel:`https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Introduceți șirul de ieșire copiat de sus în **Identificator de permisiuni** câmpul pasului de configurare a mediului pentru Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opțiuni de configurare pentru a activa partajarea datelor de la dvs Azure Data Lake Storage cu Microsoft Dataverse .":::

Customer Insights nu acceptă următoarele scenarii de partajare:
- Dacă activați partajarea datelor Dataverse, nu veți putea [crea valori prezise sau lipsă într-o entitate](predictions.md).
- Dacă activați partajarea datelor cu Dataverse, nu veți putea vizualiza niciun raport opțional PowerBI Embedded în mediul dvs. Customer Insights.

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

## <a name="copy-the-environment-configuration"></a>Copiați configurația mediului

În calitate de administrator, puteți alege să copiați configurația dintr-un mediu existent atunci când creați unul nou. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captură de ecran a opțiunilor de setări din setările de mediu.":::

Veți vedea o listă cu toate mediile disponibile în organizația dvs. de unde puteți copia datele.

Sunt copiate următoarele setări de configurare:

- Surse de date ingerate/importate
- Configurarea unificării datelor (mapare, potrivire, îmbinare)
- Segmente
- Măsuri
- Relaţii
- Activități
- Index de căutare și filtrare
- Destinații export
- Reîmprospătare planificată
- Îmbogățiri
- Management model
- Atribuiri rol

## <a name="set-up-a-copied-environment"></a>Configurați un mediu copiat

Când copiați configurația mediului, următoarele date sunt *nu* copiat:

- Profiluri de client.
- Acreditările sursă de date. Va trebui să furnizați acreditările pentru fiecare sursă de date și să reîmprospătați sursele de date manual.
- Sursele de date din folderul Common Data Model și data lake-ul gestionat de Dataverse. Va trebui să creați acele surse de date manual cu același nume ca în mediul sursă.
- Secrete de conexiune care sunt folosite pentru exporturi și îmbogățiri. Trebuie să reautentificați conexiunile și apoi să reactivați îmbogățirile și exporturile. 

Când copiați un mediu, veți vedea un mesaj de confirmare a faptului că noul mediu a fost creat. Selectați **Accesați sursele de date** pentru a vedea lista surselor de date.

Toate sursele de date vor arăta o stare **Acreditări necesare**. Editați sursele de date și introduceți acreditările pentru a le reîmprospăta.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista surselor de date care au fost copiate și care necesită autentificare.":::

După reîmprospătarea surselor de date, accesați **Date** > **Unificare**. Aici veți găsi setările din mediul sursă. Editați-le după cum este necesar sau selectați **Rulează** pentru a începe procesul de unificare a datelor și a crea entitatea clientului unificat.

Când unificarea datelor este completă, accesați **Măsuri** și **Segmente** pentru a le reîmprospăta și pe acestea.

Înainte de a reactiva exporturile și îmbogățirile, accesați **Admin** > **Conexiuni** pentru a reautentifica conexiunile în noul dumneavoastră mediu.

## <a name="change-the-owner-of-an-environment"></a>Schimbați proprietarul unui mediu

În timp ce mai mulți utilizatori pot avea permisiuni de administrator în Customer Insights, doar un utilizator este proprietarul unui mediu. În mod implicit, administratorul este cel care creează un mediu inițial. În calitate de administrator al unui mediu, puteți atribui dreptul de proprietate unui alt utilizator cu permisiuni de administrator.

1. Selectați selectorul **Mediu** în antetul aplicației.

1. Selectați pictograma **Editare**.

1. În **Editați mediul** caseta, du-te la **Informatii de baza** Etapa.

1. În **Schimbați proprietarul mediului** câmp, alegeți noul proprietar al mediului.  

1. Selectați **Revedeți și terminați**, apoi **Actualizați** pentru a aplica modificările. 

## <a name="claim-ownership-of-an-environment"></a>Revendicați dreptul de proprietate asupra unui mediu

Dacă proprietarul unui mediu părăsește organizația sau contul de utilizator este șters, mediul nu va avea niciun proprietar. Un utilizator cu permisiuni de administrator poate revendica dreptul de proprietate și poate deveni noul proprietar. Ei pot continua să dețină mediul sau [schimba proprietatea la alt administrator](#change-the-owner-of-an-environment). 

Pentru a revendica proprietatea, selectați **Preia proprietatea** butonul care apare în partea de sus a fiecărei pagini din Customer Insights când proprietarul inițial a părăsit organizația.

## <a name="reset-an-existing-environment"></a>Resetați un mediu existent

În calitate de proprietar al unui mediu, puteți reseta un mediu la o stare goală dacă doriți să ștergeți toate configurațiile și să eliminați datele ingerate.

1.  Selectați selectorul **Mediu** în antetul aplicației. 

2.  Selectați mediul pe care doriți să îl resetați și selectați punctele de suspensie (**...**). 

3. Alegeți opțiunea **Resetați**. 

4.  Pentru a confirma ștergerea, introduceți numele mediului și selectați **Resetare**.

## <a name="delete-an-existing-environment"></a>Ștergerea unui mediu existent

În calitate de proprietar al unui mediu, puteți șterge un mediu pe care îl administrați.

1.  Selectați selectorul **Mediu** în antetul aplicației.

2.  Selectați mediul pe care doriți să îl resetați și selectați punctele de suspensie (**...**). 

3. Alegeți opțiunea **Ștergere**. 

4.  Pentru a confirma ștergerea, introduceți numele mediului și selectați **Ștergere**.

> [!NOTE]
> Ștergerea unui mediu nu elimină asocierea la a Dataverse mediu.Aflați cum să [eliminați o conexiune existentă la a Dataverse mediu inconjurator](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
