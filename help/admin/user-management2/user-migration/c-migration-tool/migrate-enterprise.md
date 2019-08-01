---
description: Come eseguire la migrazione degli account utente di Analytics come Enterprise o Federated ID all’Admin Console.
seo-description: Come eseguire la migrazione degli account utente di Analytics come Enterprise o Federated ID all’Admin Console.
seo-title: Eseguire la migrazione degli account utente di Analytics per Enterprise e Federated ID
title: Eseguire la migrazione degli account utente di Analytics per Enterprise e Federated ID
uuid: f 90 bf 78 a -5603-4 bef-b 714-13215301187 c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2fcd72e6c61f8004268e583b934e9cf474e5e44f

---


# Eseguire la migrazione degli account utente di Analytics per Enterprise e Federated ID{#migrate-analytics-user-accounts-for-enterprise-and-federated-ids}

Come eseguire la migrazione degli account utente di Analytics come Enterprise o Federated ID all’Admin Console.

## Prerequisiti {#concept-e60d8deb3fc54a1a81f1f47a26658de3}

Prerequisiti per la gestione degli utenti nell’Admin Console.

Per domini e directory nuovi, seguire i passaggi per:

* Impostare una directory
* Impostare domini
* Collegare domini a directory

Consulta [Impostazione di un sistema di gestione delle identità](https://helpx.adobe.com/enterprise/using/set-up-identity.html) per ulteriore assistenza.

Se un’altra unità aziendale o un altro team avevano già creato una directory in un’altra organizzazione, seguire i passaggi descritti in [trusting di directory](https://helpx.adobe.com/enterprise/using/set-up-identity.html#Directorytrusting) per stabilire la directory nell’organizzazione che stai utilizzando per Analytics.

## Eseguire la migrazione degli account utente per Enterprise e Federated ID {#task-0cfb3e4400fd4ab58e4d9704528b05fa}

In questa procedura, potrai:

* Download a user login list from **[!UICONTROL Analytics]** &gt; **[!UICONTROL Analytics Users & Assets]**.

* Download a current users list from the **[!UICONTROL Admin Console]** &gt; **[!UICONTROL Users]**.

* Confrontare gli elenchi (cercando i duplicati in modo da evitare di sovrascrivere dati di account nell’Admin Console).
* Upload a finished [!DNL .csv] (from **[!UICONTROL Admin Console]** &gt; **[!UICONTROL Users]**) with Enterprise ID or Federated ID users to the Admin Console.

Se ti occorre trasferire gli account utente Adobe ID esistenti a un Enterprise ID o Federated ID, contatta l’Assistenza clienti di Adobe e richiedi un [trasferimento di massa delle identità utente](https://helpx.adobe.com/enterprise/using/bulk-operations.html).

**Per eseguire la migrazione degli account utente**

1. Scarica il file degli accessi utente di Analytics ([!DNL User Logins List.tab]) dalla Gestione utenti di Analytics, utilizzando uno dei metodi seguenti (a seconda che la migrazione degli utenti sia già stata effettuata o meno).
   1. *Prima della migrazione,* passa **[!UICONTROL Admin]** a &gt; **[!UICONTROL User Management (Legacy)]** &gt; **[!UICONTROL Edit Users]**, quindi fai clic **[!UICONTROL Download Report]** su.

      ![](assets/download-report.png)

      Il collegamento Scarica rapporto viene visualizzato solo per i clienti che non hanno eseguito la migrazione degli utenti.

   1. *Se hai già eseguito la migrazione,* passa **[!UICONTROL Analytics]** a &gt; **[!UICONTROL Analytics users and Assets]**.

      ![Informazioni passo](assets/admin-analytics-users-assets.png)

   1. On the [!DNL Users] page, select users, then click **[!UICONTROL Export to CSV]**.

      ![Informazioni passo](assets/export-csv-migrate.png)

   1. Open the downloaded [!DNL User List.csv] file in Excel.

      Be prepared to copy the *`Email`*, *`First Name`*, and *`Last Name`* values to a [!DNL sample.csv] file (described in the next step).

      >[!IMPORTANT]
      >
      >I valori nel file CSV devono essere delimitati da virgole.

      **Suggerimento**: durante questo passaggio, Adobe consiglia di ottimizzare l’elenco di utenti per assicurare che solo gli utenti con un ID e-mail valido siano inclusi nella migrazione di Enterprise ID o Federated ID.

1. Nell’Admin Console, scarica un elenco di utenti di Admin Console:

   1. Navigate to [Admin Console](http://adminconsole.adobe.html/#) &gt; **[!UICONTROL Users]**, then click [Export users list to CSV](https://helpx.adobe.com/enterprise/using/users.html).

      ![](assets/export-csv.png)

   1. Compare the two files: the existing Admin Console users in the exported [!DNL .csv] file ( [!DNL sample.csv], in this example) with the users in the Analytics [!DNL User Logins List.csv] file.

      >[!IMPORTANT]
      >
      >If you find duplicates, delete them from the Analytics [!DNL User Logins List.csv] file. Questo passaggio aiuta a evitare la sovrascrittura delle autorizzazioni utente esistenti di Experience Cloud nell’Admin Console e ti fornisce un elenco di account da trasferire.

1. Scarica il modello CSV dall’Admin Console:
   1. On the Users tab, click **[!UICONTROL Add users by CSV]**, then **[!UICONTROL Download CSV Template]**.

      ![Informazioni passo](assets/add-users-csv.png)

   1. Choose **[!UICONTROL Standard Template]**.

      Questo passaggio ti permette di scaricare un file modello [!DNL sample.csv].

      ![](assets/download-csv-template.png)

1. Copy the *`Email`*, *`First Name`*, and *`Last Name`* column values from [!DNL User Logins List.tab] to the corresponding columns in the [!DNL sample.csv] template.

   **Esempio di file modello**

   ![](assets/sample.png)

1. Nel modello ([!DNL sample.csv]), completa i seguenti campi obbligatori:

<table id="table_1B5EEFDB5BD8436EB760BE5FFAB1CF02"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>E-mail </p> </td> 
   <td colname="col2"> <p>Copiato da <span class="filepath">User Logins List.tab</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome </p> </td> 
   <td colname="col2"> <p>Copiato da <span class="filepath">User Logins List.tab</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cognome </p> </td> 
   <td colname="col2"> <p>Copiato da <span class="filepath">User Logins List.tab</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tipo di identità </p> </td> 
   <td colname="col2"> <p><span class="term"> Federated ID</span> o <span class="term"> Enterprise ID</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio </p> </td> 
   <td colname="col2"> <p>Assicurati che i domini nelle colonne <span class="term"> La colonna Dominio</span> e <span class="term"> e-mail</span> corrispondono ai domini stabiliti nei <a href="../c-migration-tool/migrate-enterprise.md#concept-e60d8deb3fc54a1a81f1f47a26658de3" format="dita" scope="local"> prerequisiti</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codice paese </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

For more information about the fields in the [!DNL .csv] file, see [CSV file format](https://helpx.adobe.com/enterprise/using/users.html).

>[!NOTE]
>
>Other columns, such as *`Product Configurations`* and *`Admin Roles`* can be blank.

1. On the Users tab in the Admin Console, upload the template file by clicking **[!UICONTROL Add users by CSV]** (as shown in [Step 3](../c-migration-tool/migrate-enterprise.md#step-190321c6025947e38b195daed122c063).).
1. In Analytics, run the migration tool (as described in [Migrate Analytics user accounts](../c-migration-tool/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9)).
1. Click **[!UICONTROL Migrate]** &gt; **[!UICONTROL Migrate as Enterprise IDs]**.

   ![Informazioni passo](assets/migrate-as-enterprise.png)

   When you click **[!UICONTROL Migrate]**, user are linked to the Enterprise ID/Federated ID account in Admin Console. The permissions of the legacy user account in Analytics will match the permissions granted to the Enterprise/Federated ID login in **[!UICONTROL Admin Console]** &gt; **[!UICONTROL Analytics]** &gt; **[!UICONTROL Product Profiles]**. L’ID utente viene visualizzato nel bucket Migrazione completata. Puoi disabilitare l’accesso legacy [!DNL my.omniture.com].

   After migrating users, the status under the Migration Status column changes from *`Not Initiated`* to *`Migrated`*.

   Anche gli utenti Adobe ID visualizzati nello strumento di migrazione possono essere migrati in questa procedura. Fino a quando non viene eseguito un trasferimento di identità, devono ancora accedere con il proprio Adobe ID. Contatta l’Assistenza clienti di Adobe per ricevere assistenza nel trasferimento di identità.
