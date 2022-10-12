---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611133"
---
- **Performanța modelului de antrenament** : Notele A, B sau C indică performanța predicție și vă pot ajuta să luați decizia de a utiliza rezultatele stocate în entitatea de ieșire.

  Nivelurile sunt stabilite pe baza următoarelor reguli:
  - **A** atunci când modelul a prezis cu acuratețe cel puțin 50% din predicțiile totale și când procentul de predicții exacte pentru clienții care s-au retras este mai mare decât rata inițială cu cel puțin 10%.
  - **B** atunci când modelul a prezis cu acuratețe cel puțin 50% din predicțiile totale și când procentul de predicții exacte pentru clienții care s-au retras este cu până la 10% mai mare decât rata inițială.
  - **C** atunci când modelul a prezis cu exactitate mai puțin de 50% din previziunile totale sau când procentul de predicții precise pentru clienții care au reușit este mai mic decât valoarea de referință.
  - **De bază** ia intrarea predicție pentru fereastra de timp pentru model (de exemplu, un an) și creează diferite fracțiuni de timp, împărțind-o la 2 până când ajunge la o lună sau mai puțin. Utilizează aceste fracții pentru a crea o regulă de afaceri pentru clienții care nu au achiziționat în acest interval de timp. Acești clienți sunt considerați ca fiind retrași. Ca model de referință este aleasă regula de afaceri bazată pe timp, cu cea mai mare capacitate de a prezice cine este probabil să se retragă.

- **Probabilitatea de retragere (număr de clienți)**: Grupuri de clienți în funcție de riscul de retragere prognozat. Opțional, [creați segmente de clienți](../prediction-based-segment.md) cu risc ridicat de pierdere. Astfel de segmente vă ajută să înțelegeți unde ar trebui să fie delimitarea dvs. pentru membrii segmentului.

- **Cei mai influenți factori**: Există mulți factori care sunt luați în considerare atunci când vă creați predicția. Fiecare dintre factori are importanța sa calculată pentru predicțiile agregate pe care le creează un model. Folosiți acești factori pentru a vă valida rezultatele predicție. Sau utilizați aceste informații mai târziu pentru a [creați segmente](../prediction-based-segment.md) care ar putea contribui la influențarea riscului de abandon pentru clienți.