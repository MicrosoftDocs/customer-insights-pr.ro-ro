---
title: Crearea și gestionarea mediilor
description: Aflați cum să vă înscrieți pentru serviciu și cum să gestionați mediile.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 904ce68336cba4b7a4d5a37692b72d091400559d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304895"
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

> [!NOTE]
> Organizațiile pot crea *două* medii pentru fiecare licență Customer Insights. Dacă organizația dvs. achiziționează mai multe ori licență, vă rugăm să [contactați echipa noastră de asistență](https://go.microsoft.com/fwlink/?linkid=2079641) pentru a crește numărul de medii disponibile. Pentru mai multe informații despre capacitate și capacitate suplimentară, descărcați [Ghid de licențiere Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Pentru crearea unui mediu:

1. Selectați selectorul **Mediu** în antetul aplicației.

1. Selectați **Nou**.

   > [!div class="mx-imgBorder"]
   > ![Setări de mediu.](media/environment-settings-dialog.png)

1. În dialogul **Creați un mediu**, selectați **Mediu nou**.

   Dacă doriți să [copiați date din mediul actual](#considerations-for-copy-configuration-preview), selectați **Copiere din mediul existent**. Veți vedea o listă cu toate mediile disponibile în organizația dvs. de unde puteți copia datele.

1. Furnizați următoarele detalii:
   - **Nume**: Numele pentru acest mediu. Acest câmp este deja completat dacă ați copiat dintr-un mediu existent, dar îl puteți modifica.
   - **Tip**: Selectați dacă doriți să creați un mediu de producție sau sandbox.
   - **Regiune**: Regiunea în care este implementat și găzduit serviciul.
   
1. Opțional, puteți selecta **Setări complexe**:

   - **Se salvează toate datele în**: Specifică unde doriți să stocați datele de ieșire generate de Customer Insights. Veți avea două opțiuni: **Depozitare Customer Insights** (un Azure Data Lake administrat de echipa Customer Insights) și **Azure Data Lake Storage** (Azure Data Lake Storage al dvs). Opțiunea de stocare a Customer Insights este selectată în mod implicit.

     > [!NOTE]
     > Prin salvarea datelor în Azure Data Lake Storage, sunteți de acord că datele vor fi transferate și stocate în locația geografică corespunzătoare pentru respectivul cont de stocare Azure, care poate diferi de locul în care sunt stocate datele în Dynamics 365 Customer Insights. [Aflați mai multe de la Centrul de autorizare Microsoft.](https://www.microsoft.com/trust-center)
     >
     > În prezent, entitățile ingerate sunt mereu stocate în Customer Insights Managed Data Lake. 
     > 
     > Acceptăm numai conturi Azure Data Lake Storage din aceeași regiune Azure pe care ați selectat-o la crearea mediului. 
     > 
     > Noi acceptăm numai conturi Azure Data Lake Storage care au activat spațiul de nume ierarhic.


   - Pentru opțiunea Azure Data Lake Storage, puteți alege între o opțiune bazată pe resurse și o opțiune bazată pe abonament pentru autentificare. pentru mai multe informații, consultați [Conectați detaliile privind publicul la un cont Azure Data Lake Storage Gen2 cu o entitate principală de serviciu Azure](connect-service-principal.md). Numele **Recipient** nu poate fi schimbat și va fi `customerinsights`.
   
   - Dacă doriți să utilizați [predicții](predictions.md), configurați partajarea datelor cu Microsoft Dataverse, sau activați ingestia de date din sursele de date local, furnizați URL de mediu Microsoft Dataverse sub **Configurați partajarea datelor cu Microsoft Dataverse și activați capabilități suplimentare**. Selectați **Activați partajarea datelor** pentru a partaja datele de ieșire Customer Insights cu un Microsoft Dataverse Data Lake gestionat.

     > [!NOTE]
     > - Partajarea datelor cu Microsoft Dataverse Data Lage gestionat nu este acceptat atunci când salvați toate datele pe propriul Azure Data Lake Storage.
     > - [Predicția valorilor lipsă într-o entitate](predictions.md) momentan nu este acceptată atunci când activați partajarea datelor cu Microsoft Dataverse Data Lake gestionat.

     > [!div class="mx-imgBorder"]
     > ![Opțiuni de configurare pentru a permite partajarea datelor cu Microsoft Dataverse.](media/datasharing-with-DataverseMDL.png)

   Când rulați procese, cum ar fi ingestia de date sau crearea de segmente, folderele corespunzătoare vor fi create în contul de stocare pe care l-ați specificat mai sus. Fișierele de date și fișierele model.json vor fi create și adăugate în dosare pe baza numelui procesului.

   Dacă creați mai multe medii de Customer Insights și alegeți să salvați entitățile de ieșire din acele medii în contul dvs. de stocare, vor fi create dosare separate pentru fiecare mediu cu ci_<environmentid> în recipient.

### <a name="considerations-for-copy-configuration-preview"></a>Considerații pentru configurarea copierii (previzualizare)

Sunt copiate următoarele setări de configurare:

- Configurații caracteristică
- Surse de date ingerate/importate
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
- Surse de date din folderul Model de date comune și Dataverse Data Lake gestionat. Va trebui să creați acele surse de date manual cu același nume ca în mediul sursă.

Când copiați un mediu, veți vedea un mesaj de confirmare a faptului că noul mediu a fost creat. Selectați **Accesați sursele de date** pentru a vedea lista surselor de date.

Toate sursele de date vor arăta o stare **Acreditări necesare**. Editați sursele de date și introduceți acreditările pentru a le reîmprospăta.

> [!div class="mx-imgBorder"]
> ![Surse de date copiate.](media/data-sources-copied.png)

După reîmprospătarea surselor de date, accesați **Date** > **Unificare**. Aici veți găsi setările din mediul sursă. Editați-le după cum este necesar sau selectați **Rulează** pentru a începe procesul de unificare a datelor și a crea entitatea clientului unificat.

Când unificarea datelor este completă, accesați **Măsuri** și **Segmente** pentru a le reîmprospăta și pe acestea.

## <a name="edit-an-existing-environment"></a>Editați un mediu existent

Puteți edita câteva dintre detaliile mediilor existente.

1.  Selectați selectorul **Mediu** în antetul aplicației.

2.  Selectați pictograma **Editare**.

3. În caseta **Editați mediul**, puteți actualiza **Numele afișat** al mediului, dar nu puteți schimba **Regiune** sau **Tip**.

4. Dacă un mediu este configurat pentru a stoca date în Azure Data Lake Storage, puteți actualiza fișierul **Cheia contului**. Cu toate acestea, nu puteți schimba **Numele de cont** sau numele **Containerului**.

5. Opțional, puteți actualiza de la o conexiune bazată pe cheie de cont la o conexiune bazată pe resurse sau bazată pe abonament. După actualizare, nu puteți reveni la cheia de cont după actualizare. pentru mai multe informații, consultați [Conectați detaliile privind publicul la un cont Azure Data Lake Storage Gen2 cu o entitate principală de serviciu Azure](connect-service-principal.md). Nu puteți schimba informațiile legate de **Recipient** la actualizarea conexiunii.

6. Opțional, puteți furniza un URL de mediu Microsoft Dataverse sub **Configurați partajarea datelor cu Microsoft Dataverse și activați capabilități suplimentare**. Aceste capacități includ partajarea datelor cu aplicații și soluții bazate pe Microsoft Dataverse, ingestia de date din sursele de date local sau utilizarea de [predicții](predictions.md). Selectați **Activați partajarea datelor** pentru a partaja datele de ieșire Customer Insights cu un Microsoft Dataverse Data lake gestionat.

   > [!NOTE]
   > - Partajarea datelor cu Microsoft Dataverse Data Lage gestionat nu este acceptat atunci când salvați toate datele pe propriul Azure Data Lake Storage.
   > - [Predicție a valorilor lipsă într-o entitate](predictions.md) momentan nu este acceptat atunci când activați partajarea datelor cu Microsoft Dataverse Data Lake gestionat.

   După ce activați partajarea datelor cu Microsoft Dataverse, începe o reîmprospătare completă, unică, a surselor de date și a altor procese. Dacă procesele rulează, nu vedeți opțiunea de a permite partajarea datelor cu Microsoft Dataverse. Așteptați ca acele procese să se finalizeze sau să le anulați pentru a permite partajarea datelor. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Opțiuni de configurare pentru a permite partajarea datelor cu Microsoft Dataverse.":::
   
   Când rulați procese, cum ar fi ingestia de date sau crearea de segmente, folderele corespunzătoare vor fi create în contul de stocare pe care l-ați specificat mai sus. Fișierele de date și fișierele model.json vor fi create și adăugate în subfolderele respective, în funcție de procesul pe care îl executați.

## <a name="reset-an-existing-environment"></a>Resetați un mediu existent

Ca administrator, puteți reseta un mediu la o stare goală dacă doriți să ștergeți toate configurațiile și să eliminați datele ingerate.

1.  Selectați selectorul **Mediu** în antetul aplicației. 

2.  Selectați mediul pe care doriți să îl resetați și selectați punctele de suspensie (**...**). 

3. Alegeți opțiunea **Resetați**. 

4.  Pentru a confirma ștergerea, introduceți numele mediului și selectați **Resetare**.

## <a name="delete-an-existing-environment"></a>Ștergerea unui mediu existent

În calitate de administrator, puteți șterge un mediu pe care îl administrați.

1.  Selectați selectorul **Mediu** în antetul aplicației.

2.  Selectați mediul pe care doriți să îl resetați și selectați punctele de suspensie (**...**). 

3. Alegeți opțiunea **Ștergere**. 

4.  Pentru a confirma ștergerea, introduceți numele mediului și selectați **Ștergere**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
