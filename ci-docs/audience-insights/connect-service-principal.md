---
title: Conectați-vă la un cont Gen2 Azure Data Lake Storage cu o entitate principală de serviciu
description: Utilizați o entitate principală de serviciu Azure pentru Detalii despre audiență pentru a vă conecta la propriul data lake la atașarea la Detalii despre audiență.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: cc94ad49f12067d513db4663bff60620d6501eb0
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692128"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Conectați-vă la un cont Gen2 Azure Data Lake Storage cu o entitate principală de serviciu Azure pentru Detalii despre audiență

Instrumentele automate care utilizează serviciile Azure ar trebui să aibă întotdeauna permisiuni restricționate. În loc ca aplicațiile să se conecteze ca utilizator complet privilegiat, Azure oferă entități principale de serviciu. Citiți mai departe pentru a afla cum să conectați Detalii despre audiență cu un cont Gen2 Azure Data Lake Storage care utilizează o entitate principală de serviciu Azure în loc de chei de cont de stocare. 

Puteți utiliza o entitate principală de serviciu pentru a [adăuga sau edita un folder Common Data Model ca sursă de date](connect-common-data-model.md) sau [crea un mediu nou sau actualiza un mediu existent](get-started-paid.md) în siguranță.

> [!IMPORTANT]
> - Contul de stocare Azure Data Lake Gen2 care intenționează să utilizeze principalul serviciului trebuie să aibă [Spațiul de nume ierarhic (HNS) activat](/azure/storage/blobs/data-lake-storage-namespace).
> - Aveți nevoie de permisiuni de administrator pentru abonamentul dvs. Azure pentru a crea entitatea principală de serviciu.

## <a name="create-azure-service-principal-for-audience-insights"></a>Creați entitatea principală de serviciu Azure pentru Detalii despre audiență

Înainte de a crea o nouă entitate principală de serviciu pentru Detalii despre audiență, verificați dacă acesta există deja în organizația dvs.

### <a name="look-for-an-existing-service-principal"></a>Căutați o entitate principală de serviciu existentă

1. Accesați [portalul de administrare Azure](https://portal.azure.com) și conectați-vă la organizația dvs.

2. Selectați **Azure Active Directory** din serviciile Azure.

3. Sub **Gestionare**, selectați **aplicații Enterprise**.

4. Căutați ID-ul aplicației pentru prima parte din Detalii despre audiență `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` sau numele `Dynamics 365 AI for Customer Insights`.

5. Dacă găsiți o înregistrare potrivită, înseamnă că există o entitate principală de serviciu pentru Detalii despre audiență. Nu este nevoie să o creați din nou.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captură de ecran care arată entitatea principală de serviciu existentă.":::
   
6. Dacă nu se returnează rezultate, creați o nouă entitate principală de serviciu.

### <a name="create-a-new-service-principal"></a>Creare pentru o nouă entitate principală de serviciu

1. Instalați cea mai recentă versiune a **Azure Active Directory PowerShell pentru reprezentare grafică**. Pentru mai multe informații, consultați [Instalare Azure Active Directory PowerShell pentru reprezentare grafică](/powershell/azure/active-directory/install-adv2).
   - Pe computer, selectați tasta Windows de pe tastatură și căutați **Windows PowerShell** și **Rulați ca administrator**.
   
   - În fereastra PowerShell care se deschide, introduceți `Install-Module AzureAD`.

2. Creați entitatea principală de serviciu pentru Detalii despre audiență cu modulul PowerShell Azure AD.
   - În fereastra PowerShell, introduceți `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Înlocuiți „ID-ul entității dvs. găzduite” cu ID-ul propriu-zis al entității găzduite în care doriți să creați entitatea principală de serviciu. Parametrul numele mediului `AzureEnvironmentName` este opțional.
  
   - Introduceți `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Această comandă creează entitatea principală de serviciu pentru Detalii despre audiență în entitatea găzduită selectată.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Acordați permisiuni entității principale de serviciu pentru a accesa contul de stocare

Accesați portalul Azure pentru a acorda permisiuni entității principale de serviciu pentru contul de stocare pe care doriți să îl utilizați în Detalii despre audiență.

1. Accesați [portalul de administrare Azure](https://portal.azure.com) și conectați-vă la organizația dvs.

1. Deschideți contul de stocare la care doriți să aibă acces entitatea principală de serviciu pentru Detalii despre audiență.

1. Selectați **Control acces (IAM)** din panoul de navigare și selectați **Adăugare** > **Adăugare atribuire de rol**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captură de ecran care arată portalul Azure în timp ce se adaugă o atribuire de rol.":::
   
1. În panoul **Adăugare atribuirea de rol**, setați următoarele proprietăți:
   - Rol: *Contribuitor de date blob de stocare*
   - Atribuiți accesul la: *utilizator, grup sau entitate principală de serviciu*
   - Selectați: *Dynamics 365 AI for Customer Insights* ([entitatea principală de serviciu pe care ați creat-o](#create-a-new-service-principal))

1.  Selectați **Salvare**.

Poate dura până la 15 minute pentru propagarea schimbărilor.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Introduceți ID-ul resursei Azure sau detaliile abonamentului Azure în atașarea contului de stocare la Detalii despre audiență.

Atașați un cont Azure Data Lake Storage în Detalii despre audiență pentru [stocarea datelor de ieșire](manage-environments.md) sau [folosiți-l ca sursă de date](connect-dataverse-managed-lake.md). Alegerea opțiunii Azure Data Lake vă permite să alegeți între o abordare bazată pe resurse sau o abordare bazată de abonament.

Urmați pașii de mai jos pentru a furniza informațiile necesare despre abordarea selectată.

### <a name="resource-based-storage-account-connection"></a>Conexiune la contul de stocare bazat pe resurse

1. Accesați [portalul de administrare Azure](https://portal.azure.com), conectați-vă la abonament și deschideți contul de stocare.

1. Accesați **Setări** > **Proprietăți** din panoul de navigare.

1. Copiați valoarea ID-ului resursei contului de stocare.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copiați ID-ul resursei contului de stocare.":::

1. În Detalii despre audiență, introduceți ID-ul resursei în câmpul resursei afișat în ecranul de conectare a contului de stocare.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Introduceți informația ID-ului resursei contului de stocare.":::   
   
1. Continuați cu pașii rămași din Detalii despre audiență pentru a atașa contul de stocare.

### <a name="subscription-based-storage-account-connection"></a>Conexiune la contul de stocare bazată pe abonament

1. Accesați [portalul de administrare Azure](https://portal.azure.com), conectați-vă la abonament și deschideți contul de stocare.

1. Accesați **Setări** > **Proprietăți** din panoul de navigare.

1. Analizați **Abonament**, **Grup de resurse**, și **Numele** din contul de stocare pentru a vă asigura că selectați valorile potrivite în Detalii despre audiență.

1. În Detalii despre audiență, alegeți valorile sau câmpurile corespunzătoare atunci când atașați contul de stocare.
   
1. Continuați cu pașii rămași din Detalii despre audiență pentru a atașa contul de stocare.


[!INCLUDE[footer-include](../includes/footer-banner.md)]