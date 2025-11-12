---
description: Passaggi che descrivono come creare una richiesta di Data Warehouse.
title: Configurare una destinazione di rapporto per una richiesta di Data Warehouse
feature: Data Warehouse
exl-id: 3c7faea3-4d90-4274-88f3-e9337c94155f
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '1977'
ht-degree: 81%

---

# Configurare una destinazione di rapporto per una richiesta di Data Warehouse

Durante la creazione di una richiesta di Data Warehouse, sono disponibili varie opzioni di configurazione. Le informazioni seguenti descrivono come configurare una destinazione di rapporto per la richiesta.

Per informazioni su come iniziare a creare una richiesta, nonché collegamenti ad altre importanti opzioni di configurazione, consulta [Creare una richiesta di Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

>[!NOTE]
>
>Quando configuri la destinazione di rapporto, tieni presente quanto segue:
>
>* È consigliabile utilizzare un account cloud o un’ e-mail per la destinazione di rapporto. [Gli account legacy FTP e SFTP](#legacy-destinations) sono disponibili ma non sono consigliati.
>
>* Tutti gli account cloud configurati in precedenza possono essere utilizzati per Data Warehouse. Puoi configurare gli account cloud in uno dei seguenti modi:
>
>   * Durante la configurazione dei [feed di dati](/help/export/analytics-data-feed/create-feed.md)
>   
>   * Durante l’[importazione dei dati di classificazione di Adobe Analytics](/help/components/locations/locations-manager.md) (è possibile utilizzare gli account, ma non le posizioni configurate in tali account.)
>   
>   * Dalla gestione delle posizioni, in [Componenti > Posizioni](/help/components/locations/configure-import-accounts.md).
>
>* Gli account cloud sono associati al tuo account utente di Adobe Analytics. Gli altri utenti non possono utilizzare o visualizzare gli account cloud che configuri.
>
>* È possibile modificare qualsiasi posizione creata dalla gestione delle posizioni in [Componenti > Posizioni](/help/components/locations/configure-import-accounts.md)

Per configurare la destinazione in cui vengono inviati i rapporti Data Warehouse:

1. Se non l’hai ancora fatto, inizia a creare una richiesta in Adobe Analytics selezionando **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Aggiungi**].

   Per ulteriori dettagli, consulta [Creare una richiesta di Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Nella pagina Nuova richiesta di Data Warehouse, seleziona la scheda [!UICONTROL **Destinazione del rapporto**].

   ![Scheda Destinazione rapporto](assets/dw-report-destination.png)

1. (Condizionale) Se hai già configurato un account cloud (e una relativa destinazione) in Adobe Analytics, che desideri utilizzare come destinazione del rapporto:

   >[!NOTE]
   >
   >Gli account sono disponibili solo se sono stati configurati o se sono stati condivisi con un’organizzazione di cui fai parte.
   >
   >Se sei un amministratore di sistema, è disponibile l’opzione [!UICONTROL **Mostra tutte le destinazioni**]. Abilita questa opzione se desideri avere accesso a tutti gli account e a tutte le posizioni creati da qualsiasi utente dell’organizzazione.

   1. Selezionare l&#39;account dal menu a discesa [!UICONTROL **Account**].

      È possibile utilizzare qualsiasi account cloud configurato in una delle seguenti aree di Adobe Analytics:

      * Durante l’importazione dei dati di classificazione di Adobe Analytics, come descritto nello [schema](/help/components/classifications/sets/manage/schema.md).

        Tuttavia, non è possibile utilizzare le posizioni configurate per l’importazione dei dati di classificazione. Aggiungi invece una nuova destinazione come descritto di seguito.

      * Durante la configurazione di account e posizioni nell’area delle posizioni, come descritto in [Configurare account cloud di importazione ed esportazione](/help/components/locations/configure-import-accounts.md) e [Configurare posizioni cloud di importazione ed esportazione](/help/components/locations/configure-import-locations.md).

   1. Seleziona la destinazione associata all’account dal menu a discesa [!UICONTROL **Seleziona destinazione**].<!-- Is this correct? -->

1. (Condizionale) Se non hai accesso a un account cloud già configurato in Adobe Analytics, puoi configurarne uno:

   1. Seleziona il menu a discesa [!UICONTROL **Account**], quindi seleziona [!UICONTROL **Aggiungi account**].

   1. Nella finestra di dialogo Aggiungi account specificare le informazioni seguenti:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Nome account località**] | Nome dell&#39;account di posizione. Questo nome viene visualizzato durante la creazione di una posizione |
      | [!UICONTROL **Descrizione account località**] | Fornisci una breve descrizione dell’account per distinguerlo da altri account dello stesso tipo. |
      | [!UICONTROL **Rendi l&#39;account disponibile a tutti gli utenti dell&#39;organizzazione**] | Abilita questa opzione per consentire ad altri utenti dell’organizzazione di utilizzare l’account.<p>Quando condividi gli account, tieni presente quanto segue:</p><ul><li>Gli account condivisi non possono essere non condivisi.</li><li>Gli account condivisi possono essere modificati solo dal proprietario dell&#39;account.</li><li>Chiunque può creare una posizione per l&#39;account condiviso.</li></ul> |
      | [!UICONTROL **Tipo di account**] | Seleziona il tuo tipo di account cloud. È consigliabile disporre di un singolo account per ogni tipo, con più posizioni secondo necessità all’interno di tale account.<p>Gli amministratori di sistema possono limitare i tipi di account che possono essere creati dagli utenti, come descritto in [Specificare se gli utenti possono creare account](/help/components/locations/locations-manager.md#configure-whether-users-can-create-accounts). Se non è possibile creare gli account come descritto in questa sezione, contattare l&#39;amministratore di sistema.</p> |

   1. Nella sezione [!UICONTROL **Proprietà account**], specifica informazioni specifiche sul tipo di account selezionato.

      Per istruzioni di configurazione, espandere la sezione seguente che corrisponde al tipo di account [!UICONTROL **selezionato**]. Sono disponibili anche altri tipi di account legacy, ma non sono consigliati.

      **Tipi di account**

      +++Amazon S3 con ruolo ARN

      **NOTA:** quando si utilizza Amazon S3 con Data Warehouse, è supportata solo la crittografia SSE-S3.

      Per configurare un account Amazon S3 con ruolo ARN, specifica le seguenti informazioni:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Ruolo ARN**] | È necessario fornire un ruolo ARN (nome risorsa Amazon - Amazon Resource Name) che Adobe può utilizzare per accedere all’account Amazon S3. A tale scopo, crea un criterio di autorizzazione IAM per l’account di origine, associa il criterio a un utente e quindi crea un ruolo per l’account di destinazione. Per informazioni specifiche, consulta [questa documentazione di AWS](https://repost.aws/it/knowledge-center/cross-account-access-iam). |

      {style="table-layout:auto"}

      +++

      +++Google Cloud Platform

      Per configurare un account di Google Cloud Platform, specifica le seguenti informazioni:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **ID Progetto**] | ID personale progetto Google Cloud. Consulta la [Documentazione di Google Cloud su come ottenere un ID progetto](https://cloud.google.com/resource-manager/docs/creating-managing-projects?hl=it#identifying_projects). |

      {style="table-layout:auto"}

      +++

      +++Azure SAS

      Per configurare un account SAS di Azure, specifica le informazioni seguenti:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **ID applicazione**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
      | [!UICONTROL **ID tenant**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
      | [!UICONTROL **URI di Key Vault**] | <p>Percorso per il token SAS in Azure Key Vault.  Per configurare Azure SAS, è necessario memorizzare un token SAS come segreto utilizzando Azure Key Vault. Per informazioni, consulta [Documentazione di Microsoft Azure su come impostare e recuperare un segreto da Azure Key Vault](https://learn.microsoft.com/it-it/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Dopo la creazione dell’URI dell’insieme di credenziali delle chiavi, aggiungi un criterio di accesso nell’insieme di credenziali delle chiavi per concedere l’autorizzazione all’applicazione Azure creata. Per informazioni, consulta [Documentazione di Microsoft Azure su come assegnare un criterio di accesso a Key Vault](https://learn.microsoft.com/it-it/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p><p>Oppure</p><p>Se si desidera concedere direttamente un ruolo di accesso senza creare un criterio di accesso, vedere la [documentazione di Microsoft Azure relativa all&#39;assegnazione dei ruoli di Azure tramite il portale di Azure](https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal). Questo aggiunge l’assegnazione del ruolo per l’ID applicazione per accedere all’URI dell’insieme di credenziali delle chiavi. </p> |
      | [!UICONTROL **Nome segreto di Key Vault**] | Nome segreto creato quando si aggiunge il segreto all&#39;insieme di credenziali delle chiavi di Azure. In Microsoft Azure, queste informazioni si trovano nell&#39;insieme di credenziali delle chiavi creato, nella pagina delle impostazioni di **Insieme di credenziali delle chiavi**. Per informazioni, consulta [Documentazione di Microsoft Azure su come impostare e recuperare un segreto da Azure Key Vault](https://learn.microsoft.com/it-it/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
      | [!UICONTROL **Segreto account località**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Certificati e segreti** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |

      {style="table-layout:auto"}

      +++   

      +++Azure RBAC

      Per configurare un account RBAC di Azure, specifica le informazioni seguenti:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **ID applicazione**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
      | [!UICONTROL **ID tenant**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
      | [!UICONTROL **Segreto account località**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Certificati e segreti** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |

      {style="table-layout:auto"}

      +++

      +++E-mail

      >[!NOTE]
      >
      >Gli account di posta elettronica possono essere utilizzati solo con [Feed dati](/help/export/analytics-data-feed/create-feed.md). (Gli account di posta elettronica non sono supportati con [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) o [Set di classificazione](/help/components/classifications/sets/overview.md)).

      Per configurare un account RBAC di Azure, specifica le informazioni seguenti:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Recipients (Destinatari)**] | Le notifiche e-mail possono essere inviate a utenti specifici una volta inviato il rapporto. Specifica un singolo indirizzo e-mail o un elenco di indirizzi e-mail separati da virgole. |

      {style="table-layout:auto"}

      +++

1. Continua a configurare la richiesta del Data Warehouse nella scheda [!UICONTROL **Opzioni rapporto**]. Per ulteriori informazioni, consulta [Configurare le opzioni del rapporto per una richiesta al Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-options.md).

## Tipi di account legacy

>[!IMPORTANT]
>
>Le destinazioni descritte in questa sezione sono legacy e non sono consigliate. Al contrario, durante la creazione di una destinazione di Data Warehouse, utilizza una delle seguenti destinazioni: Amazon S3, Google Cloud Platform, Azure RBAC, Azure SAS o E-mail. Le informazioni qui sopra forniscono dettagli su diascuna di queste destinazioni consigliate.

Le informazioni seguenti forniscono informazioni di configurazione per ciascuna destinazione legacy:

### FTP

I dati di Data Warehouse possono essere inviati a una posizione Adobe o FTP ospitata dal cliente. Richiede un host FTP, un nome utente e una password. Utilizza il campo del percorso per inserire i file di feed in una cartella. Le cartelle devono già esistere. I feed generano un errore se il percorso specificato non esiste.

Per completare i campi disponibili, utilizza le seguenti informazioni:

#### Campi account

* [!UICONTROL **Nome account**]: nome dell’account FTP.

* [!UICONTROL **Descrizione account**]: descrizione dell’account FTP.

* [!UICONTROL **Nome host**]: immetti l’URL della destinazione FTP desiderata. Esempio: `ftp.company.com`.

  >[!NOTE]
  >
  >  Non includere `ftp://` all’inizio dell’URL.

* [!UICONTROL **Nome utente**]: immetti il nome utente per accedere al sito FTP.

* [!UICONTROL **Password e conferma password**]: immetti la password per accedere al sito FTP.

#### Campi posizione

* [!UICONTROL **Nome posizione**]: nome della posizione sull’account FTP dove desideri inviare i file.

* [!UICONTROL **Descrizione della posizione**]: descrizione della posizione sull’account FTP.

* [!UICONTROL **Percorso directory**]: percorso della posizione sull’account FTP.

### SFTP

Per Data Warehouse, è disponibile il supporto SFTP. Richiede un host SFTP, un nome utente e il sito di destinazione per contenere una chiave pubblica RSA o DSA valida. Puoi scaricare la chiave pubblica adatta al momento della creazione della destinazione di Data Warehouse.

Per completare i campi disponibili, utilizza le seguenti informazioni:

#### Campi account

* [!UICONTROL **Nome account**]: nome dell’account FTP.

* [!UICONTROL **Descrizione account**]: descrizione dell’account FTP.

* [!UICONTROL **Nome host**]: immetti l’URL di destinazione SFTP desiderato. Esempio: `sftp.company.com`.

  >[!NOTE]
  >
  >  Non includere `sftp://` all’inizio dell’URL.

* [!UICONTROL **Nome utente**]: immetti il nome utente per accedere al sito SFTP.

* [!UICONTROL **Utilizza estensioni di file temporanee durante il caricamento**]: quando questa opzione è abilitata, durante il processo di caricamento viene utilizzata l’estensione file `.part`. Mantieni abilitata questa opzione a meno che il server SFTP non limiti la modifica dei nomi dei file al termine del caricamento.

* [!UICONTROL **Chiavi pubbliche**]: scarica la chiave pubblica appropriata durante la creazione della destinazione del Data Warehouse.

#### Campi posizione

* [!UICONTROL **Nome posizione**]: nome della posizione sull’account SFTP dove desideri inviare i file.

* [!UICONTROL **Descrizione della posizione**]: descrizione della posizione sull’account SFTP.

* [!UICONTROL **Percorso directory**]: percorso della posizione sull’account SFTP.

Per ulteriori informazioni sulla configurazione SFTP, consulta [Inviare richieste di Data Warehouse ai server SFTP](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md).

### S3

Puoi inviare i dati di Data Warehouse direttamente ai bucket Amazon S3. Questo tipo di destinazione richiede un nome bucket, un ID chiave di accesso e una chiave segreto. Consulta [Requisiti di denominazione del bucket Amazon S3](https://docs.aws.amazon.com/it_it/AmazonS3/latest/userguide/bucketnamingrules.html) nella documentazione di Amazon S3 per ulteriori informazioni.

L’utente fornito per il caricamento dei dati di Data Warehouse deve disporre delle seguenti [autorizzazioni](https://docs.aws.amazon.com/it_it/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html):

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

Sono supportate le seguenti 16 aree geografiche standard di AWS (utilizzando l’algoritmo di firma appropriato, se necessario):

* us-east-2
* us-east-1
* us-west-1
* us-west-2
* ap-south-1
* ap-northeast-2
* ap-southeast-1
* ap-southeast-2
* ap-northeast-1
* ca-central-1
* eu-central-1
* eu-west-1
* eu-west-2
* eu-west-3
* eu-north-1
* sa-east-1

>[!NOTE]
>
>L’area geografica cn-north-1 non è supportata.

### BLOB di Azure

Data warehouse supporta le destinazioni BLOB di Azure. Richiede un contenitore, un account e una chiave. Amazon crittografa automaticamente i dati inattivi. Quando scarichi i dati, questi vengono decrittografati automaticamente. Per ulteriori informazioni, consulta [Creare un account di archiviazione](https://learn.microsoft.com/it-it/azure/storage/common/storage-account-create?tabs=azure-portal#view-and-copy-storage-access-keys) nelle documentazioni di Microsoft Azure.

>[!NOTE]
>
>È necessario implementare un processo personalizzato per gestire lo spazio su disco nella destinazione di Data Warehouse. Adobe non elimina dati dal server.
