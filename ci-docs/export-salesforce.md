---
title: Exportați datele Customer Insights în Salesforce Marketing Cloud
description: Aflați cum să configurați conexiunea și să exportați către Salesforce Marketing Cloud.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: aaf5c2607099bbfccf7ed75330267da8c3c5fe1b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643875"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Exportați segmente și alte date în Salesforce Marketing Cloud (previzualizare)

Folosiți datele clienților dvs. în Salesforce Marketing Cloud exportându-le printr-o locație Protocol de transfer de fișiere securizat (SFTP).

## <a name="prerequisites-for-connection"></a>Cerințe preliminare pentru conexiune

- Disponibilitatea unei gazde SFTP și acreditările de administrator corespunzătoare. [Cum se configurează locațiile SFTP pentru Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Configurați conexiunea la Salesforce Marketing Cloud

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Salesforce Marketing Cloud** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. Dacă nu luați nicio măsură, valoarea implicită va fi Administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Furnizați un **Nume de utilizator**, **Parolă**, **Nume de gazdă** și **Folder de export** pentru contul dvs. de SFTP.

1. Selectați **Verificare** pentru a testa conexiunea.

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

Puteți configura acest export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea SFTP. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

1. Alegeți dacă doriți să vă exportați datele dvs. în mod **Comprimat cu gzip** sau **Dezarhivat** și **delimitatorul de câmp** pentru fișierele exportate.

1. Selectați entitățile, de exemplu segmente pe care doriți să le exportați.

   > [!NOTE]
   > Fiecare entitate selectată va fi împărțită în maximum cinci fișiere de ieșire la export. 

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importați datele Customer Insights din locația SFTP în Salesforce Marketing Cloud

1. Creați [extensii de date în Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) pentru a importa fișierul de date Customer Insights din locația SFTP.

2. [Importați datele din locația SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) în extensia de date Salesforce Marketing Cloud. 

3. Configurați automatizarea pentru a importa datele în extensiile de date. Aflați mai multe despre [automatizări de eliminare a fișierelor și automatizări planificate](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definiți o [automatizare de eliminare a fișierelor](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) sau o  [automatizare planificată](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Iată un exemplu de [o automatizare cu SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date prin SFTP, permiteți transferul de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi datele cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru asigurarea faptului că destinația de export îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.

[!INCLUDE [footer-include](includes/footer-banner.md)]
