---
title: Întrebări frecvente Versiune de încercare Dynamics 365 Customer Insights
description: Soluții la întrebări comune legate de configurarea și gestionarea versiunii de încercare Customer Insights. Aflați să rezolvați problemele specifice platformei și aplicației.
author: m-hartmann
ms.author: mhart
ms.date: 02/10/2022
ms.topic: get-started
ms.service: customer-insights
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: f63ed39ba8c710d0c0149e0944efaafe27e7b9bb
ms.sourcegitcommit: 5dd32dc2b18027cf2aa954356dded4bc6aab9801
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 02/12/2022
ms.locfileid: "8115983"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>Întrebări frecvente versiune de încercare Dynamics 365 Customer Insights

## <a name="sign-up"></a>Înregistrare

### <a name="what-are-the-system-requirements-for-the-trial"></a>Care sunt cerințele de sistem pentru versiunea de încercare?

Acceastă aplicație este un serviciu bazat pe cloud care nu necesită alt software special în afara unui browser de web actualizat, deși se aplică unele restricții. Pentru cea mai bună experiență de încercare, evitați accesarea site-ului de încercare în modul incognito și alegeți locația de încercare cea mai apropiată de dvs. [Aflați mai multe despre cerințele aplicației web.](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>Cum mă înscriu pentru încercare fără a Microsoft 365 chiriaş?

Puteți introduce o adresă de e-mail care nu este de serviciu și vă vom crea un cont și o entitate găzduită.

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>Mă pot înscrie pentru mai multe aplicații Dynamics 365, cum ar fi Sales, Marketing și Customer Service?

Da, puteți. Pentru a vizualiza toate încercările disponibile, [accesați pagina de hub a versiunii de încercare](https://dynamics.microsoft.com/dynamics-365-free-trial). Puteți utiliza același cont de e-mail pentru a vă înscrie pentru diferite versiuni de încercare. Cu toate acestea, nu este posibil să aveți mai multe aplicații pe același site al versiunii de încercare. Fiecare versiune de încercare va fi pe o organizație și adresă URL diferită. Datele versiunii de încercare nu vor fi partajate în toate aplicațiile.

## <a name="trial-app"></a>Versiune de încercare a aplicației

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>Nu am primit e-mailul cu detalii despre proces după înscriere, ce ar trebui să fac?

Când vă înscrieți pentru versiunea de încercare, veți primi un e-mail cu detaliile versiunii de încercare. Dacă nu vedeți e-mailul în inbox, verificați folderul de spam. Alternativ, utilizați următorii pași pentru a vă accesa aplicația:

1. Accesați site-ul versiunii de încercare și selectați **Încercați gratuit**.
1. Introduceți ID-ul de e-mail pe care l-ați utilizat pentru a vă înscrie la versiunea de încercare. Veți fi redirecționat către aplicația dvs. de încercare.

### <a name="how-do-i-add-more-users-to-a-trial"></a>Cum adaug mai mulți utilizatori la o versiune de încercare?

Pentru a adăuga utilizatori, accesați [Microsoft 365 centru de administrare](https://admin.microsoft.com) folosind contul de administrator de încercare. Urmați [instrucțiunile centrului de administrare](/microsoft-365/admin/add-users/add-users) pentru a adăuga utilizatori până la limita licenței versiunii de încercare. Dacă utilizatorul pe care îl adăugați are deja un Microsoft 365 cont, atribuiți-le un rol de securitate corespunzător în organizația de încercare. Pentru mai multe informații, vezi [Atribuiți un rol de securitate unui utilizator](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user).

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>Câți utilizatori pot adăuga în mediul meu de încercare?

Puteți adăuga un număr nelimitat de utilizatori în mediul de încercare.

### <a name="how-do-i-reset-the-trial-environment"></a>Cum resetez mediul de încercare?

Nu puteți reseta mediul de încercare. Cu toate acestea, puteți aștepta ca perioada de încercare să se încheie și apoi să vă înscrieți din nou pentru o nouă versiue de încercare.

## <a name="trial-expiration-and-extension"></a>Expirarea și prelungirea versiunii de încercare

### <a name="how-do-i-extend-the-trial"></a>Cum extind versiunea de încercare?

Puteți extinde procesul direct în aplicație. Puteți prelungi versiunea de încercare o dată.

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>Pot converti versiunea de încercare într-o licență plătită?

În general, vă recomandăm să începeți din nou cu propriile date atunci când faceți upgrade la versiunea plătită a Customer Insights. 

Opțional, dacă utilizați statistici privind publicul, puteți copia datele dintr-un mediu de încercare dacă achiziționați Customer Insights. Trebuie să fiți administratorul testului Customer Insights și administratorul global al dvs Microsoft 365 chiriașului sau administratorul Dynamics 365 din organizația dvs. pentru a migra setările dintr-un mediu de probă într-un mediu cu plată. 

După ce v-ați conectat pentru prima dată la instanța dvs. plătită de Customer Insights, vi se cere să creați un mediu nou. În acest proces, puteți alege să copiați configurația dintr-un mediu existent și să migrați majoritatea setărilor. Dacă aveți permisiunile menționate mai sus, mediul de încercare se va afișa în această listă. Pentru mai multe informații, consultați [Copiați configurația mediului](audience-insights/manage-environments.md#copy-the-environment-configuration).

### <a name="what-are-the-trial-limits-and-quotas"></a>Care sunt limitele și ofertele versiunii de încercare?

- Nu puteți utiliza propriul cont de stocare Azure Data Lake Storage pentru a stoca date de ieșire în timpul unei versiuni de încercare a statisticilor privind audiența. Cu toate acestea, puteți ingera date dintr-un cont de stocare Data Lake.
- Puteți stoca până la 3 GB de date în mediul Dataverse mediu care se aprovizionează automat atunci când porniți o versiune de încercare Customer Insights.

## <a name="customer-insights-specific-questions"></a>Întrebări specifice pentru Customer Insights

### <a name="how-do-i-start-using-the-trial"></a>Cum încep să utilizez versiunea de încercare?

După ce vă înscrieți pentru versiunea de încercare, veți ajunge în ecranul principal al aplicației. Ecranul principal oferă linkuri către ghiduri de utilizare și tutoriale. Pentru a afla mai multe, accesați linkurile din [Resurse suplimentare](trial-signup.md#additional-resources), din pagina de înscriere a versiunii de încercare.

### <a name="what-features-are-available-in-the-trial"></a>Ce caracteristici sunt disponibile în versiunea de încercare?

Majoritatea caracteristicilor capabilităților Customer Insights sunt disponibile în versiunea de încercare.

Următoarele caracteristici sunt **nu e disponibil**: 
- Nu puteți crea medii noi care utilizează propriul cont de stocare Azure Data Lake Storage.
- Nu puteți șterge mediul de încercare. 

### <a name="how-long-does-the-trial-last"></a>Cât timp durează versiunea de încercare?

Testul Customer Insights durează 30 de zile. Puteți prelungi procesul o dată după 23 de zile când vă conectați la mediul dvs. de încercare.

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>Elimin datele eșantion din versiunea de încercare?

Nu puteți elimina datele eșantion din versiunea de încercare.
