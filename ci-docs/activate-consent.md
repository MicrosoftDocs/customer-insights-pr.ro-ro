---
title: Activați regulile de consimțământ pentru segmente
description: Urmați acești pași pentru a conecta datele de consimțământ și pentru a activa verificările de consimțământ în Dynamics 365 Customer Insights. Un administrator poate dezactiva și verificările consimțământului.
ms.date: 11/12/2021
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bfa03f4b7b56b300a74ebd04721cd64b893879f1
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643118"
---
# <a name="activate-consent-rules"></a>Activați regulile de consimțământ

The [Centrul de consimțământ (previzualizare)](consent-management/overview.md) vă ajută să armonizați datele consimțământului din diverse surse. Folosiți unificatul *Consimţământ* entitate să aplice verificări implicite de consimțământ. După importarea datelor de consimțământ în Centrul de consimțământ și configurarea regulilor pentru date, *Consimţământ* entitatea este sincronizată automat cu Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Activare verificare de consimțământ

Cu datele de consimțământ importate în Centrul de consimțământ (previzualizare) și cu regulile configurate, puteți activa verificările consimțământului. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Fila Consimțământ în setările Customer Insights cu date de consimțământ activate.":::

1. În Customer Insights, accesați **Administrator** > **Sistem**.

1. Selectează **Consimțământ (previzualizare)** fila.

1. În **Activați verificările consimțământului** secțiunea, setați comutatorul la **Pe** pentru toate zonele pe care doriți să le activați.

1. Selectează **Permiteți anularea regulilor implicite de consimțământ** casetă de selectare pentru a elimina verificările implicite de consimțământ aplicate pe un anumit segment. 

1. În meniul drop-down, selectați unde doriți să permiteți înlocuiri.     

1. În **Conectați consimțământul la profilurile clienților** secțiunea, alegeți atributul care este utilizat ca identificator pentru a lega datele de consimțământ la datele clienților. Probabil va fi un număr de telefon sau o adresă de e-mail. 

1. Selectați **salva** pentru a vă aplica setările.

## <a name="disable-consent-checks"></a>Dezactivați verificările de consimțământ

Pentru a opri utilizarea datelor de consimțământ în Customer Insights, un administrator trebuie să actualizeze setările sistemului în consecință.

1. În Customer Insights, accesați **Administrator** > **Sistem**.

1. Selectează **Consimțământ (previzualizare)** fila.

1. În **Activați verificările consimțământului** secțiunea, setați comutatorul la **Off**.

> [!TIP]
> Pentru a opri utilizarea capacității de gestionare a consimțământului, consultați [Setări de sistem în Centrul de consimțământ (previzualizare)](consent-management/system-settings.md).
