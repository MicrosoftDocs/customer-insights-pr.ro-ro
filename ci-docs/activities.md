---
title: Activități de contact cu clienții sau cu afaceri
description: Definiți activitățile de contact cu clienții sau de afaceri și vizualizați-le într-o cronologie pe profilurile clienților.
ms.date: 10/26/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: srivas15
ms.author: shsri
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: d8caa477278f04c3a0a95ced15f4bea2a22aa8cd
ms.sourcegitcommit: da6a2d189edacc8f2c0f2abedcb28245f26fe74c
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/27/2022
ms.locfileid: "9723796"
---
# <a name="customer-or-business-contact-activities"></a>Activități de contact cu clienții sau cu afaceri

Activitățile clienților sunt acțiuni sau evenimente efectuate de clienți sau contacte de afaceri. De exemplu, tranzacții, durata apelului de asistență, recenzii ale site-urilor web, achiziții sau returnări. Aceste activități sunt conținute în una sau mai multe surse de date. Cu Customers Insights, consolidați-vă activitățile clienților din acestea [surse de date](data-sources.md) și asociați-le cu profilurile clienților. Aceste activități apar cronologic într-o cronologie pe profilul clientului. Includeți cronologia în aplicațiile Dynamics 365 cu [Supliment pentru cardul clientului](customer-card-add-in.md) soluţie.

## <a name="define-a-customer-activity"></a>Definiți o activitate de client

O entitate trebuie să aibă cel puțin un atribut de tip **Data** pentru a fi incluse într-o cronologie a clientului. Controlul **Adăugați activitate** este dezactivat dacă nu se găsește o astfel de entitate.

1. Mergi la **Date** > **Activități**.

1. Selectați **Adăugați activitate** pentru a începe experiența ghidată.

1. În **Date de activitate** pas, introduceți următoarele informații:

   - **Numele activității**: Selectați un nume pentru activitatea dvs.
   - **Entitate de activitate** : Selectați o entitate care include date tranzacționale sau de activitate.
   - **Cheie primară**: Selectați câmpul care identifică în mod unic o înregistrare. Nu ar trebui să conțină valori duplicate, valori goale sau valori lipsă.

     > [!NOTE]
     > Cheia primară pentru fiecare rând trebuie să rămână consecventă în timpul reîmprospătărilor sursă de date. Dacă cheia primară pentru un rând este actualizată într-o reîmprospătare sursă de date, aceasta creează duplicate în entitatea de ieșire Activitate. 

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configurați datele despre activitate cu numele, entitatea și cheia primară.":::

1. Selectați **Următorul**.

1. În **Relaţie** pas, selectați **Adaugă relația** pentru a conecta datele dvs. de activitate la înregistrarea clientului corespunzătoare. Acest pas vizualizează conexiunea dintre entități.  

   - **Cheie externă** : Câmp străin din entitatea dvs. de activitate care va fi folosit pentru a stabili o relație cu o altă entitate.
   - **La numele entității** : Entitatea client sursă corespunzătoare cu care va fi în relație entitatea dvs. de activitate. Vă puteți raporta doar la entitățile client sursă care sunt utilizate în procesul de unificare a datelor.
   - **Numele relației** : Dacă există deja o relație între această entitate de activitate și entitatea client sursă selectată, numele relației va fi în modul numai citire. Dacă nu există o astfel de relație, va fi creată o nouă relație cu numele pe care îl furnizați în această casetă.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definiți relația dintre entități.":::

   > [!TIP]
   > În mediile B la B, puteți selecta între entități de cont și alte entități. Dacă selectați o entitate de cont, calea relației este setată automat. Pentru alte entități, trebuie să definiți calea relației pentru una sau mai multe entități intermediare până când ajungeți la o entitate de cont.

1. Selectați **aplica** pentru a crea relația.

1. Selectați **Următorul**.

1. În pasul **Unificarea activităților**, alegeți evenimentul de activitate și ora de începere a activității dvs.
   - **Câmpuri obligatorii**
      - **Activitatea evenimentului**: Câmp care este evenimentul pentru această activitate.
      - **Marcă de timp**: Câmp care reprezintă ora de începere a activității dvs.

   - **Câmpuri opționale**
      - **Detalii suplimentare**: Câmp cu informații relevante pentru această activitate.
      - **Pictogramă**: Pictogramă care reprezintă cel mai bine acest tip de activitate.
      - **Adresa web**: Câmp care conține o adresă URL cu informații despre această activitate. De exemplu, sistemul tranzacțional care furnizează această activitate. Această adresă URL poate fi orice câmp din sursă de date sau poate fi construită ca un câmp nou folosind un Power Query transformare. Datele URL vor fi stocate în entitatea *Activitate unificată*, care poate fi consumată descendent folosind [API-uri](apis.md).

   - **Afișați în cronologie**
      - Alegeți dacă doriți să arătați această activitate în vizualizarea cronologiei pe profilele clienților dvs. Selectați **Da** pentru a arăta activitatea în cronologie sau **Nu** să-l ascundă.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Specificați datele despre activitatea clienților într-o entitate de activitate unificată.":::

1. Selectați **Următorul** pentru a alege tipul de activitate sau selectați **Terminați și revizuiți** pentru a salva activitatea cu tipul de activitate setat la **Alte**.

1. La pasul **Tipul activității**, alegeți tipul de activitate și selectați opțional dacă doriți să mapați semantic unele dintre tipurile de activitate pentru a fi utilizate în alte zone ale Customer Insights. În prezent, *Părere*, *·*, *de vânzări*, *·*, și *Abonament* tipurile de activitate acceptă semantica după ce sunt de acord să mapați câmpurile. Dacă un tip de activitate nu este relevant pentru noua activitate, puteți alege *Altele* sau *Creare nou* pentru un tip de activitate personalizat.

1. Selectați **Următorul**.

1. La pasul **Revizuire**, verificați selecțiile. Reveniți la oricare dintre pașii anteriori și actualizați informațiile, dacă este necesar.

1. Selectați **Salvați activitatea** pentru a aplica modificările și selectați **Terminat** a reveni la **Date** > **Activități**. Se afișează activitatea creată.

1. După ce ați creat toate activitățile, selectați **Alerga** pentru a le procesa.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-customer-activities"></a>Gestionați activitățile clienților existente

Mergi la **Date** > **Activități** pentru a vedea activitățile dvs. salvate, entitatea sursă a acestora, tipul de activitate și dacă sunt incluse în cronologia clientului. Puteți sorta lista de activități după orice coloană sau puteți utiliza caseta de căutare pentru a găsi activitatea pe care doriți să o gestionați.

Selectați o activitate pentru a vedea acțiunile disponibile.

- **Editați | ×** activitatea pentru a-și schimba configurația. Configurația se deschide la pasul de revizuire. După modificarea configurației, selectați **Salvați activitatea** și apoi selectați **Rulați** pentru a procesa modificările.
- **Redenumiți** activitatea. Selectați **Salvare** pentru a vă aplica modificările.
- **Șterge** activitatea. Pentru a șterge mai multe activități simultan, selectați activitățile și apoi **Șterge**. Confirmați ștergerea.

## <a name="view-activity-timelines-on-customer-profiles"></a>Vizualizați cronologiile activității în profilurile clienților

1. Dacă ați selectat **Afișați în cronologia activității** în configurația activității, accesați **Clienți** și selectați un profil de client pentru a vedea activitățile clientului în **Cronologia activității** secțiune.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Vizualizați activitățile configurate în Profilurile clienților.":::

1. Pentru a filtra activitățile din cronologia activității:

   - Selectați una sau mai multe dintre pictogramele de activitate pentru a rafina rezultatele pentru a include numai tipurile selectate.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrați activitățile după tip folosind pictogramele.":::

   - Selectați **Filtru** pentru a deschide un panou de filtre pentru a configura filtrele cronologice. Filtreaza dupa *ActivityType* și/sau *Data*. Selectați **Se aplică**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Utilizați panoul de filtrare pentru a configura condițiile de filtrare.":::

> [!NOTE]
> Filtrele de activitate sunt eliminate când părăsiți profilul unui client. Trebuie să le aplicați de fiecare dată când deschideți un profil de client.

## <a name="define-a-contact-activity"></a>Definiți o activitate de contact

Pentru conturile de afaceri (B-to-B), utilizați a *Profil de contact* entitate pentru a capta activitățile contactelor. Puteți vedea în cronologia activității pentru un cont care persoană de contact a fost responsabilă pentru fiecare activitate. Majoritatea pașilor urmează configurația de mapare a activității clienților.

   > [!NOTE]
   > Pentru a defini o activitate la nivel de contact, a *Profil de contact* entitate trebuie creată, fie ca a [profil de contact unificat](data-unification-contacts.md) sau prin [maparea semantică](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).
   >
   > Trebuie să le ai pe amândouă **Cont ID** și **ContactID** atribute pentru fiecare înregistrare din datele dvs. de activitate.
  
1. Mergi la **Date** > **Activități**.

1. Selectați **Adăugați o activitate**.

1. În **Date de activitate** pas, introduceți următoarele informații:

   - **Numele activității**: Selectați un nume pentru activitatea dvs.
   - **Entitate de activitate** : Selectați o entitate care include date tranzacționale sau de activitate.
   - **Cheie primară**: Selectați câmpul care identifică în mod unic o înregistrare. Nu ar trebui să conțină valori duplicate, valori goale sau valori lipsă.

     > [!NOTE]
     > Cheia primară pentru fiecare rând trebuie să rămână consecventă în timpul reîmprospătărilor sursă de date. Dacă cheia primară pentru un rând este actualizată într-o reîmprospătare sursă de date, aceasta creează duplicate în entitatea de ieșire Activitate. 


1. În **Relații** pas, creați o relație indirectă între datele dvs. sursă de activitate și conturi, folosind datele dvs. de contact ca entitate intermediară. Pentru mai multe informații, vezi [căi de relație directe și indirecte](relationships.md#relationship-paths).
   - Exemplu de relație pentru o activitate numită *Achiziții*:
      - **Date privind activitatea sursă de achiziții** > **Datele de contact** asupra atributului **ContactID**
      - **Datele de contact** > **Datele contului** asupra atributului **Cont ID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Exemplu de configurare a relației.":::

1. După configurarea relațiilor, selectați **Următorul** și finalizați configurația de cartografiere a activității. Pentru pașii detaliați despre crearea activității, consultați [defini o activitate a clientului](#define-a-customer-activity).

1. Rulați mapările activității dvs.

1. Activitățile tale la nivel de contact vor fi acum vizibile pe cronologia clientului.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Rezultatul final după configurarea activităților de contact":::

## <a name="contact-level-activity-timeline-filtering"></a>Filtrarea cronologiei activității la nivel de contact

După ce configurați o mapare a activității la nivel de contact și o rulați, cronologia activității pentru clienții dvs. va fi actualizată. Include ID-urile sau numele lor, în funcție de dvs *Profil de contact* configuratie, pentru activitatile asupra carora au actionat. Puteți filtra activitățile după persoane de contact din cronologie pentru a vedea anumite persoane de contact care vă interesează. În plus, puteți vedea toate activitățile care nu sunt atribuite unui anumit contact selectând **Activități care nu sunt mapate la o persoană de contact**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Opțiuni de filtrare disponibile pentru activitățile la nivel de contact.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
