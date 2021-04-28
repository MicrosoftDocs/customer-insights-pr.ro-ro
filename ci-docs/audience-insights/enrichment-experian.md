---
title: Îmbogățire cu îmbogățiri terță parte Experian
description: Informații generale despre îmbogățirea terță parte Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896388"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Îmbogățirea profilurilor clienților cu date demografice de la Experian (previzualizare)

Experian este lider global în raportarea creditelor pentru consumatori și afaceri și servicii de marketing. Cu Serviciile de îmbogățire a datelor Experian, puteți construi o înțelegere mai profundă a clienților dvs. îmbogățind profilurile clienților cu date demografice, cum ar fi dimensiunea gospodăriei, veniturile și multe altele.

## <a name="prerequisites"></a>Cerințe preliminare

Pentru a configura Experian, trebuie îndeplinite următoarele condiții prealabile:

- Aveți un abonament Experian activ. Pentru a obține un abonament, [contactați Experian](https://www.experian.com/marketing-services/contact) direct. [Aflați mai multe despre îmbogățirea datelor Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- O conexiune Experian a fost deja configurată de un administrator *sau* aveți permisiuni de [administrator](permissions.md#administrator). De asemenea, aveți nevoie de ID de utilizator, ID parte și numărul de model pentru contul dvs. de transport securizat (ST) activat SSH creat de Experian pentru dvs.

## <a name="configure-the-enrichment"></a>Configurați îmbogățirea

1. Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**.

1. Selectați **Doresc îmbogățirea datelor** din dala Experian.

   > [!div class="mx-imgBorder"]
   > ![Dală Experian](media/experian-tile.png "Dală Experian")
   > 

1. Selectați o [conexiune](connections.md) din lista verticală. Contactați un administrator dacă nu este disponibilă nicio conexiune. Dacă sunteți administrator, puteți crea o conexiune selectând **Adăugați conexiune** și alegând Experian din meniul cu lista verticală. 

1. Selectați **Conectați-vă la Experian** pentru a confirma alegerea.

1.  Selectați **Următorul** și alegeți **Set de date client** pe care doriți să le îmbogățiți cu date demografice de la Experian. Puteți selecta entitatea **Client** pentru a vă îmbogăți toate profilurile de clienți sau selectați o entitate de segment pentru a îmbogăți numai profilurile de clienți din acel segment.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captură de ecran atunci când alegeți setul de date pentru clienți.":::

1. Selectați **Următorul** și definiți ce tip de câmpuri din profilurile dvs. unificate ar trebui să fie utilizate pentru a căuta date demografice potrivite de la Experian. Cel puțin unul dintre câmpurile **Numele și adresa**, **Telefon** sau **E-mail** este necesar. Pentru o acuratețe mai mare a potrivirii, pot fi adăugate până la alte două câmpuri. Această selecție va afecta câmpurile de mapare la care aveți acces în pasul următor.

    > [!TIP]
    > Mai multe atribute de identificare cheie trimise către Experian generează probabil o rată de potrivire mai mare.

1. Selectați **Următorul** pentru a începe maparea câmpului.

1. Definiți câmpurile din profilurile dvs. unificate care ar trebui să fie utilizate pentru a căuta date demografice potrivite de la Experian. Câmpurile obligatorii sunt marcate.

1. Furnizați un nume pentru îmbogățire și un nume pentru entitatea de ieșire.

1. Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.

## <a name="configure-the-connection-for-experian"></a>Configurați conexiunea pentru Experian 

Trebuie să fiți administrator pentru a configura conexiunile. Selectați **Adăugați conexiune** la configurarea unei îmbogățiri *sau* mergeți la **Administrator** > **Conexiuni** și selectați **Configurare** pe dala Experian.

1. Selectați **Începeți lucrul**.

1. Introduceți un nume pentru conexiune în caseta **Nume afișat**.

1. Introduceți ID de utilizator, ID parte și număr de model valid pentru contul dvs. de transport securizat Experian.

1. Analizați și acordați-vă consimțământul pentru **Confidențialitatea și conformitatea datelor** prin selectarea casetei de selectare **De acord**

1. Selectați **Verificare** pentru a valida configurația.

1. După finalizarea verificării, selectați **Salvare**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Panoul de configurare a conexiunii Experian.":::

## <a name="enrichment-results"></a>Rezultate de îmbogățire

Pentru a începe procesul de îmbogățire, selectați **Rulare** din bara de comenzi. De asemenea, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei [reîmprospătări programate](system.md#schedule-tab). Timpul de procesare va depinde de mărimea datelor clienților dvs. și de procesele de îmbogățire stabilite pentru contul dvs. de Experian.

După finalizarea procesului de îmbogățire, puteți consulta datele din profilurile clienților nou îmbogățite din **Îmbogățirile mele**. În plus, veți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.

Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.

## <a name="next-steps"></a>Pașii următori

Creați în plus față de datele îmbogățite ale clienților. Creați [segmente](segments.md), [măsuri](measures.md) și chiar [exportați datele](export-destinations.md) pentru a oferi experiențe personalizate clienților.

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Experian, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Experian îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
