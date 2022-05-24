---
title: Activați regulile de consimțământ pentru segmente
description: Urmați acești pași pentru a conecta datele de consimțământ și pentru a activa verificările de consimțământ în Dynamics 365 Customer Insights. Un administrator poate dezactiva și verificările consimțământului.
ms.date: 04/27/2022
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f82e3a4031fee8bcaa88575cbd68b37385a7fffb
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755185"
---
# <a name="activate-consent-rules"></a>Activați regulile de consimțământ

The [Centrul de consimțământ (previzualizare)](consent-management/overview.md) vă ajută să armonizați datele consimțământului din diverse surse. Folosește unificatul *Consimţământ* entitate să aplice verificări implicite de consimțământ. După importarea datelor de consimțământ și configurarea regulilor hărții, *Consimţământ* entitatea este sincronizată automat cu Dynamics 365 Customer Insights.

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

1. În **Activați verificările consimțământului** secțiunea, setați comutatorul la **Oprit**.

> [!TIP]
> Pentru a opri utilizarea capacității de gestionare a consimțământului, consultați [Setări de sistem în Centrul de consimțământ (previzualizare)](consent-management/system-settings.md).
