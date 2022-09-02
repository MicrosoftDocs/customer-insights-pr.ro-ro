---
title: Lucrul cu API-urile Customer Insights
description: Folosirea de API-uri și înțelegerea limitărilor.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387355"
---
# <a name="work-with-customer-insights-apis"></a>Lucrul cu API-urile Customer Insights

Dynamics 365 Customer Insights furnizează API-uri pentru a vă crea propriile aplicații pe baza datelor dvs. în Customer Insights.

> [!IMPORTANT]
> Detaliile acestor API-uri sunt listate în [Referința de API-uri Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Acestea includ informații suplimentare despre operațiuni, parametri și răspunsuri.

Încercați API-urile Customer Insights, creați o înregistrare a aplicației Azure și începeți cu bibliotecile client.

## <a name="get-started-trying-the-customer-insights-apis"></a>Începeți să încercați API-urile Customer Insights

Activați API-urile Customer Insights și încercați-le. Un administrator Customer Insights trebuie să activeze accesul API la Customer Insights. Odată ce accesul este activat, orice utilizator poate folosi API cu cheia de abonament.

1. [Conectați-vă](https://home.ci.ai.dynamics.com) la Customer Insights. Dacă nu aveți încă un abonament, [înscrieți-vă pentru o versiune de încercare a Customer Insights](https://aka.ms/tryci).

1. Mergi la **Admin** > **Securitate** și selectați **API-uri** fila.

1. Dacă accesul API la mediu nu a fost configurat, selectați **Permite** .

   Activarea API-urilor creează o cheie de abonament primară și una secundară pentru instanța dvs. care este folosită în solicitările API. Pentru a regenera cheile, selectați **Regenerați primar** sau **Regenerează secundar** pe **API-uri** fila.

1. Selectați [**Explorați API-urile noastre**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) pentru a încerca API-urile.

1. Căutați și selectați o operație API și selectați **Incearca-l**.

   :::image type="content" source="media/try-api.png" alt-text="Cum să testați API-urile.":::

1. În panoul lateral, setați valoarea în meniul derulant **Autorizare** la **implicită**. Antetul `Authorization` se adaugă cu un token la purtător. Cheia dvs. de abonament este completată automat.
  
1. Opțional, adăugați toți parametrii de interogare necesari.

1. Derulați până în partea de jos a panoului lateral și selectați **Trimitere**.

   Răspunsul HTTP este afișat în partea de jos a panoului.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Creați o nouă înregistrare a aplicației în portalul Azure

Creaza un nou [înregistrarea aplicației](/graph/auth-register-app-v2) pentru a utiliza API-urile Customer Insights într-o aplicație Azure folosind permisiuni delegate.

1. Completeaza [Secțiunea de început](#get-started-trying-the-customer-insights-apis).

1. Conectați-vă la [portalul Azure](https://portal.azure.com) cu contul care poate accesa datele Customer Insights.

1. Căutați și apoi selectați **Înregistrările aplicației**.

1. Selectați **Înregistrare nouă**, furnizați un nume de aplicație și alegeți tipul de cont.

   Opțional, adăugați o adresă URL de redirecționare. http://localhost este suficient pentru dezvoltarea unei aplicații pe computerul dvs. local.

1. Selectați **Înregistrare**.

1. În noua înregistrare a aplicației, accesați **Permisiuni API**.

1. Selectați **Adăugați o permisiune** și selectați **Dynamics 365 AI pentru Customer Insights** în panoul lateral.

1. Pentru **Tipul permisiunii**, selectați **Permisiuni delegate** și apoi selectați permisiunea **user_impersonation**.

1. Selectați **Adăugare permisiuni**.

1. Selectați **Acordă consimțământul administratorului pentru...** pentru a finaliza înregistrarea aplicației.

1. Pentru a accesa API-ul fără a se conecta un utilizator, accesați [Permisiuni pentru aplicații de la server la server](#server-to-server-application-permissions).

Puteți utiliza ID-ul aplicației/clientului pentru înregistrarea acestei aplicații cu [Biblioteca de autentificare Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) pentru a obține un token purtător pe care să îl trimiteți împreună cu solicitarea dvs. către API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Pentru informații despre utilizarea API-urilor în bibliotecile noastre client, consultați [Biblioteci client Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Permisiuni pentru aplicații de la server la server

Creați o înregistrare a aplicației care nu necesită interacțiunea utilizatorului și care poate fi rulată pe un server.

1. În înregistrarea aplicației dvs. în portalul Azure, accesați **Permisiuni API**.

1. Selectați **Adăugați o permisiune**.

1. Selectați fila **API-urile pe care le folosește organizația mea** și alegeți **Dynamics 365 AI for Customer Insights** din listă.

1. Pentru **Tip permisiune**, selectați **Permisiuni de aplicație** și apoi selectați permisiunea **CustomerInsights.Api.All**.

1. Selectați **Adăugare permisiuni**.

1. Reveniți la **Permisiuni API** pentru înregistrarea aplicației.

1. Selectați **Acordă consimțământul administratorului pentru...** pentru a finaliza înregistrarea aplicației.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Adăugați numele înregistrării aplicației ca utilizator în Customer Insights.

   1. Deschideți Customer Insights, accesați **Admin** > **Securitate** și selectați **Adăugați utilizatori**.

   1. Căutați numele înregistrării aplicației dvs., selectați-l din rezultatele căutării și selectați **Salvare**.

## <a name="sample-queries"></a>Exemple de interogări

Pentru o listă scurtă de exemple de interogări OData pentru a lucra cu API-urile, consultați [Exemple de interogări OData](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Biblioteci client Customer Insights

Începeți să utilizați bibliotecile de clienți disponibile pentru API-urile Customer Insights. Toate codurile sursă ale bibliotecii și exemplele de aplicații pot fi găsite pe [pagina GitHub Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

Utilizați bibliotecile client C# de la NuGet .org. În prezent, pachetul vizează cadrele netstandard2.0 și netcoreapp2.0. Pentru mai multe informații despre NuGet pachet, vezi [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

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

1. Efectuați apeluri cu clientul pentru „metodele de extensie”, de exemplu, `GetAllInstancesAsync`. Dacă accesul la subiacent`Microsoft.Rest.HttpOperationResponse` este de preferat, utilizați „metodele de mesaje http”, de exemplu,`GetAllInstancesWithHttpMessagesAsync`.

1. Răspunsul este probabil`object` tip deoarece metoda poate returna mai multe tipuri (de exemplu,`IList<InstanceInfo>` și`ApiErrorResult`). Pentru a verifica tipul de returnare, utilizați obiectele din tipurile de răspuns specificate pe [Pagina de detalii API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) pentru acea operațiune.

   Dacă sunt necesare mai multe informații la cerere, utilizați **metode mesaj http** pentru a accesa obiectul de răspuns brut.

### <a name="nodejs-package"></a>Pachetul NodeJS

Utilizați bibliotecile client NodeJS disponibile prin NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Pachet Python

Utilizați bibliotecile client Python disponibile prin PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
