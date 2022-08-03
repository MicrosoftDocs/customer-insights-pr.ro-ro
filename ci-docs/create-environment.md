---
title: 'Cum să: creați un mediu nou'
description: Pași pentru a crea medii în Dynamics 365 Customer Insights.
ms.date: 05/31/2022
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
ms.openlocfilehash: 33c8910b7a4dd8723c0d62f2e28228cd2d8df4b7
ms.sourcegitcommit: 5716025eb4828425ca237377b02a892de8689f4a
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/13/2022
ms.locfileid: "9142834"
---
# <a name="how-to-create-a-new-environment"></a>Cum să: creați un mediu nou

După [achiziționarea unei licențe de abonament pentru Dynamics 365 Customer Insights](paid-license.md), administratorul global al Microsoft 365 chiriașul primește un e-mail care îl invită să creeze mediul. Accesați [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) pentru a începe. În acest scenariu, puteți merge direct la [Pasul 1: Furnizați informații de bază](#step-1-provide-basic-information).

După ce primul mediu este creat, administratorul global al Microsoft 365 chiriașul poate [adăugați utilizatori din organizația lor ca administratori](permissions.md). În continuare, acești administratori pot gestiona utilizatorii și mediile. Dacă organizația dvs. achiziționează mai mult de o licență pentru Customer Insights, [contactați echipa noastră de asistență](https://go.microsoft.com/fwlink/?linkid=2079641) pentru a crește numărul de medii disponibile. Pentru mai multe informații despre capacitate și capacitatea suplimentară, consultați [Ghid de licențiere Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Dacă doriți să încercați serviciul, consultați [Configurați un mediu de încercare](trial-signup.md).

## <a name="prerequisites"></a>Cerințe preliminare

Ai nevoie [permisiuni de administrator](permissions.md) în Customer Insights pentru a crea sau gestiona medii.

## <a name="start-the-environment-creation-process"></a>Începeți procesul de creare a mediului

1. Deschideți selectorul de mediu și selectați **+ Nou**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Alegeți selectorul de mediu.":::

1. Urmați experiența ghidată prezentată în secțiunile următoare pentru a furniza toate informațiile necesare pentru un mediu nou. Dacă ați configurat un mediu mai devreme, puteți, de asemenea [copiați configurația](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Pasul 1: Furnizați informații de bază

În pasul **Informații de bază**, alegeți dacă doriți să creați un mediu de la zero sau [copiați date dintr-un alt mediu](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Casetă de dialog pentru a crea un mediu nou Customer Insights.":::

Furnizați următoarele detalii:

- **Nume**: Numele pentru acest mediu. Acest câmp este deja completat dacă ați copiat dintr-un mediu existent, dar îl puteți modifica.
- **Alegeți-vă afacerea**: alegeți publicul principal pentru noul mediu. Puteți lucra cu consumatori individuali (B-la-C) sau cu [conturi de business](work-with-business-accounts.md) (B-la-B). Dacă organizația dvs. face afaceri în principal cu persoane fizice, cum ar fi un comerciant cu amănuntul sau o cafenea, alegeți consumatori individuali. În cazul în care publicul dvs. principal este alte companii, cum ar fi un producător de mașini sau o companie de hârtie, alegeți conturi de afaceri.
- **Tip**: Selectați dacă doriți să creați un mediu de tip producție sau sandbox. Mediile Sandbox nu permit reîmprospătarea datelor programate și sunt destinate pre-implementării și testării. Mediile Sandbox utilizează același public principal ca mediul de producție selectat în prezent.
- **Regiune**: Regiunea în care este implementat și găzduit serviciul. La [folosește-ți pe al tău Azure Data Lake Storage cont](own-data-lake-storage.md) sau [conectați la un existent Microsoft Dataverse organizare](customer-insights-dataverse.md), mediul Customer Insights trebuie să fie în aceeași regiune.

## <a name="step-2-configure-data-storage"></a>Pasul 2: configurați stocarea datelor

În **Stocare a datelor** pas, alegeți unde să stocați datele Customer Insights.

Există două opțiuni dintre care poți alege:

- **Stocarea datelor despre clienți** : Stocarea datelor este gestionată de echipa Customer Insights. Este opțiunea implicită și, dacă nu există cerințe specifice pentru stocarea datelor în propriul cont de stocare, vă recomandăm să utilizați această opțiune.
- **Azure Data Lake Storage**: Specificați-vă propria Azure Data Lake Storage cont pentru a stoca datele, astfel încât să aveți control deplin unde sunt stocate datele. Pentru mai multe informații, vezi [Folosește-ți pe al tău Azure Data Lake Storage cont](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Alegeți opțiunea preferată pentru a vă stoca datele.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Pasul 3: Conectați-vă la Microsoft Dataverse

Pasul **Microsoft Dataverse** vă permite să conectați Customer Insights cu mediul Dataverse. Partajați date cu Dataverse pentru a-l folosi cu aplicații de afaceri bazate pe Dataverse, cum ar fi Dynamics 365 Marketing sau aplicații bazate pe model în Power Apps.

Lăsați acest câmp necompletat dacă nu aveți al dvs Dataverse mediu și vom crea unul pentru tine.

Pentru mai multe informații, vezi [Lucrați cu datele Customer Insights în Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="partajarea datelor cu Microsoft Dataverse activat automat pentru medii net noi.":::

### <a name="step-4-finalize-the-settings"></a>Pasul 4: finalizați setările

În **Revizuire** pas, parcurgeți toate setările specificate. Când totul pare complet, selectați **Creare** pentru a configura mediul.

Puteți modifica unele dintre setări mai târziu. Pentru informații suplimentare, consultați [Gestionare medii](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Lucrați cu noul dvs. mediu

Consultați următoarele articole pentru a vă ajuta să începeți configurarea Customer Insights:

- [Adăugați mai mulți utilizatori și atribuiți permisiuni](permissions.md).
- [Ingerați sursele de date](data-sources.md) și rulați-le prin [procesul de unificare a datelor](data-unification.md) pentru a obține [profiluri unificate ale clienților](customer-profiles.md).
- [Îmbogățiți profilurile unificate ale clienților](enrichment-hub.md) sau [rulați modele predictive](predictions-overview.md).
- [Creați segmente](segments.md) pentru a grupa clienți și [măsuri](measures.md) pentru a reviziui indicatorii KPI.
- [Configurați conexiuni](connections.md) și [exporturi](export-destinations.md) pentru a procesa subseturi de date în alte aplicații.

## <a name="copy-the-environment-configuration"></a>Copiați configurația mediului

În calitate de administrator, puteți alege să copiați configurația dintr-un mediu existent atunci când creați unul nou.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captură de ecran a opțiunilor de setări din setările de mediu.":::

Veți vedea o listă cu toate mediile disponibile în organizația dvs. de unde puteți copia datele.

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

## <a name="set-up-a-copied-environment"></a>Configurați un mediu copiat

Când copiați configurația mediului, trebuie să parcurgeți câțiva pași suplimentari pentru a confirma acreditările:

- Profiluri de client. Mai întâi, autentificați-vă și asimilați sursele de date și rulați unificarea datelor pentru a recrea profilurile clienților.
- Acreditările sursă de date. Trebuie să furnizați acreditările pentru fiecare sursă de date pentru a autentifica și reîmprospăta sursele de date manual.
- Surse de date din folderul Common Data Model și Dataverse. Trebuie să creați manual acele surse de date cu același nume ca în mediul sursă.
- Secrete de conexiune care sunt folosite pentru exporturi și îmbogățiri. Trebuie să reautentificați conexiunile și apoi să reactivați îmbogățirile și exporturile.

Veți vedea un mesaj de confirmare când mediul copiat a fost creat. Selectați **Accesați sursele de date** pentru a vedea lista surselor de date.

Toate sursele de date vor arăta o stare **Acreditări necesare**. Editați sursele de date și introduceți acreditările pentru a le reîmprospăta.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista surselor de date care au fost copiate și care necesită autentificare.":::

După reîmprospătarea surselor de date, accesați **Date** > **Unificare**. Aici veți găsi setările din mediul sursă. Editați-le după cum este necesar sau selectați **Rulează** pentru a începe procesul de unificare a datelor și a crea entitatea clientului unificat.

Când unificarea datelor este completă, accesați **Măsuri** și **Segmente** pentru a le reîmprospăta și pe acestea.

Înainte de a reactiva exporturile și îmbogățirile, accesați **Admin** > **Conexiuni** pentru a reautentifica conexiunile în noul dumneavoastră mediu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
