---
title: Crearea și gestionarea mediilor
description: Aflați cum să vă înscrieți pentru serviciu și cum să gestionați mediile.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644148"
---
# <a name="manage-environments"></a>Gestionați mediile

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Acest articol explică cum să creați o nouă organizație și cum să asigurați accesul la un mediu.

## <a name="sign-up-and-create-an-organization"></a>Înscrieți-vă și creați o organizație

1. Accesați site-ul web [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).

2. Selectați **Începeți lucrul**.

3. Alegeți scenariul de înregistrare preferat și selectați linkul corespunzător.

4. Acceptați termenii și condițiile și selectați **Continuare** pentru a începe crearea organizației.

5. După crearea mediului, veți fi redirecționat către [Customer Insights](https://home.ci.ai.dynamics.com).

6. Utilizați mediul de demonstrație pentru a explora aplicația sau creați un mediu nou urmând pașii din secțiunea următoare.

7. După specificarea setărilor de mediu, selectați **Creați**.

8. Veți fi conectat după ce mediul a fost creat cu succes.

## <a name="create-an-environment-in-an-existing-organization"></a>Creați un mediu într-o organizație existentă

Există două moduri de a crea un mediu nou. Puteți fie specifica o configurație complet nouă, sau puteți copia unele setări de configurare dintr-un mediu existent.

Pentru crearea unui mediu:

1. Selectați simbolul **Setări** în antetul aplicației.

1. Selectați **Mediu nou**.

   > [!div class="mx-imgBorder"]
   > ![Setări ale mediului](media/environment-settings-dialog.png)

1. În caseta de dialog **Creare mediu nou**, selectați **Mediu nou**.

   Dacă doriți să [copiați date din mediul actual](#additional-considerations-for-copy-configuration-preview), selectați **Copiere din mediul existent**. Veți vedea o listă cu toate mediile disponibile în organizația dvs. de unde puteți copia datele.

1. Furnizați următoarele detalii:
   - **Nume**: Numele pentru acest mediu. Acest câmp este deja completat dacă ați copiat dintr-un mediu existent, dar îl puteți modifica.
   - **Regiune**: Regiunea în care este implementat și găzduit serviciul.
   - **Tip**: Selectați dacă doriți să creați un mediu de producție sau sandbox.

2. Opțional, puteți selecta **Setări complexe**:

   - **Se salvează toate datele în**: Specifică unde doriți să stocați datele de ieșire generate de Customer Insights. Veți avea două opțiuni: **spațiu de stocare Customer Insights** (un Azure Data Lake gestionat de echipa Customer Insights) și **Azure Data Lake Storage Gen2** (Azure Data Lake Storage ale dvs.). Opțiunea de stocare a Customer Insights este selectată în mod implicit.

   > [!NOTE]
   > Prin salvarea datelor în Azure Data Lake Storage, sunteți de acord că datele vor fi transferate și stocate în locația geografică corespunzătoare pentru respectivul cont de stocare Azure, care poate diferi de locul în care sunt stocate datele în Dynamics 365 Customer Insights. [Aflați mai multe de la Centrul de autorizare Microsoft.](https://www.microsoft.com/trust-center)
   >
   > În prezent, entitățile ingerate sunt întotdeauna stocate în data lake gestionat de Customer Insights.
   > Acceptăm numai conturi Azure Data Lake Storage Gen2 din aceeași regiune Azure pe care ați selectat-o la crearea mediului.
   > Acceptăm numai conturile de stocare activate pentru Nume Spațiu Ierarhic Azure Data Lake Gen2 (HNS).

   - Pentru opțiunea Azure Data Lake Storage Gen2, puteți alege între utilizarea unei opțiuni bazate pe resurse și o opțiune bazată pe abonament pentru autentificare. pentru mai multe informații, consultați [Conectați detaliile privind publicul la un cont Azure Data Lake Storage Gen2 cu o entitate principală de serviciu Azure](connect-service-principal.md). Numele **Recipient** nu poate fi schimbat și va fi „customerinsights”.
   
   - Dacă doriți să utilizați [predicții](predictions.md), introduceți URL-ul instanței Common Data Service în câmpul **Adresa serverului** sub **Folosiți predicții**.

   Când rulați procese, cum ar fi ingestia de date sau crearea de segmente, folderele corespunzătoare vor fi create în contul de stocare pe care l-ați specificat mai sus. Fișierele de date și fișierele model.json vor fi create și adăugate la subfolderele respective pe baza procesului pe care îl derulați.

   Dacă creați mai multe medii de Customer Insights și alegeți să salvați entitățile de ieșire din acele medii în contul dvs. de stocare, vor fi create dosare separate pentru fiecare mediu cu ci_<environmentid> în recipient.

### <a name="additional-considerations-for-copy-configuration-preview"></a>Considerente suplimentare pentru configurarea copiei (previzualizare)

Sunt copiate următoarele setări de configurare:

- Configurații caracteristică
- Surse de date incluse/importate
- Configurarea unificării datelor (mapare, potrivire, îmbinare)
- Segmente
- Măsuri
- Relaţii
- Activități
- Index de căutare și filtrare
- Destinații export
- Reîmprospătare planificată
- Îmbogățiri
- Management model
- Atribuiri rol

Următoarele setări *nu* sunt copiate:

- Profiluri de client.
- Acreditările sursă de date. Va trebui să furnizați acreditările pentru fiecare sursă de date și să reîmprospătați sursele de date manual.
- Surse de date din folderul Common Data Model și lake-ul gestionat Common Data Service. Va trebui să creați acele surse de date manual cu același nume ca în mediul sursă.

Când copiați un mediu, veți vedea un mesaj de confirmare a faptului că noul mediu a fost creat. Selectați **Accesați sursele de date** pentru a vedea lista surselor de date.

Toate sursele de date vor arăta o stare **Acreditări necesare**. Editați sursele de date și introduceți acreditările pentru a le reîmprospăta.

> [!div class="mx-imgBorder"]
> ![Surse de date copiate](media/data-sources-copied.png)

După reîmprospătarea surselor de date, accesați **Date** > **Unificare**. Aici veți găsi setările din mediul sursă. Editați-le după cum este necesar sau selectați **Rulează** pentru a începe procesul de unificare a datelor și a crea entitatea clientului unificat.

Când unificarea datelor este completă, accesați **Măsuri** și **Segmente** pentru a le reîmprospăta și pe acestea.

## <a name="edit-an-existing-environment"></a>Editați un mediu existent

Puteți edita câteva dintre detaliile mediilor existente.

1. Accesați **Administrare** > **Sistem** > **Despre**.

2. Selectați **Editare**.

3. Puteți actualiza **Numele afișat** al mediului, dar nu puteți schimba **Regiunea** sau **Tipul**.

4. Dacă un mediu este configurat pentru a stoca date în Azure Data Lake Storage Gen2, puteți actualiza **Cheia contului**. Cu toate acestea, nu puteți schimba **Numele de cont** sau numele **Containerului**.

5. Opțional, puteți actualiza de la o conexiune bazată pe cheie de cont la o conexiune bazată pe resurse sau bazată pe abonament. După actualizare, nu puteți reveni la cheia de cont după actualizare. pentru mai multe informații, consultați [Conectați detaliile privind publicul la un cont Azure Data Lake Storage Gen2 cu o entitate principală de serviciu Azure](connect-service-principal.md). Nu puteți schimba informațiile legate de **Recipient** la actualizarea conexiunii.

## <a name="reset-an-existing-environment"></a>Resetați un mediu existent

Puteți reseta un mediu la o stare goală dacă doriți să ștergeți toate configurațiile și să eliminați datele ingerate.

1.  Accesați **Administrare** > **Sistem** > **Despre**.

2.  Selectați **Resetare**. 

3.  Pentru a confirma ștergerea, introduceți numele mediului și selectați **Resetare**.


## <a name="delete-an-existing-environment"></a>Ștergerea unui mediu existent

1. Accesați **Administrare** > **Sistem** > **Despre**.

1. Selectați **Ștergere**.

1. Pentru a confirma ștergerea, introduceți numele mediului și selectați **Ștergere**.
