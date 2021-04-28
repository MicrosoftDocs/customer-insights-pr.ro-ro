---
title: Exportați date din Customer Insights
description: Gestionați exporturile către partajare date.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896158"
---
# <a name="exports-preview-overview"></a>Prezentare generală a exporturilor (previzualizare)

Pagina **Exporturi** vă arată toate exporturile configurate. Exporturile partajează date specifice cu diferite aplicații. Ele pot include profiluri sau entități ale clienților, scheme și detalii de mapare. Fiecare export necesită o [conexiune, configurată de un administrator, pentru a gestiona autentificarea și accesul](connections.md).

> [!NOTE]
> Până în martie 2021, exporturile au creat automat o conexiune la serviciul corespunzător. Exporturile necesită acum o [conexiune, creată și partajată de un administrator](connections.md) înainte de a le putea crea.

Faceți salt la **Date** > **Exporturi** pentru a vizualiza pagina exporturilor. Toate rolurile utilizatorilor au acces la vizualizarea exporturilor configurate. Utilizarea câmpului de căutare din bara de comandă pentru a găsi exporturile după nume, numele conexiunii sau tipul conexiunii.

## <a name="set-up-a-new-export"></a>Configurați un nou export

Pentru a configura sau edita un export, trebuie să existe conexiuni disponibile pentru dvs. Conexiunile depind de [rolul dvs. de utilizator](permissions.md):
- Administratorii au acces la toate conexiunile. De asemenea, pot crea conexiuni noi atunci când configurează un export.
- Contribuitorii pot avea acces la conexiuni specifice. Acestea depind de administratori pentru a configura și partaja conexiuni. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Spectatorii pot vizualiza doar exporturile existente, dar nu le pot crea.

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugare export** pentru a crea o nouă destinație de export.

1. În panoul **Configurați exportul**, selectați ce conexiune să utilizați. [Conexiunile](connections.md) sunt gestionate de administratori. 

1. Furnizați detaliile necesare și selectați **Salvare** pentru a crea exportul.

### <a name="edit-an-export"></a>Editarea unui export

1. Selectați elipsa verticală pentru destinația de export pe care doriți să o editați.

1. Selectați **Editați** din meniul derulant.

1. Schimbați valorile pe care doriți să le actualizați și selectați **Salvați**.

## <a name="view-exports-and-export-details"></a>Vizualizați Exporturi și detalii despre export

După crearea destinațiilor de export, acestea sunt listate pe **Date** > **Exporturi**. Toți utilizatorii pot vedea ce date sunt partajate și starea cea mai recentă a acestora.

1. Faceți salt la **Date** > **Exporturi**.

1. Utilizatorii fără permisiuni de editare selectează **Vizualizare** în loc de **Editare** pentru a vizualiza detaliile exportului.

1. Acest panou lateral arată configurarea acestui export. Fără permisiuni de editare, nu puteți modifica valorile. Selectați **Închidere** pentru a reveni la pagina de exporturi.

## <a name="run-exports-on-demand"></a>Executați exporturi la cerere

După configurarea unui export, acesta va rula cu fiecare [reîmprospătare programată](system.md#schedule-tab) atâta timp cât are o conexiune care funcționează.

Pentru a exporta date fără a aștepta o reîmprospătare programată, accesați **Date** > **Exporturi**. Aveţi două opţiuni:

- Pentru a rula toate exporturile, selectați **Executare totală** în bara de comandă. 
- Pentru a rula un singur export, selectați puncte de suspensie (...) pe un element din listă și apoi alegeți **Executare**.

## <a name="remove-an-export"></a>Eliminați un export

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați elipsa verticală pentru Exportul pe care doriți să-l eliminați.

1. Selectați **Eliminare** din meniul vertical.

1. Confirmați eliminarea selectând **Eliminare** pe ecranul de confirmare.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
