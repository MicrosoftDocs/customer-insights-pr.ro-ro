---
title: Selectați câmpurile sursă pentru unificarea datelor
description: Primul pas în procesul de unificare este selectarea entităților, atributelor, cheilor primare și a tipurilor semantice pentru a mapa datele la profilul unificat al clientului.
recommendations: false
ms.date: 08/12/2022
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
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304580"
---
# <a name="select-source-fields-for-data-unification"></a>Selectați câmpurile sursă pentru unificarea datelor

Primul pas în unificare este selectarea entităților și câmpurilor din seturile de date pe care doriți să le unificați. Selectați entitățile care conțin detalii legate de client, cum ar fi numele, adresa, numărul de telefon și e-mailul. Puteți selecta una sau mai multe entități.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>Selectați entități și câmpuri

1. Mergi la **Date** > **Unifica**.

   Pentru clienții individuali (B-to-C), the **Unifica** se afișează pagina de destinație **Incepe** la primul pas, **Câmpurile sursă**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Captură de ecran a paginii de destinație unificate pentru experiența de prima rulare pentru clienții individuali.":::

   Pentru conturile de afaceri (B-to-B), the **Unifica** se afișează pagina de destinație **Unificați conturile** arătând **Incepe** la primul pas, **Câmpurile sursă**. The **Unificați contactele (previzualizare)** pașii sunt opționali și sunt în așteptarea finalizării unificării contului.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="Captură de ecran a paginii de destinație unificate pentru experiența de prima rulare pentru conturile de afaceri.":::

1. Selectați **Începeți**.

1. Pe **Câmpurile sursă** pagina, selectați **Selectați entitățile și câmpurile**. The **Selectați entitățile și câmpurile** afișează panoul.

1. Selectați cel puțin o entitate.

1. Pentru fiecare entitate selectată, identificați câmpurile pe care doriți să le utilizați pentru a potrivi înregistrările clienților și câmpurile de inclus în profilul unificat. Aceste câmpuri sunt numite *Atribute*. Puteți selecta atributele necesare individual dintr-o entitate sau puteți include toate atributele dintr-o entitate bifând caseta de selectare la nivel de entitate. Puteți căuta cuvinte cheie în toate atributele și entitățile pentru a selecta atributele necesare pe care doriți să le mapați.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Captură de ecran a entităților și atributelor selectate.":::

   În acest exemplu, adăugăm **eCommerceContacts** și **loyCustomer** entitati. Alegând aceste entități, puteți obține informații despre care dintre clienții de afaceri online sunt membri ai programului de loialitate.

1. Selectați **Aplicare** pentru a vă confirma selecțiile. Se afișează entitățile și atributele selectate.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Selectați cheia primară și tipul semantic pentru atribute

   :::image type="content" source="media/m3_select_primary.png" alt-text="Captură de ecran a entităților selectate cu cheia principală neselectată încă." lightbox="media/m3_select_primary.png":::

Pentru fiecare entitate, efectuați următorii pași.

1. Alege **Cheia principala**. Cheia primară este un atribut unic pentru entitate. Pentru ca un atribut să fie o cheie primară validă, nu ar trebui să includă valori duplicate, valori lipsă sau valori nule. Atributele tipului de date șir, întreg și GUID sunt acceptate ca chei primare.

1. Pentru a utiliza modele AI pentru predicție inteligent de semantică, care economisește timp și îmbunătățește acuratețea, asigurați-vă că **Cartografiere inteligentă** este pornit. Maparea inteligentă oferă recomandări semantice bazate pe AI în **Tip** camp.

1. Pentru fiecare atribut, alegeți o semantică **Tip** care descrie cel mai bine acel atribut, cum ar fi numele, orașul sau adresa de e-mail.

   > [!NOTE]
   > În B-to-C, un câmp ar trebui să se mapeze la tipul semantic *Persoană.Nume complet* pentru a completa numele clientului în cardul de client. În B-to-B, numele contului ar trebui să se mapeze la *Organization.Name*. În caz contrar, cărțile client vor apărea fără nume.

   1. Pentru a înlocui un tip de atribut identificat de sistem, selectați o altă opțiune. Dacă tipul nu există, creați un tip semantic personalizat selectând **Tip** câmp pentru atribut și introduceți numele tipului semantic personalizat.

   1. Pentru a adăuga un atribut care conține o adresă URL la imaginile de profil sau siglele disponibile public, selectați entitatea și câmpul care conține adresa URL. În **Tip** câmp, introduceți următoarele:
      - Pentru o persoană: Person.ProfileImage
      - Pentru o organizație: Organization.LogoImage

1. Examinați atributele în care un tip semantic este identificat automat. Aceste atribute sunt enumerate sub **Examinați câmpurile mapate**. Numai atributele cu același tip pot fi combinate în **Unificați câmpurile clienților** Etapa. Tipurile semantice sunt folosite pentru a sugera automat perspective. Asigurați-vă că tipurile pe care le-ați ales sunt consecvente în toate entitățile selectate.

1. Pentru atributele care nu sunt mapate automat la un tip semantic, selectați un câmp de tip semantic, introduceți numele tipului de atribut personalizat sau lăsați-le nemapate. Aceste atribute sunt enumerate sub **Definiți datele în câmpurile nemapate**.

1. După parcurgerea pașilor pentru fiecare entitate, selectați **Salvați câmpurile sursă**.

1. Selectați **Următorul**.

> [!div class="nextstepaction"]
> [Următorul pas: Eliminați duplicatele](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
