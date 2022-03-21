---
title: Creați măsuri din șabloane
description: Definiți măsuri folosind șabloane pentru cazuri de utilizare obișnuite.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 0fe846691825b93732cbbe6d1c942a79e4a3934f
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359960"
---
# <a name="use-a-template-to-build-a-measure"></a>Utilizați un șablon pentru a construi o măsură

Puteți utiliza șabloane predefinite de cele utilizate în mod obișnuit [măsuri](measures.md) pentru a le crea. Descrieri detaliate ale șabloanelor și o experiență ghidată vă ajută la crearea eficientă a măsurilor. Șabloanele se bazează pe date cartografiate din entitatea *Activitate unificată*. Deci, asigurați-vă că ați configurat [activitățile clienților](activities.md) înainte de a crea o măsură dintr-un șablon.

Pentru a crea măsuri personalizate, consultați [Utilizați generatorul de măsuri pentru a crea măsuri de la zero](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Consumatori individuali (B2C)](#tab/b2c)

Șabloane de măsură disponibile: 
- Valoarea medie a tranzacției (ATV)
- Valoarea totală a tranzacțiilor
- Venitul mediu zilnic
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

1. În panoul **Editați nume**, setați numele măsurii dvs. și entitatea de ieșire. 

1. Selectați **Terminat**.

1. În secțiunea **Setați perioada de timp**, definiți intervalul de timp al datelor de utilizat. Alegeți dacă doriți ca noua măsură să acopere întregul set de date selectând **Tot timpul**, sau dacă doriți ca măsura să se concentreze pe o **Anumită perioadă de timp**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captură de ecran care arată secțiunea perioadei de timp la configurarea unei măsuri dintr-un șablon.":::

1. În secțiunea următoare, selectați **Adăugați date** pentru a alege activitățile și pentru a mapa datele corespunzătoare din entitatea *Activitate unificată*.

    1. Pasul 1 din 2: Sub **Tipul activității**, alegeți tipul entității pe care doriți să o utilizați. Pentru **Activități**, selectați entitățile pe care doriți să le mapați.
    1. Pasul 2 din 2: Alegeți atributul din entitatea *Activitate unificată* pentru componenta cerută de formulă. De exemplu, pentru Valoarea medie a tranzacției, este atributul care reprezintă valoarea tranzacției. Pentru **Marcaj de timp al activității**, alegeți atributul din entitatea de activitate unificată care reprezintă data și ora activității.
   
1. Odată ce maparea datelor are succes, puteți vedea starea drept **Finalizată** și numele activităților și atributelor mapate.

1. Acum puteți selecta **Rulare** pentru a calcula rezultatele măsurii. Pentru a-l rafina mai târziu, selectați **Salvați schița**.

# <a name="business-accounts-b-to-b"></a>[Conturi de afaceri (B2B)](#tab/b2b)

Această funcție este disponibilă numai pentru măsurile create în medii cu clienți individuali ca public țintă principal.

---