---
title: Îmbinați entitățile în unificarea datelor
description: Îmbinați entitățile pentru a crea profiluri de clienți unificate.
ms.date: 01/28/2022
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
  - ci-merge
---

# <a name="merge-entities"></a>Îmbinare entități

Faza de îmbinare este ultima fază din procesul de unificare a datelor. Scopul său este reconcilierea datelor conflictuale. Exemple de date conflictuale ar putea include un nume de client care se găsește în două seturi de date, dar care apare puțin diferit în fiecare („Grant Marshall” față de „Grant Marshal”) sau un număr de telefon care diferă în format (617-803-091X versus 617803091X ). Fuzionarea acelor puncte de date conflictuale se face pe baza atributelor.

:::image type="content" source="media/merge-fields-page.png" alt-text="Pagina de îmbinare din procesul de unificare a datelor, afișând tabelul cu câmpuri îmbinate care definesc profilul de client unificat.":::

După completarea [fazei de potrivire](match-entities.md), începeți faza de îmbinare selectând dala **Îmbinare** pe pagina **Unificare**.

## <a name="review-system-recommendations"></a>Revizuiți recomandările sistemului

În secțiunea **Date** > **Unificare** > **Îmbinare**, alegeți și excludeți atributele de îmbinat cu entitatea de profil de client unificat. Profilul de client unificat este rezultat al procesului de unificare a datelor. Unele atribute sunt combinate automat de sistem.

Pentru a vedea atributele ce sunt incluse într-unul dintre atributele dvs. îmbinate automat, selectați acel atribut îmbinat în fila de tabel **Câmpurile clienților**. Atributele care compun atributul îmbinat apar în două rânduri noi sub atributul îmbinat.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Separarea, redenumirea, excluderea și editarea câmpurilor îmbinate

Puteți să modificați modul în care sistemul procesează atributele îmbinate pentru a genera profilul de client unificat. Selectați **Afișați mai multe** și alegeți ce vreți să schimbați.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opțiuni din meniul derulant Afișați mai multe pentru a gestiona atributele combinate.":::

Pentru mai multe informații vedeți secțiunile următoare.

## <a name="separate-merged-fields"></a>Câmpuri îmbinate separate

Pentru a separa câmpurile îmbinate, găsiți atributul în tabel. Câmpurile separate sunt afișate drept puncte de date individuale în profilul de client unificat. 

1. Selectați câmpul îmbinat.
  
1. Selectați **Afișați mai multe** și alegeți **Câmpuri separate**.
 
1. Confirmați separarea.

1. Selectați **Salvare** și **Rulare** pentru a procesa modificările.

## <a name="rename-merged-fields"></a>Redenumiți câmpurile îmbinate

Schimbați numele afișat al atributelor combinate. Nu puteți modifica numele entității de ieșire.

1. Selectați câmpul îmbinat.
  
1. Selectați **Afișați mai multe** și alegeți **Redenumire**.

1. Confirmați numele afișat modificat. 

1. Selectați **Salvare** și **Rulare** pentru a procesa modificările.

## <a name="exclude-merged-fields"></a>Câmpuri îmbinate excluse

Excludeți un atribut din profilul de client unificat. Dacă câmpul e utilizat în alte procese, de exemplu într-un segment, eliminați-l din aceste procese înainte de a-l exclude din profilul clientului. 

1. Selectați un câmp îmbinat.
  
1. Selectați **Afișați mai multe** și alegeți **Excludere**.

1. Confirmați excluderea.

1. Selectați **Salvare** și **Rulare** pentru a procesa modificările. 

Pe pagina **Îmbinare**, selectați **Câmpuri excluse** pentru a vedea lista tuturor câmpurilor excluse. Acest panou vă permite să adăugați câmpuri excluse înapoi.

## <a name="edit-a-merged-field"></a>Editați un câmp îmbinat

1.  Selectați un câmp îmbinat.

1.  Selectați **Afișați mai multe** și alegeți **Editare**.

1.  Specificați cum să combinați sau să combinați câmpurile dintr-una dintre cele trei opțiuni:
    - **Importanţă**: Identifică valoarea câștigătorului pe baza rangului de importanță specificat pentru câmpurile participante. Este opțiunea implicită de combinare. Selectați **Mutați în sus/în jos** pentru a stabili clasamentul importanței.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Opțiunea de importanță din dialogul câmpurilor de îmbinare."::: 
    - **Cel mai recent**: Identifică valoarea câștigătorului pe baza celui mai recent. Necesită o dată sau un câmp numeric pentru fiecare entitate participantă în domeniul câmpurilor de îmbinare pentru a defini actualitatea.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Opțiunea de noutate din dialogul câmpurilor de îmbinare.":::
    - **Cel mai puțin recent**: Identifică valoarea câștigătorului pe baza celui mai puțin recent. Necesită o dată sau un câmp numeric pentru fiecare entitate participantă în domeniul câmpurilor de îmbinare pentru a defini actualitatea.

1.  Puteți adăuga mai multe câmpuri pentru a participa la procesul de îmbinare.

1.  Puteți redenumi câmpul combinat.

1. Selectați **Finalizat** pentru a vă aplica modificările.

1. Selectați **Salvare** și **Rulare** pentru a procesa modificările. 

## <a name="combine-fields-manually"></a>Combinați câmpurile manual

Specificați manual un atribut îmbinat.

1. Pe **Combina** pagina, selectați **Combina**.

1. Alege **Câmpuri** opțiune.

1. Specificați politica câștigătorului de îmbinare în lista derulantă **Combinați câmpurile după**.

1. Alegeți un câmp de adăugat. Selectați **Adăugați câmpuri** pentru combinarea mai multor câmpuri.

1. Furnizați un **Nume** și un **Nume al câmpului de ieșire**.

1. Selectați **Finalizat** pentru a aplica modificările.

1. Selectați **Salvare** și **Rulare** pentru a procesa modificările. 

## <a name="combine-a-group-of-fields"></a>Combinați un grup de câmpuri

Tratați un grup de câmpuri ca o singură unitate. De exemplu, dacă înregistrările noastre conțin câmpurile Adresă1, Adresă2, Oraș, Stat și Cod. Probabil că nu dorim să îmbinăm în Adresa2 a unei alte înregistrări, crezând că ne-ar face datele mai complete

1. Pe **Combina** pagina, selectați **Combina**.

1. Alege **Grup de câmpuri** opțiune.

1. Specificați politica câștigătorilor de îmbinare în **Clasează grupurile după** scapă jos.

1. Selectați **Adăuga** și alegeți dacă doriți să adăugați mai multe câmpuri sau grupuri suplimentare la câmpuri.

1. Furnizeaza un **Nume** si un **Nume de ieșire** pentru fiecare câmp combinat.

1. Furnizeaza un **Nume** pentru grupul de câmpuri. 

1. Selectați **Finalizat** pentru a aplica modificările.

1. Selectați **Salvare** și **Rulare** pentru a procesa modificările.

## <a name="change-the-order-of-fields"></a>Modificarea ordinii câmpurilor

Unele entități conțin mai multe detalii decât altele. Dacă o entitate include cele mai recente date despre un câmp, le puteți oferi prioritate față de alte entități atunci când îmbinați valorile.

1. Selectați câmpul îmbinat.
  
1. Selectați **Afișați mai multe** și alegeți **Editare**.

1. În panoul **Combinați câmpurile**, selectați **Mutați în sus / în jos** pentru a seta ordinea sau glisați și fixați-le în poziția dorită.

1. Confirmați modificarea.

1. Selectați **Salvare** și **Rulare** pentru a procesa modificările.

## <a name="configure-customer-id-generation"></a>Configurați generarea ID-ului de client 

După configurarea câmpurilor de fuzionare, puteți defini cum să generați valori CustomerId, identificatorii unici ai profilului clientului. Pasul de îmbinare în procesul de unificare a datelor generează identificatorul unic al profilului clientului. Identificatorul este CustomerId din entitatea *Client* care rezultă din procesul de unificare a datelor. 

CustomerId-ul din entitatea Client se bazează pe un hash cu prima valoare a cheilor primare non-câștigătoare nule. Aceste chei provin de la entitățile utilizate în faza de potrivire și fuzionare și sunt influențate de ordinea de potrivire. Deci, CustomerID generat se poate modifica atunci când o valoare a cheii primare se modifică în entitatea primară a comenzii de potrivire. Deci, valoarea cheii principale ar putea să nu reprezinte întotdeauna același client.

Configurarea unui ID stabil de client vă permite să evitați acel comportament.

**Configurați un ID unic al clientului**

1. Accesați **Unificare** > **Îmbinare**.

1. Selectați fila **Chei**. 

1. Plasați cursorul pe rândul **CustomerId** și selectați opțiunea **Configurați**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Control pentru a personaliza generarea ID-ului.":::

1. Selectați până la cinci câmpuri care vor cuprinde un ID de client unic și care sunt mai stabile. Înregistrările care nu se potrivesc configurației dvs. utilizează în schimb un ID configurat de sistem.  

1. Selectați **Terminat** și rulați procesul de îmbinare pentru a aplica modificările.

## <a name="group-profiles-into-households-or-clusters"></a>Profiluri de grup în gospodării sau clustere

Ca parte a procesului de configurare a generării profilului clientului, puteți defini reguli pentru a grupa profilurile aferente într-un cluster. În prezent există două tipuri de clustere disponibile - clustere de uz casnic și personalizate. Sistemul alege automat o gospodărie cu reguli predefinite dacă entitatea *Client* conține câmpurile semantice *Person.LastName* și *Location.Address*. De asemenea, puteți crea un cluster cu propriile reguli și condiții, similar cu [potrivire reguli](match-entities.md#define-rules-for-match-pairs).

**Definiți o gospodărie sau un grup**

1. Accesați **Unificare** > **Îmbinare**.

1. Pe fila **Îmbinare**, selectați **Avansat** > **Creați cluster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Control pentru a crea un nou cluster.":::

1. Alegeți între un o **Gospodărie** sau un cluster **Particularizat**. Dacă câmpurile semantice *Person.LastName* și *Location.Address* în entitatea *Client*, gospodăria este selectată automat.

1. Furnizați un nume pentru cluster și selectați **Terminat**.

1. Selectați fila **Clustere** pentru a găsi clusterul pe care l-ați creat.

1. Specificați regulile și condițiile pentru a defini clusterul.

1. Selectați **Rulare** pentru a rula procesul de îmbinare și a crea clusterul.

După rularea procesului de îmbinare, identificatorii de cluster sunt adăugați ca câmpuri noi în entitatea *Client*.

## <a name="run-your-merge"></a>Executați-vă unificarea

Indiferent dacă fuzionați manual atributele sau lăsați sistemul să le îmbine, puteți rula întotdeauna fuziunea. Selectați **Executare** pe pagina **Îmbinare** pentru a porni procesul.

> [!div class="mx-imgBorder"]
> ![Îmbinare date Salvați și rulați.](media/configure-data-merge-save-run.png "Îmbinare date Salvați și rulați")

Alege **Rulați numai îmbinarea** dacă doriți doar să vedeți rezultatul reflectat în entitatea client unificată. Procesele din aval vor fi reîmprospătate ca [definite în programul de reîmprospătare](system.md#schedule-tab).

Alegeți **Rulați procesele de îmbinare și flux spre aval** pentru a reîmprospăta sistemul cu modificările dvs. Toate procesele, inclusiv îmbogățirea, segmentele și măsurile vor fi reluate automat. După ce toate procesele din aval s-au finalizat, profilurile clienților reflectă orice modificare făcută.

Pentru a face mai multe modificări și a relua pasul, puteți anula o îmbinare în curs. Selectați **Se reîmprospătează ...** și selectați **Anulare operațiune** în panoul lateral care apare.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

:::image type="content" source="media/process-detail-path.png" alt-text="Cale de drill-down pentru a ajunge la procesarea detaliilor din legătura de stare a activității.":::

## <a name="next-step"></a>Următorul pas

Configurați [Activități](activities.md), [Îmbogățire](enrichment-hub.md), sau [Relații](relationships.md) pentru a obține mai multe informații despre clienți.

Dacă ați configurat deja activități, îmbogățire sau segmente, acestea vor fi procesate automat pentru a utiliza cele mai recente date despre clienți.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
