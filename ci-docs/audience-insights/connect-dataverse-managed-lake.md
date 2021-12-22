---
title: Conectarea la tabele în Microsoft Dataverse
description: Importați date dintr-un Microsoft Dataverse Data Lake gestionat.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: fecf3e33b5bc1eec17006fc196004be902c03b40
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900166"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Conectați-vă la date într-un data lake gestionat Microsoft Dataverse

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Acest articol oferă informații despre cum Dataverse utilizatorii se pot conecta rapid la entități analitice într-un Microsoft Dataverse lac administrat. 

> [!NOTE]
> Trebuie să fii administrator pe Dataverse organizație să continue și să vizualizeze lista entităților disponibile în lacul administrat.

## <a name="important-considerations"></a>Considerații importante

Date stocate în servicii online cum ar fi Azure Data Lake Storage pot fi stocate într-o locație diferită de locul în care sunt datele prelucrate sau stocate Dynamics 365 Customer Insights.Prin importul sau conectarea la datele stocate în serviciile online, sunteți de acord că datele pot fi transferate și stocate cu Dynamics 365 Customer Insights . [Aflați mai multe la Microsoft Trust Center](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-dataverse-managed-lake"></a>Conectați-vă la un lake gestionat de Dataverse

1. În Detalii despre audiență, accesați **Date** > **Surse de date**.

2. Selectați **Adăugați sursa de date**.

3. Selectați **Microsoft Dataverse** și selectați **Următorul**.

4. Introduceți un **Nume** pentru sursa de date și selectați **Următorul**. 

5. Furnizați **Adresa serverului** pentru organizația Dataverse și selectați **Conectare**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Ecran în pasul de ingestie de date în care un utilizator poate introduce adresa URL a mediului Dataverse.":::

6. Selectați tabelele pe care doriți să le ingerați ca entități pentru statistici despre public din lista disponibilă.    

   > [!NOTE]
   > Dacă unele tabele sunt deja selectate, acestea ar putea fi utilizate de alte aplicații Dynamics 365 (cum ar fi Dynamics 365 Sales Insights sau Customer Service Insights). Nu aveți posibilitatea să modificați selecția. Aceste tabele vor fi disponibile ca entități după crearea sursei de date.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Caseta de dialog care afișează o listă de entități din mediul Dataverse.":::

7. Salvați selecția pentru a începe sincronizarea tabelelor selectate din Dataverse. Veți găsi conexiunea recent adăugată pe pagina **Surse de date**. Acesta va fi pus în coadă pentru reîmprospătare și va afișa numărul de entități ca 0 până când toate tabelele selectate sunt sincronizate.

Numai o sursă de date dintr-un mediu poate folosi același Dataverse data lake gestionat simultan.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Editați o sursă de date lake gestionată de Dataverse

Editați selecția entității numai după crearea sursei de date. De exemplu, dacă s-au adăugat entități suplimentare la Dataverse și vreți să le importați și pe acestea.    
Pentru a vă conecta la alt data lake Dataverse, [creați o nouă sursă de date](#connect-to-a-dataverse-managed-lake).

1. În Detalii despre audiență, accesați **Date** > **Surse de date**.

2. Lângă sursa de date pe care doriți să o actualizați, selectați elipsa.

3. Selectați opțiunea **Editare** din listă.

4. Selectați entități suplimentare din lista de entități disponibile și selectați **Salvați**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
