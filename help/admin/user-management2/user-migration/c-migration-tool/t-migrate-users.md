---
description: Eseguire la migrazione dal sistema legacy di gestione utenti di Analytics all’Admin Console.
seo-description: Eseguire la migrazione dal sistema legacy di gestione utenti di Analytics all’Admin Console.
seo-title: Eseguire la migrazione degli account utente di Analytics per Adobe ID
title: Eseguire la migrazione degli account utente di Analytics per Adobe ID
uuid: 734 e 9 f 14-ef 8 d -44 de -8 ff 3-3 ee dfe 0 a 214
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2fcd72e6c61f8004268e583b934e9cf474e5e44f

---


# Eseguire la migrazione degli account utente di Analytics per Adobe ID{#migrate-analytics-user-accounts-for-adobe-ids}

Eseguire la migrazione dal sistema legacy di gestione utenti di Analytics all’Admin Console.

## Eseguire la migrazione degli account utente di Analytics per Adobe ID {#task-f3355f3b14a340feae58cfa04c0ba1c9}

Eseguire la migrazione dal sistema legacy di gestione utenti di Analytics all’Admin Console.

>[!NOTE]
>
>Se un amministratore che non ha eseguito l'accesso tramite Experience Cloud tenta di accedere allo strumento di migrazione degli ID utente, verrà reindirizzato alla pagina di accesso di Experience Cloud.

**Per eseguire la migrazione degli utenti di Analytics**

1. Navigate to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL User ID Migration]**.

   ![](assets/migration-progress.png)

   La pagina Migrazione ID utente contiene due sezioni: *Avanzamento migrazione* e *Informazioni utente*.

   **Avanzamento migrazione**

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
   <td colname="col1"> <p>Accesso legacy disattivato </p> </td> 
   <td colname="col2"> <p>L’accesso legacy con un ID della società è stato disattivato. Gli utenti adesso potranno accedere a Experience Cloud utilizzando il proprio Adobe ID o Enterprise ID. Quando tutti gli utenti avranno raggiunto questa fase, avrai completato la migrazione. </p> <p>Nella migrazione, l'accesso legacy è disattivato. Users are redirected to <span class="filepath"> experiencecloud.adobe.com</span> and must log in using the Adobe ID or Enterprise ID. </p> <p>See <a href="../c-migration-tool/t-disable-legacy-login.md#task-c9262e469814473c8a3ff3971c95570b" format="dita" scope="local"> Disable Legacy Logins</a> for more information. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Informazioni utente**

Informazioni utente descrive gli utenti nella tua organizzazione, separati per nome del dominio.

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
   <td colname="col2"> <p>I domini sono specifici degli ID e-mail dell’attuale base di utenti di Analytics. Un dominio può essere registrato da una sola organizzazione ed esclusivamente dagli amministratori di sistema. Per ulteriori informazioni, vedi <a href="https://helpx.adobe.com/enterprise/help/request-access-to-claimed-domain.html" format="html" scope="external">Richiedere l’accesso a un dominio registrato</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio registrato </p> </td> 
   <td colname="col2"> <p>Se desideri trasferire gli utenti come Enterprise ID o Federated ID, devi essere amministratore di sistema e registrare un dominio disponibile tramite l’Admin Console prima di eseguire la migrazione degli utenti. Puoi trovare ulteriori informazioni <a href="https://helpx.adobe.com/enterprise/help/identity.html" format="html" scope="external">qui</a>. </p> <p>Se non desideri registrare domini per Enterprise ID o Federated ID, salta questo passaggio ed esegui la migrazione degli utenti come Adobe ID. Puoi trovare ulteriori informazioni sui tipi di ID <a href="https://helpx.adobe.com/enterprise/help/identity.html" format="html" scope="external">qui</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Locate the domain containing the user IDs you want to migrate, then, under **[!UICONTROL Requiring Migration]**, click **[!UICONTROL Select Users]**.
1. On the [!DNL Users] page, select the users you want to migrate, then click **[!UICONTROL Migrate]**.

   When you click **[!UICONTROL Migrate]**, users receive an invitation (Migration Initiated) and must accept it. Questa azione sposta l’ID utente a Migrazione completata. In seguito, potrai disattivarne l’accesso legacy a [!DNL my.omniture.com].

   ![](assets/user-info.png)

1. Specifica il tipo di ID con cui vuoi eseguire la migrazione degli utenti ([Adobe ID o Enterprise ID](https://helpx.adobe.com/enterprise/help/identity.html)).

   After migrating users, the status under the column Migration Status changes from *`Not Initiated`* to *`Migrated`*.

   If *`Failed`* displays, hover over the icon for a description about why the migration failed.
