---
title: Relații între entități și căi de entități
description: Creați și gestionați relații între entități din mai multe surse de date.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595227"
---
# <a name="relationships-between-entities"></a>Relații între entități

Relațiile vă ajută să conectați entități și să generați un grafic al datelor dvs. atunci când entitățile partajează un identificator comun (cheie străină) la care se poate face referire de la o entitate la alta. Entitățile conectate vă permit să definiți segmente și măsuri pe baza mai multor surse de date.

Există două tipuri de relații. Relațiile de sistem care nu pot fi modificate, care sunt create automat și relațiile personalizate create și configurate de utilizatori.

În timpul proceselor de potrivire și îmbinare, relațiile de sistem sunt create în culise bazate pe potrivire inteligentă. Aceste relații ajută la corelarea înregistrărilor profilului clienților cu înregistrările altor entități corespunzătoare. Următoarea diagramă ilustrează crearea a trei relații de sistem atunci când entitatea client este asociată cu entități suplimentare pentru a produce entitatea de profil final pentru clienți.

> [!div class="mx-imgBorder"]
> ![Se creează relația](media/relationships-entities-merge.png "Se creează relația")

- **Relația *CustomerToContact*** a fost creată între entitatea Client și entitatea de contact. Entitatea Client face ca câmpul cheie **Contact_contactId** să se raporteze la câmpul cheie al entității de contact **contactId**.
- **Relația *CustomerToAccount*** a fost creată între entitatea Client și entitatea de cont. Entitatea Client face ca câmpul cheie **Account_accountId** să se raporteze la câmpul cheie al entității de cont **accountId**.
- **Relația *CustomerToWebAccount*** a fost creată între entitatea Client și entitatea WebAccount. Entitatea Client face ca câmpul cheie **WebAccount_webaccountId** să se raporteze la câmpul cheie al entității WebAccount **webaccountId**.

## <a name="create-a-relationship"></a>Creați o relație

Definiți relațiile particularizate pe pagina **Relații**. Fiecare relație constă dintr-o entitate sursă (entitatea care deține cheia străină) și o entitate țintă (entitatea la care face referire cheia străină a entității sursă).

1. În detalii despre public, accesați **Date** > **Relații**.

2. Selectați **Relație nouă**.

3. Pe panoul **Adăugați relație**, furnizați următoarele informații:

   > [!div class="mx-imgBorder"]
   > ![Introduceți detaliile relației](media/relationships-add.png "Introduceți detaliile relației")

   - **Numele relației**: Nume care reflectă scopul relației (de exemplu, **AccountWebLogs**).
   - **Descriere**: Descrierea relației.
   - **Entitatea sursă**: Selectați entitatea care este utilizată ca sursă în relație (de exemplu, WebLog).
   - **Cardinalitate**: Selectați cardinalitatea înregistrărilor entității sursă. De exemplu, „multe” înseamnă că mai multe înregistrări Weblog sunt legate de un WebAccount.
   - **Câmpul cheie sursă**: Acesta reprezintă câmpul cheie străină din entitatea sursă. De exemplu, WebLog are **accountId** drept câmp de cheie străină.
   - **Entitatea țintă**: Selectați entitatea care este utilizată ca țintă în relație (de exemplu, WebAccount).
   - **Cardinalitate țintă**: Selectați cardinalitatea înregistrărilor entității țintă. De exemplu, „una” înseamnă că mai multe înregistrări Weblog sunt legate de un WebAccount.
   - **Câmpul cheie țintă**: Acest câmp reprezintă câmpul cheie al entității țintă. De exemplu, WebAccount are **accountId** drept câmp de cheie.

> [!NOTE]
> Sunt acceptate doar relații mulți-la-unu și unu-la-unu. Relațiile de mulți la mulți pot fi create folosind două relații mulți-la-unu și o entitate de legătură (o entitate care este utilizată pentru a conecta entitatea sursă și entitatea țintă).

## <a name="delete-a-relationship"></a>Ștergeți o relație

1. În detalii despre public, accesați **Date** > **Relații**.

2. Bifați caseta de selectare pentru relațiile pe care doriți să le eliminați.

3. Selectați **Ștergere** în partea de sus a tabelului **Relații**.

4. Confirmați ștergerea.

## <a name="next-step"></a>Următorul pas

Relațiile de sistem și personalizate sunt utilizate pentru a crea segmente bazate pe mai multe surse de date care nu mai sunt izolate. Pentru mai multe informații, consultați [Segmente](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]