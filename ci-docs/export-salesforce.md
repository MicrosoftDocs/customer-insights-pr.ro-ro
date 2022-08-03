---
title: Exportați datele în Salesforce Marketing Cloud (previzualizare)
description: Aflați cum să configurați conexiunea și să exportați către Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197053"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Exportați datele în Salesforce Marketing Cloud (previzualizare)

Folosiți datele clienților dvs. în Salesforce Marketing Cloud exportându-le printr-o locație Protocol de transfer de fișiere securizat (SFTP).

## <a name="prerequisites"></a>Cerințe preliminare

- Un [Gazdă SFTP pentru Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) și acreditările de administrator corespunzătoare.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Configurați conexiunea la Salesforce Marketing Cloud

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **Salesforce Marketing Cloud**.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Furnizați un **Nume de utilizator**, **Parolă**, **Nume de gazdă** și **Folder de export** pentru contul dvs. de SFTP.

1. Selectați **Verificare** pentru a testa conexiunea.

1. Examinați [confidențialitatea și conformitatea datelor](connections.md#data-privacy-and-compliance) și selectați **Sunt de acord**.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Faceți salt la **Date** > **Exporturi**.

1. Selectați **Adăugați export**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea SFTP. Contactați un administrator dacă nu este disponibilă nicio conexiune.

1. Introduceți un nume pentru export.

1. Alegeți dacă doriți să vă exportați datele dvs. în mod **Comprimat cu gzip** sau **Dezarhivat** și **delimitatorul de câmp** pentru fișierele exportate.

1. Selectați entitățile, de exemplu segmente, pe care doriți să le exportați.

   > [!NOTE]
   > Fiecare entitate selectată va fi împărțită în maximum cinci fișiere de ieșire atunci când este exportată.

1. Selectați **Salvare**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importați datele Customer Insights din locația SFTP în Salesforce Marketing Cloud

1. Creați [extensii de date în Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) pentru a importa fișierul de date Customer Insights din locația SFTP.

2. [Importați datele din locația SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) în extensia de date Salesforce Marketing Cloud.

3. Configurați automatizarea pentru a importa datele în extensiile de date. Aflați mai multe despre [automatizări de eliminare a fișierelor și automatizări planificate](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definiți o [automatizare de eliminare a fișierelor](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) sau o  [automatizare planificată](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Iată un exemplu de [o automatizare cu SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
