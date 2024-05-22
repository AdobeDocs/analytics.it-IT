---
description: Passaggi che descrivono come creare una richiesta di Data Warehouse.
title: Configurare una destinazione di rapporto per una richiesta di Data Warehouse
feature: Data Warehouse
exl-id: 3c7faea3-4d90-4274-88f3-e9337c94155f
source-git-commit: 23d519975111dc43b515c6c5bc67d7001d05c0d8
workflow-type: tm+mt
source-wordcount: '2612'
ht-degree: 97%

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

   1. Seleziona l’account dal menu a discesa [!UICONTROL **Seleziona account**].

      È possibile utilizzare qualsiasi account cloud configurato in una delle seguenti aree di Adobe Analytics:

      * Durante l’importazione dei dati di classificazione di Adobe Analytics, come descritto nello [schema](/help/components/classifications/sets/manage/schema.md).

        Tuttavia, non è possibile utilizzare le posizioni configurate per l’importazione dei dati di classificazione. Aggiungi invece una nuova destinazione come descritto di seguito.

      * Durante la configurazione di account e posizioni nell’area delle posizioni, come descritto in [Configurare account cloud di importazione ed esportazione](/help/components/locations/configure-import-accounts.md) e [Configurare posizioni cloud di importazione ed esportazione](/help/components/locations/configure-import-locations.md).

   1. Seleziona la destinazione associata all’account dal menu a discesa [!UICONTROL **Seleziona destinazione**].<!-- Is this correct? -->

1. (Condizionale) Se non hai accesso a un account cloud già configurato in Adobe Analytics, puoi configurarne uno:

   1. Seleziona [!UICONTROL **Aggiungi account**], quindi specifica le seguenti informazioni:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Tipo di account**] | Seleziona il tuo tipo di account cloud. È consigliabile disporre di un singolo account per ogni tipo, con più posizioni secondo necessità all’interno di tale account. <p>Dopo aver scelto un tipo di account, vengono visualizzati i relativi campi specifici. </p> |
      | [!UICONTROL **Nome account**] | Specifica un nome per l’account. Questo nome viene visualizzato durante la creazione di una posizione. <!-- true? --> |
      | [!UICONTROL **Descrizione account**] | Fornisci una breve descrizione dell’account per distinguerlo da altri account dello stesso tipo. |

      Per le istruzioni di configurazione, espandi la sezione sotto, che corrisponde al [!UICONTROL **Tipo di account**] che hai selezionato.

      Utilizza uno dei seguenti tipi di account durante la configurazione di una destinazione di rapporto. Per istruzioni sulla configurazione, espandi il tipo di account. Sono disponibili anche ulteriori [destinazioni legacy](#legacy-destinations), ma non sono consigliate.

      +++Amazon S3

      Per configurare un account Amazon S3 con ruolo ARN, specifica le seguenti informazioni:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Ruolo ARN**] | È necessario fornire un ruolo ARN (nome risorsa Amazon - Amazon Resource Name) che Adobe può utilizzare per accedere all’account Amazon S3. A tale scopo, crea un criterio di autorizzazione IAM per l’account di origine, associa il criterio a un utente e quindi crea un ruolo per l’account di destinazione. Per informazioni specifiche, consulta [questa documentazione di AWS](https://repost.aws/it/knowledge-center/cross-account-access-iam).<p>Per informazioni su come impostare l’autorizzazione del bucket, consulta l’articolo [Come posso fornire l’accesso tra account diversi per gli oggetti che si trovano nei bucket di Amazon S3?](https://repost.aws/it/knowledge-center/cross-account-access-s3) nel knowledge center di Amazon. |
      | [!UICONTROL **Utente ARN**] | L’utente ARN (nome risorsa Amazon) è fornito da Adobe. È necessario collegare questo utente al criterio creato. |

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
      | [!UICONTROL **URI di Key Vault**] | <p>Percorso per l’URI SAS in Azure Key Vault.  Per configurare Azure SAS, è necessario memorizzare un URI SAS come segreto utilizzando Azure Key Vault. Per informazioni, consulta [Documentazione di Microsoft Azure su come impostare e recuperare un segreto da Azure Key Vault](https://learn.microsoft.com/it-it/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Dopo la creazione dell’URI di Key Vault:<ul><li>Aggiungi un criterio di accesso a Key Vault per concedere l’autorizzazione all’applicazione Azure creata.</li><li>Assicurati che all’ID applicazione sia stato assegnato il ruolo incorporato di `Key Vault Certificate User` per accedere all’URI di Key Vault</br><p>Per ulteriori informazioni, consulta [Ruoli incorporati di Azure](https://learn.microsoft.com/it-it/azure/role-based-access-control/built-in-roles).</p></li></ul><p>Per informazioni, consulta [Documentazione di Microsoft Azure su come assegnare un criterio di accesso a Key Vault](https://learn.microsoft.com/it-it/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
      | [!UICONTROL **Nome segreto di Key Vault**] | Nome segreto creato quando si aggiunge il segreto ad Azure Key Vault. In Microsoft Azure, queste informazioni si trovano nel Key Vault creato, nelle pagine delle impostazioni di **Key Vault**. Per informazioni, consulta [Documentazione di Microsoft Azure su come impostare e recuperare un segreto Azure Key Vault](https://learn.microsoft.com/it-it/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
      | [!UICONTROL **Segreto**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Certificati e segreti** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      Per configurare un account RBAC di Azure, specifica le informazioni seguenti:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **ID applicazione**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
      | [!UICONTROL **ID tenant**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
      | [!UICONTROL **Segreto**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Certificati e segreti** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++E-mail

      Per configurare un account e-mail, specifica le informazioni seguenti:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Recipients (Destinatari)**] | Le notifiche e-mail possono essere inviate a utenti specifici una volta inviato il rapporto. Specifica un singolo indirizzo e-mail o un elenco di indirizzi e-mail separati da virgole.<!-- How does this differ from the Notification email tab? --> |

   1. Seleziona [!UICONTROL **Aggiungi posizione**], quindi specifica le seguenti informazioni: 
|Campo | Funzione |
|---------|----------|
| [!UICONTROL **Nome**] | Il nome della posizione.   |
| [!UICONTROL **Descrizione**] | Fornisci una breve descrizione dell’account per distinguerlo da altri dello stesso tipo. |
| [!UICONTROL **Account posizione**] | Seleziona l’account della posizione che hai creato in [Aggiungi un account](#add-an-account). |

   1. Nella sezione [!UICONTROL **Proprietà posizione**], specifica le informazioni specifiche sul tipo di account dell’account di posizione.

      Per le istruzioni di configurazione, espandi la sezione seguente che corrisponde al [!UICONTROL **Tipo di account**] selezionato in precedenza.

      +++Amazon S3

      Per configurare una posizione Amazon S3, specifica le seguenti informazioni:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Nome del bucket**] | Il bucket all’interno dell’account Amazon S3 in cui desideri inviare i dati di Adobe Analytics. <p>Assicurati che l’utente ARN fornito da Adobe disponga dell’autorizzazione `S3:PutObject` per caricare i file in questo bucket. Questa autorizzazione consente all’utente ARN di caricare i file iniziali e di sovrascrivere i file per i caricamenti successivi.</p><p>I nomi dei bucket devono soddisfare regole di denominazione specifiche. Ad esempio, devono contenere da 3 a 63 caratteri, possono essere composte solo da lettere minuscole, numeri, punti (.) e trattini (-) e devono iniziare e terminare con una lettera o un numero. [Un elenco completo delle regole di denominazione è disponibile nella documentazione di AWS](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html?lang=it). </p> |
      | [!UICONTROL **Prefisso chiave**] | La cartella all’interno del bucket in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio, folder_name/ |

      {style="table-layout:auto"}

+++

      +++Google Cloud Platform

      Per configurare una posizione di Google Cloud Platform, specifica le informazioni seguenti:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Nome del bucket**] | Il bucket all’interno dell’account GCP in cui desideri inviare i dati di Adobe Analytics. <p>Accertati di aver concesso una delle seguenti autorizzazioni all’entità fornita dall’Adobe: (per informazioni sulla concessione delle autorizzazioni, consulta [Aggiungere un’entità a un criterio a livello di bucket](https://cloud.google.com/storage/docs/access-control/using-iam-permissions?hl=it#bucket-add) nella documentazione di Google Cloud.)<ul><li>`roles/storage.objectCreator`: utilizza questa autorizzazione se desideri limitare l’entità principale alla sola creazione di file nell’account GCP. </br>**Importante:** se utilizzi questa autorizzazione per il reporting pianificato, utilizza un nome file univoco per ogni nuova esportazione pianificata. In caso contrario, la generazione dei rapporti non riuscirà perché l’entità principale non ha accesso alla sovrascrittura dei file esistenti.</li><li>`roles/storage.objectUser`: utilizza questa autorizzazione se desideri che l’entità principale abbia accesso alla visualizzazione, all’elenco, all’aggiornamento e all’eliminazione dei file nel tuo account GCP.</br>Questa autorizzazione consente all’entità principale di sovrascrivere i file esistenti per i caricamenti successivi, senza la necessità di generare automaticamente nomi di file univoci per ogni nuova esportazione pianificata.</li></ul><p>Se l’organizzazione utilizza [Vincoli dei criteri di organizzazione](https://cloud.google.com/storage/docs/org-policy-constraints) per consentire solo l’account Google Cloud Platform nel tuo elenco consentiti, è necessario il seguente ID organizzazione di proprietà dell’Adobe Google Cloud Platform: <ul><li>`DISPLAY_NAME`: `adobe.com`</li><li>`ID`: `178012854243`</li><li>`DIRECTORY_CUSTOMER_ID`: `C02jo8puj`</li></ul> </p> |
      | [!UICONTROL **Prefisso chiave**] | La cartella all’interno del bucket in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio, folder_name/ |

      {style="table-layout:auto"}

+++

      +++Azure SAS

      Per configurare una posizione SAS di Azure, specifica le informazioni seguenti:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Nome contenitore**] | Il contenitore all’interno dell’account specificato nel punto in cui desideri inviare i dati di Adobe Analytics. |
      | [!UICONTROL **Prefisso chiave**] | La cartella all’interno del contenitore in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio: `folder_name/`<p>Accertati che l’archivio dell’URI SAS specificato nel campo nome segreto di Key Vault durante la configurazione dell’account SAS di Azure abbia l’autorizzazione `Write`. Questo consente all’URI SAS di creare file nel contenitore Azure. <p>Se desideri che l’URI SAS sovrascriva anche i file, assicurati che l’archivio dell’URI SAS disponga dell’autorizzazione `Delete`.</p><p>Per ulteriori informazioni, consulta [Risorse di archiviazione BLOB](https://learn.microsoft.com/it-it/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources) nella documentazione dell’archiviazione BLOB di Azure.</p> |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      Per configurare una posizione RBAC di Azure, specifica le informazioni seguenti:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Nome contenitore**] | Il contenitore all’interno dell’account specificato nel punto in cui desideri inviare i dati di Adobe Analytics. Assicurati di concedere le autorizzazioni per caricare i file nell’applicazione Azure creata in precedenza. |
      | [!UICONTROL **Prefisso chiave**] | La cartella all’interno del contenitore in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio: `folder_name/`<p>Accertati che l’ID applicazione specificato durante la configurazione dell’account RBAC di Azure disponga del ruolo `Storage Blob Data Contributor` per accedere al contenitore (cartella).</p> <p>Per ulteriori informazioni, consulta [Ruoli incorporati di Azure](https://learn.microsoft.com/it-it/azure/role-based-access-control/built-in-roles).</p> |
      | [!UICONTROL **Nome account**] | L’account di archiviazione Azure. |

      {style="table-layout:auto"}

+++

1. Continua a configurare la richiesta del Data Warehouse nella scheda [!UICONTROL **Opzioni rapporto**]. Per ulteriori informazioni, consulta [Configurare le opzioni del rapporto per una richiesta al Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-options.md).

## Destinazioni legacy

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

* [!UICONTROL **Utilizza estensioni di file temporanee durante il caricamento**]: quando questa opzione è abilitata, durante il processo di caricamento viene utilizzata l’estensione file `.part`. Mantieni attiva questa opzione a meno che il server SFTP non limiti la modifica dei nomi dei file al termine del caricamento.

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
