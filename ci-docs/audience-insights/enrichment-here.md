---
title: Îmbogățirea HERE Technologies de terță parte
description: Informații generale despre îmbogățirea terță parte HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 1cbbad9bfe559bcb15b23894fc7475507aae8add
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376385"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Îmbogățirea profilurilor clienților cu HERE Technologies (previzualizare)

HERE Technologies este o companie de platformă de localizare care oferă date și servicii centrate pe locație. Cu serviciile de îmbogățire a datelor de la HERE Technologies, puteți construi o înțelegere mai precisă a locației clienților dvs. cu normalizarea adreselor, extragerea latitudinii și longitudinii și multe altele.

## <a name="prerequisites"></a>Cerințe preliminare

Pentru a configura îmbogățirile HERE Technologies, trebuie îndeplinite următoarele condiții prealabile:

- Aveți un abonament activ HERE Technologies. Pentru a obține un abonament, puteți să vă [înscrieți aici](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) sau [contactați HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direct. [Aflați mai multe despre îmbogățirea locației HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- O [conexiune](connections.md) HERE este disponibilă *sau* aveți permisiuni de [administrator](permissions.md#admin) și cheia API HERE Technologies.

## <a name="configure-the-enrichment"></a>Configurați îmbogățirea

1. Accesați **Date** > **Îmbogățire**. 

1. Selectați **Doresc îmbogățirea datelor** pe dala HERE Technologies și selectați **Începeți**.

   > [!div class="mx-imgBorder"]
   > ![Dală HERE Technologies.](media/HERE-tile.png "Dală HERE Technologies")

1. Selectați o [conexiune](connections.md) din lista derulantă. Contactați un administrator dacă nu este disponibilă nicio conexiune. Dacă sunteți administrator, puteți crea o conexiune selectând **Adăugați conexiune**. Alegeți **HERE Technologies** din lista derulantă. 

1. Selectați **Conectați-vă la HERE Technologies** pentru a confirma selecția.

1.  Selectați **Următorul** și alegeți **Set de date client** pe care doriți să le îmbogățiți cu date de localizare de la HERE Technologies. Puteți selecta entitatea **Client** pentru a vă îmbogăți toate profilurile de clienți sau selectați o entitate de segment pentru a îmbogăți numai profilurile de clienți din acel segment.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Captură de ecran atunci când alegeți setul de date pentru clienți.":::

1. Alegeți dacă doriți să mapați câmpurile la adresa primară și/sau secundară. Puteți specifica o mapare a câmpului pentru ambele adrese și puteți îmbogăți profilurile pentru ambele adrese separat. De exemplu, dacă există o adresă de domiciliu și a companiei. Selectați **Următorul**.

1. Definiți ce câmpuri din profilurile dvs. unificate ar trebui utilizate pentru a căuta date de locație potrivite de la HERE Technologies. Câmpurile **Stradă 1** și **Cod poștal** sunt obligatorii pentru adresa primară și/sau secundară selectată. Pentru o precizie mai mare a potrivirii, pot fi adăugate mai multe câmpuri.

   > [!div class="mx-imgBorder"]
   > ![Pagina de configurare pentru îmbogățirii HERE Technologies.](media/enrichment-HERE-configuration.png "Pagina de configurare pentru îmbogățirii HERE Technologies")

1. Selectați **Următorul** pentru a completa maparea câmpului.

1. Oferiți un nume pentru îmbogățire. 

1. Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.

## <a name="configure-the-connection-for-here-technologies"></a>Configurați conexiunea pentru HERE Technologies 

Trebuie să fiți administrator pentru a configura conexiunile. Selectați **Adăugați conexiune** la configurarea unei îmbogățiri *sau* mergeți la **Administrator** > **Conexiuni** și selectați **Configurare** pe dala HERE Technologies.

1. Introduceți un nume pentru conexiune în caseta **Nume afișat**.

1. Furnizați o cheie API HERE Technologies validă.

1. Examinați și furnizați consimțământul pentru **Confidențialitatea și respectarea datelor** prin selectarea **Sunt de acord**.

1. Selectați **Verificare** pentru a valida configurația.

1. După finalizarea verificării, selectați **Salvare**.

   > [!div class="mx-imgBorder"]
   > ![Pagina de configurare a conexiunii HERE Technologies.](media/enrichment-HERE-connection.png "Pagina de configurare a conexiunii HERE Technologies")

## <a name="enrichment-results"></a>Rezultate de îmbogățire

Pentru a începe procesul de îmbogățire, selectați **Rulare** din bara de comenzi. De asemenea, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei [reîmprospătări programate](system.md#schedule-tab). Timpul de procesare va depinde de mărimea datelor clienților dvs. și de timpii de răspuns API de la HERE Technologies.

După finalizarea procesului de îmbogățire, puteți consulta datele din profilurile clienților nou îmbogățite din **Îmbogățirile mele**. În plus, veți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.

Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.

## <a name="next-steps"></a>Pașii următori

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către HERE Technologies, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că HERE Technologies îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul dvs. Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
