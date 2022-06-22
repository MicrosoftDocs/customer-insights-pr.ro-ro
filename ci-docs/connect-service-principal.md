---
title: Conectați-vă la un cont Azure Data Lake Storage folosind un director de serviciu
description: Utilizați un principal de serviciu Azure pentru a vă conecta la propriul data lake.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 36ad957f59b23df6ee83d9d90898ef03ddfd320a
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011856"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Conectați-vă la un cont Azure Data Lake Storage folosind un director de serviciu Azure

Acest articol discută cum să vă conectați Dynamics 365 Customer Insights cu un Azure Data Lake Storage cont utilizând un principal de serviciu Azure în loc de cheile contului de stocare.

Instrumentele automate care utilizează serviciile Azure ar trebui să aibă întotdeauna permisiuni restricționate. În loc ca aplicațiile să se conecteze ca utilizator complet privilegiat, Azure oferă entități principale de serviciu. Puteți utiliza principalele de servicii în siguranță [adăugați sau editați un dosar Common Data Model ca sursă de date](connect-common-data-model.md) sau [creați sau actualizați un mediu](create-environment.md).

> [!IMPORTANT]
>
> - Contul Data Lake Storage care va folosi principalul serviciu trebuie să fie Gen2 și să aibă [spațiu de nume ierarhic activat](/azure/storage/blobs/data-lake-storage-namespace). Conturile de stocare Azure Data Lake Gen1 nu sunt acceptate.
> - Aveți nevoie de permisiuni de administrator pentru entitate găzduită Azure pentru a crea un principal de serviciu.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Creați un director de serviciu Azure pentru Customer Insights

Înainte de a crea un nou principal de serviciu pentru Customer Insights, verificați dacă acesta există deja în organizația dvs.

### <a name="look-for-an-existing-service-principal"></a>Căutați o entitate principală de serviciu existentă

1. Accesați [portalul de administrare Azure](https://portal.azure.com) și conectați-vă la organizația dvs.

2. Din **Servicii Azure**, selectați **Azure Active Directory**.

3. Sub **Administra**, Selectați **Aplicația Microsoft**.

4. Adăugați un filtru pentru **ID aplicație începe cu**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` sau caută numele `Dynamics 365 AI for Customer Insights`.

5. Dacă găsiți o înregistrare potrivită, înseamnă că directorul serviciului există deja.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captură de ecran care arată un director de serviciu existent.":::

6. Dacă nu se returnează niciun rezultat, puteți [creați un nou principal de serviciu](#create-a-new-service-principal). În majoritatea cazurilor, acesta există deja și trebuie doar să acordați permisiuni principalului serviciu pentru a accesa contul de stocare.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Acordați permisiuni entității principale de serviciu pentru a accesa contul de stocare

Accesați portalul Azure pentru a acorda permisiuni principalului serviciu pentru contul de stocare pe care doriți să îl utilizați în Customer Insights. Unul dintre următoarele roluri trebuie să fie atribuit contului de stocare sau containerului:

|Acreditare|Cerințe|
|----------|------------|
|Utilizator conectat în prezent|**Rol** : Storage Blob Data Reader, Storage Blob Contributor sau Storage Blob Owner.<br>**Nivel** : Permisiunile pot fi acordate pentru contul de stocare sau container.</br>|
|Principalul serviciului Customer Insights -<br>Folosind Azure Data Lake Storage ca un sursă de date</br>|Opțiunea 1<ul><li>**Rol** : Storage Blob Data Reader, Storage Blob Data Contributor sau Storage Blob Data Owner.</li><li>**Nivel** : Permisiunile ar trebui acordate pentru contul de stocare.</li></ul>Opțiunea 2 *(fără a partaja accesul principal al serviciului la contul de stocare)*<ul><li>**Rolul 1** : Storage Blob Data Reader, Storage Blob Data Contributor sau Storage Blob Data Owner.</li><li>**Nivel** : Permisiunile trebuie acordate pe container.</li><li>**Rolul 2** : Stocare Blob Data Delegator.</li><li>**Nivel** : Permisiunile ar trebui acordate pentru contul de stocare.</li></ul>|
|Principalul serviciului Customer Insights - <br>Folosind Azure Data Lake Storage ca ieșire sau destinație</br>|Opțiunea 1<ul><li>**Rol** : Colaborator de date stocare blob sau proprietar stocare blob.</li><li>**Nivel** : Permisiunile ar trebui acordate pentru contul de stocare.</li></ul>Opțiunea 2 *(fără a partaja accesul principal al serviciului la contul de stocare)*<ul><li>**Rol** : Colaborator de date stocare blob sau proprietar stocare blob.</li><li>**Nivel** : Permisiunile trebuie acordate pe container.</li><li>**Rolul 2** : Storage Blob Delegator.</li><li>**Nivel** : Permisiunile ar trebui acordate pentru contul de stocare.</li></ul>|

1. Accesați [portalul de administrare Azure](https://portal.azure.com) și conectați-vă la organizația dvs.

1. Deschideți contul de stocare la care doriți să aibă acces principalul serviciu pentru Customer Insights.

1. În panoul din stânga, selectați **Control acces (IAM)**, apoi selectați **Adăugare** > **Adăugați atribuirea de roluri**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captură de ecran care arată portalul Azure în timp ce se adaugă o atribuire de roluri.":::

1. Pe panoul **Adăugați atribuirea de roluri**, setați următoarele proprietăți:
   - Rol: Cititor de date de stocare blob, contributor de stocare blob sau proprietar de stocare blob pe baza acreditărilor enumerate mai sus.
   - Atribuiți accesul la: **utilizator, grup sau entitate principală de serviciu**
   - Selectați membrii: **Dynamics 365 AI pentru Customer Insights** (cel [principalul serviciului](#create-a-new-service-principal) ați căutat mai devreme în această procedură)

1. Selectați **Revizuire + atribuire**.

Poate dura până la 15 minute pentru propagarea schimbărilor.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Introduceți ID-ul resursei Azure sau detaliile abonamentului Azure în atașamentul contului de stocare la Customer Insights

Puteți atașa un cont Data Lake Storage în Customer Insights la [stocarea datelor de ieșire](manage-environments.md) sau [folosește-l ca sursă de date](connect-dataverse-managed-lake.md). Această opțiune vă permite să alegeți între o abordare bazată pe resurse sau abonament. În funcție de abordarea pe care o alegeți, urmați procedura din una dintre următoarele secțiuni.

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

### <a name="create-a-new-service-principal"></a>Creare pentru o nouă entitate principală de serviciu

1. Instalați cea mai nouă versiune a Azure Active Directory PowerShell for Graph. Pentru mai multe informații, accesați [Instalare Azure Active Directory PowerShell pentru Graph](/powershell/azure/active-directory/install-adv2).

   1. Pe computer, apăsați tasta Windows de pe tastatură și căutați **Windows PowerShell** și selectați **Rulat ca administrator**.

   1. În fereastra PowerShell care se deschide, introduceți `Install-Module AzureAD`.

2. Creați directorul de servicii pentru Customer Insights cu modul Azure AD PowerShell.

   1. În fereastra PowerShell, introduceți `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. A inlocui *[ID-ul dvs. director]* cu ID-ul directorului real al abonamentului Azure în care doriți să creați principalul serviciu. Parametrul numelui mediului, `AzureEnvironmentName`, este opțional.
  
   1. Introduceți `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Această comandă creează principalul serviciu pentru Customer Insights pentru abonamentul Azure selectat.

[!INCLUDE [footer-include](includes/footer-banner.md)]
