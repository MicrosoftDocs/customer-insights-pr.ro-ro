---
title: Conectați-vă la un cont Azure Data Lake Storage folosind un director de serviciu
description: Utilizați un principal de serviciu Azure pentru a vă conecta la propriul data lake.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1af01e5579f85d7c8bc8976a003f53ef2dd280d1
ms.sourcegitcommit: b7189b8621e66ee738e4164d4b3ce2af0def3f51
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/03/2022
ms.locfileid: "8088162"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Conectați-vă la un cont Azure Data Lake Storage folosind un director de serviciu Azure

Acest articol discută cum să vă conectați Dynamics 365 Customer Insights cu un Azure Data Lake Storage cont utilizând un principal de serviciu Azure în loc de cheile contului de stocare. 

Instrumentele automate care utilizează serviciile Azure ar trebui să aibă întotdeauna permisiuni restricționate. În loc ca aplicațiile să se conecteze ca utilizator complet privilegiat, Azure oferă entități principale de serviciu. Puteți utiliza principalele de servicii în siguranță [adăugați sau editați un dosar Common Data Model ca sursă de date](connect-common-data-model.md) sau [creați sau actualizați un mediu](create-environment.md).

> [!IMPORTANT]
> - Contul Data Lake Storage care va folosi principalul serviciu trebuie să fie Gen2 și să aibă [spațiu de nume ierarhic activat](/azure/storage/blobs/data-lake-storage-namespace). Conturile de stocare Azure Data Lake Gen1 nu sunt acceptate.
> - Aveți nevoie de permisiuni de administrator pentru abonamentul Azure pentru a crea un principal de serviciu.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Creați un director de serviciu Azure pentru Customer Insights

Înainte de a crea un nou principal de serviciu pentru Customer Insights, verificați dacă acesta există deja în organizația dvs.

### <a name="look-for-an-existing-service-principal"></a>Căutați o entitate principală de serviciu existentă

1. Accesați [portalul de administrare Azure](https://portal.azure.com) și conectați-vă la organizația dvs.

2. Din **Servicii Azure**, selectați **Azure Active Directory**.

3. Sub **Gestionare**, selectați **aplicații Enterprise**.

4. Căutați ID-ul aplicației Microsoft:
   - Detalii despre public: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` cu numele `Dynamics 365 AI for Customer Insights`
   - Detalii despre angajament: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` cu denumirea `Dynamics 365 AI for Customer Insights engagement insights`

5. Dacă găsiți o înregistrare potrivită, înseamnă că directorul serviciului există deja. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captură de ecran care arată un director de serviciu existent.":::
   
6. Dacă nu se returnează rezultate, creați o nouă entitate principală de serviciu.

>[!NOTE]
>A face uz de întreaga putere a Dynamics 365 Customer Insights, vă sugerăm să adăugați ambele aplicații la directorul serviciului.

### <a name="create-a-new-service-principal"></a>Creare pentru o nouă entitate principală de serviciu

1. Instalați cea mai nouă versiune a Azure Active Directory PowerShell for Graph. Pentru mai multe informații, accesați [Instalare Azure Active Directory PowerShell pentru Graph](/powershell/azure/active-directory/install-adv2).

   1. Pe computer, selectați tasta Windows de pe tastatură și căutați **Windows PowerShell** și selectați **Rulat ca administrator**.
   
   1. În fereastra PowerShell care se deschide, introduceți `Install-Module AzureAD`.

2. Creați directorul de servicii pentru Customer Insights cu modul Azure AD PowerShell.

   1. În fereastra PowerShell, introduceți `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Înlocuiți *[D-ul entității dvs. găzduite]* cu ID-ul real al entității găzduite unde doriți să creați entitatea principală de serviciu. Parametrul numelui mediului, `AzureEnvironmentName`, este opțional.
  
   1. Introduceți `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Această comandă creează entitatea principală de serviciu pentru Detalii despre audiență în entitatea găzduită selectată. 

   1. Introduceți `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Această comandă creează principalul de serviciu pentru statistici de implicare pe entitatea găzduită selectată.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Acordați permisiuni entității principale de serviciu pentru a accesa contul de stocare

Accesați portalul Azure pentru a acorda permisiuni entității principale de serviciu pentru contul de stocare pe care doriți să îl utilizați în Detalii despre audiență.

1. Accesați [portalul de administrare Azure](https://portal.azure.com) și conectați-vă la organizația dvs.

1. Deschideți contul de stocare la care doriți să aibă acces entitatea principală de serviciu pentru Detalii despre audiență.

1. În panoul din stânga, selectați **Control acces (IAM)**, apoi selectați **Adăugare** > **Adăugați atribuirea de roluri**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captură de ecran care arată portalul Azure în timp ce se adaugă o atribuire de roluri.":::

1. Pe panoul **Adăugați atribuirea de roluri**, setați următoarele proprietăți:
   - Rol: **Contribuitor de date blob de stocare**
   - Atribuiți accesul la: **utilizator, grup sau entitate principală de serviciu**
   - Selectați: **Dynamics 365 AI for Customer Insights** și **Dynamics 365 AI for Customer Insights** (cei doi [directorii serviciului](#create-a-new-service-principal) creați mai devreme în această procedură)

1.  Selectați **Salvare**.

Poate dura până la 15 minute pentru propagarea schimbărilor.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Introduceți ID-ul resursei Azure sau detaliile abonamentului Azure în atașarea contului de stocare la detalii despre public.

Puteți atașa un cont Data Lake Storage în statisticile publicului la [stochează datele de ieșire](manage-environments.md) sau [folosiți-l ca sursă de date](connect-common-data-service-lake.md). Această opțiune vă permite să alegeți între o abordare bazată pe resurse sau abonament. În funcție de abordarea pe care o alegeți, urmați procedura din una dintre următoarele secțiuni.

### <a name="resource-based-storage-account-connection"></a>Conexiune la contul de stocare bazat pe resurse

1. Accesați [portalul de administrare Azure](https://portal.azure.com), conectați-vă la abonament și deschideți contul de stocare.

1. În panoul din stânga, accesați **Setări** > **Proprietăți**.

1. Copiați valoarea ID-ului resursei contului de stocare.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copiați ID-ul resursei contului de stocare.":::

1. În statistici privind publicul, introduceți ID-ul resursei în câmpul de resurse afișat pe ecranul de conectare a contului de stocare.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Introduceți informația ID-ului resursei contului de stocare.":::   

1. Continuați cu pașii rămași din Detalii despre audiență pentru a atașa contul de stocare.

### <a name="subscription-based-storage-account-connection"></a>Conexiune la contul de stocare bazată pe abonament

1. Accesați [portalul de administrare Azure](https://portal.azure.com), conectați-vă la abonament și deschideți contul de stocare.

1. În panoul din stânga, accesați **Setări** > **Proprietăți**.

1. Analizați **Abonament**, **Grup de resurse**, și **Numele** din contul de stocare pentru a vă asigura că selectați valorile potrivite în Detalii despre audiență.

1. În detalii privind publicul, alegeți valorile pentru câmpurile corespunzătoare atunci când atașați contul de stocare.

1. Continuați cu pașii rămași din Detalii despre audiență pentru a atașa contul de stocare.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
