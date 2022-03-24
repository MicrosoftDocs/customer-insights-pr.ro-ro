---
title: Îmbogățiți profilurile clienților cu date despre locație din Azure Maps
description: Informații generale despre îmbogățire de primă parte Azure Maps.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 2cc44f7b453d2aca328c397b14787c8a02c5e490
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376661"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Îmbogățirea profilurilor clienților cu Azure Maps (previzualizare)

Azure Maps oferă date și servicii axate pe locație pentru a oferi experiențe bazate pe date geospațiale cu informații de locație încorporate. Serviciile de îmbogățire a datelor Azure Maps îmbunătățesc precizia informațiilor despre locație despre clienții dvs. Aduce capabilități precum normalizarea adreselor și extragerea latitudinii și longitudinii la Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Cerințe preliminare

Pentru a configura îmbogățirea datelor Azure Maps, trebuie îndeplinite următoarele condiții prealabile:

- Trebuie să aveți un abonament activ la Azure Maps. Pentru a obține un abonament, puteți să vă [înscrieți sau obțineți o încercare gratuită](https://azure.microsoft.com/services/azure-maps/).

- O [conexiune](connections.md) Azure Maps este disponibilă, *sau* aveți permisiuni de [administrator](permissions.md#admin) și o cheie API Azure Maps activă.

## <a name="configure-the-enrichment"></a>Configurați îmbogățirea

1. Accesați **Date** > **Îmbogățire**. 

1. Pe dala **Locație**, selectați **Îmbogățiți-mi datele**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Dală Azure Maps.":::

1. Selectați o [conexiune](connections.md) din lista derulantă. Contactați un administrator dacă nu este disponibilă o conexiune Azure Maps. Dacă sunteți administrator, puteți să [configurați conexiunea pentru Azure Maps](#configure-the-connection-for-azure-maps). 

1. Selectați **Următorul** pentru a confirma selecția.

1. Alegeți **Set de date pentru clienți** doriți să vă îmbogățiți cu date despre locație din Azure Maps. Puteți selecta entitatea **Client** pentru a vă îmbogăți toate profilurile unificate de clienți sau selectați o entitate de segment pentru a îmbogăți numai profilurile de clienți din acel segment.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Captură de ecran la alegerea setului de date pentru clienți.":::

1. Alegeți dacă doriți să mapați câmpurile la adresa primară și/sau secundară. Puteți specifica o mapare a câmpului pentru ambele adrese și puteți îmbogăți profilurile pentru ambele adrese separat&mdash;de exemplu, pentru o adresă de domiciliu și o adresă de afaceri. Selectați **Următorul**.

1. Definiți care câmpuri din profilurile dvs. unificate pentru a utiliza pentru a căuta date de locație potrivite din Azure Maps. Câmpurile **Strada 1** și **Cod Poștal/Zip** sunt obligatorii pentru adresa primară sau secundară selectată. Pentru o precizie mai mare a potrivirii, puteți adăuga mai multe câmpuri.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Pagina de configurare pentru îmbogățire Azure Maps.":::

1. Selectați **Următorul** pentru a completa maparea câmpului.

1. Evaluați dacă doriți să modificați **Setări avansate**. Acestea sunt furnizate pentru a oferi flexibilitate maximă pentru gestionarea cazurilor de utilizare avansate, dar valorile implicite vor fi adecvate în majoritatea cazurilor:
   - **Tipul adreselor**: Comportamentul implicit este acela că îmbogățirea va returna cea mai bună potrivire a adresei chiar dacă este incompletă. Pentru a obține numai adrese complete&mdash;de exemplu, adrese care includ numărul casei&mdash;debifați toate casetele de selectare, cu excepția **Adrese punct**. 
   - **Limba**: În mod implicit, adresele sunt returnate în limba pentru regiunea căreia sa stabilit că aparține adresei. Pentru a aplica o limbă de adresă standardizată, selectați limba din meniul derulant. De exemplu, selectând **Engleză** va returna **Copenhagen, Denmark** în loc de **København, Danmark**.

1. Oferiți un nume pentru îmbogățire.

1. Examinați-vă alegerile, apoi selectați **Salvați îmbogățirea**.

## <a name="configure-the-connection-for-azure-maps"></a>Configurați conexiunea pentru Azure Maps

Trebuie să fiți administrator în statisticile publicului pentru a configura conexiunile. Selectați **Adăugați conexiune** când configurați o îmbogățire sau accesați **Administrator** > **Conexiuni** și selectați **Configurare** pe dala Azure Maps.

1. În caseta **Numele afișat**, introduceți un nume pentru conexiune.

1. Furnizați o cheie API Azure Maps validă.

1. Analizați și acordați-vă consimțământul pentru **Confidențialitatea și conformitatea datelor** prin selectarea casetei de selectare **De acord**

1. Selectați **Verificare** pentru a valida configurația.

1. După finalizarea verificării, selectați **Salvare**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Pagina de configurare pentru conexiune Azure Maps.":::

## <a name="enrichment-results"></a>Rezultate de îmbogățire

Pentru a începe procesul de îmbogățire, selectați **Rulare** din bara de comenzi. De asemenea, puteți lăsa sistemul să ruleze automat îmbogățirea ca parte a unei [reîmprospătări programate](system.md#schedule-tab). Timpul de procesare va depinde de mărimea datelor clienților dvs. și de timpul de răspuns al API-ului.

După finalizarea procesului de îmbogățire, puteți consulta datele profilurilor de clienți nou îmbogățite de la **Îmbogățirile mele**. În plus, veți găsi ora ultimei actualizări și numărul de profiluri îmbogățite.

Puteți accesa o vedere detaliată a fiecărui profil îmbogățit selectând **Vizualizați datele îmbogățite**.

## <a name="next-steps"></a>Pașii următori

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către Azure Maps, permiteți transfer de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi date cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru a vă asigura că Azure Maps îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru mai multe informații, accesați [Declarație de confidențialitate Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această îmbogățire oricând, pentru a întrerupe utilizarea acestei funcționalități.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
