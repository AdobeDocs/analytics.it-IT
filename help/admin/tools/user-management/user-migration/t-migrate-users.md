---
description: Eseguire la migrazione dal sistema legacy di gestione utenti di Analytics all’Admin Console.
title: Eseguire la migrazione degli account utente di Analytics per Adobe ID
feature: Admin Tools
exl-id: 198367a1-8156-4cc3-af8a-d92c61699eda
role: Admin
TQID: https://experienceleague.adobe.com/bD-qiEI3KbDBNe4aO01-MqzjoZ-OMcGAnd9vnMTBmZs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: d124af73-4061-4b84-9063-ae2b60f2c1f3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 398
ht-degree: 70%

---

# Eseguire la migrazione degli account utente di Analytics per Adobe ID

Eseguire la migrazione dal sistema legacy di gestione utenti di Analytics all’Admin Console.

>[!NOTE]
>
>Se un amministratore che non ha eseguito l’accesso tramite Experience Cloud tenta di accedere allo strumento di migrazione degli ID utente, verrà reindirizzato alla pagina di accesso di Experience Cloud.

1. Passa a **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User ID Migration]**.

   ![](/help/admin/tools/user-management/user-migration/assets/migration-progress.png)

   La pagina Migrazione ID utente include due sezioni: *Avanzamento migrazione* e *Informazioni utente*.

## Avanzamento migrazione

<table id="table_F9F1CFF762C745E198CB075A02BA2DDA"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Fase </th> 
      <th colname="col2" class="entry"> Descrizione </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Migrazioni completate </p> </td> 
      <td colname="col2"> <p>Gli utenti hanno accettato l’invito. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Accesso legacy disabilitato </p> </td> 
      <td colname="col2"> <p>L’accesso legacy tramite un ID società è disabilitato. Ora gli utenti accedono all’Experience Cloud utilizzando il proprio Adobe ID o Enterprise ID. Quando tutti gli utenti avranno raggiunto questa fase, avrai completato la migrazione. </p> <p>Durante la migrazione, l’accesso legacy è disattivato. Gli utenti vengono reindirizzati a <span class="filepath"> experiencecloud.adobe.com</span> e devono accedere utilizzando il loro Adobe ID o Enterprise ID. </p> </td> 
   </tr> 
   </tbody> 
   </table>

## Informazioni utente

Informazioni utente delinea gli utenti dell’organizzazione, separati per nome di dominio.

<table id="table_3822E27AF81E4A188562FEB5131548A5"> 
<thead> 
<tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
</tr>
</thead>
<tbody> 
<tr> 
   <td colname="col1"> <p>Dominio </p> </td> 
   <td colname="col2"> <p>I domini sono specifici per gli ID e-mail della base di utenti Analytics corrente. Un dominio può essere registrato da una sola organizzazione ed esclusivamente dagli amministratori di sistema. Per ulteriori informazioni, vedi <a href="https://helpx.adobe.com/it/enterprise/help/request-access-to-claimed-domain.html">Richiedere l’accesso a un dominio registrato</a>. </p> </td> 
</tr> 
<tr> 
   <td colname="col1"> <p>Dominio registrato </p> </td> 
   <td colname="col2"> <p>Se desideri eseguire la migrazione degli utenti come Enterprise ID o Federated ID, devi essere un amministratore di sistema e registrare un dominio disponibile tramite Adobe Admin Console prima di eseguire la migrazione degli utenti. Puoi trovare ulteriori informazioni <a href="https://helpx.adobe.com/it/enterprise/help/identity.html">qui</a>. </p> <p>Se non desideri registrare domini per Enterprise ID o Federated ID, salta questo passaggio ed esegui la migrazione degli utenti come Adobe ID. <a href="https://helpx.adobe.com/it/enterprise/help/identity.html">Qui</a> puoi trovare ulteriori informazioni sui tipi di ID. </p> </td> 
</tr> 
</tbody> 
</table>

1. Individua il dominio contenente gli ID utente che desideri trasferire quindi, in **[!UICONTROL Requiring Migration]**, fai clic su **[!UICONTROL Select Users]**.
1. Nella pagina [!DNL Users], seleziona gli utenti di cui vuoi eseguire la migrazione, quindi fai clic su **[!UICONTROL Migrate]**.

   Quando fai clic su **[!UICONTROL Migrate]**, gli utenti ricevono un invito (Migrazione avviata) che devono accettare. Questa azione sposta l’ID utente a Migrazione completata. In seguito, potrai disattivarne l’accesso legacy a `[!DNL my.omniture.com].`

   ![](/help/admin/tools/user-management/user-migration/assets/user-info.png)

1. Specifica il tipo di ID con cui vuoi eseguire la migrazione degli utenti (Adobe ID o Enterprise ID)

   Dopo avere trasferito gli utenti, lo stato della colonna Stato di migrazione cambia da *`Not Initiated`* a *`Migrated`*.

   Se viene visualizzato *`Failed`*, passa il puntatore sull’icona per vedere il motivo per cui la migrazione non è riuscita.
