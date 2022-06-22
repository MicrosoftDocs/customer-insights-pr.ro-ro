---
title: Conectarea la tabele în Microsoft Dataverse
description: Importați date dintr-un Microsoft Dataverse Data Lake gestionat.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: c470956b0453ac2558ed85acdeebba120a0ca55d
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011718"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Conectați-vă la date într-un data lake gestionat Microsoft Dataverse

Microsoft Dataverse utilizatorii se pot conecta rapid la entități analitice într-un Microsoft Dataverse lac administrat.

> [!NOTE]
> Trebuie să fii administrator pe Dataverse organizație să continue și să vizualizeze lista entităților disponibile în lacul administrat.

## <a name="important-considerations"></a>Considerații importante

1. Date stocate în servicii online cum ar fi Azure Data Lake Storage pot fi stocate într-o locație diferită de locul în care sunt datele prelucrate sau stocate Dynamics 365 Customer Insights.Prin importul sau conectarea la date stocate în serviciile online, sunteți de acord că datele pot fi transferate și stocate cu Dynamics 365 Customer Insights . [Aflați mai multe la Microsoft Trust Center](https://www.microsoft.com/trust-center).
2. Numai Dataverse entitati cu [urmărirea modificărilor](/power-platform/admin/enable-change-tracking-control-data-synchronization) activate sunt vizibile. Aceste entități pot fi exportate în Dataverse -lacul de date gestionat și utilizat în Customer Insights. Înafara cutiei Dataverse tabelele au urmărirea modificărilor activată în mod implicit. Trebuie să activați urmărirea modificărilor pentru tabelele personalizate. Pentru a verifica dacă a Dataverse tabelul este activat pentru urmărirea modificărilor, accesați [Power Apps](https://make.powerapps.com) > **Date** > **Mese**. Găsiți tabelul care vă interesează și selectați-l. Mergi la **Setări** > **Opțiuni avansate** și revizuiți **Urmareste schimbarile** setare.

## <a name="connect-to-a-dataverse-managed-lake"></a>Conectați-vă la un lake gestionat de Dataverse

1. Accesați **Date** > **Surse de date**.

1. Selectați **Adăugați sursa de date**.

1. Selectaţi **Microsoft Dataverse**.

1. Introduceți a **Nume** pentru sursă de date și opțional **Descriere**.

1. Furnizați **Adresa serverului** pentru organizația Dataverse și selectați **Conectare**.

1. Selectați tabelele pe care doriți să le ingerați ca entități în Customer Insights din lista disponibilă.

   > [!NOTE]
   > Dacă unele tabele sunt deja selectate, acestea ar putea fi utilizate de alte aplicații Dynamics 365 (cum ar fi Dynamics 365 Sales Insights sau Customer Service Insights). Nu aveți posibilitatea să modificați selecția. Aceste tabele vor fi disponibile ca entități după crearea sursei de date.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Caseta de dialog care afișează o listă de entități din mediul Dataverse.":::

1. Salvați selecția pentru a începe sincronizarea tabelelor selectate din Dataverse. Veți găsi conexiunea recent adăugată pe pagina **Surse de date**. Acesta va fi pus în coadă pentru reîmprospătare și va afișa numărul de entități ca 0 până când toate tabelele selectate sunt sincronizate.

Numai o sursă de date dintr-un mediu poate folosi același Dataverse data lake gestionat simultan.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Editați o sursă de date lake gestionată de Dataverse

Editați selecția entității numai după crearea sursei de date. De exemplu, dacă s-au adăugat entități suplimentare la Dataverse și vreți să le importați și pe acestea.
Pentru a vă conecta la alt data lake Dataverse, [creați o nouă sursă de date](#connect-to-a-dataverse-managed-lake).

1. Accesați **Date** > **Surse de date**.

1. Lângă sursă de date pe care doriți să o actualizați, selectați **Editați | ×**.

1. Selectați entități suplimentare din lista de entități disponibile și selectați **Salvați**.