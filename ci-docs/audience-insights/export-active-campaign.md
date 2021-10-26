---
title: Exportați datele Customer Insights către ActiveCampaign
description: Aflați cum să configurați conexiunea și să exportați către ActiveCampaign.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4fbdd5a51a3df35d31ad072eef64d20ee967d7ee
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618168"
---
# <a name="export-segments-to-activecampaign-preview"></a>Exportați segmente în ActiveCampaign (previzualizare)

Exportați segmente de profiluri unificate ale clienților în ActiveCampaign și folosiți-le pentru activități de marketing.

## <a name="prerequisites"></a>Cerințe preliminare

-   Aveți un [Cont ActiveCampaign](https://www.activecampaign.com/) și acreditările de administrator corespunzătoare.
-   Aveți [segmente configurate](segments.md) în Detalii despre audiență.
-   Profilurile de clienți unificate din segmentele exportate conțin un câmp cu o adresă de e-mail.

## <a name="known-limitations"></a>Limitări cunoscute

- Puteți exporta până la 1 milion de profiluri de clienți per export către ActiveCampaign și poate dura până la 90 minute până la finalizare.
- Exportul către ActiveCampaign este limitat la segmente.
- Numărul de profiluri de clienți pe care le puteți exporta în ActiveCampaign depinde de contractul dvs. cu ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>Configurați conexiunea la ActiveCampaign

1. Salt la **Administrator** > **Conexiuni**.

1. Selectați **Adăugați conexiune** și alegeți **ActiveCampaign** pentru a configura conexiunea.

1. Dați conexiunii dvs. un nume ușor de recunoscut în câmpul **Nume afișat**. Numele și tipul conexiunii descriu această conexiune. Vă recomandăm să alegeți un nume care să explice scopul și ținta conexiunii.

1. Alegeți cine poate utiliza această conexiune. În mod implicit, sunt doar de administratori. Pentru mai multe informații, consultați [Permiteți contribuitorilor să utilizeze o conexiune pentru exporturi](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduceți [Cheia API ActiveCampaign și REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). Numele de gazdă REST Endpoint este doar numele gazdei, fără https://. 

1. Selectați **Sunt de acord** pentru a confirma **Confidențialitatea și conformitatea datelor**.

1. Selectați **Conectare** pentru a inițializa conexiunea la ActiveCampaign.

1. Selectați **Adăugați-vă ca utilizator de export** și furnizați acreditările dvs. Customer Insights.

1. Selectați **Salvare** pentru a finaliza conexiunea.

## <a name="configure-an-export"></a>Configurați un export

Puteți configura un export dacă aveți acces la o conexiune de acest tip. Pentru mai multe informații, consultați [Permisiuni necesare pentru configurarea unui export](export-destinations.md#set-up-a-new-export).

1. Faceți salt la **Date** > **Exporturi**.

1. Pentru a crea un nou export, selectați **Adăugare destinație**.

1. În câmpul **Conexiune pentru export**, alegeți o conexiune din secțiunea ActiveCampaign. Dacă nu vedeți numele acestei secțiuni, nu sunt disponibile conexiuni de acest tip.

1. Introduceți [**ID listă ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

1. În secțiunea **Potrivirea datelor**, în câmpul **E-mail**, selectați câmpul ce reprezintă adresa de e-mail a unui client. Este nevoie să exportați segmente la ActiveCampaign. Opțional, puteți exporta Prenume, Nume de familie, și Telefon pentru a crea e-mailuri mai particularizate. Selectați Adăugare atribut pentru a mapa aceste câmpuri.

1. Selectați **Salvare**.

Salvarea unui export nu se execută imediat.

Exportul rulează cu fiecare [reîmprospătare programată](system.md#schedule-tab). Puteți de asemenea [exporta date la cerere](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidențialitatea și conformitatea datelor

Când activați Dynamics 365 Customer Insights pentru a transmite date către ActiveCampaign, permiteți transfer de date în afara limitelor de conformitate pentru Dynamics 365 Customer Insights, inclusiv date potențial sensibile, cum ar fi date cu caracter personal. Microsoft va transfera astfel de date la instrucțiunile dvs., dar sunteți responsabil pentru a vă asigura că ActiveCampaign îndeplinește orice obligații de confidențialitate sau securitate pe care le aveți. Pentru informații suplimentare, consultați [Angajamentul de respectare a confidențialității Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administratorul Dynamics 365 Customer Insights poate să elimine această destinație de export oricând, pentru a întrerupe utilizarea acestei funcționalități.
