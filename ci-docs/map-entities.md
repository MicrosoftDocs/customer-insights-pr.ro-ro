---
title: Selectați câmpurile sursă pentru unificarea datelor
description: Primul pas în procesul de unificare este selectarea de entități, atribute, chei primare și tipuri semantice pentru a mapa datele la profilul unificat al clientului.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a962f1353b6e25b40c60b39a81ac936873f34d92
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741010"
---
# <a name="select-source-fields-for-data-unification"></a>Selectați câmpurile sursă pentru unificarea datelor

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Primul pas în unificare este selectarea entităților și câmpurilor din seturile de date pe care doriți să le unificați. Selectați entitățile care conțin detalii legate de client, cum ar fi numele, adresa, numărul de telefon și e-mailul. Puteți selecta una sau mai multe entități.

## <a name="select-entities-and-fields"></a>Selectați entități și câmpuri

1. Mergi la **Date** > **Unifica**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Captură de ecran a paginii de destinație unificate pentru experiența de prima rulare cu Începeți evidențiat.":::

1. Selectați **Începeți**.

1. Pe **Câmpurile sursă** pagina, selectați **Selectați entitățile și câmpurile**. The **Selectați entitățile și câmpurile** afișează panoul.

1. Selectați cel puțin o entitate.

1. Pentru fiecare entitate selectată, identificați câmpurile pe care doriți să le utilizați pentru a potrivi înregistrările clienților și câmpurile de inclus în profilul unificat. Aceste câmpuri sunt numite *Atribute*. Puteți selecta atributele necesare în mod individual dintr-o entitate sau puteți include toate atributele dintr-o entitate bifând caseta de selectare la nivel de entitate. Puteți căuta cuvinte cheie în toate atributele și entitățile pentru a selecta atributele necesare pe care doriți să le mapați.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Captură de ecran a entităților și atributelor selectate.":::

   În acest exemplu, adăugăm **Contacte** și **Loialitatea clienților** entitati. Alegând aceste entități, puteți obține informații despre care dintre clienții de afaceri online sunt membri ai programului de loialitate.

1. Selectați **Aplicare** pentru a vă confirma selecțiile. Se afișează entitățile și atributele selectate.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Selectați cheia primară și tipul semantic pentru atribute

   :::image type="content" source="media/m3_select_primary.png" alt-text="Captură de ecran a entităților selectate cu cheia primară nu este selectată." lightbox="media/m3_select_primary.png":::

Pentru fiecare entitate, efectuați următorii pași.

1. Alege **Cheia principala**. Cheia primară este un atribut unic pentru entitate. Pentru ca un atribut să fie o cheie primară validă, nu ar trebui să includă valori duplicate, valori lipsă sau valori nule. Atributele tipului de date șir, întreg și GUID sunt acceptate ca chei primare.

1. Pentru a utiliza modele AI pentru predicție inteligent de semantică, economisiți timp și îmbunătățiți acuratețea, asigurați-vă că **Cartografiere inteligentă** este pornit. Maparea inteligentă evidențiază recomandările semantice bazate pe inteligență artificială în câmpul **Tip**. Puteți suprascrie selecția sugerată alegând orice tip semantic din lista de opțiuni disponibile.

1. Pentru fiecare atribut, alegeți o semantică **Tip** care descrie cel mai bine acel atribut, cum ar fi numele, orașul sau adresa de e-mail.

   > [!NOTE]
   > Un câmp ar trebui să fie mapat la tipul semantic *Persoană.Nume complet* pentru a completa numele clientului în cardul de client. În caz contrar, cărțile client vor apărea fără nume.

   1. Pentru a modifica un tip de atribut identificat de sistem, selectați un alt tip. Dacă tipul nu există, creați un tip semantic personalizat selectând **Tip** câmp pentru atribut și introduceți numele tipului semantic personalizat.

   1. Pentru a adăuga un atribut care conține o adresă URL la imaginile de profil sau siglele disponibile public, selectați entitatea și câmpul care conține adresa URL. În **Tip** câmp, introduceți următoarele:
      - Pentru o persoană: Person.ProfileImage
      - Pentru o organizație: Organization.LogoImage

   1. Pentru un atribut de nume de cont, introduceți „Organization.Name” în **Tip** camp.

1. Examinați atributele în care un tip semantic este identificat automat. Aceste atribute sunt enumerate sub **Examinați câmpurile mapate**. Numai atributele cu același tip pot fi combinate în **Câmpuri unificate pentru clienți** Etapa. Tipurile semantice sunt folosite pentru a sugera automat perspective. Asigurați-vă că tipurile pe care le-ați ales sunt consecvente în toate entitățile selectate.

1. Pentru atributele care nu sunt mapate automat la un tip semantic, selectați un câmp de tip semantic, introduceți numele tipului de atribut personalizat sau lăsați-le nemapate. Aceste atribute sunt enumerate sub **Definiți datele în câmpurile nemapate**.

1. După parcurgerea pașilor pentru fiecare entitate, selectați **Salvați câmpurile sursă**.

1. Selectați **Următorul**.

> [!div class="nextstepaction"]
> [Pasul următor: Eliminați duplicatele](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
