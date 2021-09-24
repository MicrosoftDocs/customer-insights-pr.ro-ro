---
title: Creați o legătură între detaliile despre public și detalii despre angajament
description: Creați o legătură activă între statistici despre public și statistici despre angajament pentru a permite partajarea bidirecțională a datelor.
ms.date: 09/08/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fdbc93292291814b2e1a62fee2c5ff796ae14e2
ms.sourcegitcommit: 4e5b7ec50c7612765a9ec2c8673e0cc43b357abb
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/10/2021
ms.locfileid: "7487122"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Creați o legătură între detaliile despre public și detalii despre angajament

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Integrarea dintre statistici despre implicare și statistici despre public leagă mediile de ambele capabilități și permite partajarea datelor bidirecțional între ele.

Utilizați profiluri și segmente unificate din statistici privind publicul pentru mai multe opțiuni de analiză în statistici despre angajament. Exportați evenimente care au o valoare comercială ridicată din statistici despre angajament. Utilizați aceste evenimente pentru a adăuga date la profiluri unificate în detalii despre public.

## <a name="prerequisites"></a>Cerințe preliminare

- Profilurile cu detalii despre public trebuie să fie stocate într-un cont Azure Data Lake Storage pe care îl dețineți sau într-un data lake [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md)&ndash;gestionat. 
- Mediul detaliilor dvs. despre public ar trebui să aibă un mediu Dataverse asociat. Și dacă și acel mediu utilizează Dataverse pentru stocarea datelor, asigurați-vă că verificați opțiunea **Activați partajarea datelor** în detaliile despre public. Pentru mai multe informații, consultați [Creați și configurați un mediu plătit în detalii despre public](../audience-insights/get-started-paid.md).
- Aveți nevoie de permisiuni de administrator atât pentru mediile de angajament, cât și pentru medii de public.
- Mediile conectate trebuie să se afle în aceeași regiune geografică.

> [!NOTE]
> - În cazul în care abonamentul dvs. de detalii privind publicul este o versiune de încercare care utilizează un data lake gestionat intern cu statistici de public, contactați [pirequest@microsoft.com](mailto:pirequest@microsoft.com) pentru ajutor. 
> - În cazul în care mediul dvs. de detalii despre public îl folosește pe al dvs. Azure Data Lake Storage pentru a stoca date, trebuie să adăugați un cont principal de serviciu Azure cu privire la angajament în contul dvs. de stocare. Pentru detalii, accesați [Conectați-vă la un cont Azure Data Lake Storage cu un director de serviciu Azure pentru informații despre public](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Crearea unui link de mediu

Puteți crea un link de mediu actualizând setările **Administrator** > **Mediu** în statistici despre angajament.

**Pentru a stabili un link activ între detalii despre public și detalii despre angajament**

1. Pe pagina **Administrator de mediu**, selectați fila **Conectați mediile**.

    :::image type="content" source="media/integrate1.png" alt-text="Configurați un mediu.":::

1. Selectați **Configurarea mediilor** în colțul din stânga sus sau în partea de jos a ecranului.

     :::image type="content" source="media/integrate2.png" alt-text="Selectați un mediu de detalii despre public.":::

1. Selectați un mediu de informații despre public, apoi selectați ***Următorul** pentru a termina. Acum puteți selecta caracteristici opționale pentru mediile conectate.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Activați atributele și segmentele profilurilor unificate pentru statisticile publicului

După conectarea mediilor, puteți selecta caracteristici opționale pentru mediile conectate. Aceste caracteristici permit atributele și segmentele de profil unificate din statistici privind publicul pentru analiza interactivă a datelor despre clienți.

**Pentru a analiza datele web în statistici despre angajament**

1. Pe pagina **Administrator de mediu**, porniți comutatorul **Partajați date din statistici privind publicul cu statistici despre implicare**, apoi selectați **Următorul**.

    :::image type="content" source="media/integrate4.png" alt-text="Selectați caracteristici.":::

1. Selectați atributele profilurilor unificate care vor deveni dimensiuni în statistici despre angajament. (Nu toate atributele sunt dimensiuni utile. De exemplu, este puțin probabil să aveți nevoie de **Prenume** sau **Nume de familie** ca atribut pentru analiza evenimentelor site-ului dvs. web.)

    :::image type="content" source="media/integrate5.png" alt-text="Organizare dimensiuni.":::

   >[!NOTE]
   > Toate atributele profilului statisticilor publicului care reprezintă identificatori (cum ar fi **ID** și **ID alternativ**) sunt filtrate din atributele disponibile și devin dimensiuni în perspectivele de angajament.

1. Când ați terminat selectarea atributelor, selectați **Următorul**.
1. Adăugați utilizatori care pot vizualiza dimensiunile și segmentele profilului detaliilor despre public și segmente în detalii despre angajament.

    :::image type="content" source="media/integrate6.png" alt-text="Gestionați accesul la datele clienților.":::

   > [!IMPORTANT]
   > Dacă nu adăugați în mod explicit utilizatori în acest pas, datele vor fi ascunse utilizatorilor în detalii despre angajament.
   > Pentru ca segmentele de statistici privind publicul să apară în statistici despre implicare, trebuie mai întâi să [rulați procesele de îmbinare și aval](../audience-insights/merge-entities.md). Procesele din aval sunt importante, deoarece generează un tabel unic care pregătește segmentele de informații despre public pentru a fi partajate cu datele de implicare. (Dacă este programată o reîmprospătare a sistemului, aceasta va include automat procesele din aval.)

1. Examinați selecția, apoi selectați **Finalizare**.

    :::image type="content" source="media/integrate7.png" alt-text="Examinați setările datelor clienților.":::

## <a name="export-refined-events-to-audience-insights"></a>Exportați evenimente rafinate la detaliile despre public

După ce creați o legătură între medii, puteți exporta evenimente rafinate de la statistici de angajament la statistici de public și le puteți ingera ca o nouă sursă de date. 

Pentru mai multe informații, accesați [Integrați date web din statistici despre angajament cu detalii despre public](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
