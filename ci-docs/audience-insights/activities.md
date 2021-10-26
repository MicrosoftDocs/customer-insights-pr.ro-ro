---
title: Activități ale clienților
description: Definiți activitățile clienților și vizualizați-le într-o cronologie pe profilurile clienților.
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c250efcd54ec126c0726b22a971cdedd89760d6b
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617984"
---
# <a name="customer-activities"></a>Activități ale clienților

Combinați activitățile clienților din [diverse surse de date](data-sources.md) în Dynamics 365 Customer Insights pentru a crea o cronologie care listează activitățile cronologic. Includeți cronologia în aplicațiile Dynamics 365 cu soluția [Program de completare card client](customer-card-add-in.md) sau într-un tablou de bord Power BI.

## <a name="define-an-activity"></a>Definiți o activitate

Sursele dvs. de date pot include entități cu date tranzacționale și de activitate din mai multe surse de date. Identificați aceste entități și selectați activitățile pe care doriți să le vizualizați în cronologia clientului. Alegeți entitatea care include activitatea sau activitățile dvs. țintă.

O entitate trebuie să aibă cel puțin un atribut de tip **Date** pentru a fi inclus într-o cronologie a clienților și nu puteți adăuga entități fără câmpuri **Date**. Controlul **Adăugați activitate** este dezactivat dacă nu se găsește o astfel de entitate.

1. În Detalii despre audiență, accesați **Date** > **Activități**.

1. Selectați **Adăugați activitate** pentru a începe experiența asistată pentru procesul de configurare a activității.

1. În pasul **Date despre activitate**, setați valorile pentru următoarele câmpuri:

   - **Numele activității**: Selectați un nume pentru activitatea dvs.
   - **Entitate**: Selectați o entitate care include date de tranzacție sau de activitate.
   - **Cheie primară**: Selectați câmpul care identifică în mod unic o înregistrare. Nu ar trebui să conțină valori duplicate, valori goale sau valori lipsă.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configurați datele despre activitate cu numele, entitatea și cheia primară.":::

1. Selectați **Următorul** pentru a trece la pasul următor.

1. În pasul **Relație**, configurați detaliile pentru a vă conecta datele de activitate la înregistrarea de cont corespunzătoare. Acest pas vizualizează conexiunea dintre entități.  

   - **Primul pas**: Câmp străin din entitatea dvs. de activitate care va fi utilizat pentru a stabili o relație cu o altă entitate.
   - **Al doilea pas**: Entitate client sursă corespunzătoare cu care entitatea de activitate va fi în relație. Vă puteți raporta doar la entitățile client sursă care sunt utilizate în procesul de unificare a datelor.
   - **Al treilea pas**: Dacă există deja o relație între această entitate de activitate și entitatea client sursă selectată, numele relației va fi în modul doar în citire. Dacă nu există o astfel de relație, va fi creată o nouă relație cu numele pe care îl furnizați în această casetă.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definiți relația dintre entități.":::

   > [!TIP]
   > În mediile B2B, puteți selecta între entități de cont și alte entități. Dacă selectați o entitate de cont, calea relației este setată automat. Pentru alte entități, trebuie să definiți calea relației pentru una sau mai multe entități intermediare până când ajungeți la o entitate de cont.

1. Selectați **Următorul** pentru a trece la pasul următor. 

1. În pasul **Unificarea activităților**, alegeți evenimentul de activitate și ora de începere a activității dvs. 
   - **Câmpuri obligatorii**
      - **Activitatea evenimentului**: Câmp care este evenimentul pentru această activitate.
      - **Marcă de timp**: Câmp care reprezintă ora de începere a activității dvs.

   - **Câmpuri opționale**
      - **Detalii suplimentare**: Câmp cu informații relevante pentru această activitate.
      - **Pictogramă**: Pictogramă care reprezintă cel mai bine acest tip de activitate.
      - **Adresa web**: Câmp care conține o adresă URL cu informații despre această activitate. De exemplu, sistemul tranzacțional care furnizează această activitate. Această adresă URL poate fi orice câmp din sursa de date sau poate fi construită ca un câmp nou folosind o transformare Power Query. Datele URL vor fi stocate în entitatea *Activitate unificată*, care poate fi consumată descendent folosind [API-uri](apis.md).

   - **Afișați în cronologie**
      - Alegeți dacă doriți să arătați această activitate în vizualizarea cronologiei pe profilele clienților dvs. Selectați **Da** pentru a arăta activitatea în cronologie sau **Nu** să-l ascundă.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Specificați datele despre activitatea clienților într-o entitate de activitate unificată.":::

1. Selectați **Următorul** pentru a trece la următorul pas. Puteți selecta **Finalizați și examinați** pentru a salva activitatea acum cu tipul de activitate setat la **Altele**. 

1. La pasul **Tipul activității**, alegeți tipul de activitate și selectați opțional dacă doriți să mapați semantic unele dintre tipurile de activitate pentru a fi utilizate în alte zone ale Customer Insights. În prezent, tipuri de activități *Feedback*, *Loialitate*, *SalesOrder*, *SalesOrderLine* și *Abonament* pot fi mapate semantic după acceptarea mapării câmpurilor. Dacă un tip de activitate nu este relevant pentru noua activitate, puteți alege *Altele* sau *Creare nou* pentru un tip de activitate personalizat.

1. Selectați **Următorul** pentru a trece la următorul pas. 

1. La pasul **Revizuire**, verificați selecțiile. Reveniți la oricare dintre pașii anteriori și actualizați informațiile, dacă este necesar.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Examinați câmpurile specificate pentru o activitate.":::
   
1. Selectați **Salvați activitatea** pentru a aplica modificările și selectați **Terminat** a reveni la **Date** > **Activități**. Aici vedeți ce activități sunt setate să fie afișate în cronologie. 

1. Pe pagina **Activități**, selectați **Rulați** pentru a rula activitatea. 

> [!TIP]
> Sunt [șase tipuri de stări](system.md#status-types) pentru sarcini/procese. În plus, majoritatea proceselor [depind de alte procese din aval](system.md#refresh-policies). Puteți selecta starea unui proces pentru a vedea detalii despre evoluția întregii lucrări. După selectarea **Vizualizare detalii** pentru una dintre sarcinile jobului, găsiți informații suplimentare: timpul de procesare, ultima dată de procesare și toate erorile și avertismentele asociate sarcinii.


## <a name="manage-existing-activities"></a>Gestionați activitățile existente

Pe **Date** > **Activități**, puteți vizualiza toate activitățile salvate și le puteți gestiona. Fiecare activitate este reprezentată de un rând care include și detalii despre sursă, entitate și tipul de activitate.

Următoarele acțiuni sunt disponibile când selectați o activitate. 

- **Editați**: Deschide configurarea activității la pasul de revizuire. Puteți modifica oricare sau toate configurațiile curente din acest pas. După modificarea configurației, selectați **Salvați activitatea** și apoi selectați **Rulați** pentru a procesa modificările.

- **Redenumire**: Deschide un dialog în care puteți introduce un nume diferit pentru activitatea selectată. Selectați **Salvare** pentru a vă aplica modificările.

- **Ștergeți**: Deschide o casetă de dialog pentru a confirma ștergerea activității selectate. De asemenea, puteți șterge mai multe activități simultan selectând activitățile și apoi selectând pictograma de ștergere. Selectați **Ștergere**, apoi confirmați ștergerea.

## <a name="view-activity-timelines-on-customer-profiles"></a>Vizualizați cronologiile activității în profilurile clienților

După ce ați configurat activitățile clienților, selectați **Afișați în cronologia activității** în configurația activității pentru a găsi toate activitățile clienților dvs. în profilul lor de client.

Pentru a deschide cronologia pentru un client, accesați **Clienți** și alegeți profilul de client pe care doriți să îl vizualizați.

Dacă un client a participat la o activitate pe care ați configurat-o, o veți găsi în secțiunea **Cronologia activității**.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Vizualizați activitățile configurate în Profilurile clienților.":::

Există mai multe moduri de a filtra activitățile în cronologia activității:

- Puteți selecta una sau mai multe dintre pictogramele de activitate pentru a vă rafina rezultatele, pentru a include numai tipurile selectate.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrați activitățile după tip folosind pictogramele.":::

- Puteți selecta **Filtru** pentru a deschide un panou de filtrare pentru a vă configura filtrele cronologiei.

   1. Puteți filtra după *ActivityType* și *Data*
   1. Selectați **Aplicare** pentru a utiliza filtrele din cronologia activității.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Utilizați panoul de filtrare pentru a configura condițiile de filtrare.":::

Pentru a elimina filtrele, selectați **x** lângă fiecare filtru aplicat cronologiei sau selectați **Ștergeți filtrele**.


> [!NOTE]
> Filtrele de activitate sunt eliminate când părăsiți profilul unui client. Trebuie să le aplicați de fiecare dată când deschideți un profil de client.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
