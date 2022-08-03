---
title: Îmbogățiți profilurile companiei cu Leadspace (previzualizare)
description: Informații generale despre îmbogățirea terță parte Leadspace.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 3f23fe7177f931db3e3179970915d0cd3c736f87
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196225"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Îmbogățiți profilurile companiei cu Leadspace (previzualizare)

Leadspace este o companie ce se ocupă cu știința datelor și care oferă o platformă de date pentru clienți B la B. Permite medii cu profiluri de clienți unificate bazate pe conturi să își îmbogățească datele. Îmbogăţiți *Profilurile clienților* cu atribute precum dimensiunea companiei, locația sau industria. Îmbogăţiți *Profiluri de contact* cu atribute precum titlul, persoana sau verificarea prin e-mail.

## <a name="prerequisites"></a>Cerințe preliminare

- O licență Leadspace activă.
- [Profiluri unificate ale clienților](customer-profiles.md) bazat pe conturi.
- Un Leadspace [conexiune](connections.md) este [configurat](#configure-the-connection-for-leadspace) de către un administrator. Luați legătura în mod direct cu [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) pentru detalii despre produsul lor.

## <a name="configure-the-connection-for-leadspace"></a>Configurați conexiunea pentru Leadspace

Trebuie să fii un [administrator](permissions.md#admin) în Customer Insights și au „cheia perpetuă” (denumită ca **Jeton Leadspace**).

1. Selectați **Adăugați conexiune** atunci când configurați o îmbogățire sau mergeți la **Admin** > **Conexiuni** și selectați **Înființat** pe tigla Leadspace.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Pagina de configurare a conexiunii Leadspace.":::

1. Introduceți un nume pentru conexiune și un simbol Leadspace valid.

1. Examinați și furnizați consimțământul pentru [Confidențialitatea și respectarea datelor](#data-privacy-and-compliance) prin selectarea **Sunt de acord**.

1. Selectați **Verifica** pentru a valida configurația și apoi selectați **Salvați**.

### <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Leadspace, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că Leadspace îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul dvs. Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.

## <a name="configure-the-enrichment"></a>Configurați îmbogățirea

1. Accesați **Date** > **Îmbogățire** și selectați fila **Descoperire**.

1. Selectați **Îmbogățiți-mi datele** pe **Datele companiei** din țiglă Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captură de ecran a dalei Leadspace.":::

1. Examinați prezentarea generală și apoi selectați **Următorul**.

1. Selectați conexiunea. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Selectați **Următorul**.

1. Selectează **Set de date despre client** și alegeți profilul sau segmentul pe care doriți să îl îmbogățiți cu datele companiei de la Leadspace. The *Client* entitate îmbogățește toate profilurile dvs. de clienți, în timp ce un segment îmbogățește numai profilurile de clienți conținute în acel segment.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Captură de ecran atunci când alegeți setul de date pentru clienți.":::

1. Definiți ce tip de câmpuri din profilurile dvs. unificate să utilizați pentru potrivire: adresa principală și/sau secundară. Puteți specifica o mapare a câmpului pentru ambele adrese și puteți îmbogăți profilurile pentru ambele adrese separat. De exemplu, pentru o adresă de domiciliu și o adresă de afaceri. Selectați **Următorul**.

1. Mapați câmpurile dvs. la datele companiei din Leadspace. Câmpul **Numele companiei** este obligatoriu. Pentru o precizie mai mare a potrivirii, până la două alte câmpuri, **Site-ul companiei** și **Locația companiei**, pot fi adăugate.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panoul de mapare a câmpului Leadspace.":::

1. Selectați **Următorul** pentru a completa maparea câmpului.

1. Bifați caseta de selectare dacă aveți *Profiluri de contact* pe care ați vrea să-l îmbogățiți. Customer Insights va mapa automat câmpurile necesare.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Contactul Leadspace înregistrează îmbogățirea.":::

1. Selectați **Următorul**.

1. Furnizeaza un **Nume** pentru îmbogățire și pentru **Numele entității de ieșire**.

1. Selectați **Salvați îmbogățirea** după ce v-ați revizuit alegerile.

1. Selectați **Alerga** pentru a începe procesul de îmbogățire sau aproape pentru a reveni la **Îmbogățiri** pagină.

## <a name="view-enrichment-results"></a>Vedeți rezultatele îmbogățirii

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Pentru informații suplimentare, consultați [API-uri Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Pașii următori

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
