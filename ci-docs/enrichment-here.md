---
title: Îmbogățiți profilurile clienților cu tehnologiile HERE (previzualizare)
description: Informații generale despre îmbogățirea terță parte HERE Technologies.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d88085b6be156dd1c895e9e5b38cc9d77acbdb95
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052066"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Îmbogățiți profilurile clienților cu tehnologiile HERE (previzualizare)

HERE Technologies este o companie de platformă de localizare care oferă date și servicii centrate pe locație. Serviciile de îmbogățire a datelor HERE Technologies îmbunătățesc precizia informațiilor despre locație despre clienții dvs. Oferă normalizarea adreselor, extragerea latitudinii și longitudinii și multe altele.

## <a name="prerequisites"></a>Cerințe preliminare

- Un abonament activ HERE Technologies. Pentru a obține un abonament, [înscrie-te aici](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) sau [contactați AICI Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direct. [Aflați mai multe despre îmbogățirea locației HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- A AICI [conexiune](connections.md) este [configurat](#configure-the-connection-for-here-technologies) de către un administrator.

## <a name="configure-the-connection-for-here-technologies"></a>Configurați conexiunea pentru HERE Technologies

Trebuie să fii un [administrator](permissions.md#admin) în Customer Insights și aveți o cheie activă HERE Technologies API.

1. Selectați **Adăugați conexiune** când configurați o îmbogățire sau accesați **Admin** > **Conexiuni** și selectați **Înființat** pe tigla HERE Technologies.

1. Introduceți un nume pentru conexiune și o cheie validă HERE Technologies API.

1. Examinați și furnizați consimțământul pentru [Confidențialitatea și respectarea datelor](#data-privacy-and-compliance) prin selectarea **Sunt de acord**.

1. Selectați **Verifica** pentru a valida configurația și apoi selectați **Salvați**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Pagina de configurare a conexiunii HERE Technologies.":::

### <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către HERE Technologies, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că HERE Technologies îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul dvs. Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.

## <a name="configure-the-enrichment"></a>Configurați îmbogățirea

1. Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**.

1. Selectați **Îmbogățiți-mi datele** pe **Locație** de AICI țiglă Tehnologii.

   :::image type="content" source="media/HERE-tile.png" alt-text="Dală HERE Technologies.":::

1. Examinați prezentarea generală și apoi selectați **Următorul**.

1. Selectați conexiunea. Contactați un administrator dacă unul nu este disponibil.

1. Selectați **Următorul**.

1. Selectează **Set de date despre client** și alegeți profilul sau segmentul pe care doriți să îl îmbogățiți cu date de la HERE Technologies. The *Client* entitate îmbogățește toate profilurile dvs. de clienți, în timp ce un segment îmbogățește numai profilurile de clienți conținute în acel segment.

1. Definiți ce tip de câmpuri din profilurile dvs. unificate să utilizați pentru potrivire: adresa principală și/sau secundară. Puteți specifica o mapare a câmpului pentru ambele adrese și puteți îmbogăți profilurile pentru ambele adrese separat. De exemplu, pentru o adresă de domiciliu și o adresă de afaceri. Selectați **Următorul**.

1. Hartați câmpurile dvs. la datele de la HERE Technologies. Câmpurile **Stradă 1** și **Cod poștal** sunt obligatorii pentru adresa primară și/sau secundară selectată. Pentru o precizie mai mare a potrivirii, adăugați mai multe câmpuri.

1. Selectați **Următorul** pentru a completa maparea câmpului.

1. Furnizeaza un **Nume** pentru îmbogățire și pentru **Numele entității de ieșire**.

1. Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.

1. Selectați **Alerga** pentru a începe procesul de îmbogățire sau aproape pentru a reveni la **Îmbogățiri** pagină.

## <a name="view-enrichment-results"></a>Vedeți rezultatele îmbogățirii

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

The **Număr de clienți îmbogățiți pe domeniu** oferă o detaliere a acoperirii fiecărui câmp îmbogățit.

## <a name="next-steps"></a>Pașii următori

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
