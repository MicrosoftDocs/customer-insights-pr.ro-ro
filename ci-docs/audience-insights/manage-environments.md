---
title: Crearea și gestionarea mediilor
description: Aflați cum să vă înscrieți pentru serviciu și cum să gestionați mediile.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 2f115269b9d07dd118ec18cc48b55de8aea9b5bb
ms.sourcegitcommit: 98267da3f3eddbdfbc89600a7f54e5e664a8f069
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/28/2021
ms.locfileid: "6683488"
---
# <a name="manage-environments"></a>Gestionați mediile

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Comutați medii

Selectați controlul **Mediu** din colțul din dreapta sus al paginii pentru a modifica mediile.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Captură de ecran a comenzii pentru a schimba mediul.":::

Administratorii pot [crea](get-started-paid.md) și gestiona medii.

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
   > - [Predicție a valorilor lipsă într-o entitate](predictions.md) și rapoartele PowerBI Embedded în statistici privind audiența (dacă sunt activate în mediul dvs.) nu sunt în prezent acceptate atunci când activați partajarea datelor cu data lake Microsoft Dataverse gestionat.

   După ce activați partajarea datelor cu Microsoft Dataverse, începe o reîmprospătare completă, unică, a surselor de date și a altor procese. Dacă procesele rulează, nu vedeți opțiunea de a permite partajarea datelor cu Microsoft Dataverse. Așteptați ca acele procese să se finalizeze sau să le anulați pentru a permite partajarea datelor. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Opțiuni de configurare pentru a permite partajarea datelor cu Microsoft Dataverse.":::
   
   Când rulați procese, cum ar fi ingestia de date sau crearea de segmente, folderele corespunzătoare vor fi create în contul de stocare pe care l-ați specificat mai sus. Fișierele de date și fișierele model.json vor fi create și adăugate în subfolderele respective, în funcție de procesul pe care îl executați.

## <a name="copy-the-environment-configuration"></a>Copiați configurația mediului

Când creați un mediu nou, puteți alege să copiați configurația dintr-un mediu existent. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captură de ecran a opțiunilor de setări din setările de mediu.":::

Veți vedea o listă cu toate mediile disponibile în organizația dvs. de unde puteți copia datele.

Sunt copiate următoarele setări de configurare:

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

Următoarele date *nu* sunt copiate:

- Profiluri de client.
- Acreditările sursă de date. Va trebui să furnizați acreditările pentru fiecare sursă de date și să reîmprospătați sursele de date manual.
- Surse de date din folderul Model de date comune și Dataverse Data Lake gestionat. Va trebui să creați acele surse de date manual cu același nume ca în mediul sursă.

Când copiați un mediu, veți vedea un mesaj de confirmare a faptului că noul mediu a fost creat. Selectați **Accesați sursele de date** pentru a vedea lista surselor de date.

Toate sursele de date vor arăta o stare **Acreditări necesare**. Editați sursele de date și introduceți acreditările pentru a le reîmprospăta.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista surselor de date care au fost copiate și care necesită autentificare.":::

După reîmprospătarea surselor de date, accesați **Date** > **Unificare**. Aici veți găsi setările din mediul sursă. Editați-le după cum este necesar sau selectați **Rulează** pentru a începe procesul de unificare a datelor și a crea entitatea clientului unificat.

Când unificarea datelor este completă, accesați **Măsuri** și **Segmente** pentru a le reîmprospăta și pe acestea.

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
