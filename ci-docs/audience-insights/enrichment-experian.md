---
title: Îmbogățire cu îmbogățire de terță parte Experian
description: Informații generale despre îmbogățire de terță parte Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ad1023135516ca9c49818d19aa84df68d16b2e3c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229979"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Îmbogățiți profilurile clienților cu date demografice din Experian (previzualizare)

Experian este un lider global în raportarea creditelor de consum și de afaceri și servicii de marketing. Cu serviciile Experian de îmbogățire a datelor, puteți construi o înțelegere mai profundă a clienților dvs. îmbogățind profilurile clienților cu date demografice, cum ar fi dimensiunea gospodăriei, veniturile și multe altele.

## <a name="prerequisites"></a>Cerințe preliminare

Pentru a configura Experian, trebuie îndeplinite următoarele condiții prealabile:

- Trebuie să aveți un abonament activ la Experian. Pentru a obține un abonament, [contactați Experian](https://www.experian.com/marketing-services/contact) direct. [Aflați mai multe desore Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- O conexiune Experian a fost deja configurată de un administrator *sau* aveți permisiuni de [administrator](permissions.md#administrator). De asemenea, aveți nevoie de ID-ul de utilizator, ID-ul de parte și numărul de model pentru contul dvs. de transport securizat (ST) activat SSH care a fost Experian creat pentru dvs.

## <a name="supported-countriesregions"></a>Țări / regiuni acceptate

În prezent, acceptăm îmbogățirea profilurilor clienților numai în Statele Unite.

## <a name="configure-the-enrichment"></a>Configurați îmbogățirea

1. Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**.

1. Selectați **Îmbogățește datele mele** pe dala Experian.

   > [!div class="mx-imgBorder"]
   > ![dală Experian.](media/experian-tile.png "Experian tile")
   > 

1. Selectați o [conexiune](connections.md) din lista derulantă. Contactați un administrator dacă nu este disponibilă nicio conexiune. Dacă sunteți administrator, puteți crea o conexiune selectând **Adăugați conexiune** și alegând Experian din lista derulantă. 

1. Selectați **Conectați-vă la Experian** pentru a confirma selectarea conexiunii.

1.  Selectați **Următorul** și alegeți **Set de date client** doriți să vă îmbogățiți cu date demografice din Experian. Puteți selecta entitatea **Client** pentru a vă îmbogăți toate profilurile de clienți sau selectați o entitate de segment pentru a îmbogăți numai profilurile de clienți din acel segment.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captură de ecran atunci când alegeți setul de date pentru clienți.":::

1. Selectați **Următorul** și definiți din ce tip de câmpuri din profilurile dvs. unificate trebuie utilizat pentru a căuta date demografice potrivite din Experian. Cel puțin unul dintre câmpurile **Numele și adresa**, **Telefon** sau **E-mail** este necesar. Pentru o acuratețe mai mare a potrivirii, pot fi adăugate până la alte două câmpuri. Această selecție va afecta câmpurile de mapare la care aveți acces în pasul următor.

    > [!TIP]
    > Mai multe atribute de identificare cheie trimise către Experian probabil va produce o rată de potrivire mai mare.

1. Selectați **Următorul** pentru a începe maparea câmpului.

1. Definiți care câmpuri din profilurile dvs. unificate ar trebui utilizate pentru a căuta date demografice potrivite din Experian. Câmpurile obligatorii sunt marcate.

1. Furnizați un nume pentru îmbogățire și un nume pentru entitatea de ieșire.

1. Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.

## <a name="configure-the-connection-for-experian"></a>Configurați conexiunea pentru Experian 

Trebuie să fiți administrator pentru a configura conexiunile. Selectați **Adăugați conexiune** la configurarea unei îmbogățiri *sau* accesați **Administrator** > **Conexiuni** și selectați **Configurat** pe dala Experian.

1. Selectați **Începeți lucrul**.

1. Introduceți un nume pentru conexiune în caseta **Nume afișat**.

1. Introduceți un ID de utilizator, un ID de parte și un număr de model valide pentru contul dvs. Experian de transport securizat.

1. Examinați și furnizați consimțământul pentru **Confidențialitatea și respectarea datelor** prin selectarea **Sunt de acord**.

1. Selectați **Verificare** pentru a valida configurația.

1. După finalizarea verificării, selectați **Salvare**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian panou de configurare a conexiunii.":::

## <a name="enrichment-results"></a>Rezultate de îmbogățire

Pentru a începe procesul de îmbogățire, selectați **Rulare** din bara de comenzi. De asemenea, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei [reîmprospătări programate](system.md#schedule-tab). Timpul de procesare va depinde de mărimea datelor clienților dvs. și de procesele de îmbogățire stabilite pentru contul dvs. de către Experian.

După finalizarea procesului de îmbogățire, puteți consulta datele din profilurile clienților nou îmbogățite din **Îmbogățirile mele**. În plus, veți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.

Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.

## <a name="next-steps"></a>Pașii următori

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Experian, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi date cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru a vă asigura că Experian îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul dvs. Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
