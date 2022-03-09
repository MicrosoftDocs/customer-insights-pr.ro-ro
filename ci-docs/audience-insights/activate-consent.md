---
title: Activați regulile de consimțământ pentru segmente
description: Urmați acești pași pentru a conecta datele privind consimțământul și pentru a activa verificările consimțământului în statisticile privind publicul. Un administrator poate dezactiva și verificările consimțământului.
ms.date: 11/12/2021
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4b55c82229b1a6189c0dd67d145386344286df8a
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227508"
---
# <a name="activate-consent-rules"></a>Activați regulile de consimțământ

The [Centrul de consimțământ (previzualizare)](../consent-management/overview.md) vă ajută să armonizați datele consimțământului din diverse surse. Folosiți unificatul *Consimţământ* entitate să aplice verificări implicite de consimțământ. După importarea datelor de consimțământ în Centrul de consimțământ și configurarea regulilor pentru date, *Consimţământ* entitatea este sincronizată automat cu informațiile despre public.

## <a name="enable-consent-checks"></a>Activare verificare de consimțământ

Cu datele de consimțământ importate în Centrul de consimțământ (previzualizare) și cu regulile configurate, puteți activa verificările consimțământului. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Fila Consimțământ în setările statisticilor privind publicul cu date de consimțământ activate.":::

1. În Detalii despre audiență, accesați **Administrator** > **Sistem**.

1. Selectează **Consimțământ (previzualizare)** fila.

1. În **Activați verificările consimțământului** secțiunea, setați comutatorul la **Pe** pentru toate zonele pe care doriți să le activați.

1. Selectează **Permiteți anularea regulilor implicite de consimțământ** casetă de selectare pentru a elimina verificările implicite de consimțământ aplicate pe un anumit segment. 

1. În meniul drop-down, selectați unde doriți să permiteți înlocuiri.     

1. În **Conectați consimțământul la profilurile clienților** secțiunea, alegeți atributul care este utilizat ca identificator pentru a lega datele de consimțământ la datele clienților. Probabil va fi un număr de telefon sau o adresă de e-mail. 

1. Selectați **salva** pentru a vă aplica setările.

## <a name="disable-consent-checks"></a>Dezactivați verificările de consimțământ

Pentru a opri utilizarea datelor de consimțământ în statisticile privind publicul, un administrator trebuie să actualizeze setările sistemului în consecință.

1. În Detalii despre audiență, accesați **Administrator** > **Sistem**.

1. Selectează **Consimțământ (previzualizare)** fila.

1. În **Activați verificările consimțământului** secțiunea, setați comutatorul la **Off**.

> [!TIP]
> Pentru a opri utilizarea capacității de gestionare a consimțământului, consultați [Setări de sistem în Centrul de consimțământ (previzualizare)](../consent-management/system-settings.md).
