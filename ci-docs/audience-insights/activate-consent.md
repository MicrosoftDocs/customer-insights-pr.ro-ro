---
title: Activați regulile de consimțământ pentru segmente
description: Urmați acești pași pentru a conecta datele privind consimțământul și pentru a activa verificările consimțământului în statisticile privind publicul. Un administrator poate dezactiva și verificările consimțământului.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 45899738d39bd5caa433e123f9fe59020e831998
ms.sourcegitcommit: 79b09498d1328e5551fb8684c44af1fb149f9881
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790791"
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

1. Selectați **Salvați** pentru a vă aplica setările.

## <a name="disable-consent-checks"></a>Dezactivați verificările de consimțământ

Pentru a opri utilizarea datelor de consimțământ în statisticile privind publicul, un administrator trebuie să actualizeze setările sistemului în consecință.

1. În Detalii despre audiență, accesați **Administrator** > **Sistem**.

1. Selectează **Consimțământ (previzualizare)** fila.

1. În **Activați verificările consimțământului** secțiunea, setați comutatorul la **Off**.
