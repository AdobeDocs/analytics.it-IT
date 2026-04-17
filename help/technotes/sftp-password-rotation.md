---
title: Requisiti di sicurezza per server FTP e SFTP
description: Scopri i requisiti di sicurezza per i server FTP e SFTP.
feature: Data Configuration and Collection
role: Admin
source-git-commit: 26ae4edacbc3591d4d3358afe009bf7831d45efb
workflow-type: tm+mt
source-wordcount: '1898'
ht-degree: 1%

---

# Requisiti di sicurezza per server FTP e SFTP

Questa pagina descrive i requisiti di sicurezza per i server FTP e SFTP esistenti che ricevono dati forniti da Adobe Analytics Data Feeds o Data Warehouse.

* **Server FTP esistenti**: devono essere aggiornati per utilizzare SFTP, come descritto nella sezione seguente, [Aggiornare i server FTP per utilizzare SFTP](#upgrade-ftp-servers-to-use-sftp).

  L’aggiornamento da FTP a SFTP è un requisito perché SFTP consente una maggiore sicurezza.

  In alternativa, per un livello di sicurezza più elevato, puoi passare a una destinazione cloud moderna. Per ulteriori informazioni, vedere [Configurare gli account di importazione ed esportazione cloud](https://experienceleague.adobe.com/it/docs/analytics/components/locations/configure-import-accounts).

* **Server SFTP esistenti (e server SFTP appena aggiornati)**: è necessario che le vecchie password siano ruotate, come descritto nella sezione seguente, [Ruota la password SFTP](#rotate-your-sftp-password).

  La rotazione regolare della password SFTP è una best practice per la sicurezza che consente di proteggere i dati.

>[!IMPORTANT]
>
>Considera le seguenti situazioni prima di completare i passaggi descritti in questo articolo.
>
>* **Adobe consiglia di passare a una destinazione cloud moderna anziché eseguire l&#39;aggiornamento a SFTP, se possibile.**
>FTP e SFTP sono tipi di destinazione legacy. Invece di aggiornare gli account FTP a SFTP e ruotare le password SFTP come descritto in questo articolo, Adobe consiglia di passare a un tipo di destinazione cloud moderno (come Amazon S3, Google Cloud Platform o Azure). Queste destinazioni cloud forniscono un livello di sicurezza più elevato. Per ulteriori informazioni, vedere [Configurare gli account di importazione ed esportazione cloud](https://experienceleague.adobe.com/it/docs/analytics/components/locations/configure-import-accounts).
>
>* **Se gli account FTP e SFTP sono utilizzati esclusivamente per le classificazioni, esegui la migrazione ai set di classificazione.**
>Se il tuo account FTP o SFTP è utilizzato esclusivamente per le classificazioni, devi migrare dall&#39;**Importazione classificazioni** ai **Set di classificazione**, anziché aggiornare gli account FTP a SFTP e ruotare le password SFTP come descritto in questo articolo. L&#39;importazione di classificazioni diventerà obsoleta e non sarà più accessibile dopo il **31 agosto 2026**. Per ulteriori informazioni, vedere [Panoramica sui set di classificazione](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/sets/overview).

## Prerequisiti

### Inventario degli account FTP

I processi descritti in questa pagina durante l’aggiornamento dei server FTP per utilizzare SFTP devono essere completati per ogni sito FTP utilizzato per feed di dati e Data Warehouse.

Di conseguenza, è necessario identificare tutti gli account FTP che ricevono dati per feed di dati o Data Warehouse. Queste informazioni sono visualizzate nelle impostazioni di configurazione FTP, come descritto nella sezione [Tipi di account legacy](/help/components/locations/configure-import-accounts.md#configure-a-location-account) dell&#39;articolo [Configurare gli account di importazione ed esportazione cloud](/help/components/locations/configure-import-accounts.md).

Per ogni account, raccogli le seguenti informazioni:

* **Host**: il nome host del server FTP a cui il tuo account si connette (ad esempio, `ftp.omniture.com`, `ftp2.omniture.com` e così via).

* **Porta**: quando si utilizza un server SFTP ospitato da Adobe, i client SFTP si connettono alla porta 22. Connessioni FTP con porta d&#39;uso non sicura 21.

* **Nome utente**: nome utente utilizzato per accedere al server FTP.

* **Segreto account località**: il segreto account corrente per l&#39;account. Questo è il segreto account (password) che si utilizza attualmente durante il download dei dati inviati alla posizione FTP. Queste informazioni non sono disponibili dall’interfaccia di Adobe Analytics.

### Conferma di poter aggiornare le credenziali negli strumenti

Assicurati di poter aggiornare le password SFTP in qualsiasi strumento o script utilizzato per connettersi al sito SFTP (ad esempio, un client SFTP, uno script automatizzato o una piattaforma di terze parti).

Tutti i client devono connettersi tramite SFTP con una password come fallback.

## Aggiornare i server FTP per utilizzare SFTP

>[!IMPORTANT]
>
>Se i dati FTP vengono inviati a un partner di terze parti (ad esempio, una società di consulenza o un fornitore di analisi), coordinati con loro prima di seguire i passaggi descritti in questo articolo.

### Passaggio 1: generare le chiavi SSH dell’organizzazione per il download dei dati

In questa sezione viene descritto come generare le chiavi SSH dell&#39;organizzazione (una coppia di chiavi pubblica/privata) utilizzate per **scaricare dati** dal server SFTP.

>[!NOTE]
>
>In un passaggio futuro, scaricherai un’altra chiave pubblica fornita da Adobe. Fa parte di una seconda coppia di chiavi pubblica/privata, utilizzata da Adobe per **caricare dati** sul server SFTP.

Per impostare un trasferimento sicuro per il download dei dati dal server FTP:

1. Accedi alla workstation in cui scarichi i dati dal server FTP.

1. Genera una coppia di chiavi pubblica/privata da utilizzare per il trasferimento sicuro.

   Quando si utilizza un server FTP ospitato da Adobe, Adobe supporta le chiavi RSA e ed25519.

   * **In un ambiente Linux**: eseguire il comando seguente per generare la coppia di chiavi ed25519:

     ```
     ssh-keygen -t ed25519 -C "your-comment-or-email"
     ```

     Se i criteri non consentono di utilizzare le chiavi ed25519, eseguire il comando seguente per generare la coppia di chiavi RSA:

     ```
     ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
     ```

   * **In un ambiente Windows**: utilizzare PuTTYgen.

1. Creare un file denominato [!DNL `authorized_keys`] (senza estensione).

1. Copiare il contenuto della chiave pubblica nel file [!DNL `authorized_keys`].

1. In un passaggio futuro, tornerai a questo file [!DNL `authorized_keys`] per aggiungere la chiave pubblica di Adobe, utilizzata da Adobe per caricare dati sul server SFTP. Quindi aggiungerai il file [!DNL `authorized_keys`] al server SFTP.

### Passaggio 2: creare un nuovo account di posizione SFTP in Adobe Analytics

Crea un nuovo account di posizione SFTP per sostituire ogni account FTP esistente.

Quando crei un nuovo account di posizione SFTP, devi utilizzare lo stesso nome host e lo stesso nome utente utilizzati nell’account FTP esistente che sta sostituendo.

>[!NOTE]
>
>In un passaggio futuro, configurerai questo nuovo account posizione da utilizzare come destinazione per le consegne di feed di dati e Data Warehouse.

#### Creare l’account SFTP

1. In Adobe Analytics, vai a [!UICONTROL **Componenti**] > [!UICONTROL **Percorsi**].

1. Selezionare la scheda [!UICONTROL **Account località**].

1. Seleziona [!UICONTROL **Aggiungi account**].

1. Nel campo a discesa [!UICONTROL **Tipo di account**], seleziona [!UICONTROL **SFTP (legacy)**].

1. Completa i campi seguenti:

   | Nome campo: | Funzione |
   |---------|----------|
   | [!UICONTROL **Nome host**] | Il nome host SFTP (ad esempio, `ftp.omniture.com`). |
   | [!UICONTROL **Porta**] | Porta del firewall attraverso la quale verranno inviati i dati. Questa è la porta 22 per le connessioni SFTP ospitate da Adobe. |
   | [!UICONTROL **Nome utente**] | Nome utente SFTP. Utilizza lo stesso nome utente utilizzato per il tuo account FTP. |

1. Seleziona [!UICONTROL **Salva**].

1. Nella finestra di dialogo [!UICONTROL **Account creato**] scaricare la chiave pubblica RSA o ed25519, quindi selezionare **[!UICONTROL OK]**. Questa è la chiave pubblica SSH utilizzata da Adobe per caricare dati sul server SFTP. Puoi usare questa chiave nella sezione seguente, [Aggiungi la chiave pubblica SSH di Adobe al server SFTP](#add-adobes-ssh-public-key-to-the-sftp-server).

1. Ripeti questo processo per ogni account SFTP che desideri creare.

1. Continua con la sezione seguente, [Carica la chiave pubblica sul server SFTP](#upload-the-public-key-to-the-sftp-server).

#### Aggiungi la chiave pubblica SSH di Adobe al file `authorized_keys` e caricala sul tuo server FTP

La chiave pubblica appena scaricata nel passaggio 7 della sezione precedente fa parte di una coppia di chiavi pubblica/privata utilizzata da Adobe per **caricare dati** sul server SFTP.

È necessario aggiungere questa chiave pubblica allo stesso file `authorized_keys` in cui è stata precedentemente aggiunta la chiave di download dell&#39;organizzazione (quella generata in [Passaggio 1: generare la chiave di download dell&#39;organizzazione e aggiungerla al server FTP](#step-1-generate-your-organizations-download-key-and-add-it-to-your-ftp-server)).

Per aggiungere la chiave pubblica SSH di Adobe al file `authorized_keys` e caricarlo sul server FTP:

1. Accedi alla workstation in cui scarichi i dati dal server FTP.

1. Apri il file [!DNL `authorized_keys`] e aggiungi la chiave di caricamento di Adobe. Questo file deve già contenere la chiave di download della tua organizzazione da [Passaggio 1: genera la chiave di download della tua organizzazione e aggiungila al server FTP](#step-1-generate-your-organizations-download-key-and-add-it-to-your-ftp-server).

1. Carica il file [!DNL `authorized_keys`] sul server FTP:

   1. Connettiti al server FTP e accedi con il tuo nome utente e la tua password.\
      Può trattarsi di un server FTP ospitato da Adobe o del tuo server FTP.
   1. Creare una directory [!DNL .ssh] (se non esiste già).
   1. Caricare il file [!DNL `authorized_keys`] nella directory [!DNL .ssh].

1. Aggiorna le impostazioni del firewall per consentire le connessioni in entrata dal server SFTP. Quando utilizzi un server SFTP ospitato da Adobe, consenti le connessioni in entrata dagli intervalli IP di Adobe sulla porta 22.

1. Verifica la connessione accedendo al server utilizzando il client SFTP.

1. Ripeti questo processo per ogni account SFTP creato nella sezione precedente, [Crea l&#39;account SFTP](#create-the-sftp-account).

1. Continua con la seguente sezione, [Aggiungi una posizione all&#39;interno dell&#39;account](#add-a-location-within-the-account).

#### Aggiungi una posizione all’interno dell’account

1. Nella scheda **Percorsi**, seleziona **Aggiungi percorso**.

1. Specifica un nome, una descrizione e se questa posizione verrà utilizzata con feed di dati o Data Warehouse.

1. Nel campo [!UICONTROL **Account località**], seleziona l&#39;account appena creato.

1. Nel campo [!UICONTROL **Percorso directory**], specifica il percorso della directory sul server SFTP. Le cartelle nel percorso devono esistere già. In caso contrario, si verifica un errore. Ad esempio: `/folder_name/folder_name`.

1. Seleziona **Salva**.

1. Ripeti questo processo per ogni account SFTP creato.

Per istruzioni dettagliate, vedere [Configurare i percorsi di importazione ed esportazione del cloud](https://experienceleague.adobe.com/it/docs/analytics/components/locations/configure-import-locations).

### Passaggio 3: modificare feed di dati e richieste di Data Warehouse per utilizzare la nuova destinazione SFTP

Aggiorna eventuali feed di dati pianificati esistenti e richieste Data Warehouse che al momento inviano dati a destinazioni FTP per utilizzare le nuove destinazioni SFTP create.

#### Modifica feed dati

Modifica ogni feed di dati pianificato configurato con la vecchia destinazione FTP per utilizzare la nuova destinazione SFTP:

1. In Adobe Analytics, seleziona [!UICONTROL **Amministratore**] > [!UICONTROL **Feed dati**].

1. Individua il feed di dati da modificare. Per individuare un feed di dati, puoi [filtrare e cercare nell&#39;elenco dei feed di dati](#filter-and-search-the-list-of-data-feeds).

1. Selezionare il feed di dati nella colonna [!UICONTROL **Nome feed**].

   Viene visualizzata la pagina [!UICONTROL **Modifica _nome_feed_**].

1. Nella sezione [!UICONTROL **Destinazione**], nel campo [!UICONTROL **Account**], utilizza il menu a discesa per selezionare la nuova destinazione SFTP creata.

1. Nel campo [!UICONTROL **Posizione**], utilizza il menu a discesa per selezionare la posizione nell&#39;account SFTP.

1. Seleziona [!UICONTROL **Salva**].

Per informazioni più dettagliate, vedere [Modificare un feed dati](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed) in [Gestire feed dati](/help/export/analytics-data-feed/df-manage-feeds.md).

#### Modificare le richieste Data Warehouse

Modifica ogni richiesta Data Warehouse pianificata configurata con la vecchia destinazione FTP per utilizzare la nuova destinazione SFTP:

1. In Adobe Analytics, seleziona [!UICONTROL **Strumenti**] > [!UICONTROL **Data Warehouse**].

1. Nella pagina Data Warehouse, seleziona la richiesta da modificare.

   ![Gestire una richiesta](assets/dw-manage-request.png)

1. Seleziona [!UICONTROL **Modifica**].

1. Selezionare la scheda [!UICONTROL **Destinazione report**].

1. Nel campo [!UICONTROL **Account**], utilizza il menu a discesa per selezionare la nuova destinazione SFTP creata.

1. Nel campo [!UICONTROL **Posizione**], utilizza il menu a discesa per selezionare la posizione nell&#39;account SFTP.

1. Seleziona [!UICONTROL **Salva modifiche**].

Per informazioni più dettagliate, vedi [Modifica richieste](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests) in [Gestione richieste Data Warehouse](/help/export/data-warehouse/data-warehouse-requests-manage.md).

### Passaggio 4: aggiornare le impostazioni del firewall

Se non lo hai già fatto, devi aggiornare le impostazioni del firewall come segue:

* **Quando si utilizzano i server FTP di Adobe**: è necessario aggiornare le impostazioni del firewall per consentire **connessioni in uscita** sulla porta 22.

* **Quando si utilizza il proprio server FTP**: è necessario aggiornare le impostazioni del firewall per consentire la connessione **in entrata** su qualsiasi porta che ospita il servizio, in genere la porta 22.

È inoltre necessario rimuovere le vecchie regole FTP, ad esempio consentire connessioni in entrata sulla porta 21. L&#39;FTP utilizza la porta 21 e una serie di porte aggiuntive per il trasferimento dei dati. Come best practice per la sicurezza, è consigliabile rimuovere questo accesso non necessario tramite il firewall.)

### Passaggio 5: verificare che le richieste pianificate di feed dati e Data Warehouse vengano consegnate correttamente

Dopo aver aggiornato ogni richiesta esistente di Feed dati e Data Warehouse per utilizzare il nuovo account e la nuova posizione SFTP, attendi la successiva consegna pianificata. Verifica che i dati arrivino alla nuova destinazione come previsto.

### Passaggio 6: ruotare la password sul server SFTP aggiornato

Dopo aver aggiornato un server FTP a SFTP, devi ruotare la password SFTP, come descritto nella sezione seguente, [Ruotare la password SFTP](#rotate-your-sftp-password).

## Ruotare la password SFTP

Se l’autenticazione basata su chiave non riesce, una password SFTP funge da metodo di autenticazione di fallback.

Ruota la password SFTP subito dopo l’aggiornamento da FTP a SFTP. Dovrebbe continuare a essere ruotato regolarmente, in base alle politiche stabilite.

1. Contatta l’Assistenza clienti di Adobe e richiedi una nuova password.

1. Per ogni account SFTP, fornisci **Nome host** e **Nome utente**.

   L’Assistenza clienti genera una nuova password per ogni account FTP.

1. Aggiorna la password in qualsiasi client utilizzi per connettersi al server SFTP.


<!--
< **_Ignore everything after this_** >

-------

## Set up a new SFTP server or upgrade your existing FTP server

## Upgrade your FTP server to use SFTP where files are delivered or FTP account to use SFTP

Set up an SFTP server where Data Feed and Data Warehouse files can be delivered. This could beYou first need to upgrade your FTP server to use SFTP To upgrade an FTP account to use SFTP, follow the steps in [Connect to an FTP account with SFTP](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md).

## Create an SFTP account

## Rotate the passphrase on SFTP accounts


 
Adobe recommends that you periodically rotate the account secrets (passwords) on your FTP accounts that are associated with Data Feeds and Data Warehouse. 
 
Regular rotation of account secrets is a security best practice that helps protect your data. 
 
To ensure uninterrupted reception of data, follow the steps in [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets) prior to changing any account secrets.  
 
>[!IMPORTANT] 
> 
>If your FTP data is delivered to a third-party partner (for example, a consulting firm or Adobe Analytics vendor), coordinate with them before rotating account secrets. The third-party partner will need to update their own tools and scripts with the new account secrets immediately after the new account secrets are provided by your FTP host provider (either Adobe or another provider).

## When rotating account secrets is not necessary 
 
### Transition from FTP to a cloud destination 
 
FTP and SFTP are legacy destination types. Rather than rotating FTP account secrets, Adobe recommends moving to a modern cloud destination type (such as Amazon S3, Google Cloud Platform, or Azure), which provide a higher level of security. For more information, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts). 
 
### Transition from the Classifications importer to Classification sets 
 
If your FTP account is used exclusively for Classifications, you should migrate from the **Classifications importer** to **Classification sets**, rather than rotating your FTP account secrets. The Classification importer will be deprecated and no longer accessible after **August 31, 2026**. For more information, see [Classification sets overview](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/sets/overview). 

## Prepare to rotate account secrets 
 
Complete the following steps before attempting to rotate FTP account secrets: 
 
### Step 1: Inventory your FTP accounts 
 
Identify all FTP accounts that are receiving data for Data Feeds or Data Warehouse. This information is shown in your FTP configuration settings, as described in the [Legacy account types](/help/components/locations/configure-import-accounts.md#configure-a-location-account) section of the article [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md). 
 
For each account, gather the following information: 
 
* **Host**: The FTP destination of the host your account connects to (for example, `ftp.omniture.com`, `ftp2.omniture.com`, and so forth). 
 
* **Port**: SFTP clients connect on port 22. FTP connections that are non-secure use port 21. 
 
* **Username**: The username used to log in to the FTP site. 
 
* **location account secret**: The current account secret for the account. This is the account secret (password) that you use currently when downloading data delivered to your FTP location. This information is not available from the Adobe Analytics interface. 
 
 
### Step 2: Confirm that you can update credentials in your tools 
 
Make sure you can update the FTP account secret in whatever tool or script you use to connect to the FTP site (for example, an FTP client, automated script, or third-party platform). 
 
### Step 3: Create FTP cloud location accounts with your current credentials 
 
Create new FTP cloud location accounts to replace your existing FTP location accounts. These new accounts will be used as the destination for your Data Feeds and Data Warehouse deliveries.  
 
When creating the new FTP accounts, you must use the same hostname, username, and account secret that are used in your existing FTP accounts. 
 
#### Create each FTP account 
 
1. In Adobe Analytics, go to **Components** > **Locations**. 
 
1. Select the **Location accounts** tab. 
 
1. Select **Add account**. 
 
1. In the **Account type** drop-down field, select **FTP (legacy)**. 
 
1. Complete the following fields: 

   | Field name | Function |
   |---------|----------|
   | **Hostname** |  Your Adobe FTP hostname (for example, `ftp.omniture.com`). | 
   | **Port** | SFTP clients connect on port 22. FTP connections that are non-secure use port 21. | 
   | **Username** | Your current FTP username. |
   | **Location account secret** | Your current FTP account secrets (password).  |
 
1. Select **Save**. 
 
Repeat this process for each FTP account. 
 
For detailed instructions, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts). 
 
#### Add a location within the account 
 
1. On the **Locations** tab, select **Add location**. 
 
1. Specify a name, description, and whether this location will be used with Data Feeds or Data Warehouse. 
 
1. In the [!UICONTROL **Location account**] field, select the account you just created. 
 
1. In the [!UICONTROL **Directory path**] field, specify the path to the directory on the FTP server. Folders must already exist; feeds throw an error if the specified path does not exist. For example, `/folder_name/folder_name`. 
 
1. Select **Save**. 
 
Repeat this process for each location. 
 
For detailed instructions, see [Configure cloud import and export locations](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-locations). 
 
### Step 4: Reference the new FTP cloud accounts from any scheduled Data Feeds and Data Warehouse requests 
 
Update any existing scheduled Data Feeds and Data Warehouse requests to use the FTP cloud accounts you created.  
 
* **Data Feeds**: Go to **Admin** > **Data Feeds**, edit each scheduled  Data Feed that uses an FTP account, then change the destination to the newly created FTP cloud account. 
 
  For detailed instructions, see [Edit a data feed](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md). 
 
* **Data Warehouse**: Go to **Tools** > **Data Warehouse**, edit each scheduled Data Warehouse request that uses an FTP account, then change the report destination to the newly created FTP cloud account. 
 
  For detailed instructions, see [Edit requests](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests) in [Manage Data Warehouse requests](/help/export/data-warehouse/data-warehouse-requests-manage.md). 
 
### Step 5: Ensure that scheduled Data Feeds and Data Warehouse requests are being delivered correctly. 
 
After updating each existing Data Feed and Data Warehouse request to use the new FTP account and location, wait for the next scheduled delivery. Verify that data arrives at the new destination as expected. 

## Request a new account secret 
 
>[!IMPORTANT] 
>
>Before requesting a new account secret, consider the following:
>
>* The steps in this section apply only if you are using an Adobe-provided FTP account. For example, the FTP hostname is `ftp.omniture.com`, `ftp2.omniture.com` or similar.   If your FTP hostname is not provided by Adobe, please contact your FTP host provider for details on changing the account secret.
> 
>* Request a new account secret only after you complete all the preparation steps described in [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets). 
>
>* After Adobe Customer Care or your third-party FTP host provider provides a new account secret, the old account secret is immediately invalidated. There is no way to revert to the previous account secret. 
>
 
To request a new account secret from Adobe: 
 
1. Contact Adobe Customer Care. 
 
1. For each FTP account, provide the **Hostname** and **Username** for each account that needs a new account secret. 
 
   Customer Care will generate a new account secret for each FTP account. 

1. Continue immediately with the following section, [After you receive the new account secret](#after-you-receive-the-new-account-secret).
 
## After you receive the new account secret 
 
Act immediately after receiving the new credentials. Any delay results in failed deliveries for active Data Feeds and Data Warehouse requests. 
 
### Step 1: Update your tools and scripts 
 
Update the FTP account secret in any tool, script, or automated process that connects to the FTP account. Make sure all team members and third-party partners who access the account are notified. 
 
### Step 2: Update your cloud location accounts 
 
1. In Adobe Analytics, go to **Components** > **Locations**. 

1. Select the **Location accounts** tab. 

1. Find the FTP account that you created in Step 3 of section, [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets).

1. Select **Edit details**. 

1. Enter the new account secret and confirm it. 

1. Select **Save**. 
 
Repeat this process for each account that was reset. 

For more detailed information about this process, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts).
 
### Step 3: Test your connections 
 
Verify that your Data Feeds or Data Warehouse requests that use the FTP account are working correctly with the new account secret. 
 
>[!TIP] 
> 
>If your current tools use SFTP with SSH keys that haven't been recently rotated, consider rotating those keys as well.

 
## Troubleshooting 
 
If something goes wrong after the account secret is rotated and you cannot restore connectivity, you can create a new FTP account. After the new account is set up, point your Data Feed or Data Warehouse request to the new account and update your cloud location accordingly. 

For information about how to create an FTP account, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts).

To set up secure transfer with your FTP server: 

1. Generate a public/private key pair to use for secure transfer.

   This process differs depending on whether your FTP server is Adobe-hosted or self-hosted:

   +++ For an Adobe-hosted FTP server:

   Generate a public/private key pair: 
   
      * **In a Linux environment**: Run the following command to generate the ed25519 key pair: 

        ```
        ssh-keygen -t ed25519 -C "your-comment-or-email"
        ```

        If your policy does not allow you to use ed25519 keys, run the following command to generate the RSA key pair (**Note:** The RSA key typically applies to customers who operate under FIPS 186-4, as ed25519 is first supported in the newer FIPS 186-5):

        ```
        ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
        ```

      * **In a Windows environment**: Use PuTTYgen.

   +++

   +++ For a self-hosted FTP server: 
   
   If you want to set up secure transfer with your own FTP server, you must have an SFTP hostname, username, and SFTP account within Adobe Analytics that contains a valid RSA or ed25519 public key from Adobe. This key must be installed on your SFTP server. You download this public key as part of the process of [creating the SFTP account](#create-the-sftp-account).

   +++

1. Create a file named [!DNL `authorized_keys`] (no extension).



3 basic steps: Set up SFTP on customer side, then on Adobe side, then change passphrase. 

1. FTP site: ftp.omniture.com - Using username/password to connect. Adobe uses the same username/password to connect to the site.

2. user can then upload their public key to that server, then start connecting to that server with their private key using SFTP. (They also need to open Port 22 in the firewall and they would close the other ports they don't need.)

3. In Locations, create a new location, use the same username. 

4. After they create that location, we give them our public key, and they have to install it on their SFTP server.

5. Then they switch all their data feeds to use the new Location. And then we'll use SFTP to send the data. 

6. Then they call Customer Care to get new passphrase (rotate passphrase), and then they change the passphrase on their side. Passphrase is only used if SSH fails (they have the wrong keys--a bad actor could use bad keys and then use the password. But they don't have to coordinate the switching of the passphrase with installation of SFTP. )


If they're using a third-party to do this, the third-party would need to set up SFTP - This is the same as we have documented right now. It doesn't have to be immediate, though, like we were assuming before. 


If it's they're own FTP site, it would be the same. They would need to start using SFTP with their FTP server, then get our public key and install it on their server. Shouldn't matter if the FTP site is hosted by Adobe or not. 

-->

