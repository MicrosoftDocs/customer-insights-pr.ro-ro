---
title: Vizualizați și creați segmente
description: Cum să creați, să editați și să ștergeți segmente și unde să le utilizați.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: e99c04e6c92d8ca16c2d69957e0f5b7dba0ac757
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225391"
---
# <a name="view-and-create-segments"></a>Vizualizați și creați segmente

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Segmentele vă permit să identificați subseturi de vizitatori pe baza caracteristicilor sau interacțiunilor site-ului web. Segmentele vă permit să aplicați filtre și să analizați aceste subseturi. Analiza vă poate ajuta să examinați și să răspundeți la tendințele afacerii dvs. 

:::image type="content" source="media/segments-page.png" alt-text="Captură de ecran a aplicației cu datele despre angajamente care afișează lista segmentelor existente într-un spațiu de lucru.":::

## <a name="view-segments"></a>Vizualizare segmente

1. În panoul de navigare din stânga, accesați **Date**. 

1. Selectați **Segmente** pentru a vedea o listă cu toate segmentele din spațiul de lucru. 

## <a name="create-a-segment"></a>Creați un segment

Segmentele constau din reguli și condiții care sunt conectate cu operatori logici. Condițiile aplică filtre unei dimensiuni selectate. Fiecare segment poate utiliza până la cinci dimensiuni.

Următorul exemplu arată un segment cu două condiții într-o singură regulă. Acesta filtrează toate evenimentele site-ului web în care browserul este Chrome și sistemele de operare sunt iOS sau Android.

:::image type="content" source="media/segment-sample.png" alt-text="Exemple de segmente cu două condiții într-o regulă de filtrat pentru evenimentele site-ului web.":::

Această secțiune descrie modul de a crea un *segment necompletat* de la zero.

1. Accesați **Date** > **Segmente**.

1. Selectați **Segment nou**.

1. În **Biblioteca de resurse**, selectați (+) de lângă atributul pe care doriți să îl filtrați. În prezent, puteți crea segmente numai pe baza dimensiunilor.

   :::image type="content" source="media/create-new-segment.png" alt-text="Crearea unui nou segment.":::

1. În secțiunea **Regulă**, alegeți un operator și o valoare pentru atributul selectat. Următoarele operații sunt acceptate.

   :::image type="content" source="media/choose-operator-segment.png" alt-text="Alegeți un operator pentru noul dvs. segment.":::

   - **este**: necesită o corespondență exactă pentru a include valori. Utilizări **egal cu** pentru o singură valoare sau **oricare dintre** pentru a include valori multiple.
   - **nu este**: necesită o corespondență exactă pentru a exclude valori. Utilizări **egal cu** pentru o singură valoare sau **oricare dintre** pentru a include valori multiple.
   - **începe cu**: un șir care începe cu valorile corespondente.
   - **se termină cu**: un șir care se termină cu valorile corespondente.
   - **conține**: un șir conținut în valori corespondente.

1. Pentru a adăuga mai multe condiții unui grup, puteți utiliza operatori logici. Atributele proiectate sunt luate în calcul atunci când se utilizează operatori de mulțimi.
   - Operator **ȘI**: Ambele condiții trebuie îndeplinite ca parte a procesului de segmentare. Această opțiune este cea mai utilă atunci când definiți condiții pentru diferite entități.
   - Operatorul **SAU**: Fiecare dintre condiții trebuie îndeplinită ca parte a procesului de segmentare. Această opțiune este cea mai utilă atunci când definiți condiții multiple pentru aceeași entitate.

1. Selectați **Salvare** și numele segmentului. 

Segmentul va fi listat în pagina **Segmente** și îl puteți aplica tuturor rapoartelor și canalelor din spațiul de lucru.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Utilizați un segment într-un raport sau într-o pâlnie

Puteți aplica segmente unui raport sau unei pâlnii pentru a le filtra pe baza condițiilor din segment. Cu toate acestea, nu puteți aplica segmente la raportul de utilizare în timp real.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Un raport de vizualizare a paginii cu o listă verticală extinsă pentru a alege care segmente să aplicați.":::

Pentru a aplica un segment, deschideți raportul sau canalul. Selectați **+ Adăugați o condiție** și alegeți **Filtrați după segment**. Alegeți segmentul din lista pe care doriți să o aplicați. Segmentul va fi aplicat raportului. Dacă un grafic nu acceptă segmentul, apare o eroare. Pentru mai multe informații, consultați [Creați și gestionați rapoarte de canalizare](funnel-reports.md).
 
Puteți aplica *până la trei segmente* la un raport sau o pâlnie.

## <a name="edit-a-segment"></a>Editați un segment

1. Accesați **Date** > **Segmente**.
1. Selectați segmentul din listă pentru a-l deschide. 
1. Schimbați sau adăugați valori după cum este necesar.
1. Selectați **Salvare** pentru a vă aplica modificările.

## <a name="change-the-name-of-a-segment"></a>Modificați numele unui segment

1. Accesați **Date** > **Segmente**.
1. În lista de segmente, selectați **Mai mult [...]**. 
1. Din lista derulantă, alegeți **Editeaza nume**.
1. Introduceți numele nou și selectați **Redenumiți**.

## <a name="delete-a-segment"></a>Ștergeți un segment

1. Accesați **Date** > **Segmente**.
1. În lista de segmente, selectați **Mai mult [...]**. 
1. Din lista derulantă, alegeți **Ștergeți**.
1. Pentru a confirma, selectați **Ștergeți**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
