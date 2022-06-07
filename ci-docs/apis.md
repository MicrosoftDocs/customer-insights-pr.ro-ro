---
title: Lucrați cu API-uri
description: Folosirea de API-uri și înțelegerea limitărilor.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 9a04276f7326533cd389cba6554f468123463bac
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808521"
---
# <a name="work-with-customer-insights-apis"></a>Lucrul cu API-urile Customer Insights

Dynamics 365 Customer Insights furnizează API-uri pentru a vă crea propriile aplicații pe baza datelor dvs. în Customer Insights.

> [!IMPORTANT]
> Detaliile acestor API-uri sunt listate în [Referința de API-uri Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Acestea includ informații suplimentare despre operațiuni, parametri și răspunsuri.

Acest articol descrie cum să accesați API-urile Customer Insights, să creați o înregistrare a aplicației Azure și să începeți cu bibliotecile client.

## <a name="get-started-trying-the-customer-insights-apis"></a>Începeți să încercați API-urile Customer Insights

1. [Conectați-vă](https://home.ci.ai.dynamics.com) la Customer Insights. Dacă nu aveți încă un abonament, [înscrieți-vă pentru o versiune de încercare a Customer Insights](https://aka.ms/tryci).

1. Pentru a activa API-urile în mediul dvs. Customer Insights, accesați **Admin** > **Securitate**. Veți avea nevoie de permisiuni de administrator pentru asta.

1. Accesați fila **API-uri** și selectați butonul **Permite**.    
 
   Activarea API-urilor creează o cheie de abonament primară și una secundară pentru instanța dvs. care este folosită în solicitările API. Puteți regenera cheile selectând **Regenerați primar** sau **Regenerează secundar** pe **Admin** > **Securitate** > **API-uri**.

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. Selectați **Explorați API-urile noastre** pentru [a încerca API-urile](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Alegeți o operațiune API și selectați **Încearcă**.

1. În panoul lateral, setați valoarea în meniul derulant **Autorizare** la **implicită**. Antetul `Authorization` se adaugă cu un token la purtător. Cheia dvs. de abonament va fi populată automat.
  
1. Opțional, adăugați toți parametrii de interogare necesari.

1. Derulați până în partea de jos a panoului lateral și selectați **Trimitere**.

Răspunsul HTTP va apărea curând mai jos.

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Creați o nouă înregistrare a aplicației în portalul Azure

Acești pași vă ajută să începeți să utilizați API-urile Customer Insights într-o aplicație Azure utilizând permisiuni delegate. Asigurați-vă că completați [Secțiunea de început](#get-started-trying-the-customer-insights-apis) mai întâi.

1. Conectați-vă la [portalul Azure](https://portal.azure.com) cu contul care poate accesa datele Customer Insights.

1. În stânga, selectați **Înregistrări aplicații**.

1. Selectați **Înregistrare nouă**, furnizați un nume de aplicație și alegeți tipul de cont.

   Opțional, adăugați o adresă URL de redirecționare. http://localhost este suficient pentru dezvoltarea unei aplicații pe computerul dvs. local.

1. În noua înregistrare a aplicației, accesați **Permisiuni API**.

1. Selectați **Adăugați o permisiune** și selectați **Dynamics 365 AI pentru Customer Insights** în panoul lateral.

1. Pentru **Tipul permisiunii**, selectați **Permisiuni delegate** și apoi selectați permisiunea **user_impersonation**.

1. Selectați **Adăugare permisiuni**. Dacă trebuie să accesați API-ul fără conectarea unui utilizator, consultați secțiunea [Permisiuni pentru aplicații de la server la server](#server-to-server-application-permissions).

1. Selectați **Acordă consimțământul administratorului pentru...** pentru a finaliza înregistrarea aplicației.

Puteți utiliza ID-ul aplicației/clientului pentru această înregistrare a aplicației cu Biblioteca de autentificare Microsoft (MSAL) pentru a obține un token pentru purtător pe care îl trimiteți cu cererea dvs. către API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Pentru mai multe informații despre MSAL, consultați [Prezentare generală a bibliotecii de autentificare Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).

Pentru mai multe informații despre înregistrarea aplicațiilor în Azure, consultați [Înregistrați o aplicație](/graph/auth-register-app-v2).

Pentru informații despre utilizarea API-urilor în bibliotecile noastre client, consultați [Biblioteci client Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Permisiuni pentru aplicații de la server la server

[Secțiunea înregistrarea aplicației](#create-a-new-app-registration-in-the-azure-portal) descrie modul de înregistrare a unei aplicații care necesită conectarea unui utilizator pentru autentificare. Aflați cum să creați o înregistrare a aplicației care nu necesită interacțiunea utilizatorului și care poate fi rulată pe un server.

1. În înregistrarea aplicației dvs. în portalul Azure, accesați **Permisiuni API**.

1. Selectați **Adăugați o permisiune**. 

1. Selectați fila **API-urile pe care le folosește organizația mea** și alegeți **Dynamics 365 AI for Customer Insights** din listă. 

1. Pentru **Tip permisiune**, selectați **Permisiuni de aplicație** și apoi selectați permisiunea **CustomerInsights.Api.All**.

1. Selectați **Adăugare permisiuni**.

1. Reveniți la **Permisiuni API** pentru înregistrarea aplicației.

1. Selectați **Acordă consimțământul administratorului pentru...** pentru a finaliza înregistrarea aplicației.

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. În concluzie, trebuie să adăugăm numele înregistrării aplicației ca utilizator în Customer Insights.  
   
   Deschideți Customer Insights, accesați **Admin** > **Securitate** și selectați **Adăugați utilizator**.

1. Căutați numele înregistrării aplicației dvs., selectați-l din rezultatele căutării și selectați **Salvare**.

## <a name="sample-queries"></a>Exemple de interogări

Am compilat o listă scurtă de exemple de interogări OData pentru a lucra cu API-urile: [Exemple de interogări OData](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Biblioteci client Customer Insights

Această secțiune vă ajută să începeți să utilizați bibliotecile client disponibile pentru API-urile Customer Insights. Toate codurile sursă ale bibliotecii și exemplele de aplicații pot fi găsite pe [pagina GitHub Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Aflați cum să începeți să utilizați bibliotecile client C# de la NuGet.org. Pentru mai multe informații despre pachetul NuGet, consultați [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). În prezent, acest pachet vizează cadrele netstandard2.0 și netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Adăugați biblioteca client C# la un proiect C#

1. În Visual Studio, deschideți **Manager pachet NuGet** pentru proiectul dumneavoastră.

1. Căutați **Microsoft.Dynamics.CustomerInsights.Api**.

1. Selectați **Instalare** pentru a adăuga pachetul la proiect.
 
   Alternativ, rulați această comandă în **Consola Manager pachet NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Utilizați biblioteca de client C#

1. Folosiți [Biblioteca de autentificare Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) pentru a obține un `AccessToken` folosind [înregistrarea aplicației Azure](#create-a-new-app-registration-in-the-azure-portal) existentă.

1. După autentificarea și achiziția cu succes a unui token, construiți unul nou sau utilizați unul existent`HttpClient` cu **DefaultRequestHeaders „Autorizare”** setat la **„Jeton de acces” purtător** și **Ocp-Apim-Subscription-Key** setat la [**cheie de abonament** din mediul dvs. Customer Insights](#get-started-trying-the-customer-insights-apis).   
 
   Resetați antetul **Autorizare** când este cazul. De exemplu, când tokenul a expirat.

1. Introduceți această `HttpClient` în construcția clientului `CustomerInsights`.

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Efectuați apeluri cu clientul pentru „metodele de extensie”,"—de exemplu, `GetAllInstancesAsync`. Dacă accesul la `Microsoft.Rest.HttpOperationResponse` subiacent este preferat, utilizați „metode de mesaj http”—de exemplu `GetAllInstancesWithHttpMessagesAsync`.

1. Răspunsul va fi probabil de tip `object` deoarece metoda poate returna mai multe tipuri (de exemplu, `IList<InstanceInfo>` și `ApiErrorResult`). Pentru a verifica tipul de returnare, utilizați obiectele din tipurile de răspuns specificate pe [Pagina de detalii API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) pentru acea operațiune.    
   
   Dacă sunt necesare mai multe informații la cerere, utilizați **metode mesaj http** pentru a accesa obiectul de răspuns brut.

### <a name="nodejs-package"></a>Pachetul NodeJS

Utilizați bibliotecile client NodeJS disponibile prin NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Pachet Python

Utilizați bibliotecile client Python disponibile prin PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
