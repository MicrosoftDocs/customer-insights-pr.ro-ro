---
title: Unificați câmpurile clienților pentru unificarea datelor
description: Îmbinați entitățile pentru a crea profiluri de clienți unificate.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: ceb2724ad490c1ba44fd9b7ff2be04721892fca4
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082959"
---
# <a name="unify-customer-fields-for-data-unification"></a>Unificați câmpurile clienților pentru unificarea datelor

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

În acest pas al procesului de unificare, alegeți și excludeți atributele de îmbinat în entitatea dvs. de profil unificat. De exemplu, dacă trei entități aveau date de e-mail, poate doriți să păstrați toate cele trei câmpuri separate de e-mail sau să le îmbinați într-un singur câmp de e-mail pentru profilul unificat. Unele atribute sunt combinate automat de către sistem. Puteți crea ID-uri de clienți stabile și unice și puteți grupa profiluri asociate într-un cluster.

:::image type="content" source="media/m3_unify.png" alt-text="Pagina de îmbinare din procesul de unificare a datelor, afișând tabelul cu câmpuri îmbinate care definesc profilul de client unificat.":::

## <a name="review-and-update-the-customer-fields"></a>Examinați și actualizați câmpurile pentru clienți

1. Examinați lista câmpurilor care vor fi unificate sub **Câmpurile clientului** fila tabelului. Faceți orice modificări, dacă este cazul.

   1. Pentru orice câmpuri combinate, puteți:
      - [Editare](#edit-a-merged-field)
      - [Redenumire](#rename-fields)
      - [Separare](#separate-merged-fields)
      - [Excludere](#exclude-fields)
      - [Deplasați-vă în sus sau în jos](#change-the-order-of-fields)

   1. Pentru orice câmp, puteți:
      - [Combinare câmpuri](#combine-fields-manually)
      - [Combinați un grup de câmpuri](#combine-a-group-of-fields)
      - [Redenumire](#rename-fields)
      - [Excludere](#exclude-fields)
      - [Deplasați-vă în sus sau în jos](#change-the-order-of-fields)

1. Opțional, [generați configurația ID-ului clientului](#configure-customer-id-generation).

1. Opțional, [grupează profilurile în gospodării sau clustere](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Pasul următor: revizuiți unificarea](review-unification.md)

### <a name="edit-a-merged-field"></a>Editați un câmp îmbinat

1. Selectați un câmp îmbinat și alegeți **Editați | ×**. Se afișează panoul Combinați câmpuri.

1. Specificați cum să combinați sau să combinați câmpurile dintr-una dintre cele trei opțiuni:
    - **Importanţă**: Identifică valoarea câștigătorului pe baza rangului de importanță specificat pentru câmpurile participante. Este opțiunea implicită de combinare. Selectați **Mutați în sus/în jos** pentru a stabili clasamentul importanței.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Opțiunea de importanță din dialogul câmpurilor de îmbinare.":::

    - **Cel mai recent**: Identifică valoarea câștigătorului pe baza celui mai recent. Necesită o dată sau un câmp numeric pentru fiecare entitate participantă în domeniul câmpurilor de îmbinare pentru a defini actualitatea.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Opțiunea de noutate din dialogul câmpurilor de îmbinare.":::

    - **Cel mai puțin recent**: Identifică valoarea câștigătorului pe baza celui mai puțin recent. Necesită o dată sau un câmp numeric pentru fiecare entitate participantă în domeniul câmpurilor de îmbinare pentru a defini actualitatea.

1. Puteți adăuga mai multe câmpuri pentru a participa la procesul de îmbinare.

1. Puteți redenumi câmpul combinat.

1. Selectați **Finalizat** pentru a vă aplica modificările.

### <a name="rename-fields"></a>Redenumiți câmpurile

Schimbați numele afișat al câmpurilor îmbinate sau separate. Nu puteți modifica numele entității de ieșire.

1. Selectați câmpul și alegeți **Redenumiți**.

1. Introduceți noul nume afișat.

1. Selectați **Terminat**.

### <a name="separate-merged-fields"></a>Câmpuri îmbinate separate

Pentru a separa câmpurile îmbinate, găsiți atributul în tabel. Câmpurile separate sunt afișate drept puncte de date individuale în profilul de client unificat.

1. Selectați câmpul îmbinat și alegeți **Câmpuri separate**.

1. Confirmați separarea.

### <a name="exclude-fields"></a>Excludeți câmpuri

Excludeți un câmp îmbinat sau separat din profilul de client unificat. Dacă câmpul e utilizat în alte procese, de exemplu într-un segment, eliminați-l din aceste procese înainte de a-l exclude din profilul clientului.

1. Selectați un câmp și alegeți **Exclude**.

1. Confirmați excluderea.

Pentru a vedea lista tuturor câmpurilor excluse, selectați **Câmpuri excluse**. Dacă este necesar, puteți citi câmpul exclus.

### <a name="change-the-order-of-fields"></a>Modificarea ordinii câmpurilor

Unele entități conțin mai multe detalii decât altele. Dacă o entitate include cele mai recente date despre un câmp, le puteți oferi prioritate față de alte entități atunci când îmbinați valorile.

1. Selectați câmpul.
  
1. Alege **Deplasați-vă în sus/jos** pentru a seta ordinea sau trageți și plasați-le în poziția dorită.

### <a name="combine-fields-manually"></a>Combinați câmpurile manual

Combinați câmpuri separate pentru a crea un atribut îmbinat.

1. Selectați **Combina** > **Câmpuri**. Se afișează panoul Combinați câmpuri.

1. Specificați politica câștigătorului de îmbinare în lista derulantă **Combinați câmpurile după**.

1. Selectați **Adăugați câmp** pentru a combina mai multe domenii.

1. Furnizați un **Nume** și un **Nume al câmpului de ieșire**.

1. Selectați **Finalizat** pentru a aplica modificările.

### <a name="combine-a-group-of-fields"></a>Combinați un grup de câmpuri

Tratați un grup de câmpuri ca o singură unitate. De exemplu, dacă înregistrările noastre conțin câmpurile Adresa1, Adresa2, Orașul, Statul și Codul poștal, nu dorim să îmbinăm Adresa2 a unei alte înregistrări, crezând că ne-ar face datele mai complete.

1. Selectați **Combina** > **Grup de câmpuri**.

1. Specificați politica câștigătorilor de îmbinare în **Clasează grupurile după** scapă jos.

1. Selectați **Adăuga** și alegeți dacă doriți să adăugați mai multe câmpuri sau grupuri la câmpuri.

1. Furnizeaza un **Nume** si un **Nume de ieșire** pentru fiecare câmp combinat.

1. Furnizeaza un **Nume** pentru grupul de câmpuri.

1. Selectați **Finalizat** pentru a aplica modificările.

## <a name="configure-customer-id-generation"></a>Configurați generarea ID-ului clientului

Definiți cum să generați valorile ID-ului clientului, identificatorii unici ai profilului clientului. Pasul de unificare a câmpurilor din procesul de unificare a datelor generează identificatorul unic al profilului clientului. Identificatorul este *Număr de înregistrare client* în *Client* entitate care rezultă din procesul de unificare a datelor.

The *Număr de înregistrare client*  se bazează pe un hash al primei valori a cheilor primare ale câștigătoarei non-nule. Aceste chei provin de la entitățile utilizate în unificarea datelor și sunt influențate de ordinea potrivirii.Deci, ID-ul de client generat se poate schimba atunci când o valoare a cheii primare se modifică în entitatea principală a comenzii de potrivire. Este posibil ca valoarea cheii primare să nu reprezinte întotdeauna același client.

Configurarea unui ID stabil de client vă permite să evitați acel comportament.

1. Selectați fila **Chei**.

1. Plasați cursorul pe **Număr de înregistrare client** rând și selectați **Configurați**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Control pentru a personaliza generarea ID-ului.":::

1. Selectați până la cinci câmpuri care vor cuprinde un ID de client unic și care sunt mai stabile. Înregistrările care nu se potrivesc configurației dvs. utilizează în schimb un ID configurat de sistem.  

1. Selectați **Terminat**.

## <a name="group-profiles-into-households-or-clusters"></a>Profiluri de grup în gospodării sau clustere

Puteți defini reguli pentru gruparea profilurilor asociate într-un cluster. În prezent există două tipuri de clustere disponibile - clustere de uz casnic și personalizate. Sistemul alege automat o gospodărie cu reguli predefinite dacă entitatea *Client* conține câmpurile semantice *Person.LastName* și *Location.Address*. De asemenea, puteți crea un cluster cu propriile reguli și condiții, similar cu [potrivire reguli](match-entities.md#define-rules-for-match-pairs).

1. Selectați **Avansat** > **Creați cluster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Control pentru a crea un nou cluster.":::

1. Alegeți între un o **Gospodărie** sau un cluster **Particularizat**. Dacă câmpurile semantice *Person.LastName* și *Location.Address* în entitatea *Client*, gospodăria este selectată automat.

1. Furnizați un nume pentru cluster și selectați **Terminat**.

1. Selectați fila **Clustere** pentru a găsi clusterul pe care l-ați creat.

1. Specificați regulile și condițiile pentru a defini clusterul.

1. Selectați **Terminat**. Clusterul este creat când procesul de unificare este încheiat. Identificatorii clusterului sunt adăugați ca câmpuri noi la *Client* entitate.

> [!div class="nextstepaction"]
> [Pasul următor: revizuiți unificarea](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
