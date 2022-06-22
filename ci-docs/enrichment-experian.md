---
title: Îmbogățire cu îmbogățire de terță parte Experian
description: Informații generale despre îmbogățire de terță parte Experian.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 735da18e584b0d9db76b557f4d16dbdf1757f33c
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954102"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Îmbogățiți profilurile clienților cu date demografice din Experian (previzualizare)

Experian este un lider global în raportarea creditelor de consum și de afaceri și servicii de marketing. Cu serviciile Experian de îmbogățire a datelor, puteți construi o înțelegere mai profundă a clienților dvs. îmbogățind profilurile clienților cu date demografice, cum ar fi dimensiunea gospodăriei, veniturile și multe altele.

## <a name="supported-countriesregions"></a>Țări / regiuni acceptate

În prezent, acceptăm îmbogățirea profilurilor clienților numai în Statele Unite.

## <a name="prerequisites"></a>Cerințe preliminare

- Un activ Experian abonament. Pentru a obține un abonament, [contactați Experian](https://www.experian.com/marketing-services/contact) direct. [Aflați mai multe desore Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Un Experian [conexiune](connections.md) este [configurat](#configure-the-connection-for-experian) de către un administrator.

- Experian ID de utilizator, ID-ul părții și numărul de model pentru contul dvs. de transport securizat (ST) activat pentru SSH Experian creat pentru tine.

## <a name="configure-the-connection-for-experian"></a>Configurați conexiunea pentru Experian

Trebuie să fii un [administrator](permissions.md#admin) în Customer Insights și au un Experian ID utilizator, ID-ul părții și numărul de model.

1. Selectați **Adăugați conexiune** când configurați o îmbogățire sau accesați **Admin** > **Conexiuni** și selectați **Înființat** pe Experian ţiglă.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian panou de configurare a conexiunii.":::

1. Introduceți un nume pentru conexiune și un ID de utilizator valid, un ID de partid și un număr de model pentru dvs Experian Cont Transport Securizat.

1. Examinați și furnizați consimțământul pentru [Confidențialitatea și respectarea datelor](#data-privacy-and-compliance) prin selectarea **Sunt de acord**.

1. Selectați **Verifica** pentru a valida configurația și apoi selectați **Salvați**.

### <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Experian, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi date cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru a vă asigura că Experian îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Administratorul dvs. Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.

## <a name="configure-the-enrichment"></a>Configurați îmbogățirea

1. Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**.

1. Selectați **Îmbogățiți-mi datele** pe **Demografie** din Experian ţiglă.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian țiglă în pagina de prezentare generală a îmbogățirii.":::

1. Examinați prezentarea generală și apoi selectați **Următorul**.

1. Selectați conexiunea. Contactați un administrator dacă unul nu este disponibil.

1. Selectați **Următorul**.

1. Selectează **Set de date despre client** și alegeți profilul sau segmentul din care doriți să vă îmbogățiți cu date demografice Experian. The *Client* entitate îmbogățește toate profilurile dvs. de clienți, în timp ce un segment îmbogățește numai profilurile de clienți conținute în acel segment.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captură de ecran atunci când alegeți setul de date pentru clienți.":::

1. Definiți din ce tip de câmpuri din profilurile dvs. unificate să utilizați pentru potrivirea datelor demografice Experian. Cel puțin unul dintre câmpurile **Numele și adresa**, **Telefon** sau **E-mail** este necesar. Pentru o precizie mai mare a potrivirii, adăugați alte câmpuri. Selectați **Următorul**.

1. Hartați câmpurile cu datele demografice de la Experian.

1. Selectați **Următorul** pentru a completa maparea câmpului.

1. Furnizeaza un **Nume** pentru îmbogățire și pentru **Numele entității de ieșire**.

1. Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.

1. Selectați **Alerga** pentru a începe procesul de îmbogățire sau aproape pentru a reveni la **Îmbogățiri** pagină.

## <a name="enrichment-results"></a>Rezultate de îmbogățire

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

The **Număr de clienți îmbogățiți pe domeniu** oferă o detaliere a acoperirii fiecărui câmp îmbogățit.

## <a name="next-steps"></a>Pașii următori

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
