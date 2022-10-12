---
title: Predictiți pierderea abonamentului (conține videoclip)
description: Prognozați dacă un client prezintă riscul de a nu mai utiliza produsele sau serviciile cu abonament ale companiei dvs.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610251"
---
# <a name="predict-subscription-churn"></a>Previzionați retragerea abonamentului

Prognozați dacă un client prezintă riscul de a nu mai utiliza produsele sau serviciile cu abonament ale companiei dvs. Datele abonamentului includ abonamente active și inactive pentru fiecare client, astfel încât există mai multe intrări pentru fiecare ID de client.

Trebuie să aveți cunoștințe de afaceri pentru a înțelege ce înseamnă pierderea pentru afacerea dvs. Acceptăm definițiile de abandon bazate pe timp, ceea ce înseamnă că se consideră că un client a schimbat o perioadă de timp după încheierea abonamentului.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Încercați abonamentul churn predicție folosind date exemplu: [Abonament churn predicție exemplu de ghid](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Cerințe preliminare

- Minimum [Permisiuni de colaborare](permissions.md).
- Cel puțin 10 profiluri de clienți, de preferință mai mult de 1.000 de clienți unici.
- Customer Identifier, un identificator unic pentru a potrivi abonamentele cu clienții dvs.
- Date de abonament pentru cel puțin dublul intervalului de timp selectat. De preferință, doi-trei ani de date de abonament. Istoricul abonamentelor trebuie să includă:
  - **ID abonament:** Identificatorul unic al unui abonament.
  - **Data de încheiere a abonamentului:** Data expirării abonamentului pentru client.
  - **Data începerii abonamentului:** Data începerii abonamentului pentru client.
  - **Data tranzacției:** Data la care a avut loc schimbarea abonamentului. De exemplu, un client care cumpără sau anulează un abonament.
  - **Este un abonament recurent:** Câmp boolean adevărat/fals care determină dacă abonamentul se va reînnoi cu același ID de abonament fără intervenția clientului.
  - **Frecvența recurenței (în luni):** Pentru abonamentele recurente, luna în care abonamentul se va reînnoi. De exemplu, un abonament anual care se reînnoiește automat pentru un client în fiecare an pentru încă un an are valoarea 12.
  - **Suma abonamentului** : Suma de valută pe care o plătește un client pentru reînnoirea abonamentului. Poate ajuta la identificarea tiparelor pentru diferite niveluri de abonamente.
- Cel puțin două înregistrări de activitate pentru 50% dintre clienții pentru care doriți să calculați pierderea. Activitățile clienților trebuie să includă:
  - **Cheia principala:** Identificator unic pentru o activitate. De exemplu, o vizită pe un site web sau o înregistrare de utilizare care arată vizionarea de către client a unui episod de emisiune TV.
  - **Timestamp-ul:** Data și ora evenimentului identificate prin cheia primară.
  - **Eveniment:** Numele evenimentului pe care doriți să îl utilizați. De exemplu, un câmp numit „UserAction” într-un serviciu de redare în flux video ar putea avea valoarea „Vizualizat”.
  - **Detalii:** Informații detaliate despre eveniment. De exemplu, un câmp numit „ShowTitle” într-un serviciu de redare în flux video ar putea avea valoarea unui videoclip vizualizat de un client.
- Mai puțin de 20% valori lipsă în câmpul de date al entității furnizate.

## <a name="create-a-subscription-churn-prediction"></a>Creați o predicție de renunțare la abonament

Selectați **Salveaza schita** oricând pentru a salva predicție ca schiță. Proiectul predicție este afișat în **Previziunile mele** fila.

1. Mergi la **Inteligența** > **Previziuni**.

1. Pe **Crea** filă, selectați **Utilizați modelul** pe **Model de retragere a clienților** ţiglă.

1. Selectați **Abonament** pentru tipul de baraj și apoi **Incepe**.

1. **Denumiți acest model** și **Numele entității de ieșire** pentru a le distinge de alte modele sau entități.

1. Selectați **Următorul**.

### <a name="define-customer-churn"></a>Definiți retragerea clienților

1. Introduceți numărul de **Zile de la încheierea abonamentului** la care compania dvs. consideră că un client s-a retras. Această perioadă este de obicei legată de activități comerciale, cum ar fi oferte sau alte eforturi de marketing care încearcă să prevină pierderea clientului.

1. Introduceți numărul de **Zile pentru a investiga viitorul pentru a prezice pierderea**. De exemplu, preziceți riscul de retragere pentru clienții dvs. în următoarele 90 de zile pentru a se alinia la eforturile dvs. de marketing de retenție. Predicția riscului de retragere pentru perioade mai lungi sau mai scurte de timp poate face mai dificilă abordarea factorilor din profilul dvs. de risc de retragere, în funcție de cerințele dvs. comerciale specifice.

1. Selectați **Următorul**.

### <a name="add-required-data"></a>Adăugați datele necesare

1. Selectați **Adăugați date** pentru **Istoricul abonamentului**.

1. Selectați tipul de activitate semantică **Abonament** care conține informațiile necesare despre istoricul abonamentului. Dacă activitatea nu a fost configurată, selectați **Aici** și creează-l.

1. Sub **Activități**, dacă atributele activității au fost mapate semantic atunci când activitatea a fost creată, alegeți atributele sau entitatea specifice pe care doriți să se concentreze calculul. Dacă maparea semantică nu a avut loc, selectați **Editați | ×** și mapați datele dvs.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Adăugați datele necesare pentru modelul de eliminare a abonamentului":::

1. Selectați **Următorul** și revizuiți atributele necesare pentru acest model.

1. Selectați **Salvare**.

1. Selectați **Adăugați date** pentru **Activități ale clienților**.

1. Selectați tipul de activitate semantică care oferă informații despre activitatea clientului. Dacă activitatea nu a fost configurată, selectați **Aici** și creează-l.

1. Sub **Activități**, dacă atributele activității au fost mapate semantic atunci când activitatea a fost creată, alegeți atributele sau entitatea specifice pe care doriți să se concentreze calculul. Dacă maparea semantică nu a avut loc, selectați **Editați | ×** și mapați datele dvs.

1. Selectați **Următorul** și revizuiți atributele necesare pentru acest model.

1. Selectați **Salvare**.

1. Adăugați mai multe activități sau selectați **Următorul**.

### <a name="set-update-schedule"></a>Configurați planificarea actualizărilor

1. Alegeți frecvența pentru a vă reanaliza modelul. Această setare este importantă pentru a actualiza acuratețea predicțiilor pe măsură ce noi date sunt ingerate în Customer Insights. Majoritatea firmelor pot reinstrui o dată pe lună și pot obține o precizie bună pentru predicția lor.

1. Selectați **Următorul**.

### <a name="review-and-run-the-model-configuration"></a>Examinați și rulați configurația modelului

The **Examinați și alergați** pasul arată un rezumat al configurației și oferă șansa de a face modificări înainte de a crea predicție.

1. Selectați **Editați | ×** pe oricare dintre pașii pentru a revizui și a face orice modificări.

1. Dacă sunteți mulțumit de selecțiile dvs., selectați **Salvați și rulați** pentru a începe rularea modelului. Selectați **Terminat**. The **Previziunile mele** se afișează fila în timp ce predicție este creată. Procesul poate dura câteva ore până la finalizare, în funcție de cantitatea de date utilizate în predicție.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Vedeți rezultatele predicție

1. Mergi la **Inteligența** > **Previziuni**.

1. În **Previziunile mele** fila, selectați predicție pe care doriți să-l vizualizați.

Există trei secțiuni principale de date în pagina de rezultate:

- **Performanța modelului de antrenament** : Notele A, B sau C indică performanța predicție și vă pot ajuta să luați decizia de a utiliza rezultatele stocate în entitatea de ieșire.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Imagine a casetei de informare a scorului modelului cu nota A.":::

  Nivelurile sunt stabilite pe baza următoarelor reguli:
  - **A** atunci când modelul a prezis cu exactitate cel puțin 50% din totalul previziunilor și când procentul de predicții precise pentru clienții care au reușit este mai mare decât rata medie istorică de pierdere cu cel puțin 10%.
  - **B** atunci când modelul a prezis cu exactitate cel puțin 50% din previziunile totale și când procentul de predicții precise pentru clienții care au reușit este cu până la 10% mai mare decât rata medie istorică de pierdere.
  - **C** atunci când modelul a prezis cu exactitate mai puțin de 50% din previziunile totale sau când procentul de predicții precise pentru clienții care au reușit este mai mic decât rata medie istorică de pierdere.
  
- **Probabilitatea de retragere (număr de clienți)**: Grupuri de clienți în funcție de riscul de retragere prognozat. Opțional, [creați segmente de clienți](prediction-based-segment.md) cu risc ridicat de pierdere. Astfel de segmente vă ajută să înțelegeți unde ar trebui să fie delimitarea dvs. pentru membrii segmentului.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Graficul care arată distribuția rezultatelor retragerii, împărțită în intervale cuprinse între 0-100%":::

- **Cei mai influenți factori:** Există mulți factori care sunt luați în considerare atunci când vă creați predicția. Fiecare dintre factori are importanța sa calculată pentru predicțiile agregate pe care le creează un model. Folosiți acești factori pentru a vă valida rezultatele predicție. Sau utilizați aceste informații mai târziu pentru a [creați segmente](.//prediction-based-segment.md) care ar putea contribui la influențarea riscului de abandon pentru clienți.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Listă care arată factorii influenți și importanța lor în predicția rezultatului retragerii.":::

> [!NOTE]
> În entitatea de ieșire pentru acest model, *ChurnScore* este probabilitatea prezisă de abandon și *IsChurn* este o etichetă binară bazată pe *ChurnScore* cu prag de 0,5. Dacă acest prag implicit nu funcționează pentru scenariul dvs.,[creați un nou segment](segments.md) cu pragul preferat. Pentru a vedea scorul de pierdere, accesați **Date** > **Entități** și vizualizați fila de date pentru entitatea de ieșire pe care ați definit-o pentru acest model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
