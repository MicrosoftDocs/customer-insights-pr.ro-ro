---
title: Configurați setările de securitate
description: Aflați despre setările de securitate în Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387264"
---
# <a name="configure-security-settings"></a>Configurați setările de securitate

Gestionați cheile API, accesați datele clienților și configurați o legătură privată Azure.

## <a name="manage-api-keys"></a>Gestionați cheile API

Vizualizați și gestionați cheile pentru a utiliza [API-uri Customer Insights](apis.md) cu datele din mediul dumneavoastră.

1. Mergi la **Admin** > **Securitate** și selectați **API-uri** fila.

1. Dacă accesul API la mediu nu a fost configurat, selectați **Permite** . Sau, pentru a bloca accesul API la mediu, selectați **Dezactivați** si confirma.

1. Gestionați cheile API primare și secundare:

   1. Pentru a afișa cheia API principală sau secundară, selectați **Spectacol** simbol.

   1. Pentru a copia cheia API primară sau secundară, selectați **Copie** simbol.

   1. Pentru a crea noi chei API primare sau secundare, selectați **Regenerați primar** sau **Regenerează secundar** .

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Accesați în siguranță datele clienților cu Customer Lockbox (Previzualizare)

Customer Insights folosește Power Platform Capacitatea de blocare a clientului. Customer Lockbox oferă o interfață pentru a revizui și a aproba (sau respinge) solicitările de acces la date. Aceste solicitări apar atunci când accesul la date la datele clienților este necesar pentru a rezolva un caz de asistență. Pentru a utiliza această funcție, Customer Insights trebuie să aibă o conexiune existentă la a Microsoft Dataverse mediu în chiriașul dvs.

Pentru mai multe informații despre Customer Lockbox, consultați [rezumat](/power-platform/admin/about-lockbox#summary) de Power Platform Caseta de blocare a clientului. Articolul descrie, de asemenea, [fluxul de lucru](/power-platform/admin/about-lockbox#workflow) si necesarul [înființat](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) pentru a activa Customer Lockbox.

> [!IMPORTANT]
> Administratori globali pentru Power Platform sau Power Platform administratorii pot aproba cererile Customer Lockbox emise pentru Customer Insights.

## <a name="set-up-an-azure-private-link"></a>Configurați o legătură privată Azure

[Legătură privată Azure](/azure/private-link/private-link-overview) permite Customer Insights să se conecteze la dvs Azure Data Lake Storage cont printr-un punct final privat din rețeaua virtuală. Pentru datele dintr-un cont de stocare, care nu este expus la internetul public, Private Link permite conectarea la acea rețea restricționată.

> [!IMPORTANT]
> Cerința minimă pentru rol pentru a configura o conexiune Private Link:
>
> - Informații despre clienți: administrator
> - Rol încorporat Azure: [Colaborator cont de stocare](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Permisiuni pentru rolul Azure personalizat: [Microsoft.Storage/storageAccounts/read și Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. În Customer Insights, accesați **Admin** > **Securitate** și selectați **Linkuri private** fila.

1. Selectați **Adăugați link privat** .

   The **Adăugați link privat** panoul listează conturile de stocare de la chiriașul dvs. pe care aveți permisiuni să le vedeți.

1. Selectați abonamentul, grupul de resurse și contul de stocare.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord** .

1. Selectați **Salvare**.

1. Accesați contul dvs. Data Lake Storage și deschideți linkul prezentat pe ecran.

1. Aprobați legătura privată.


[!INCLUDE [footer-include](includes/footer-banner.md)]
