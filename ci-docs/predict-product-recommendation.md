---
title: Preziceți recomandări de produse
description: Preziceți produsele pe care un client este probabil să le cumpere sau să interacționeze cu acestea.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610297"
---
# <a name="predict-product-recommendations"></a>Preziceți recomandări de produse

Modelul de recomandare a produsului creează seturi de recomandări predictive pentru produse. Recomandările se bazează pe comportamentul de cumpărare anterior și pe clienții cu modele de achiziție similare. Acest model este destinat consumatorilor individuali (B-to-C).

Trebuie să aveți cunoștințe de afaceri despre diferitele tipuri de produse pentru afacerea dvs. și despre modul în care clienții dvs. interacționează cu acestea. Susținem recomandarea de produse care au fost achiziționate anterior de clienții dvs. sau recomandări pentru produse noi.

Recomandările de produse pot fi supuse legilor și reglementărilor locale și așteptărilor clienților, pe care modelul nu este conceput pentru a le lua în considerare în mod specific. Prin urmare, **trebuie să revizuiți recomandările înainte de a le livra clienților dvs** pentru a vă asigura că respectați toate legile sau reglementările aplicabile și așteptările clienților pentru ceea ce puteți recomanda.

Ieșirea acestui model oferă recomandări bazate pe ID-ul produsului. Mecanismul dvs. de livrare trebuie să mapați ID-urile de produs prezise la conținut adecvat pentru ca clienții dvs. să țină cont de localizare, conținut de imagine și alt conținut sau comportament specific companiei.

> [!TIP]
> Încercați recomandarea de produs predicție folosind date mostre: [Recomandare produs predicție exemplu de ghid](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Cerințe preliminare

- Macar [Permisiuni de colaborator](permissions.md)
- Cel puțin 100 de clienți, de preferință mai mult de 10.000 de clienți.
- Customer Identifier, un identificator unic pentru a potrivi tranzacțiile cu un client individual
- Cel puțin un an de date tranzacționale, de preferință doi până la trei ani pentru a include o anumită sezonalitate. În mod ideal, cel puțin trei sau mai multe tranzacții pentru fiecare ID de client. Istoricul tranzacțiilor trebuie să includă:
  - **ID-ul de tranzacție** : identificatorul unic al unei achiziții sau tranzacții.
  - **Data tranzacției** : Data achiziției sau tranzacției.
  - **Valoarea tranzacției** : Valoarea numerică a achiziției sau tranzacției.
  - **ID unic de produs** : ID-ul produsului sau serviciului achiziționat dacă datele dvs. sunt la nivel de element rând.
  - **Cumpărați sau returnați** : O valoare booleană adevărat/fals unde *Adevărat* identifică că o tranzacție a fost o returnare. În cazul în care datele de cumpărare sau returnare nu sunt furnizate în model și **Valoarea tranzacției** este negativ, deducem un randament.
- O entitate de date din catalogul de produse de utilizat ca filtru de produs.

> [!NOTE]
> - Modelul necesită istoricul tranzacțiilor clienților dvs., unde tranzacția este orice date care descriu o interacțiune utilizator-produs. De exemplu, achiziționarea unui produs, participarea la un curs sau participarea la un eveniment.
> - Poate fi configurată o singură entitate istorică a tranzacțiilor. Dacă există mai multe entități de cumpărare, combinați-le Power Query înainte de ingerarea datelor.
> - Dacă detaliile comenzii și comenzii sunt entități diferite, alăturați-vă acestora înainte de a le utiliza în model. Modelul nu funcționează doar cu un ID de comandă sau un ID de primire într-o entitate.

## <a name="create-a-product-recommendation-prediction"></a>Creați o predicție de recomandare de produs

Selectați **Salveaza schita** oricând pentru a salva predicție ca schiță. Proiectul predicție este afișat în **Previziunile mele** fila.

1. Mergi la **Inteligența** > **Previziuni**.

1. Pe **Crea** filă, selectați **Utilizați modelul** pe **Recomandări de produse (previzualizare)** ţiglă.

1. Selectați **Începeți**.

1. **Denumiți acest model** și **Numele entității de ieșire** pentru a le distinge de alte modele sau entități.

1. Selectați **Următorul**.

### <a name="define-product-recommendation-preferences"></a>Definiți preferințele de recomandare a produselor

1. Seteaza **Numărul de produse** a recomanda unui client. Această valoare depinde de modul în care metoda dvs. de livrare umple datele.

1. Alegeți dacă doriți să includeți produse pe care clienții le-au achiziționat anterior în **Achiziții repetate așteptate** camp.

1. Seteaza **Uită-te la fereastra din spate** cu intervalul de timp pe care modelul îl ia în considerare înainte de a recomanda din nou produsul utilizatorului. De exemplu, indicați că un client achiziționează un laptop la fiecare doi ani. Modelul se uită la istoricul achizițiilor din ultimii doi ani, iar dacă găsește un articol, articolul este filtrat din recomandări.

1. Selectați **Următorul**

### <a name="add-purchase-history"></a>Adăugați istoricul achizițiilor

1. Selectați **Adăugați date** pentru **Istoricul tranzacțiilor clienților**.

1. Selectați tipul de activitate semantică **SalesOrderLine** care conține informațiile necesare despre istoricul tranzacțiilor sau achizițiilor. Dacă activitatea nu a fost configurată, selectați **Aici** și creează-l.

1. Sub **Activități**, dacă atributele activității au fost mapate semantic atunci când activitatea a fost creată, alegeți atributele sau entitatea specifice pe care doriți să se concentreze calculul. Dacă maparea semantică nu a avut loc, selectați **Editați | ×** și mapați datele dvs.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Panoul lateral care arată alegerea activităților specifice sub tipul semantic.":::

1. Selectați **Următorul** și revizuiți atributele necesare pentru acest model.

1. Selectați **Salvare**.

1. Selectați **Următorul**.

### <a name="add-product-information-and-filters"></a>Adăugați informații despre produse și filtre

Uneori, numai anumite produse sunt benefice sau adecvate pentru tipul de predicție pe care îl construiți. Utilizați filtre de produse pentru a identifica un subset de produse cu caracteristici specifice pe care să le recomandați clienților dvs. Modelul va utiliza toate produsele disponibile pentru a învăța modele, dar va utiliza numai produsele care corespund filtrului de produs în ieșirea sa.

1. Adăugați entitatea catalogului dvs. de produse care conține informații pentru fiecare produs. Hartați informațiile necesare și selectați **Salvați**.

1. Selectați **Următorul**.

1. Selectați **Filtre de produs**:

   - **Fără filtre**: Utilizați toate produsele din recomandarea produsului predicție.

   - **Definiți anumite filtre de produse**: Utilizați produse specifice în recomandarea produsului predicție. În **Atributele catalogului de produse** panoul, selectați atributele din entitatea catalogului de produse pe care doriți să le includeți în filtru.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Panoul lateral afișat atribuit în entitatea din catalogul de produse de selectat pentru filtrele de produse.":::

1. Alegeți dacă doriți ca filtrul de produs să fie utilizat **și** sau **sau** pentru a combina în mod logic selecția dvs. de atribute din catalogul de produse.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Exemplu de configurație a filtrelor de produs combinate cu conectori AND logici.":::

1. Selectați **Următorul**.

### <a name="set-update-schedule"></a>Configurați planificarea actualizărilor

1. Alegeți o frecvență pentru a vă reanaliza modelul. Această setare este importantă pentru a actualiza acuratețea predicțiilor pe măsură ce noi date sunt ingerate în Customer Insights. Majoritatea firmelor pot reinstrui o dată pe lună și pot obține o precizie bună pentru predicția lor.

1. Selectați **Următorul**.

### <a name="review-and-run-the-model-configuration"></a>Examinați și rulați configurația modelului

The **Examinați și alergați** pasul arată un rezumat al configurației și oferă șansa de a face modificări înainte de a crea predicție.

1. Selectați **Editați | ×** pe oricare dintre pașii pentru a revizui și a face orice modificări.

1. Dacă sunteți mulțumit de selecțiile dvs., selectați **Salvați și rulați** pentru a începe rularea modelului. Selectați **Terminat**. The **Previziunile mele** se afișează fila în timp ce predicție este creată. Procesul poate dura câteva ore până la finalizare, în funcție de cantitatea de date utilizate în predicție.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Vedeți rezultatele predicție

1. Mergi la **Inteligența** > **Previziuni**.

1. În **Previziunile mele** fila, selectați predicție pe care doriți să-l vizualizați.

Există cinci secțiuni principale de date în pagina de rezultate.

- **Performanta modelului:** Notele A, B sau C indică performanța predicție și vă pot ajuta să luați decizia de a utiliza rezultatele stocate în entitatea de ieșire.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Imagine a rezultatului performanței modelului cu nota A.":::

  Nivelurile sunt stabilite pe baza următoarelor reguli:
  - **A** când valoarea „Succes @ K” este cu cel puțin 10% mai mare decât valoarea de bază.
  - **B** când valoarea „Succes @ K” este cu 0% până la 10% mai mare decât valoarea de bază.
  - **C** când valoarea „Succes @ K” este mai mică decât valoarea de bază.
  - **De bază** : Cele mai recomandate produse în funcție de achiziție sunt numărate la toți clienții + regulile învățate identificate de model = un set de recomandări pentru clienți. Predicțiile sunt apoi comparate cu produsele de top, calculate după numărul de clienți care au achiziționat produsul. Dacă un client are cel puțin un produs recomandat în produsele sale, care a fost văzut și în produsele cumpărate de top, acesta este considerat o parte a liniei de bază. De exemplu, dacă 10 dintre acești clienți au achiziționat un produs recomandat din totalul de 100 de clienți, valoarea de bază este de 10%.
  - **Succes @ K** : Recomandările sunt create pentru toți clienții și comparate cu setul de validare al perioadei de timp a tranzacțiilor. De exemplu, într-o perioadă de 12 luni, luna 12 este pusă deoparte ca set de date de validare. Dacă modelul prezice cel puțin un lucru pe care l-ați cumpăra în luna 12 pe baza a ceea ce a învățat din cele 11 luni anterioare, clientul ar crește măsurătoarea „Success @ K”.

- **Cele mai sugerate produse (cu număr):** Primele cinci produse care au fost prezise pentru clienții dvs.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Grafic care prezintă primele 5 cele mai recomandate produse.":::

- **Factori cheie de recomandare:** Modelul folosește istoricul tranzacțiilor clienților pentru a face recomandări de produse. Învață modele bazate pe achiziții anterioare și găsește similitudini între clienți și produse. Aceste asemănări sunt apoi utilizate pentru a genera recomandări de produse.
  Următorii factori ar putea influența o recomandare de produs generată de model.
  - **Tranzacții anterioare** : Un produs recomandat sa bazat pe modele de cumpărare anterioare. De exemplu, modelul poate recomanda un *Surface Arc Mouse* dacă cineva a cumpărat recent un *Surface Book 3* și un *Surface Pen*. Modelul a aflat că, din punct de vedere istoric, mulți clienți au cumpărat un *Surface Arc Mouse* după achiziționarea unui *Surface Book 3* și a unui *Surface Pen*.
  - **Similitudinea clientului**: Un produs recomandat a fost achiziționat în mod istoric de alți clienți care prezintă modele de achiziție similare. De exemplu, lui John is s-au recomandat *Surface Headphones 2* pentru că Jennifer și Brad au cumpărat recent *Surface Headphones 2*. Modelul crede că John este similar cu Jennifer și Brad, deoarece au avut în mod istoric modele de cumpărare similare.
  - **Asemănarea produsului**: Un produs recomandat este similar cu alte produse cumpărate anterior de client. Modelul consideră că două produse sunt similare dacă au fost cumpărate împreună sau de către clienți similari. De exemplu, cineva primește o recomandare pentru o *Unitate de stocare USB* deoarece anterior au cumpărat un *Adaptor USB-C la USB* iar modelul crede că *Unitate de stocare USB* este similar cu *Adaptor USB-C la USB* pe baza modelelor istorice de cumpărare.

  Fiecare recomandare de produs este influențată de unul sau mai mulți dintre acești factori. Procentul recomandărilor în care fiecare factor de influență a jucat un rol este vizualizat într-un grafic. În exemplul următor, 100% din recomandări au fost influențate de tranzacțiile anterioare, 60% de similitudinea clienților și 22% de similaritatea produsului. Plasați cursorul peste barele din grafic pentru a vedea procentajul exact la care au contribuit factorii de influență.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Factori cheie de recomandare învățați de model pentru a genera recomandări de produse.":::

- **Statistici de date** : O prezentare generală a numărului de tranzacții, clienți și produse pe care modelul le-a luat în considerare. Se bazează pe datele de intrare care au fost utilizate pentru a învăța tiparele și a genera recomandări de produse.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Statistici de date despre datele de intrare utilizate de model pentru a învăța modele.":::
  
  Modelul folosește toate datele disponibile pentru a învăța modele. Prin urmare, dacă utilizați filtrarea produselor în configurația modelului, această secțiune arată numărul total de produse pe care modelul le-a analizat pentru a afla modele, care ar putea diferi de numărul de produse care corespund criteriilor de filtrare definite. Filtrarea se aplică pe rezultatul generat de model.

- **Exemple de recomandări de produse:** Un eșantion de recomandări despre care modelul consideră că ar putea fi achiziționate de către client. Dacă se adaugă un catalog de produse, ID-urile produselor sunt înlocuite cu nume de produse.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Listă care prezintă sugestii de mare încredere pentru un set selectat de clienți individuali.":::

> [!NOTE]
> În entitatea de ieșire pentru acest model, *Scor* arată măsura cantitativă a recomandării. Modelul recomandă produse cu un scor mai mare față de produsele cu un scor mai mic. Pentru a vizualiza scorul, accesați **Date** > **Entități** și vizualizați fila de date pentru entitatea de ieșire pe care ați definit-o pentru acest model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
