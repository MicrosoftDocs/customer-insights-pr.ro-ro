---
title: Aduceți propriul seif cu chei Azure pentru a gestiona secretele
description: Aflați cum să configurați Customer Insights pentru a utiliza propriul seif de chei Azure.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: d4f2d5ebc828053c40e22065f4915c4d0f84153f
ms.sourcegitcommit: 6ec4626a185892dfb781d3c7af4384f9c13f3723
ms.translationtype: MT
ms.contentlocale: ro-RO
ms.lasthandoff: 05/17/2022
ms.locfileid: "8763594"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Aduceți-vă propriul seif de chei Azure (versiune preliminară)

Conectarea unui dedicat [Seif pentru chei Azure](/azure/key-vault/general/basic-concepts) într-un mediu Customer Insights ajută organizațiile să îndeplinească cerințele de conformitate.
Seiful de chei dedicat poate fi utilizat pentru a etapiza și a folosi secrete în limita de conformitate a unei organizații. Customer Insights poate folosi secretele din Azure Key Vault pentru [stabiliți conexiuni](connections.md) către sisteme terțe.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Conectați seiful de chei la mediul Customer Insights

### <a name="prerequisites"></a>Cerințe preliminare

Pentru a configura seiful de chei în Customer Insights, trebuie îndeplinite următoarele cerințe preliminare:

- Aveți un abonament activ Azure.

- Ai un [Administrator](permissions.md#admin) rol în Customer Insights. Află mai multe despre [permisiunile utilizatorului în Customer Insights](permissions.md#assign-roles-and-permissions).

- Aveți roluri [Colaborator](/azure/role-based-access-control/built-in-roles#contributor) și [Administrator de acces utilizator](/azure/role-based-access-control/built-in-roles#user-access-administrator) pe seiful de chei sau grupul de resurse căruia îi aparține seiful de chei. Pentru mai multe informații, accesați [Adăugați sau eliminați atribuțiile de rol Azure utilizând portalul Azure](/azure/role-based-access-control/role-assignments-portal). Dacă nu aveți rolul de administrator al accesului utilizatorului pe seiful cheii, trebuie să configurați permisiunile de control al accesului bazate pe roluri pentru principalul serviciului Azure pentru Dynamics 365 Customer Insights separat. Urmați pașii pentru a [utiliza un director de serviciu Azure](connect-service-principal.md) pentru seiful de chei care ar trebui să fie legat.

- Seiful cheii trebuie să aibă firewall Key Vault **dezactivat**.

- Seiful cheilor este în același [Locație Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) ca mediu Customer Insights. Regiunea mediului în Customer Insights este listată sub **Admin** > **Sistem** > **Despre** > **Regiune**.

### <a name="link-a-key-vault-to-the-environment"></a>Conectați un seif cheie la mediu

1. Mergi la **Admin** > **Securitate**, apoi selectați **Seif de chei** fila.
1. Pe dala **Cheie seif**, selectați **Configurare**.
1. Alegeți un **Abonament**.
1. Alegeți un seif cu chei din lista derulantă **Cheie seif**. Dacă se afișează prea multe seifuri de chei, selectați un grup de resurse pentru a limita rezultatele căutării.
1. Acceptați afirmația **Confidențialitatea și respectarea datelor**.
1. Selectați **Salvare**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Pași pentru a configura un seif de chei conectat în Customer Insights.":::

Dala **Key Vault** arată acum numele seifului cheii legate, grupul de resurse și abonamentul. Este gata de utilizare în configurarea conexiunii.
Pentru detalii despre permisiunile din seiful de chei care sunt acordate Customer Insights, accesați [Permisiuni acordate pentru seiful de chei](#permissions-granted-on-the-key-vault), mai târziu în acest articol.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Utilizați seiful cheii în configurarea conexiunii

Când [configurarea conexiunilor](connections.md) la sistemele terțe, secretele din Key Vault conectat pot fi folosite pentru a configura conexiunile.

1. Salt la **Administrator** > **Conexiuni**.
1. Selectați **Adăugați conexiune**.
1. Pentru tipurile de conexiuni acceptate, un comutator **Utilizați Key Vault** este disponibil dacă ați conectat un seif de chei.
1. În loc să introduceți secretul manual, puteți alege numele secret care indică valoarea secretă din seiful cheii.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Panou de conexiune cu o conexiune SFTP care utilizează un Key Vault secret.":::

## <a name="supported-connection-types"></a>Tipuri de conexiune acceptate

Sunt acceptate următoarele conexiuni de [export](export-destinations.md):

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Permisiuni acordate pentru seiful de chei

Următoarele permisiuni sunt acordate pentru Customer Insights pe un seif de chei conectat, dacă oricare dintre ele [Politica de acces Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) sau [Controlul accesului Azure bazat pe roluri](/azure/key-vault/general/rbac-guide?tabs=azure-cli) este activat.

### <a name="key-vault-access-policy"></a>Politica de acces Key Vault

| Tipul        | Permisiuni          |
| ----------- | -------------------- |
| Tastă         | [Obțineți Chei](/rest/api/keyvault/keys/get-keys/get-keys), [Obțineți Cheia](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Secretă      | [Obțineți Secrete](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Obțineți Secret](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Certificat | [Obțineți certificate](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Obțineți certificat](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Valorile precedente sunt minime pentru listare și citire în timpul execuției.

### <a name="azure-role-based-access-control"></a>Controlul accesului bazat pe roluri Azure

Rolurile Key Vault Reader și Key Vault Secrets User vor fi adăugate pentru Customer Insights. Pentru detalii despre aceste roluri, accesați [Roluri încorporate Azure pentru operațiunile planului de date Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Recomandări

- Utilizați un seif de chei separat sau dedicat care conține numai secretele necesare pentru Customer Insights. Citiți mai multe despre de ce [se recomandă seifuri de chei separate](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Urmați [cele mai bune practici pentru utilizarea Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) pentru controlul opțiunilor de acces, backup, audit și recuperare.

## <a name="frequently-asked-questions"></a>Întrebări frecvente

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Poate Customer Insights să scrie secrete sau să suprascrie secrete în seiful de chei?

Nu. Doar permisiunile de citire și lista prezentate în [permisiuni acordate](#permissions-granted-on-the-key-vault) secțiunea de mai devreme în acest articol sunt acordate pentru Customer Insights. Sistemul nu poate adăuga, șterge sau suprascrie secrete în seiful cheii. Acesta este și motivul pentru care nu puteți introduce acreditări atunci când o conexiune utilizează Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Pot schimba o conexiune de la utilizarea secretelor Key Vault la autentificarea implicită?

Nu. Nu puteți reveni la o conexiune implicită după ce ați configurat-o utilizând un secret dintr-un seif de chei conectat. Creați o conexiune separată și ștergeți-o pe cea veche dacă nu mai aveți nevoie de ea.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Cum pot revoca accesul la un seif pentru chei pentru Customer Insights?

În funcție dacă [Politica de acces Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) sau [Controlul accesului bazat pe roluri Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) este activat, trebuie să eliminați permisiunile pentru directorul serviciului `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` cu denumirea `Dynamics 365 AI for Customer Insights`. Toate conexiunile care utilizează seiful cheii nu vor mai funcționa.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Un secret utilizat într-o conexiune a fost eliminat din seiful cheii. Ce pot să fac?

O notificare apare în Customer Insights când un secret configurat din seiful de chei nu mai este accesibil. Activați [soft-delete](/azure/key-vault/general/soft-delete-overview) pe seiful cheii pentru a restabili secretele dacă sunt eliminate accidental.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>O conexiune nu funcționează, dar secretul meu se află în seiful cheii. Care ar putea fi cauza?

O notificare apare în Customer Insights atunci când nu poate accesa seiful de chei. Cauza ar putea fi:

- Permisiunile pentru principalul serviciului Customer Insights au fost eliminate. Acestea trebuie restaurate manual.

- Este activat firewall-ul de pe seiful de chei. Firewall-ul trebuie să fie dezactivat pentru a face din nou seiful de chei accesibil pentru Customer Insights.
