---
title: Conectați-vă la entități din Common Data Service data lake gestionat
description: Importați date dintr-un Common Data Service Data Lake gestionat.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596974"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Conectați-vă la date într-un data lake gestionat Common Data Service

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Acest articol oferă informații despre modul în care clienții Dynamics 365 existenți se pot conecta rapid la entitățile lor analitice din Common Data Service Lake gestionat. Trebuie să fiți administrator pe organizația Common Data Service pentru a continua și vedea lista entităților disponibile în datele Lake gestionate.

## <a name="important-considerations"></a>Considerații importante

Date stocate în servicii online cum ar fi Azure Data Lake Storage pot fi stocate într-o locație diferită de locul în care sunt datele prelucrate sau stocate Dynamics 365 Customer Insights. Prin importul sau conectarea la datele stocate în servicii online, sunteți de acord că datele pot fi transferate și stocate cu Dynamics 365 Customer Insights. [Aflați mai multe la Centrul de autorizare Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Conectați-vă la un lake gestionat de Common Data Service

1. În Detalii despre audiență, accesați **Date** > **Surse de date**.

2. Selectați **Adăugați sursa de date**.

3. Selectați **Conectați-vă la Common Data Service** și selectați **Următorul**.

4. Introduceți un **Nume** pentru sursa de date și selectați **Următorul**. Numire recomandări: 
   - Începeți cu o literă.
   - Folosiți numai litere și cifre. Nu sunt permise caracterele speciale și spațiile.
   - Folosiți între 3 și 64 de caractere.

5. Furnizați **Adresa serverului** pentru organizația dvs. Common Data Service și selectați **Autentificare**.

   > [!div class="mx-imgBorder"]
   > ![Caseta de dialog pentru introducerea adresei serverului Common Data Service](media/enter-CDS-org-details.png)

6. Selectați entitățile pe care doriți să le ingerați din lista disponibilă.    

   > [!NOTE]
   > Dacă unele entități sunt deja selectate, acestea ar putea fi utilizate de alte aplicații Dynamics 365 (cum ar fi Dynamics 365 Sales Insights sau Customer Service Insights). Nu aveți posibilitatea să modificați selecția. Aceste entități vor fi disponibile după crearea sursei de date.

   > [!div class="mx-imgBorder"]
   > ![Caseta de dialog care arată o listă de entități din organizația Common Data Service](media/select-analytical-entities.png)

7. Salvați selecția dvs. pentru a începe sincronizarea entităților selectate cu lake-ul gestionat de Common Data Service. Veți găsi conexiunea recent adăugată pe pagina **Surse de date**. Acesta va fi pus în coadă pentru actualizare și va arăta numărul entităților ca fiind 0 până când toate entitățile sunt sincronizate.

Numai o sursă de date dintr-un mediu poate folosi același Common Data Service data lake gestionat simultan.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Editați o sursă de date lake gestionată de Common Data Service

Editați selecția entității numai după crearea sursei de date. De exemplu, dacă s-au adăugat entități suplimentare la Common Data Service și vreți să le importați și pe acestea.    
Pentru a vă conecta la un Common Data Service diferit, [creați o sursă de date noi](#connect-to-a-common-data-service-managed-lake).

1. În Detalii despre audiență, accesați **Date** > **Surse de date**.

2. Lângă sursa de date pe care doriți să o actualizați, selectați elipsa.

3. Selectați opțiunea **Editare** din listă.

4. Selectați entități suplimentare din lista de entități disponibile și selectați **Salvați**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]