---
description: Come eseguire la migrazione degli account utente di Analytics come Enterprise ID o Federated ID all’Admin Console.
title: Eseguire la migrazione degli account utente di Analytics per Enterprise ID e Federated ID
uuid: f90bf78a-5603-4bef-b714-13215301187c
translation-type: tm+mt
source-git-commit: a492de4ccbcd6f3f8ca81c9fecbcca4780e0f589
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 100%

---


# Eseguire la migrazione degli account utente di Analytics per Enterprise ID e Federated ID {#migrate-analytics-user-accounts-for-enterprise-and-federated-ids}

Come eseguire la migrazione degli account utente di Analytics come Enterprise ID o Federated ID all’Admin Console.

## Prerequisiti {#prereqs}

Prerequisiti per la gestione degli utenti nell’Admin Console.

Per domini e directory nuovi, seguire i passaggi per:

* Impostare una directory
* Impostare domini
* Collegare domini a directory

Consulta [Impostazione di un sistema di gestione delle identità](https://helpx.adobe.com/it/enterprise/using/set-up-identity.html) per ulteriore assistenza.

Se un’altra unità aziendale o un altro team avevano già creato una directory in un’altra organizzazione, seguire i passaggi descritti in [trusting di directory](https://helpx.adobe.com/it/enterprise/using/set-up-identity.html#Directorytrusting) per stabilire la directory nell’organizzazione che stai utilizzando per Analytics.

## Eseguire la migrazione degli account utente di per Enterprise ID e Federated ID {#task-0cfb3e4400fd4ab58e4d9704528b05fa}

Segui questa procedura per:

* Scaricare un elenco di login utente da **[!UICONTROL Analytics]** > **[!UICONTROL Analytics Users & Assets]**.

* Scaricare un elenco degli utenti correnti da **[!UICONTROL Admin Console]** > **[!UICONTROL Users]**.

* Confrontare gli elenchi (cercando i duplicati in modo da evitare di sovrascrivere dati di account nell’Admin Console)
* Caricare un file [!DNL .csv] completo (da **[!UICONTROL Admin Console]** > **[!UICONTROL Users]**) con utenti Enterprise ID o Federated ID in Admin Console.

Se ti occorre trasferire gli account utente Adobe ID esistenti a un Enterprise ID o Federated ID, contatta l’Assistenza clienti di Adobe e richiedi un [trasferimento di massa delle identità utente](https://helpx.adobe.com/it/enterprise/using/bulk-operations.html).

**Per eseguire la migrazione degli account utente**

1. Scaricare il file degli accessi utente di Analytics ([!DNL User Logins List.tab]) da Gestione utenti di Analytics, utilizzando uno dei metodi seguenti (a seconda che la migrazione degli utenti sia già stata effettuata o meno)
   1. *Prima della migrazione,* passa a **[!UICONTROL Admin]** > **[!UICONTROL User Management (Legacy)]** > **[!UICONTROL Edit Users]**, quindi fai clic su **[!UICONTROL Download Report]**.

      ![](assets/download-report.png)

      Il collegamento Scarica rapporto viene visualizzato solo per i clienti che non hanno eseguito la migrazione degli utenti.

   1. *Se hai già eseguito la migrazione degli utenti,* passa a **[!UICONTROL Analytics]** > **[!UICONTROL Analytics users and Assets]**.

      ![Informazioni sul passaggio](assets/admin-analytics-users-assets.png)

   1. Nella pagina [!DNL Users], seleziona gli utenti e fai clic su **[!UICONTROL Export to CSV]**.

      ![Informazioni sul passaggio](assets/export-csv-migrate.png)

   1. Apri il file [!DNL User List.csv] scaricato in Excel.

      Preparati a copiare i valori *`Email`*, *`First Name`* e *`Last Name`* in un file [!DNL sample.csv] (come descritto nel passaggio successivo).

      >[!IMPORTANT] I valori nel file CSV devono essere delimitati da virgole.

      >[!TIP] Durante questo passaggio, Adobe consiglia di ottimizzare l’elenco di utenti in modo che solo gli utenti con un ID e-mail valido siano inclusi nella migrazione di Enterprise ID o Federated ID.

1. Nell’[!UICONTROL Admin Console], scarica un elenco di utenti di Admin Console.

   1. Passa a [!UICONTROL Admin Console] > **[!UICONTROL Users]**, quindi fai clic su [Esporta elenco utenti a CSV](https://helpx.adobe.com/it/enterprise/using/users.html).

      ![](assets/export-csv.png)

   1. Confronta i due file: gli utenti esistenti di Admin Console nel file [!DNL .csv] esportato ([!DNL sample.csv], in questo esempio) con gli utenti nel file [!DNL User Logins List.csv] di Analytics.

      >[!IMPORTANT] Se trovi duplicati, eliminali dal file [!DNL User Logins List.csv] di Analytics. Questo passaggio aiuta a evitare la sovrascrittura delle autorizzazioni utente esistenti di Experience Cloud nell’Admin Console e ti fornisce un elenco di account da migrare.

1. Scarica il modello CSV dall’Admin Console:
   1. Nella scheda Utenti, fai clic su **[!UICONTROL Add users by CSV]**, quindi **[!UICONTROL Download CSV Template]**.

      ![Informazioni sul passaggio](assets/add-users-csv.png)

   1. Scegli **[!UICONTROL Standard Template]**.

      Questo passaggio ti permette di scaricare un file modello [!DNL sample.csv].

      ![](assets/download-csv-template.png)

1. Copia i valori delle colonne *`Email`*, *`First Name`* e *`Last Name`* da [!DNL User Logins List.tab] nelle colonne corrispondenti del modello [!DNL sample.csv].

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
   <td colname="col2"> <p>Copiato da <span class="filepath"> User Logins List.tab</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome </p> </td> 
   <td colname="col2"> <p>Copiato da <span class="filepath"> User Logins List.tab</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cognome </p> </td> 
   <td colname="col2"> <p>Copiato da <span class="filepath"> User Logins List.tab</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tipo di identità </p> </td> 
   <td colname="col2"> <p><span class="term"> Federated ID</span> o <span class="term"> Enterprise ID</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio </p> </td> 
   <td colname="col2"> <p>Assicurati che i domini nelle colonne Le colonne <span class="term"> Dominio</span> e <span class="term"> E-mail</span> corrispondono ai domini stabiliti nei prerequisiti</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codice paese </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

Per ulteriori informazioni sui campi nel file [!DNL .csv], consulta [Formato del file CSV](https://helpx.adobe.com/it/enterprise/using/users.html).

>[!NOTE] Altre colonne, ad esempio [!UICONTROL Product Configurations] e [!UICONTROL Admin Roles], possono restare vuote.

1. Sulla scheda Utenti nell’Admin Console, carica il file modello facendo clic su **[!UICONTROL Add users by CSV]** (come indicato nel passaggio 3).
1. In Analytics, esegui lo strumento di migrazione (come descritto in [Eseguire la migrazione degli account utente di Analytics](/help/admin/user-management2/user-migration/t-migrate-users.md)).
1. Fai clic su **[!UICONTROL Migrate]** > **[!UICONTROL Migrate as Enterprise IDs]**.

   ![Informazioni sul passaggio](assets/migrate-as-enterprise.png)

   Quando fai clic su **[!UICONTROL Migrate]**, gli utenti vengono collegati all’account Enterprise ID/Federated ID nell’Admin Console. Le autorizzazioni dell’account utente legacy in Analytics corrisponderanno alle autorizzazioni concesse all’accesso Enterprise ID/Federated ID in **[!UICONTROL Admin Console]** > **[!UICONTROL Analytics]** > **[!UICONTROL Product Profiles]**. L’ID utente viene visualizzato nel bucket Migrazione completata. Puoi disabilitare l’accesso legacy [!DNL my.omniture.com].

   Dopo avere eseguito la migrazione degli utenti, lo stato della colonna Stato di migrazione cambia da **[!UICONTROL Not Initiated]** a **[!UICONTROL Migrated]**.

   Anche gli utenti Adobe ID visualizzati nello strumento di migrazione possono essere migrati in questa procedura. Fino a quando non viene eseguito un trasferimento di identità, devono ancora accedere con il proprio Adobe ID. Contatta l’Assistenza clienti di Adobe per ricevere assistenza nel trasferimento di identità.
