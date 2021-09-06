---
title: Relații între entități și căi de entități
description: Creați și gestionați relații între entități din mai multe surse de date.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 1853fcd8db2918a0b4a19fa0934e2f0ddbcf6d093c85fdf2068a13f954035dec
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ro-RO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035246"
---
# <a name="relationships-between-entities"></a>Relații între entități

Relațiile conectează entități și definesc un grafic al datelor dvs. atunci când entitățile partajează un identificator comun, o cheie străină. La această cheie străină se poate face referire de la o entitate la alta. Entitățile conectate vă permit definirea de segmente și măsuri pe baza mai multor surse de date.

Există trei tipuri de relații: 
- Relații de sistem needitable, create de sistem ca parte a procesului de unificare a datelor
- Relații moștenite non-editabile, care sunt create automat din ingerarea surselor de date 
- Relații particularizate editabile, create și configurate de utilizatori

## <a name="non-editable-system-relationships"></a>Relații de sistem non-editabile

În timpul unificării datelor, relațiile de sistem sunt create automat pe baza potrivirii inteligente. Aceste relații ajută la corelarea înregistrărilor profilului clienților cu înregistrările corespunzătoare. Următoarea diagramă ilustrează crearea a trei relații bazate pe sistem. Entitatea client este asociată cu alte entități pentru a produce entitatea unificată *Client*.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagramă cu căi de relație pentru entitatea client cu trei relații 1-n.":::

- **Relația *CustomerToContact*** a fost creată între entitatea *Client* și entitatea de *contact*. Entitatea *Client* face ca câmpul cheie **Contact_contactID** să se raporteze la câmpul cheie al entității de *Contact* **contactID**.
- **Relația *CustomerToAccount*** a fost creată între entitatea *Client* și entitatea de *Cont*. Entitatea *Client* face ca câmpul cheie **Account_accountID** să se raporteze la câmpul cheie al entității de *cont* **accountID**.
- **Relația *CustomerToWebAccount*** a fost creată între entitatea *Client* și entitatea *WebAccount*. Entitatea *Client* face ca câmpul cheie **WebAccount_webaccountID** să se raporteze la câmpul cheie al entității *WebAccount* **webaccountID**.

## <a name="non-editable-inherited-relationships"></a>Relații moștenite non-editabile

În timpul procesului de ingestie de date, sistemul verifică sursele de date pentru relațiile existente. Dacă nu există nicio relație, sistemul le creează automat. Aceste relații sunt utilizate și în procesele din aval.

## <a name="create-a-custom-relationship"></a>Crearea unei relații particularizate

Relația constă dintr-o *entitate sursă* care conține cheia străină și o *entitate țintă* pe care o indică cheia externă a entității sursă. 

1. În detalii despre public, accesați **Date** > **Relații**.

2. Selectați **Relație nouă**.

3. Pe panoul **Relație nouă**, furnizați următoarele informații:

   :::image type="content" source="media/relationship-add.png" alt-text="Panou lateral de relație nouă, cu câmpuri de intrare necompletate.":::

   - **Numele relației**: Numele care reflectă scopul relației. Exemplu: CustomerToSupportCase.
   - **Descriere**: Descrierea relației.
   - **Entitate sursă**: Entitate care este utilizată ca sursă în relație. Exemplu: SupportCase.
   - **Entitate țintă**: Entitate care este utilizată ca țintă în relație. Exemplu: Client.
   - **Cardinalitatea sursă**: Specificați cardinalitatea entității sursă. Cardinalitatea descrie numărul de elemente posibile dintr-un set. Se referă întotdeauna la cardinalitatea țintă. Puteți alege între **Unu** și **Mulți**. Sunt acceptate doar relații mulți-la-unu și unu-la-unu.  
     - Mai-multe-la-una: Mai multe înregistrări sursă se pot referi la o înregistrare țintă. Exemplu: Mai multe cazuri de asistență de la un singur client.
     - Una-la-una: O singură înregistrare sursă se referă la o singură înregistrare țintă. Exemplu: Un ID de loialitate pentru un singur client.

     > [!NOTE]
     > Relațiile mulți-la-mai-mulți pot fi create folosind două relații multe-la-una și o entitate care leagă, care conectează entitatea sursă și entitatea țintă.

   - **Cardinalitate țintă**: Selectați cardinalitatea înregistrărilor entității țintă. 
   - **Câmpul cheie sursă**: Câmpul cheie străină din entitatea sursă. Exemplu: SupportCase ar putea utiliza CaseID ca un câmp cu cheie străină.
   - **Câmpul cheie țintă**: Câmpul cheie al entității țintă. Exemplu Clientul ar putea folosi câmpul cheie **Număr de înregistrare client**.

4. Pentru a crea conexiunea particularizată, selectați **Salvare**.

## <a name="view-relationships"></a>Vizualizare relații

Pagina Relații listează toate relațiile care au fost create. Fiecare rând reprezintă o relație, care include, de asemenea, detalii despre entitatea sursă, entitatea țintă și cardinalitatea. 

:::image type="content" source="media/relationships-list.png" alt-text="Lista relațiilor și opțiunilor din bara de acțiuni a paginii Relații.":::

Această pagină oferă un set de opțiuni pentru relațiile existente și noi: 
- **Nouă relație**: [Creați o relație particularizată](#create-a-custom-relationship).
- **Vizualizator**: [Explorați vizualizatorul relației](#explore-the-relationship-visualizer) pentru a vedea o diagramă de rețea a relațiilor existente și cardinalitatea acestora.
- **Filtrați după**: Alegeți tipul de relații de afișat în listă.
- **Căutați relații**: Utilizați o căutare bazată pe text pe proprietățile relațiilor.

### <a name="explore-the-relationship-visualizer"></a>Explorați vizualizatorul de relații

Vizualizatorul de relații arată o diagramă de rețea a relațiilor existente între entitățile conectate și cardinalitatea acestora. De asemenea, vizualizează calea relației.

Pentru a personaliza vizualizarea, puteți schimba poziția casetelor glisându-le pe pânză.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Captură de ecran a diagramei de rețea a vizualizatorului de relații cu conexiuni între entități conexe.":::

Opțiuni disponibile: 
- **Exportați ca imagine**: Salvați vizualizarea curentă ca fișier imagine.
- **Treceți la aspectul orizontal/vertical**: Schimbați alinierea entităților și a relațiilor.
- **Editați**: Actualizați proprietățile relațiilor particularizate în panoul de editare și salvați modificările.

### <a name="relationship-path"></a>Calea relației

Calea relației descrie entitățile care sunt conectate cu relațiile dintre o entitate sursă și o entitate țintă. Este utilizat atunci când creați un segment sau o măsură care include alte entități decât entitatea de profil unificat și există mai multe opțiuni pentru a ajunge la entitatea de profil unificat.

Calea relației informează sistemul despre care relații pentru a accesa entitatea de profil unificat. Căile de relație diferite pot produce rezultate diferite.

De exemplu, entitatea *eCommerce_eCommercePurchases* are următoarele relații cu entitatea profilul unificat *Client*:

- eCommerce_eCommercePurchases > Client
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Client
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Client 

Calea relației determină ce entități puteți utiliza atunci când creați reguli pentru măsuri sau segmente. Alegerea opțiunii cu cea mai lungă cale de relație va produce probabil mai puține rezultate, deoarece înregistrările de potrivire trebuie să facă parte din toate entitățile. În acest exemplu, un client trebuie să fi achiziționat bunuri prin e-commerce (eCommerce_eCommercePurchases), la un punct de vânzare (POS_posPurchases) și să participe la programul nostru de fidelizare (loyaltyScheme_loyCustomers). Atunci când alegeți prima opțiune, veți obține probabil mai multe rezultate, deoarece clienții trebuie să existe doar într-o singură entitate suplimentară.

## <a name="manage-existing-relationships"></a>Gestionați relațiile existente 

În pagina Relații, fiecare relație este reprezentată de un rând. 

Selectați o relație și alegeți una dintre următoarele opțiuni: 
 
- **Editați**: Actualizați proprietățile relațiilor particularizate în panoul de editare și salvați modificările.
- **Ștergeți**: Ștergeți relațiile particularizate.
- **Vizualizare**: Vizualizați relațiile create și moștenite de sistem. 

## <a name="next-step"></a>Următorul pas

Relațiile de sistem și personalizate sunt obișnuite să [creeze segmente](segments.md) și cu [măsuri](measures.md) pe baza mai multor surse de date care nu mai sunt în silozuri.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
