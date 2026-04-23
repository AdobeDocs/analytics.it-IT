---
title: Requisiti di sicurezza per server FTP e SFTP
description: Scopri i requisiti di sicurezza per i server FTP e SFTP.
feature: Data Configuration and Collection
role: Admin
source-git-commit: 9067b57a7436656b6776de08e8411ee0a87f2b20
workflow-type: tm+mt
source-wordcount: '1881'
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
>Se il tuo account FTP o SFTP è utilizzato esclusivamente per le classificazioni, devi migrare dall&#39;**Importazione classificazioni** ai **Set di classificazione**, anziché aggiornare gli account FTP a SFTP e ruotare le password SFTP come descritto in questo articolo. L&#39;importazione di classificazioni diventerà obsoleta e non sarà più accessibile dopo il **31 agosto 2026**. Per ulteriori informazioni, vedere [Panoramica sui set di classificazione](https://experienceleague.adobe.com/it/docs/analytics/components/classifications/sets/overview).

## Prerequisiti

### Inventario degli account FTP

Devi completare i passaggi di aggiornamento SFTP su questa pagina per ogni sito FTP utilizzato con feed di dati o Data Warehouse.

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

   Quando utilizzi un server SFTP ospitato da Adobe, Adobe supporta le chiavi RSA e ed25519.

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

1. Nel menu a discesa [!UICONTROL **Tipo di account**], seleziona [!UICONTROL **SFTP (legacy)**].

1. Completa i campi seguenti:

   | Nome campo: | Funzione |
   |---------|----------|
   | [!UICONTROL **Nome host**] | Il nome host SFTP (ad esempio, `ftp.omniture.com`). |
   | [!UICONTROL **Porta**] | Porta del firewall attraverso la quale verranno inviati i dati. Questa è la porta 22 per le connessioni SFTP ospitate da Adobe. |
   | [!UICONTROL **Nome utente**] | Nome utente SFTP. Utilizza lo stesso nome utente utilizzato per il tuo account FTP. |

1. Seleziona [!UICONTROL **Salva**].

1. Nella finestra di dialogo [!UICONTROL **Account creato**], scarica la chiave pubblica RSA o ed25519, quindi seleziona [!UICONTROL **OK**]. Questa è la chiave pubblica SSH utilizzata da Adobe per caricare dati sul server SFTP. Puoi usare questa chiave nella sezione seguente, [Aggiungi la chiave pubblica SSH di Adobe al server SFTP](#add-adobes-ssh-public-key-to-the-sftp-server).

1. Ripeti questo processo per ogni account SFTP che desideri creare.

1. Continua con la sezione seguente, [Carica la chiave pubblica sul server SFTP](#upload-the-public-key-to-the-sftp-server).

#### Aggiungi la chiave pubblica SSH di Adobe al file [!DNL `authorized_keys`] e caricala sul tuo server FTP

La chiave pubblica appena scaricata nel passaggio 7 della sezione precedente fa parte di una coppia di chiavi pubblica/privata utilizzata da Adobe per **caricare dati** sul server SFTP.

È necessario aggiungere questa chiave pubblica allo stesso file [!DNL `authorized_keys`] in cui è stata precedentemente aggiunta la chiave di download dell&#39;organizzazione (quella generata in [Passaggio 1: generare le chiavi SSH dell&#39;organizzazione per il download dei dati](#step-1-generate-your-organizations-ssh-keys-for-downloading-data)).

Per aggiungere la chiave pubblica SSH di Adobe al file [!DNL `authorized_keys`] e caricarlo sul server FTP:

1. Accedi alla workstation in cui scarichi i dati dal server FTP.

1. Apri il file [!DNL `authorized_keys`] e aggiungi la chiave di caricamento di Adobe. Questo file deve contenere già la chiave di download della tua organizzazione da [Passaggio 1: genera le chiavi SSH della tua organizzazione per scaricare i dati](#step-1-generate-your-organizations-ssh-keys-for-downloading-data).

1. Carica il file [!DNL `authorized_keys`] sul server FTP:

   1. Connettiti al server FTP e accedi con il tuo nome utente e la tua password.
Può trattarsi di un server FTP ospitato da Adobe o del tuo server FTP.
   1. Creare una directory [!DNL .ssh] (se non esiste già).
   1. Caricare il file [!DNL `authorized_keys`] nella directory [!DNL .ssh].

1. Aggiorna le impostazioni del firewall per consentire le connessioni in entrata dal server SFTP. Quando utilizzi un server SFTP ospitato da Adobe, consenti le connessioni in entrata dagli intervalli IP di Adobe sulla porta 22.

1. Verifica la connessione accedendo al server utilizzando il client SFTP.

1. Ripeti questo processo per ogni account SFTP creato nella sezione precedente, [Crea l&#39;account SFTP](#create-the-sftp-account).

1. Continua con la seguente sezione, [Aggiungi una posizione all&#39;interno dell&#39;account](#add-a-location-within-the-account).

#### Aggiungi una posizione all’interno dell’account

1. Nella scheda [!UICONTROL **Percorsi**], seleziona [!UICONTROL **Aggiungi percorso**].

1. Specifica un nome, una descrizione e se questa posizione verrà utilizzata con feed di dati o Data Warehouse.

1. Nel campo [!UICONTROL **Account località**], seleziona l&#39;account appena creato.

1. Nel campo [!UICONTROL **Percorso directory**], specifica il percorso della directory sul server SFTP. Le cartelle nel percorso devono esistere già. In caso contrario, si verifica un errore. Ad esempio: `/folder_name/folder_name`.

1. Seleziona [!UICONTROL **Salva**].

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


