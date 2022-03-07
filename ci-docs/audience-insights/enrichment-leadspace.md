---
title: Îmbogățirea profilurilor companiei cu îmbogățirea terță parte Leadspace
description: Informații generale despre îmbogățirea terță parte Leadspace.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f89ef6842c21cf6b78154586f818beffbcdcffb9
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230649"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Îmbogățirea profilurilor companiei cu Leadspace (previzualizare)

Leadspace este o companie ce se ocupă cu știința datelor și care oferă o platformă de date pentru clienți B la B. Permite medii cu profiluri de clienți unificate bazate pe conturi să își îmbogățească datele. Îmbogăţiți *Profilurile clienților* cu atribute precum dimensiunea companiei, locația sau industria. Îmbogăţiți *Profiluri de contact* cu atribute precum titlul, persoana sau verificarea prin e-mail.

## <a name="prerequisites"></a>Cerințe preliminare

Pentru a configura Leadspace, trebuie îndeplinite următoarele cerințe preliminare:

- Aveți o licență Leadspace activă.
- Aveți [profiluri unificate ale clienților](customer-profiles.md) pe baza conturilor.
- O conexiune Leadspace a fost deja configurată de un administrator sau aveți permisiuni de [administrator](permissions.md#administrator) și „cheia perpetuă" (denumită **Tokenul Leadspace**). Luați legătura în mod direct cu [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) pentru detalii despre produsul lor.

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

1. Bifați caseta de selectare dacă aveți *Profiluri de contact* pe care ați vrea să-l îmbogățiți. Statisticile publicului vor mapa automat câmpurile obligatorii.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Contactul Leadspace înregistrează îmbogățirea.":::
 
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


[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Leadspace, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Leadspace îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul dvs. Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
