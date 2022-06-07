---
title: Folosește-ți pe al tău Azure Data Lake Storage cont Gen2
author: mukeshpo
description: Aflați despre cerințele pentru a vă folosi propriul dvs Azure Data Lake Storage cont pentru a stoca datele Customer Insights.
ms.author: mukeshpo
ms.date: 05/30/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 9fcd7645e34bf310ac3a1b98a0dd9a60598b19dc
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833952"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Folosește-ți pe al tău Azure Data Lake Storage cont Gen2

Dynamics 365 Customer Insights vă oferă opțiunea de a stoca toate datele dvs [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction).

Prin salvarea datelor în Data Lake Storage, sunteți de acord că datele vor fi transferate și stocate în locația geografică corespunzătoare pentru acel cont de stocare Azure. Pentru mai multe informații, vezi [Centrul de încredere Microsoft](https://www.microsoft.com/trust-center).

Administratorii din Customer Insights pot [creează medii](create-environment.md) și [specificați opțiunea de stocare a datelor](create-environment.md#step-2-configure-data-storage) în procesul.

## <a name="prerequisites-to-use-your-storage-account"></a>Cerințe preliminare pentru a vă folosi contul de stocare

- Azure Data Lake Storage conturile trebuie să fie în aceeași regiune Azure pe care ați selectat-o la crearea mediului Customer Insights. Puteți verifica regiunea din mediul Customer Insights sub **Admin** > **Sistem** > **Despre**.
- Data Lake Storage trebuie să fie Gen2 și să aibă [spațiu de nume ierarhic activat](/azure/storage/blobs/create-data-lake-storage-account). Conturile de stocare Gen1 nu sunt acceptate.
- Un container numit`customerinsights` trebuie să existe în contul de stocare. Trebuie să-l creați înainte de a vă folosi propriul Data Lake Storage în Customer Insights. Administratorul care configurează mediul Customer Insights are nevoie de rolul Storage Blob Data Contributor sau Storage Blob Data Owner pe contul de stocare sau`customerinsights` recipient. Pentru mai multe informații despre atribuirea permisiunii într-un cont de stocare, consultați [Creați un cont de stocare](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Conectați Customer Insights cu contul dvs. de stocare

Când creați un mediu nou, asigurați-vă că există contul Data Lake Storage și că sunt îndeplinite toate cerințele preliminare.

1. În **Stocare a datelor** pas în timpul creării mediului, set **Salvați datele de ieșire** la **Azure Data Lake Storage Gen2**.
1. Alege cum să **Conectați-vă spațiul de stocare**. Puteți alege între o opțiune bazată pe resurse și o opțiune bazată pe abonament pentru autentificare. Pentru mai multe informații, vezi [Conectați-vă la un Azure Data Lake Storage cont utilizând un Azure Service Principal](connect-service-principal.md).
   - Pentru **Abonament Azure**, alege **Abonament**, **de resurse**, și **Cont de stocare** care contine`customerinsights` recipient.
   - Pentru **Cheia de cont**, furnizați **Nume de cont** si **Cheia de cont** pentru contul Data Lake Storage. Folosirea acestei metode de autentificare implică faptul că sunteți informat dacă organizația dvs. rotește cheile. Trebuie [actualizați configurația mediului](manage-environments.md#edit-an-existing-environment) cu noua cheie când este rotită.

Când procesele de sistem, cum ar fi ingerarea datelor, sunt finalizate, sistemul creează folderele corespunzătoare în contul de stocare. Fișierele de date și fișierele *model.json* sunt create și adăugate în dosare pe baza numelui procesului.

Dacă creați mai multe medii ale Customer Insights și alegeți să salvați entitățile de ieșire din acele medii în contul dvs. de stocare, Customer Insights creează dosare separate pentru fiecare mediu cu `ci_environmentID` în recipient.
