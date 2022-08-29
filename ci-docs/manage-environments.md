---
title: Gestionați mediile
description: Aflați cum să gestionați mediile existente Customer Insights ca administrator.”
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 8b4a88bdb75c6e638a76c39d18647681ad4556d7
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304304"
---
# <a name="manage-environments"></a>Gestionați mediile

Administratorii [crea](create-environment.md) și gestionați mediile. Ele pot modifica unele setări în mediile existente. Afacere, tip, regiune, opțiune de stocare și Dataverse setările sunt remediate după crearea mediului. Dacă doriți să modificați aceste setări, [reseta mediul](#reset-an-existing-environment-preview) sau [crea un mediu nou](create-environment.md).

## <a name="edit-an-existing-environment"></a>Editați un mediu existent

Editați detaliile unui mediu existent, cum ar fi numele sau setarea mediului implicit.

1. Selectați selectorul **Mediu** în antetul aplicației.

1. Selectați pictograma **Editare**.

   :::image type="content" source="media/edit-environment.png" alt-text="Pictogramă pentru a edita setările de mediu.":::

1. În **Editați mediul** panoul, actualizați setările de mediu.

1. Selectați **Revedeți și terminați**, apoi **Actualizați** pentru a aplica modificările.

## <a name="change-the-owner-of-an-environment"></a>Schimbați proprietarul unui mediu

Mai mulți utilizatori pot avea permisiuni de administrator, dar un singur utilizator este proprietarul unui mediu. În mod implicit, administratorul este cel care creează un mediu inițial. În calitate de administrator al unui mediu, puteți atribui dreptul de proprietate unui alt utilizator cu permisiuni de administrator.

1. Selectați selectorul **Mediu** în antetul aplicației.

1. Selectați pictograma **Editare**.

1. În **Editați mediul** panou, du-te la **Informatii de baza** Etapa.

1. În **Schimbați proprietarul mediului** câmp, alegeți noul proprietar al mediului.  

1. Selectați **Revedeți și terminați**, apoi **Actualizați** pentru a aplica modificările.

## <a name="claim-ownership-of-an-environment"></a>Revendicați dreptul de proprietate asupra unui mediu

Dacă contul de utilizator al proprietarului este șters sau suspendat, mediul nu va avea un proprietar. Orice utilizator administrator poate revendica dreptul de proprietate și poate deveni noul proprietar. Administratorul proprietarului poate continua să dețină mediul sau [schimba proprietatea la alt administrator](#change-the-owner-of-an-environment).

Pentru a revendica proprietatea, selectați **Preia proprietatea** butonul care apare în partea de sus a fiecărei pagini din Customer Insights când proprietarul inițial a părăsit organizația.

## <a name="reset-an-existing-environment-preview"></a>Resetați un mediu existent (previzualizare)

În calitate de proprietar al unui mediu, resetați un mediu la o stare goală dacă doriți să ștergeți toate configurațiile și să eliminați datele ingerate.

1. Selectați selectorul **Mediu** în antetul aplicației.

1. Selectați mediul pe care doriți să îl resetați și selectați elipsa verticală (&vellip;).

1. Alege **Resetare (previzualizare)**.

   :::image type="content" source="media/reset-environment.png" alt-text="Control pentru a reseta un mediu.":::

1. Alegeți dacă doriți să resetați întregul mediu, totul cu excepția surselor de date sau orice este configurat în partea de sus a profilului unificat al clientului.

1. Pentru a confirma, introduceți numele mediului și selectați **Resetați**.

## <a name="delete-an-existing-environment"></a>Ștergerea unui mediu existent

În calitate de proprietar al unui mediu, îl puteți șterge.

> [!IMPORTANT]
> Ștergerea unui mediu nu elimină conexiunea la a Dataverse mediu inconjurator. Dacă intenționați să vă conectați la fel Dataverse mediu într-un nou mediu Customer Insights în viitor, trebuie [elimina acea conexiune la Dataverse mediu inconjurator](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

1. Selectați selectorul **Mediu** în antetul aplicației.

1. Selectați mediul pe care doriți să îl ștergeți și selectați elipsa verticală (&vellip;). 

1. Alege **Șterge**.

   :::image type="content" source="media/delete-environment.png" alt-text="Control pentru a șterge mediul.":::

1. Pentru a confirma ștergerea, introduceți numele mediului și selectați **Ștergere**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
