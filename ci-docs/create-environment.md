---
title: Creați un mediu nou
description: Pași pentru a crea medii în Dynamics 365 Customer Insights.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304259"
---
# <a name="create-a-new-environment"></a>Creați un mediu nou

După [achiziționarea unei licențe de abonament pentru Dynamics 365 Customer Insights](paid-license.md), administratorul global al Microsoft 365 chiriașul primește un e-mail care îl invită să creeze mediul. Accesați [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) pentru a începe. În acest scenariu, începeți cu [Pasul 1: Furnizați informații de bază](#step-1-provide-basic-information).

După ce primul mediu este creat, administratorul global al Microsoft 365 chiriașul poate [adăugați utilizatori din organizația lor ca administratori](permissions.md). Acești administratori pot administra apoi utilizatorii și mediile. Dacă organizația dvs. achiziționează mai mult de o licență pentru Customer Insights, [contactați echipa noastră de asistență](https://go.microsoft.com/fwlink/?linkid=2079641) pentru a crește numărul de medii disponibile. Pentru mai multe informații despre capacitate și capacitatea suplimentară, consultați [Ghid de licențiere Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544). Odată ce aveți posibilitatea de a crea medii suplimentare, accesați [Începeți procesul de creare a mediului](#start-the-environment-creation-process).

> [!TIP]
> Dacă doriți să încercați serviciul, consultați [Configurați un mediu de încercare](trial-signup.md).

## <a name="prerequisites"></a>Cerințe preliminare

[Permisiuni de administrator](permissions.md) în Customer Insights

## <a name="start-the-environment-creation-process"></a>Începeți procesul de creare a mediului

1. Deschideți selectorul de mediu și selectați **+ Nou**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Alegeți selectorul de mediu.":::

1. Urmați experiența ghidată prezentată în secțiunile următoare pentru a furniza toate informațiile necesare pentru un mediu nou.

## <a name="step-1-provide-basic-information"></a>Pasul 1: Furnizați informații de bază

1. Alegeți dacă doriți să creați un mediu de la zero sau să copiați date dintr-un alt mediu. [Copierea datelor dintr-un alt mediu](#copy-the-environment-configuration) necesită pași suplimentari.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Casetă de dialog pentru a crea un mediu nou Customer Insights.":::

1. Furnizați următoarele detalii:

   - **Nume** : Nume pentru acest mediu. Acest câmp este deja completat dacă ați copiat dintr-un mediu existent, dar îl puteți modifica.
   - **Alege-ți afacerea** : Publicul principal pentru noul mediu: consumatori individuali (B-to-C) sau [conturi de afaceri](work-with-business-accounts.md) (B-la-B). Dacă organizația dvs. face afaceri în principal cu persoane fizice, cum ar fi un comerciant cu amănuntul sau o cafenea, alegeți consumatori individuali. Dacă publicul dvs. principal este alte companii, cum ar fi un producător de mașini sau o companie de hârtie, alegeți conturi de afaceri.
   - **Tip** : Tip de mediu: producție sau sandbox. Mediile Sandbox nu permit reîmprospătarea datelor programate și sunt destinate pre-implementării și testării. Mediile Sandbox utilizează același public principal ca mediul de producție selectat în prezent.
   - **Regiune** : Regiunea în care este implementat și găzduit serviciul. La [folosește-ți pe al tău Azure Data Lake Storage cont](own-data-lake-storage.md) sau [conectați la un existent Microsoft Dataverse organizare](customer-insights-dataverse.md), mediul Customer Insights trebuie să fie în aceeași regiune.

1. Selectați **Următorul**.

## <a name="step-2-configure-data-storage"></a>Pasul 2: configurați stocarea datelor

1. Alegeți unde să stocați datele Customer Insights:

   - **Stocarea datelor despre clienți** : Stocarea datelor este gestionată automat. Este opțiunea implicită și, dacă nu există cerințe specifice pentru stocarea datelor în propriul cont de stocare, vă recomandăm să utilizați această opțiune.
   - **Azure Data Lake Storage**: Al tau Azure Data Lake Storage cont pentru a stoca datele, astfel încât să aveți control deplin unde sunt stocate datele. Urmați pașii din [Folosește-ți pe al tău Azure Data Lake Storage cont](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Alegeți opțiunea preferată pentru a vă stoca datele.":::

1. Selectați **Următorul**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>Pasul 3: Conectați-vă la Microsoft Dataverse

Daca ai un Dataverse mediu, conectați Customer Insights. Partajați date cu Dataverse pentru a-l folosi cu aplicații de afaceri bazate pe Dataverse, cum ar fi Dynamics 365 Marketing sau aplicații bazate pe model în Power Apps.

1. Urmați pașii din [Lucrați cu datele Customer Insights în Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="partajarea datelor cu Microsoft Dataverse activat automat pentru medii net noi.":::

1. Selectați **Următorul**.

## <a name="step-4-finalize-the-settings"></a>Pasul 4: finalizați setările

Examinați setările specificate. Când totul pare complet, selectați **Creare** pentru a configura mediul.

Pentru a modifica unele dintre setări mai târziu, consultați [Gestionați mediile](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Lucrați cu noul dvs. mediu

Consultați următoarele articole pentru a vă ajuta să începeți configurarea Customer Insights:

- [Adăugați mai mulți utilizatori și atribuiți permisiuni](permissions.md).
- [Ingerați sursele de date](data-sources.md) și rulați-le prin [procesul de unificare a datelor](data-unification.md) pentru a obține [profiluri unificate ale clienților](customer-profiles.md).
- [Îmbogățiți profilurile unificate ale clienților](enrichment-hub.md) sau [rulați modele predictive](predictions-overview.md).
- [Creați segmente](segments.md) pentru a grupa clienți și [măsuri](measures.md) pentru a reviziui indicatorii KPI.
- [Configurați conexiuni](connections.md) și [exporturi](export-destinations.md) pentru a procesa subseturi de date în alte aplicații.

## <a name="copy-the-environment-configuration"></a>Copiați configurația mediului

În calitate de administrator, dacă ați ales să copiați configurația dintr-un mediu existent, selectați din lista tuturor mediilor disponibile din organizația dvs.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captură de ecran a opțiunilor de setări din setările de mediu.":::

Sunt copiate următoarele setări de configurare:

- Surse de date importate prin Power Query
- Configurarea unificării datelor
- Segmente
- Măsuri
- Relaţii
- Activități
- Index de căutare și filtrare
- Exporturi
- Planificare reîmprospătare
- Îmbogățiri
- Predicție modele
- Atribuiri rol

### <a name="set-up-a-copied-environment"></a>Configurați un mediu copiat

Când copiați configurația mediului, se afișează un mesaj de confirmare când a fost creat mediul copiat. Efectuați următorii pași pentru a confirma acreditările.

1. Selectați **Accesați sursele de date** pentru a vedea lista surselor de date. Toate sursele de date arată **Acreditări necesare** stare.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Lista surselor de date care au fost copiate și care necesită autentificare.":::

1. Editați sursele de date și introduceți acreditările pentru a le reîmprospăta. Surse de date din folderul Common Data Model și Dataverse trebuie creat manual cu același nume ca în mediul sursă.

1. După reîmprospătarea surselor de date, accesați **Date** > **Unificare**. Aici veți găsi setările din mediul sursă. Editați-le după cum este necesar sau selectați **Unifica** > **Unificați profilurile și dependențele clienților** pentru a începe procesul de unificare a datelor și a crea entitatea client unificată.

   > [!TIP]
   > Pentru conturi și contacte, selectați **Unificați conturile** > **Unificați profilurile și dependențele**.

1. Când unificarea datelor este completă, accesați **Măsuri** și **Segmente** pentru a le reîmprospăta.

1. Mergi la **Admin** > **Conexiuni** pentru a reautentifica conexiunile în noul dumneavoastră mediu.

1. Mergi la **Date** > **Îmbogăţire** și **Date** > **Exporturi** pentru a le reactiva.

[!INCLUDE [footer-include](includes/footer-banner.md)]
