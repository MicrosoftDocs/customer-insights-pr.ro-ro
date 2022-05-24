---
title: Eșantion de ghid de predicție pentru recomandarea produsului
description: Utilizați acest exemplu de ghid pentru a încerca modelul preinstalat de predicție a recomandării de produs.
ms.date: 05/16/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762701"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Eșantion de ghid de predicție pentru recomandarea produsului

Vă vom explica un exemplu complet de predicție a recomandării de produs folosind datele eșantion furnizate mai jos.

## <a name="scenario"></a>Scenariu

Contoso este o companie care produce cafea și aparate de cafea de înaltă calitate, pe care le vinde prin intermediul site-ului web Contoso Coffee. Scopul lor este să înțeleagă ce produse ar trebui să recomande clienților lor recurenti. Știind ce sunt mai mulți clienți **probabil să cumpere**, îi poate ajuta să economisească eforturile de marketing concentrându-se pe anumite elemente.

## <a name="prerequisites"></a>Cerințe preliminare

- Cel puțin [Permisiuni de contributor](permissions.md) în Customer Insights.
- Vă recomandăm să implementați pașii următori [într-un mediu nou](manage-environments.md).

## <a name="task-1---ingest-data"></a>Sarcina 1 - Ingerare date

Examinați articolele [despre ingerarea de date](data-sources.md) și [importul surselor de date folosind Power Query conectori](connect-power-query.md) specific. Următoarele informații presupun că v-ați familiarizat cu ingerarea datelor în general.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerarea datelor clienților de pe platforma de comerț electronic

1. Creați un sursă de date numită **eCommerce**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.

1. Introduceți adresa URL pentru persoanele de contact din comerțul electronic: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:
   - **DateOfBirth**: Dată
   - **CreatedOn**: Dată/Oră/Zonă

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformați data nașterii în dată.":::

1. În câmpul „Nume” din panoul din dreapta, redenumiți sursa de date din **Interogare** în **eCommerceContacts**

1. **Salvați** sursa de date.

### <a name="ingest-online-purchase-data"></a>Ingerați date de cumpărare online

1. Adăugați un alt set de date la aceeași sursă de date **eCommerce**. Alegeți din nou conectorul **Text/CSV**.

1. Introduceți adresa URL pentru **Achiziții online** date [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:
   - **PurchasedOn**: Dată/Oră
   - **TotalPrice**: Monedă

1. În câmpul **Nume** din panoul lateral, redenumiți sursa de date din **Interogare** în **eCommercePurchases**.

1. **Salvați** sursa de date.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerați datele clienților din schema de loialitate

1. Creați o sursă de date numită **LoyaltyScheme**, alegeți opțiunea de import și selectați conectorul **Text/CSV**.

1. Introduceți adresa URL pentru persoanele de contact de comerț electronic [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. În timp ce editați datele, selectați **Transformare** și apoi **Utilizați primul rând ca anteturi**.

1. Actualizați tipul de date pentru coloanele enumerate mai jos:
   - **DateOfBirth**: Dată
   - **RewardsPoints**: Număr întreg
   - **CreatedOn**: Dată/Oră

1. În câmpul **Nume** din panoul din dreapta, redenumiți sursa de date din **Interogare** în **loyCustomers**.

1. **Salvați** sursa de date.

## <a name="task-2---data-unification"></a>Sarcina 2 - Unificarea datelor

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Sarcina 3 - Configurați recomandarea produsului predicție

Cu profilurile de clienți unificate, acum putem rula recomandarea de produs predicție.

1. Accesați **Informații** > **Predicție** alegeți **Recomandarea produsului**.

1. Selectați **Începeți**.

1. Denumiți modelul **Modelul de recomandare pentru produsul OOB predicție** și entitatea de ieșire **OOBProductRecommendationModelPrediction**.

1. Definiți trei condiții pentru model:

   - **Numărul de produse**: Setați această valoare la **5**. Această setare definește câte produse doriți să le recomandați clienților dvs.

   - **Se așteaptă repetarea achizițiilor**: Selectați **Da** pentru a indica faptul că doriți să includeți produse în recomandarea pe care clienții dvs. au achiziționat-o anterior.

   - **Fereastră de privire retrospectivă:** Selectați cel puțin **365 de zile**. Această setare definește cât de departe va privi modelul înapoi spre activitatea clientului pentru a o utiliza drept intrare pentru recomandările sale.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferințe de model pentru modelul de recomandare produs.":::

1. În **Adăugați datele necesare** pas, selectați **Adăugați date**.

1. În **Adăugați date** panoul, alegeți **SalesOrderLine** ca entitate din istoricul achizițiilor. În acest moment, probabil că nu este încă configurat. Deschideți linkul în panou pentru a crea activitatea cu următorii pași:
   1. Introduceți un **Numele activității** și alegeți *eCommercePurchases:eCommerce* la fel de **Entitate de activitate**. The **Cheia principala** este *PurchaseId*.
   1. Definiți și denumiți relația cu *eCommerceContacts: entitate de comerț electronic* și alegeți **ContactId** ca cheie străină.
   1. Pentru unificarea activității, setați **Activitatea evenimentului** la fel de *Pretul total* și Timestamp la *CumpăratLa*. Puteți specifica mai multe câmpuri așa cum este descris în [Activități ale clienților](activities.md).
   1. Pentru **Tip de activitate**, alege *SalesOrderLine*. Harta urmatoarele campuri de activitate:
      - ID-ul liniei de comandă: PurchaseId
      - ID comandă: PurchaseId
      - Datele comenzii: PurchasedOn
      - ID produs: ProductId
      - Suma: TotalPrice
   1. Examinați și finalizați activitatea înainte de a reveni la configurația modelului.

1. Înapoi în **Selectați activități** pas, alegeți activitatea nou creată în **Activități** secțiune. Selectați **Următorul** iar maparea atributelor este deja completată. Selectați **salva**.

1. În acest exemplu de ghid, sărim peste **Adăugați informații despre produs** și **Filtre de produs** setat deoarece nu avem date despre informații despre produs.

1. În **Actualizări de date** pas, setați programul modelului.

   Modelul trebuie să se antreneze în mod regulat pentru a învăța noi modele atunci când sunt ingerate date noi. Pentru acest exemplu, selectați **Lunar**.

1. După examinarea tuturor detaliilor, selectați **Salvați și rulați**. Va dura câteva minute pentru a rula modelul prima dată.

## <a name="task-4---review-model-results-and-explanations"></a>Sarcina 4 - Examinați rezultatele modelului și explicațiile

Lăsați modelul să finalizeze pregătirea și notarea datelor. Acum puteți revizui explicațiile modelului de recomandare a produsului. Pentru mai multe informații, consultați [Examinați starea și rezultatele unei predicții](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Activitatea 5 - Creați un segment de produse achiziționate

Rularea modelului de producție creează o nouă entitate pe care o puteți vedea în **Date** > **Entități**.

Puteți crea un segment nou pe baza entității create de model.

1. Mergeți la **Segmente**. Selectați **Nou** și alegeți **Creați din Inteligență**.

   ![Crearea unui segment cu rezultatul modelului.](media/segment-intelligence.png)

1. Selectați punctul final **OOBProductRecommendationModelPrediction** și definiți segmentul:

   - Câmp: ID produs
   - Valoare: selectați primele trei ID-uri de produs

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Creați un segment din rezultatele modelului.":::

Acum aveți un segment care este actualizat dinamic, care identifică clienții care ar putea fi interesați să achiziționeze cele mai recomandate trei produse.

Pentru mai multe informații, consultați [Creați și gestionați segmente](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
