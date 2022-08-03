---
title: Creați măsuri din șabloane
description: Definiți măsuri folosind șabloane pentru cazuri de utilizare obișnuite.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170788"
---
# <a name="create-measures-from-templates"></a>Creați măsuri din șabloane

Utilizați șabloane predefinite de utilizate în mod obișnuit [măsuri](measures.md) pentru a le crea. Șabloanele se bazează pe date cartografiate din entitatea *Activitate unificată*. Deci, asigurați-vă că ați configurat [activitățile clienților](activities.md) înainte de a crea o măsură dintr-un șablon.

Șabloanele de măsură sunt acceptate numai în medii pentru **clienți individuali**. Pentru a crea măsuri personalizate sau pentru a crea măsuri pentru B-to-B, consultați [Utilizați generatorul de măsură](measure-builder.md).

Șabloane de măsură disponibile:
- Valoarea medie a tranzacției (ATV)
- Valoarea totală a tranzacțiilor
- Venitul mediu zilnic
- Venitul mediu lunar
- Venitul mediu anual
- Numărul de tranzacții
- Puncte de fidelitate câștigate
- Puncte de fidelitate valorificate
- Soldul punctelor de fidelitate
- Durată activă a ciclului de viață a clientului
- Durata apartenenței la programul de fidelitate
- Timp de la ultima achiziție

## <a name="build-a-new-measure-using-a-template"></a>Construiți o nouă măsură folosind un șablon

1. Mergi la **Măsuri**.

1. Selectați **Nou** și selectați **Alegeți un șablon**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Captură de ecran a meniului derulant atunci când creați o nouă măsură cu evidențiere pe șablon.":::

1. Găsiți șablonul care se potrivește nevoilor dvs. și selectați **Alegeți șablonul**.

1. Examinați datele necesare și selectați **Începeți** dacă aveți toate datele la locul lor.

1. Selectați **Editează detaliile** lângă Nume măsură. Furnizați un nume pentru măsura. Opțional, adăugați [Etichete](work-with-tags-columns.md#manage-tags) la masura.

   :::image type="content" source="media/measures_edit_details.png" alt-text="caseta de dialog Editare detalii.":::

1. Selectați **Terminat**.

1. În **Setați perioada de timp** secțiunea, definiți intervalul de timp al datelor. Alegeți dacă doriți ca noua măsură să acopere întregul set de date selectând **Tot timpul**, sau dacă doriți ca măsura să se concentreze pe o **Anumită perioadă de timp**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captură de ecran care arată secțiunea perioadei de timp la configurarea unei măsuri dintr-un șablon.":::

1. În secțiunea următoare, selectați **Adăugați date** pentru a alege activitățile și pentru a mapa datele corespunzătoare din entitatea *Activitate unificată*.

    1. Pasul 1 din 2: Sub **Tipul activității**, alegeți tipul entității pe care doriți să o utilizați. Pentru **Activități**, selectați entitățile pe care doriți să le mapați, apoi selectați **Următorul**.
    1. Pasul 2 din 2: Alegeți atributul din entitatea *Activitate unificată* pentru componenta cerută de formulă. De exemplu, pentru Valoarea medie a tranzacției, este atributul care reprezintă valoarea tranzacției. Pentru **Marca temporală a activității**, alegeți atributul din *Activitate unificată* entitate care reprezintă data și ora activității.
    1. Selectați **Salvare**.

    Când maparea datelor are succes, se afișează starea **Complet** și se afișează numele activităților și atributelor mapate.

1. Selectați **Alerga** pentru a calcula rezultatele măsurii. Selectați **Salveaza schita** dacă doriți să păstrați configurația curentă și să rulați măsura mai târziu. The **Măsuri** afișează pagina.

## <a name="next-step"></a>Pasul următor

Utilizați măsurile existente pentru a crea [un segment de clienți](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
