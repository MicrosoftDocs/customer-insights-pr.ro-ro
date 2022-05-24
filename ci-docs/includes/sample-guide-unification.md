---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755559"
---
După ingerarea datelor, începeți procesul de unificare a datelor pentru a crea un profil unificat de client. Pentru informații suplimentare, consultați [Unificare date](../data-unification.md).

### <a name="select-source-fields"></a>Selectați câmpurile sursă

1. După ingerarea datelor, mapați contactele de la datele de comerț electronic și de loialitate la tipuri de date obișnuite. Mergi la **Date** > **Unifica**.

1. Selectați entitățile care reprezintă profilul clientului - **eCommerceContacts** și **loyCustomers**.

   ![unificați sursele de date privind comerțul electronic și loialitatea.](../media/unify-ecommerce-loyalty.png)

1. Selectați **ContactId** ca cheie primară pentru **eCommerceContacts** și **LoyaltyID** ca cheie primară pentru **loyCustomers**.

1. Selectați **Următorul**. Omite înregistrările duplicate și selectează **Următorul**.

### <a name="match-conditions"></a>Condiții de meci

1. Alege **eCommerceContact: eCommerce** ca entitate principală și includ toate înregistrările.

1. Alege **loyCustomers: LoyaltyScheme** și include toate înregistrările.

1. Adăugați o regulă:
   - Selectați **Numele complet** atât pentru eCommerceContacts, cât și pentru loyCustomers.
   - Selectați **Tip (Telefon, Nume, Adresă, ...)** pentru **Normaliza**.
   - Setați **Nivel de precizie**: **De bază** și **Valoare**: **Mare**.
   - introduce **Nume complet, e-mail** pentru nume.

1. Adăugați o a doua condiție pentru adresa de e-mail:
   - Selectați **E-mail** atât pentru eCommerceContacts, cât și pentru loyCustomers.
   - Lăsați Normalizarea necompletată.
   - Setați **Nivel de precizie**: **De bază** și **Valoare**: **Mare**.

   ![Unificați regula de potrivire pentru nume și e-mail.](../media/unify-match-rule.png)

1. Selectați **Terminat**.

1. Selectați **Următorul**.

### <a name="unify-fields"></a>Unificați câmpurile

1. Redenumiți **ContactId** pentru **Clienti loiali** entitate la **ContactIdLOYALTY** pentru a o diferenția de celelalte ID-uri ingerate.

1. Selectați **Următorul** pentru a revizui și apoi selectați **Creați profiluri de clienți**.
