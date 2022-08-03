---
title: Utilizați consimțământul clientului
description: Respectați preferințele de consimțământ ale clienților dvs. în Customer Insights importând datele de consimțământ.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99fe24cb47a8c20f629182d9a1c6adfd36a1eaf7
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188063"
---
# <a name="use-customer-consent"></a>Utilizați consimțământul clientului

Reglementările privind protecția datelor și confidențialitatea oferă persoanelor dreptul de a guverna modul în care o organizație își folosește datele personale. Exemple de astfel de reglementări sunt Regulamentul general privind protecția datelor din Uniunea Europeană sau Legea privind confidențialitatea consumatorilor din California din Statele Unite. Aceste reglementări permit oamenilor să renunțe la colectarea, prelucrarea sau partajarea datelor lor personale de către terți.  

Clienții pot alege să își retragă sau să-și rețină consimțământul pentru anumite forme de contact. De asemenea, aceștia pot solicita să renunțați la colectarea, stocarea, utilizarea sau vânzarea datelor lor personale. Este important ca organizația dvs. să respecte consimțământul tuturor clienților și preferințele de confidențialitate.  

Dynamics 365 Customer Insights vă ajută să onorați solicitările clienților dvs. importând și stocând preferințele acestora ca parte a profilurilor unificate ale clienților.

Dacă datele de consimțământ sunt stocate separat de profilurile dvs. de clienți, [adăugați datele dvs. de consimțământ ca un nou sursă de date](#import-and-unify-consent-data). Sursă de date care conține datele consimțământului este adăugat la procesul de unificare a datelor. Unificarea cu succes a datelor de consimțământ și a profilurilor clienților conduce apoi la profiluri de clienți unificate care conțin informațiile privind consimțământul. Pentru profilurile de clienți care conțin deja informații privind consimțământul, accesați direct [utilizați datele consimțământului](#use-consent-data) secțiune.

## <a name="prerequisites"></a>Cerințe preliminare

Următoarele informații trebuie să fie disponibile în datele dvs. sursă pentru a unifica datele de consimțământ cu alte profiluri de clienți:

- Cheie alternativă pentru a mapa informațiile de consimțământ la profilurile utilizatorilor din Customer Insights. De exemplu, o adresă de e-mail sau un număr de telefon.
- Valoarea consimțământului pentru a determina starea consimțământului clientului.

Luați în considerare adăugarea următoarelor *opțional* informație:

- Cheie primară pentru a actualiza starea consimțământului dacă un client solicită o modificare.
- Tip de consimțământ, dacă există mai multe modalități de procesare a informațiilor despre clienți.
- Data consimțământului sau orice alt tip de date relevante pentru scenariile dvs. de consimțământ.

Exemplu de tabel al unei baze de date simple de consimțământ cu mai multe opțiuni de consimțământ:

|ID de consimțământ (cheie primară)   |E-mail (cheie alternativă)  |Opțiunea de consimțământ  |Valoarea consimțământului  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Buletin informativ       |  Fals       |
|2    |  holly@contoso.com       |  Actualizări de produs       |  Adevărat       |
|3    |  frank@contoso.com       |  Buletin informativ       | Adevărat        |
|4    |  frank@contoso.com       |  Actualizări de produs       |  Fals       |

## <a name="import-and-unify-consent-data"></a>Importați și unificați datele de consimțământ

Importați datele de consimțământ în același mod în care ați ingerat alte surse de date în Customer Insights. Pentru mai multe informații despre sursele de date acceptate și despre cum să le importați, consultați [Prezentare generală a surselor de date](data-sources.md).

Pentru mai multe informații despre unificarea surselor de date, consultați [Prezentare generală a unificării datelor](data-unification.md).

## <a name="use-consent-data"></a>Utilizați datele de consimțământ

Odată ce datele dvs. de consimțământ fac parte din profilurile dvs. unificate de clienți, le puteți utiliza în Customer Insights. De exemplu, creați un segment cu o regulă pentru a vă asigura că respectați preferințele privind confidențialitatea și protecția datelor ale clienților dvs. Regulile care susțin preferințele de consimțământ sunt folosite pentru a exclude utilizatorii dintr-un segment pe baza atributelor profilului. Adăugați o regulă la un segment care exclude profilurile clienților care nu au furnizat consimțământul pentru contact.

Referindu-ne la exemplul de tabel de mai sus, un segment poate conține această regulă:`Consent option=Newsletter & Consent value=True`. Această configurație are ca rezultat un segment care onorează preferințele de contact pentru a trimite un buletin informativ.

Pentru mai multe informații despre segmentele de construcție, consultați [Creați segmente](segment-builder.md).

Odată ce segmentul este creat, puteți utiliza unul dintre multele [opțiuni de export](export-destinations.md) pentru a utiliza segmentul în alte aplicații.

## <a name="ensure-updated-consent-status"></a>Asigurați-vă starea de consimțământ actualizată

Este important să păstrați actualizat starea consimțământului pentru clienții dvs. Actualizarea programată în Customer Insights importă întotdeauna cea mai recentă stare a surselor dvs. de date. Aceste informații sunt apoi procesate prin unificarea datelor și rezultă în profiluri actualizate ale clienților. Aceste profiluri actualizate sunt apoi folosite pentru a reîmprospăta segmentele pentru a vă asigura că lucrați cu cele mai actualizate informații.

Cu alte cuvinte, asigurați-vă că datele sursă care sunt importate în Customer Insights au întotdeauna cele mai recente informații.

Pentru mai multe informații, consultați [Actualizează segmentele manual](segments.md#refresh-segments) sau [configurați o reîmprospătare programată](system.md#schedule-tab).

[!INCLUDE [footer-include](includes/footer-banner.md)]
