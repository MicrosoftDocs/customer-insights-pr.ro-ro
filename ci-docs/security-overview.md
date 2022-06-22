---
title: Setări de securitate în Customer Insights
description: Aflați despre setările de securitate în Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947430"
---
# <a name="security-settings-in-customer-insights"></a>Setări de securitate în Customer Insights

The **Securitate** pagina listează opțiuni pentru a configura permisiunile utilizatorului și caracteristicile care ajută la realizarea Dynamics 365 Customer Insights mai sigur. Numai administratorii pot accesa această pagină.

Mergi la **Admin** > **Securitate** pentru a configura setările.

The **Securitate** pagina include următoarele file:

- [Utilizatori](#users-tab)
- [API-uri](#apis-tab)
- [Linkuri private](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [Accesați în siguranță datele clienților cu Customer Lockbox (Previzualizare)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Fila Utilizatori

Accesul la Customer Insights este limitat la utilizatorii din organizația dvs. care au fost adăugați la aplicație de către un administrator. The **Utilizatori** fila vă permite să gestionați accesul utilizatorilor și permisiunile acestora. Pentru mai multe informații, vezi [Permisiunile utilizatorului](permissions.md).

## <a name="apis-tab"></a>Fila API-uri

Vizualizați și gestionați cheile pentru a utiliza [API-uri Customer Insights](apis.md) cu datele mediului dumneavoastră.

Puteți crea chei primare și secundare noi selectând **Regenerați primar** sau **Regenerează secundar**. 

Pentru a bloca accesul API la mediu, selectați **Dezactivați**. Dacă API-urile sunt dezactivate, puteți selecta **Permite** pentru a acorda din nou acces.

## <a name="private-links-tab"></a>Fila Linkuri private

[Legătură privată Azure](/azure/private-link/private-link-overview) haideți să conectăm Customer Insights la dvs Azure Data Lake Storage cont printr-un punct final privat din rețeaua virtuală. Pentru datele dintr-un cont de stocare, care nu este expus la internetul public, Private Link permite conectarea la acea rețea restricționată.

> [!IMPORTANT]
> Cerința minimă a rolului pentru a configura o conexiune Private Link:
>
> - Informații despre clienți: administrator
> - Rol încorporat Azure: [Colaborator cont de stocare](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Permisiuni pentru rolul Azure personalizat: [Microsoft.Storage/storageAccounts/read și Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Configurarea legăturii private în Customer Insights este un proces în doi pași. Mai întâi, inițiați crearea unui link privat de la **Admin** > **Securitate** > **Linkuri private** în Customer Insights. The **Adăugați link privat** panoul listează conturile de stocare de la chiriașul dvs. pe care aveți permisiuni să le vedeți. Selectați contul de stocare și furnizați consimțământul pentru a crea legătura privată.

Apoi, trebuie să aprobați legătura privată din partea contului Data Lake Storage. Deschideți linkul prezentat pe ecran pentru a aproba noul link privat.

## <a name="key-vault-tab"></a>Fila Key Vault

The **Seif de chei** fila vă permite să vă conectați și să vă gestionați propria [Seif pentru chei Azure](/azure/key-vault/general/basic-concepts) la mediu.
Seiful de chei dedicat poate fi utilizat pentru a etapiza și a folosi secrete în limita de conformitate a unei organizații. Customer Insights poate folosi secretele din Azure Key Vault pentru [stabiliți conexiuni](connections.md) către sisteme terțe.

Pentru mai multe informații, vedeți [Aduceți-vă propriul seif de chei Azure](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Accesați în siguranță datele clienților cu Customer Lockbox (Previzualizare)

Customer Insights folosește Power Platform Capacitatea de blocare a clientului. Customer Lockbox oferă o interfață pentru a revizui și a aproba (sau respinge) solicitările de acces la date. Aceste solicitări apar atunci când accesul la date la datele clienților este necesar pentru a rezolva un caz de asistență. Pentru a utiliza această funcție, Customer Insights trebuie să aibă o conexiune existentă la a Microsoft Dataverse mediu în chiriașul dvs.

Pentru mai multe informații despre Customer Lockbox, consultați [rezumat](/power-platform/admin/about-lockbox#summary) de Power Platform Caseta de blocare a clientului. Articolul descrie, de asemenea, [fluxul de lucru](/power-platform/admin/about-lockbox#workflow) si necesarul [înființat](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) pentru a activa Customer Lockbox.

> [!IMPORTANT]
> Administratori globali pentru Power Platform sau Power Platform administratorii pot aproba cererile Customer Lockbox emise pentru Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]
