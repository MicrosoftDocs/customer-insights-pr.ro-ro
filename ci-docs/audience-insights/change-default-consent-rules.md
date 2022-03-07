---
title: Gestionați regulile implicite de consimțământ pe segmente
description: Cu capacitatea de gestionare a consimțământului, puteți dezactiva sau modifica regulile implicite de consimțământ dacă sunt activate suprascrierile.
ms.date: 12/01/2021
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4eae4da67fd4c6e70800f495ba30366d4fc9a0dd
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228954"
---
# <a name="disable-or-change-default-consent-rules"></a>Dezactivați sau modificați regulile implicite de consimțământ

Dacă organizațiile dvs. utilizează [capacitatea de gestionare a consimțământului](../consent-management/overview.md) combinate cu informații despre public, [administratorii pot aplica regulile de consimțământ](activate-consent.md) pentru segmente. 

Cu regulile de consimțământ impuse în zona de segment, fiecare segment informează despre starea verificării consimțământului și regulile. Dacă sunt permise înlocuiri, regulile implicite de consimțământ sunt dezactivate pentru anumite segmente. Fiecare creator al unui segment poate adăuga mai multe reguli de consimțământ pe lângă regulile implicite la un segment. 

## <a name="for-administrators"></a>Pentru administratori

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="Generator de segmente cu opțiuni pentru regulile de consimțământ.":::

**Pentru a dezactiva regulile implicite de consimțământ:**

1. În **Reguli de consimțământ** notificare, selectați **Vezi detalii**. 

1. Seteaza **Reguli implicite de consimțământ** comuta la **Oprit**.

**Pentru a adăuga mai multe reguli de consimțământ:**

1. În **Reguli de consimțământ** notificare, selectați **Vezi detalii**. 

1. Selectați **Adăugați reguli de consimțământ** și alegeți o regulă de consimțământ din **Selectați tipul de date de consimțământ** scapă jos.

1. Selectați **salva** pentru a aplica noua regulă pe segment.

## <a name="for-contributors"></a>Pentru colaboratori

Pentru a crea un segment fără reguli de consimțământ forțat, trebuie să lucrați cu administratorul pentru a le dezactiva pe segmentul dvs. Cu toate acestea, puteți adăuga propriile reguli de consimțământ la segmentele pe care le dețineți și pe care le gestionați.

Este un proces în trei etape: 
1. [Creați segmentul](segments.md) în perspectivele audienței și salvați-o. 

1. Distribuiți numele segmentului administratorului dvs. și cereți-i să o facă [activați înlocuirile pentru segmentul dvs](activate-consent.md). 

1. Deschideți segmentele din nou. În **Reguli de consimțământ** notificare, selectați **Vezi detalii** și adăugați regulile de consimțământ pe care doriți să le aplicați. Apoi, **salva** și **Alerga** segmentul dvs.



[!INCLUDE[footer-include](../includes/footer-banner.md)] 
