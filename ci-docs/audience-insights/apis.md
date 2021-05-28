---
title: Lucrați cu API-uri
description: Folosirea de API-uri și înțelegerea limitărilor.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 4d41d7d328dfa6699b5f5e992d3a5bf3179490d8
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016635"
---
# <a name="work-with-customer-insights-apis"></a>Lucrul cu API-urile Customer Insights

Dynamics 365 Customer Insights oferă API-uri pentru a vă crea propriile aplicații bazate pe datele dvs. în Customer Insights.

> [!IMPORTANT]
> Detaliile acestor API-uri sunt listate în [Referința pentru API-uri Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Acestea includ informații suplimentare despre operațiuni, parametri și răspunsuri.

Acest articol vă ghidează să accesați API-urile Customer Insights, să creați o înregistrare de aplicație Azure și să vă ajute să începeți cu bibliotecile client disponibile.

## <a name="get-started-trying-the-customer-insights-apis"></a>Începeți să încercați API-urile Customer Insights

1. [Conectați-vă](https://home.ci.ai.dynamics.com) la Customer Insights. Dacă nu aveți încă un abonament, [înscrieți-vă pentru o versiune de încercare a Customer Insights](https://aka.ms/tryci).

1. Pentru a activa API-urile din mediul dvs. Customer Insights, accesați **Administrator** > **Permisiuni**. Veți avea nevoie de permisiuni de administrator pentru asta.

1. Accesați fila **API-uri** și selectați butonul **Permite**.    
   Activarea API-urilor creează o cheie de abonament primară și una secundară pentru instanța dvs. care este folosită în solicitările API. Puteți regenera cheile selectând **Regenerare cheie primară** sau **Regenerare cheie secundară** din **Administrator** > **Permisiuni** > **API-uri**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Activați API-urile Customer Insights":::

1. Selectați **Explorați API-urile noastre** pentru [a încerca API-urile](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Alegeți o operațiune API și selectați **Încearcă**.

1. În panoul lateral, setați valoarea în meniul vertical **Autorizare** la **implicit**. Antetului `Authorization` i se adaugă un token pentru purtător. Cheia dvs. de abonament va fi populată automat.
  
1. Opțional, adăugați toți parametrii de interogare necesari.

1. Derulați până în partea de jos a panoului lateral și selectați **Trimitere**.

Răspunsul HTTP va apărea curând mai jos.


   :::image type="content" source="media/try-apis.gif" alt-text="Gif animat care arată cum se selectează testarea API-urilor.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Creați o nouă înregistrare a aplicației în portalul Azure

Acești pași vă ajută să începeți să utilizați API-urile Customer Insights într-o aplicație Azure utilizând permisiuni delegate. Asigurați-vă că ați terminat întâi [Secțiunea Introducere](#get-started-trying-the-customer-insights-apis).

1. Conectați-vă la [portalul Azure](https://portal.azure.com) cu contul care poate accesa datele Customer Insights.

1. În stânga, selectați **Înregistrări aplicații**.

1. Selectați **Înregistrare nouă** furnizați un nume de aplicație și alegeți tipul de cont.
   Opțional, adăugați o adresă URL de redirecționare. http://localhost este suficient pentru dezvoltarea unei aplicații pe computerul dvs. local.

1. În noua înregistrare a aplicației, accesați **Permisiuni API**.

   :::image type="content" source="media/app-registration-1.gif" alt-text="Gif animat pentru a seta permisiunea API în înregistrarea aplicației.":::

1. Selectați **Adăugați o permisiune** și selectați **Customer Insights** în panoul lateral.

1. Pentru **Tip permisiune**, selectați **Permisiuni delegate** și selectați permisiunea **user_impersonation**.

1. Selectați **Adăugare permisiuni**. Dacă trebuie să accesați API-ul fără conectarea unui utilizator, consultați secțiunea [Permisiuni pentru aplicații de la server la server](#server-to-server-application-permissions).

1. Selectați **Acordă consimțământul administratorului pentru...** pentru a finaliza înregistrarea aplicației.

Puteți utiliza ID-ul aplicației/clientului pentru această înregistrare a aplicației cu Biblioteca de autentificare Microsoft (MSAL) pentru a obține un token pentru purtător pe care îl trimiteți cu cererea dvs. către API.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="GIF animat pentru a acorda consimțământul administratorului.":::

Pentru mai multe informații despre MSAL, consultați [Prezentare generală a bibliotecii de autentificare Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).

Pentru mai multe informații despre înregistrarea aplicațiilor în Azure, consultați [Noua experiență de înregistrare a aplicației în portalul Azure](/azure/active-directory/develop/app-registration-portal-training-guide).

Pentru informații despre utilizarea API-urilor cu bibliotecile clienților noștri, consultați [Biblioteci client Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Permisiuni pentru aplicații de la server la server

[Secțiunea înregistrarea aplicației](#create-a-new-app-registration-in-the-azure-portal) descrie modul de înregistrare a unei aplicații care necesită conectarea unui utilizator pentru autentificare. Aflați cum să creați o înregistrare a aplicației care nu necesită interacțiunea utilizatorului și care poate fi rulată pe un server.

1. În înregistrarea aplicației dvs. în portalul Azure, accesați **Permisiuni API**.

1. Selectați **Adăugați o permisiune**. 

1. Selectați fila **API-urile pe care le folosește organizația mea** și alegeți **Dynamics 365 AI for Customer Insights** din listă. 

1. Pentru **Tip permisiune**, selectați **Permisiuni aplicație** și selectați permisiunea **CustomerInsights.Api.All**.

1. Selectați **Adăugare permisiuni**.

1. Reveniți la **Permisiuni API** pentru înregistrarea aplicației.

1. Selectați **Acordă consimțământul administratorului pentru...** pentru a finaliza înregistrarea aplicației.

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="GIF animat pentru a acorda consimțământul administratorului.":::

1. În concluzie, trebuie să adăugăm numele înregistrării aplicației ca utilizator în Customer Insights.    
   Deschideți Customer Insights, accesați **Administrator** > **Permisiuni** și selectați **Adăugare utilizator**.

1. Căutați numele înregistrării aplicației dvs., selectați-l din rezultatele căutării și selectați **Salvare**.

## <a name="customer-insights-client-libraries"></a>Biblioteci client Customer Insights

Această secțiune vă ajută să începeți să utilizați bibliotecile client disponibile pentru API-urile Customer Insights. Toate codurile sursă ale bibliotecii și exemplele de aplicații pot fi găsite pe [pagina GitHub Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Aflați cum să începeți să utilizați bibliotecile client C# de la NuGet.org. Pentru mai multe informații despre pachetul NuGet, consultați [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). În prezent, acest pachet vizează cadrele netstandard2.0 și netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Adăugați biblioteca client C# la un proiect C#

1. În Visual Studio, deschideți **Manager pachet NuGet** pentru proiectul dumneavoastră.

1. Căutați **Microsoft.Dynamics.CustomerInsights.Api**.

1. Selectați **Instalare** pentru a adăuga pachetul la proiect.
   Alternativ, rulați această comandă în **Consola Manager pachet NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Adăugați pachetul NuGet la un proiect Visual Studio":::

#### <a name="use-the-c-client-library"></a>Utilizați biblioteca de client C#

1. Folosiți [Biblioteca de autentificare Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) pentru a obține un `AccessToken` folosind [înregistrarea aplicației Azure](#create-a-new-app-registration-in-the-azure-portal) existentă.

1. După autentificarea și achiziționarea cu succes a unui token, construiți un nou `HttpClient` sau utilizați unul existent cu suplimentul **DefaultRequestHeaders „Autorizare”** setat la **Purtător <access token>** și **Ocp-Apim-Subscription-Key** setat la [**cheie de abonament** din mediul dvs. Customer Insights](#get-started-trying-the-customer-insights-apis).    
   Resetați antetul **Autorizare** când este cazul. De exemplu, când tokenul a expirat.

1. Introduceți această `HttpClient` în construcția clientului `CustomerInsights`.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Eșantion de httpclient":::

1. Efectuați apeluri cu clientul pentru „metodele de extensie”, de exemplu, `GetAllInstancesAsync`. Dacă accesul la `Microsoft.Rest.HttpOperationResponse` subiacent este preferat, utilizați „metode de mesaj http”, de exemplu `GetAllInstancesWithHttpMessagesAsync`.

1. Răspunsul va fi probabil de tip `object` deoarece metoda poate returna mai multe tipuri (de exemplu, `IList<InstanceInfo>` și `ApiErrorResult`). Pentru a verifica tipul de returnare, puteți folosi în siguranță funcția cast pentru obiectele din tipurile de răspuns specificate în [pagina de detalii API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) pentru respectiva operațiune.    
   Dacă sunt necesare mai multe informații la cerere, utilizați **metode mesaj http** pentru a accesa obiectul de răspuns brut.

### <a name="nodejs-package"></a>Pachetul NodeJS

Utilizați bibliotecile client NodeJS disponibile prin NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Pachet Python

Utilizați bibliotecile client Python disponibile prin PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
