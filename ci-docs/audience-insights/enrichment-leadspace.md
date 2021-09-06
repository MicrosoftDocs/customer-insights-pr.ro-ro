---
title: Îmbogățirea profilurilor companiei cu îmbogățirea terță parte Leadspace
description: Informații generale despre îmbogățirea terță parte Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 34b73b37670ed45e2c31ea164c0788b793bee433829ce21317c83903f3fca1fe
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031718"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Îmbogățirea profilurilor companiei cu Leadspace (previzualizare)

Leadspace este o companie de știință a datelor care oferă o platformă de date pentru clienți B2B. Aceasta permite clienților cu profiluri de clienți unificate pentru companii să-și îmbogățească datele. Îmbogățirile includ mai multe atribute, cum ar fi dimensiunea companiei, locația, industria și multe altele.

## <a name="prerequisites"></a>Cerințe preliminare

Pentru a configura Leadspace, trebuie îndeplinite următoarele cerințe preliminare:

- Aveți o licență Leadspace activă.
- Aveți [profiluri de clienți unificate](customer-profiles.md) pentru companii.
- O conexiune Leadspace a fost deja configurată de un administrator sau aveți permisiuni de [administrator](permissions.md#administrator) și „cheia perpetuă" (denumită **Tokenul Leadspace**). Luați legătura în mod direct cu [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) pentru detalii despre produsul lor.

## <a name="configure-the-enrichment"></a>Configurați îmbogățirea

1. În Detalii despre audiență, accesați **Date** > **Îmbogățire**.

1. Selectați **Doresc îmbogățirea datelor** pe dala Leadspace și selectați **Începeți**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captură de ecran a dalei Leadspace.":::

1. Selectați o [conexiune](connections.md) din lista derulantă. Contactați un administrator dacă nu este disponibilă nicio conexiune. Dacă sunteți administrator, puteți crea o conexiune selectând **Adăugați conexiune** și alegând **Leadspace**. 

1. Selectați **Conectați-vă la Leadspace** pentru a confirma conexiunea.

1. Selectați **Următorul** și alegeți **Set de date client** pe care doriți să le îmbogățiți cu date despre companie de la Leadspace. Puteți selecta entitatea **Client** pentru a vă îmbogăți toate profilurile de clienți sau selectați o entitate de segment pentru a îmbogăți numai profilurile de clienți din acel segment.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Captură de ecran atunci când alegeți setul de date pentru clienți.":::

1. Selectați **Următorul** și definiți ce câmpuri din profilurile dvs. unificate sunt utilizate pentru a căuta datele companiei potrivite de la Leadspace. Câmpul **Numele companiei** este obligatoriu. Pentru o precizie mai mare a potrivirii, până la două alte câmpuri, **Site-ul companiei** și **Locația companiei**, pot fi adăugate.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panoul de mapare a câmpului Leadspace.":::

1. Selectați **Următorul** pentru a completa maparea câmpului.

1. Furnizați un nume pentru îmbogățire și selectați **Salvați îmbogățirea** după ce v-ați analizat alegerile.


## <a name="configure-the-connection-for-leadspace"></a>Configurați conexiunea pentru Leadspace 

Trebuie să fiți administrator pentru a configura conexiunile. Selectați **Adăugați conexiune** la configurarea unei îmbogățiri *sau* mergeți la **Administrator** > **Conexiuni** și selectați **Configurare** pe dala Leadspace.

1. Selectați **Începeți lucrul**. 

1. Introduceți un nume pentru conexiune în caseta **Nume afișat**.

1. Furnizați un token Leadspace valid.

1. Examinați și furnizați consimțământul pentru **Confidențialitatea și respectarea datelor** prin selectarea **Sunt de acord**.

1. Selectați **Verificare** pentru a valida configurația.

1. După finalizarea verificării, selectați **Salvare**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Pagina de configurare a conexiunii Leadspace.":::

## <a name="enrichment-results"></a>Rezultate de îmbogățire

După reîmprospătarea îmbogățirii, puteți examina datele companiei nou îmbogățite sub [Îmbogățirile mele](enrichment-hub.md). Puteți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.

Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.

Pentru informații suplimentare, consultați [API-uri Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Pașii următori

Creați în plus față de datele îmbogățite ale clienților. Creați [segmente](segments.md) și [măsuri](measures.md), și chiar [exportați datele](export-destinations.md) pentru a oferi clienților dvs. experiențe particularizate.

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Leadspace, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Leadspace îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul dvs. Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
