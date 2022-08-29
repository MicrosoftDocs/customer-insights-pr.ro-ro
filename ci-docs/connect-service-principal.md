---
title: Conectați-vă la un cont Azure Data Lake Storage folosind un director de serviciu Azure
description: Utilizați un principal de serviciu Azure pentru a vă conecta la propriul data lake.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: eba10068c48db5c147100c25a397bcc13b014784
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304212"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Conectați-vă la un cont Azure Data Lake Storage folosind un director de serviciu Azure

Dynamics 365 Customer Insights oferă o opțiune de conectare la un Azure Data Lake Storage cont utilizând un principal de serviciu Azure în loc de cheile contului de stocare.

Instrumentele automate care utilizează serviciile Azure trebuie să aibă permisiuni restricționate. În loc ca aplicațiile să se conecteze ca utilizator complet privilegiat, Azure oferă entități principale de serviciu. Folosiți directorii de servicii în siguranță [adăugați sau editați un dosar Common Data Model ca sursă de date](connect-common-data-model.md) sau [creați sau actualizați un mediu](create-environment.md).

## <a name="prerequisites"></a>Cerințe preliminare

- Contul Data Lake Storage care va utiliza principalul serviciu trebuie să fie Gen2. Conturile de stocare Azure Data Lake Gen1 nu sunt acceptate.
- Contul Data Lake Storage are [spațiu de nume ierarhic activat](/azure/storage/blobs/data-lake-storage-namespace).
- Permisiuni de administrator pentru entitate găzduită Azure, dacă trebuie să creați un nou principal de serviciu.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Creați un director de serviciu Azure pentru Customer Insights

Înainte de a crea un nou principal de serviciu pentru Customer Insights, verificați dacă acesta există deja în organizația dvs. În cele mai multe cazuri, există deja.

### <a name="look-for-an-existing-service-principal"></a>Căutați o entitate principală de serviciu existentă

1. Accesați [portalul de administrare Azure](https://portal.azure.com) și conectați-vă la organizația dvs.

2. Din **Servicii Azure**, selectați **Azure Active Directory**.

3. Sub **Administra**, Selectați **Aplicația Microsoft**.

4. Adăugați un filtru pentru **ID aplicație începe cu**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` sau caută numele `Dynamics 365 AI for Customer Insights`.

5. Dacă găsiți o înregistrare potrivită, înseamnă că directorul serviciului există deja. [Acordați permisiuni](#grant-permissions-to-the-service-principal-to-access-the-storage-account) pentru ca principalul serviciu să acceseze contul de stocare.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captură de ecran care arată un director de serviciu existent.":::

6. Dacă nu se returnează niciun rezultat, [creați un nou principal de serviciu](#create-a-new-service-principal).

### <a name="create-a-new-service-principal"></a>Creare pentru o nouă entitate principală de serviciu

1. Instalați cea mai nouă versiune a Azure Active Directory PowerShell for Graph. Pentru mai multe informații, accesați [Instalare Azure Active Directory PowerShell pentru Graph](/powershell/azure/active-directory/install-adv2).

   1. Pe computer, apăsați tasta Windows de pe tastatură și căutați **Windows PowerShell** și selectați **Rulat ca administrator**.

   1. În fereastra PowerShell care se deschide, introduceți `Install-Module AzureAD`.

2. Creați directorul de servicii pentru Customer Insights cu modul Azure AD PowerShell.

   1. În fereastra PowerShell, introduceți `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. A inlocui *[ID-ul dvs. director]* cu ID-ul directorului real al abonamentului Azure în care doriți să creați principalul serviciu. Parametrul numelui mediului, `AzureEnvironmentName`, este opțional.
  
   1. Introduceți `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Această comandă creează principalul serviciu pentru Customer Insights pentru abonamentul Azure selectat.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Acordați permisiuni entității principale de serviciu pentru a accesa contul de stocare

Pentru a acorda permisiuni principalului serviciu pentru contul de stocare pe care doriți să-l utilizați în Customer Insights, unul dintre următoarele roluri trebuie să fie atribuit contului de stocare sau containerului:

|Acreditare|Cerințe|
|----------|------------|
|Utilizator conectat în prezent|**Rol** : Storage Blob Data Reader, Storage Blob Contributor sau Storage Blob Owner.<br>**Nivel** : Permisiuni acordate pentru contul de stocare sau container.</br>|
|Principalul serviciului Customer Insights -<br>Folosind Azure Data Lake Storage ca un sursă de date</br>|Opțiunea 1<ul><li>**Rol** : Storage Blob Data Reader, Storage Blob Data Contributor sau Storage Blob Data Owner.</li><li>**Nivel** : Permisiuni acordate pentru contul de stocare.</li></ul>Opțiunea 2 *(fără a partaja accesul principal al serviciului la contul de stocare)*<ul><li>**Rolul 1** : Storage Blob Data Reader, Storage Blob Data Contributor sau Storage Blob Data Owner.</li><li>**Nivel** : Permisiuni acordate pe container.</li><li>**Rolul 2** : Stocare Blob Data Delegator.</li><li>**Nivel** : Permisiuni acordate pentru contul de stocare.</li></ul>|
|Principalul serviciului Customer Insights - <br>Folosind Azure Data Lake Storage ca ieșire sau destinație</br>|Opțiunea 1<ul><li>**Rol** : Colaborator de date stocare blob sau proprietar stocare blob.</li><li>**Nivel** : Permisiuni acordate pentru contul de stocare.</li></ul>Opțiunea 2 *(fără a partaja accesul principal al serviciului la contul de stocare)*<ul><li>**Rol** : Colaborator de date stocare blob sau proprietar stocare blob.</li><li>**Nivel** : Permisiuni acordate pe container.</li><li>**Rolul 2** : Storage Blob Delegator.</li><li>**Nivel** : Permisiuni acordate pentru contul de stocare.</li></ul>|

1. Accesați [portalul de administrare Azure](https://portal.azure.com) și conectați-vă la organizația dvs.

1. Deschideți contul de stocare la care doriți ca principalul serviciu pentru Customer Insights să aibă acces.

1. În panoul din stânga, selectați **Control acces (IAM)**, apoi selectați **Adăugare** > **Adăugați atribuirea de roluri**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captură de ecran care arată portalul Azure în timp ce se adaugă o atribuire de roluri.":::

1. Pe panoul **Adăugați atribuirea de roluri**, setați următoarele proprietăți:
   - **Rol** : Storage Blob Data Reader, Storage Blob Contributor sau Storage Blob Owner pe baza acreditărilor enumerate mai sus.
   - **Atribuiți acces la** :**Utilizator, grup sau principal de serviciu**
   - **Selectați** membri: **Dynamics 365 AI pentru Customer Insights** (cel [principalul serviciului](#create-a-new-service-principal) ați căutat mai devreme în această procedură)

1. Selectați **Revizuire + atribuire**.

Poate dura până la 15 minute pentru propagarea schimbărilor.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Introduceți ID-ul resursei Azure sau detaliile abonamentului Azure în atașamentul contului de stocare la Customer Insights

Atașați un cont Data Lake Storage în Customer Insights la [stocarea datelor de ieșire](manage-environments.md) sau [folosește-l ca sursă de date](connect-dataverse-managed-lake.md). Alegeți între a [bazate pe resurse](#resource-based-storage-account-connection) sau a [pe bază de abonament](#subscription-based-storage-account-connection) abordați și urmați acești pași.

### <a name="resource-based-storage-account-connection"></a>Conexiune la contul de stocare bazat pe resurse

1. Accesați [portalul de administrare Azure](https://portal.azure.com), conectați-vă la abonament și deschideți contul de stocare.

1. În panoul din stânga, accesați **Setări** > **Puncte finale**.

1. Copiați valoarea ID-ului resursei contului de stocare.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copiați ID-ul resursei contului de stocare.":::

1. În Customer Insights, inserați ID-ul resursei în câmpul de resurse afișat pe ecranul de conectare a contului de stocare.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Introduceți informația ID-ului resursei contului de stocare.":::

1. Continuați cu pașii rămași din Customer Insights pentru a atașa contul de stocare.

### <a name="subscription-based-storage-account-connection"></a>Conexiune la contul de stocare bazată pe abonament

1. Accesați [portalul de administrare Azure](https://portal.azure.com), conectați-vă la abonament și deschideți contul de stocare.

1. În panoul din stânga, accesați **Setări** > **Proprietăți**.

1. Examinați **Abonament**, **de resurse**, si **Nume** a contului de stocare pentru a vă asigura că selectați valorile corecte în Customer Insights.

1. În Customer Insights, alegeți valorile pentru câmpurile corespunzătoare atunci când atașați contul de stocare.

1. Continuați cu pașii rămași din Customer Insights pentru a atașa contul de stocare.

[!INCLUDE [footer-include](includes/footer-banner.md)]
