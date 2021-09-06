---
title: Mapați entitățile pentru unificarea datelor
description: Mapați datele pentru a crea profiluri de clienți unificate.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 570683876b10cb83d8af14552ca9bea9d80613575005d49a9af37cc16b8e75c9
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034421"
---
# <a name="map-entities-and-attributes"></a>Entități de hartă și atribute

**Maparea** este prima etapă a procesului de unificare a datelor din detaliile despre public. Maparea constă din trei faze:

- *Selectare entitate*: Identificați entitățile combinabile care duc la un set de date cu informații mai complete despre clienții dvs.
- *Selectarea atributelor*: Pentru fiecare entitate, identificați coloanele pe care doriți să le combinați și să le reconciliați în fazele de *Potrivire* și *Combinare*. Aceste coloane sunt numite *Atribute*.
- *Selectarea cheii primare și a tipului semantic*: Pentru fiecare entitate, identificați un atribut pe care doriți să îl definiți ca cheie primară pentru acea entitate și, pentru fiecare atribut, identificați un tip semantic care descrie cel mai bine acel atribut.

Pentru mai multe informații despre fluxul general de unificare a datelor, consultați [Unificare](data-unification.md).

## <a name="select-the-first-entities"></a>Selectați primele entități

1. În Detalii despre public, accesați **Date** > **Unificare** > **Mapare**.

2. Începeți faza de mapare selectând **Selectați entități**.

3. Selectați entitățile și atributele pe care doriți să le utilizați în fazele *potrivire* și *îmbinare*. Puteți selecta atributele necesare individual dintr-o entitate sau puteți include toate atributele dintr-o entitate selectând caseta de selectare **Includeți toate câmpurile** de la nivelul entității. Vă recomandăm să selectați cel puțin două entități pentru a beneficia de procesul de unificare a datelor.

   > [!div class="mx-imgBorder"]
   > ![Adăugați exemple de entități.](media/data-manager-configure-map-add-entities-example.png "Adăugați exemple de entități")

   În acest exemplu, adăugăm entitățile **eCommerceContacts** și **loyCustomers**. Alegând aceste entități, puteți obține informații despre care dintre clienții de afaceri online sunt membri ai programului de loialitate.
   
   Puteți căuta cuvinte cheie în toate atributele și entitățile pentru a selecta atributele necesare pe care doriți să le mapați.
   
     > [!div class="mx-imgBorder"]
   > ![Exemplu de câmpuri de căutare.](media/data-manager-configure-map-search-fields-example.png "Exemplu de câmpuri de căutare")

4. Selectați **Aplicare** pentru a vă confirma selecțiile.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Selectați cheia primară și tipul semantic pentru atribute

După selectarea entităților dvs., pagina **Hartă** listează entitățile selectate pentru examinare. Definiți cheia primară pentru o entitate și identificați tipul semantic pentru un atribut din entitate.

- **Cheia primară**: Selectați un atribut ca cheie primară pentru fiecare entitate. Pentru ca un atribut să fie o cheie primară validă, nu ar trebui să includă valori duplicate, valori lipsă sau valori nule. Atributele tipului de date șir, întreg și GUID sunt acceptate ca chei primare și vor fi afișate într-un câmp din care puteți selecta.

- **Tip de atribut semantic**: Categorii de atribute, cum ar fi adresa de e-mail sau numele. Pentru a utiliza modele de inteligență artificială pentru predicție inteligentă de semantică, economie de timp și îmbunătățirea preciziei, setați **Mapare inteligentă** la **PORNITĂ**. Maparea inteligentă evidențiază recomandările semantice bazate pe inteligență artificială în câmpul **Tip**. Dacă o setați la **OPRIT**, veți vedea recomandările noastre regulate de mapare. Puteți selecta orice tip semantic din lista de opțiuni disponibile și puteți înlocui selecția sugerată.

> [!div class="mx-imgBorder"]
> ![Tipul de atribut și predicție semantică.](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Tipul de atribut și predicție semantică")

Adăugarea unui tip semantic particularizat este de asemenea posibilă. Selectați câmpul tip pentru un atribut și introduceți numele dvs. de tip semantic particularizat. Astfel, puteți modifica tipurile de atribute care au fost identificate automat de sistem.

Toate atributele pentru care un tip semantic este identificat automat sunt grupate în secțiunea **Examinați câmpurile mapate**. Examinați aceste atribute și tipurile lor semantice, deoarece acestea vor fi utilizate pentru a combina entitățile dvs. în etapa de îmbinare a unificării datelor.

Atributele care nu sunt mapate automat la un tip semantic sunt grupate în secțiunea **Definiți datele în câmpurile nemapate**. Selectați câmpul de tip semantic pentru atributele nemapate sau introduceți numele tipului de atribut personalizat.

> [!div class="mx-imgBorder"]
> ![Cheie primară și tip de atribut.](media/data-manager-configure-map-add-attributes.png "Cheie primară și tip de atribut")

> [!NOTE]
> Un câmp ar trebui să fie mapat la tipul semantic Person.FullName pentru a completa numele clientului pe cardul clientului. În caz contrar, cărțile client vor apărea fără nume. 

## <a name="add-and-remove-attributes-and-entities"></a>Adăugați și eliminați atribute și entități

1. Pe **Unificare** > **Mapare**, selectați **Editați câmpurile**.

2. În panoul **Editați câmpurile**, adăugați sau eliminați atribute și entități. Folosiți căutarea sau derulați pentru a găsi și selecta atributele și entitățile de interes. Nu puteți elimina un atribut sau o entitate dacă au fost deja potrivite.

   > [!div class="mx-imgBorder"]
   > ![Adăugare sau eliminare atribute.](media/configure-data-map-edit.png "Adăugare sau eliminare atribute")

3. Selectați **Se aplică**.

## <a name="add-images-to-profiles"></a>Adăugați imagini la profiluri

Dacă o entitate conține URL-uri pentru imagini de profil sau logo-uri disponibile public, le puteți adăuga la profilul de client unificat.

Selectați entitatea și găsiți câmpul care conține adresa URL a imaginii de profil. În câmpul de intrare **Tip**, introduceți manual valoarea următoare: 
- Pentru o persoană: Person.ProfileImage
- Pentru o organizație: Organization.LogoImage

Continuați cu pașii de unificare și asigurați-vă că atributul care conține adresa URL a imaginii este, de asemenea, adăugat în pasul [Îmbinare](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Setați atribute pentru organizații

Pentru organizații (previzualizare), tipul de atribut ar trebui să fie asociat cu „Organization.Name”
> [!div class="mx-imgBorder"]
> ![Cheie primară și tip de atribut B2B](media/configure-data-map-edit-b2b.png "Cheie primară și tip de atribut B2B")

## <a name="next-step"></a>Următorul pas

Ca parte a procesului de unificare a datelor, accesați pagina **Potrivire**. Vizita [**Potrivire**](match-entities.md) pentru a vă informa cu privire la această fază.

> [!TIP]
> Consultați videoclipul următor: [Introducere: Crearea unui profil de client unificat](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]