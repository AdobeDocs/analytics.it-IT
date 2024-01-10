---
description: Passaggi che descrivono come creare una richiesta Data Warehouse.
title: Configurare una destinazione di rapporto per una richiesta Data Warehouse
feature: Data Warehouse
exl-id: 3c7faea3-4d90-4274-88f3-e9337c94155f
source-git-commit: baac0c0384b714cf2ca536149ca10eec3a7065ad
workflow-type: tm+mt
source-wordcount: '2201'
ht-degree: 2%

---

# Configurare una destinazione di rapporto per una richiesta Data Warehouse

Durante la creazione di una richiesta Data Warehouse sono disponibili varie opzioni di configurazione. Le informazioni seguenti descrivono come configurare una destinazione di rapporto per la richiesta.

Per informazioni su come iniziare a creare una richiesta, nonché collegamenti ad altre importanti opzioni di configurazione, vedi [Creare una richiesta Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

>[!NOTE]
>
>Quando configuri una destinazione di rapporto, tieni presente quanto segue:
>
>* È consigliabile utilizzare un account cloud o un messaggio e-mail per la destinazione del rapporto. Gli account FTP e SFTP legacy sono disponibili ma non sono consigliati.
>
>* Gli account cloud sono associati al tuo account utente di Adobe Analytics. Gli altri utenti non possono utilizzare o visualizzare gli account cloud configurati dall’utente.
>
>* Tutti gli account cloud che hai precedentemente [configurato per feed dati](/help/export/analytics-data-feed/create-feed.md) sono disponibili per l’utilizzo in Data Warehouse.
>
>* Account cloud configurati per [importazione dei dati di classificazione di Adobe Analytics](/help/components/locations/locations-manager.md) da una destinazione cloud può essere utilizzato durante la configurazione di una destinazione di rapporto. Tuttavia, non è possibile utilizzare le posizioni configurate per l’importazione dei dati di classificazione.

Per configurare la destinazione in cui vengono inviati i rapporti Data Warehouse:

1. Inizia a creare una richiesta in Adobe Analytics selezionando **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Aggiungi**].

   Per ulteriori dettagli, vedi [Creare una richiesta Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Nella pagina Nuova richiesta Data Warehouse, seleziona la [!UICONTROL **Destinazione del rapporto**] scheda.

   ![Scheda Destinazione rapporto](assets/dw-report-destination.png)

1. (Condizionale) Se è già stato configurato un account (e una destinazione su tale account) che desideri utilizzare come destinazione del rapporto:

   1. (Facoltativo) Se sei un amministratore di sistema, il [!UICONTROL **Mostra tutte le destinazioni**] è disponibile. Abilita questa opzione se desideri avere accesso a tutti gli account e a tutte le posizioni creati da qualsiasi utente dell’organizzazione.

   1. Seleziona l’account da [!UICONTROL **Seleziona account**] menu a discesa.

      Qualsiasi account cloud configurato per [importazione dei dati di classificazione di Adobe Analytics](/help/components/locations/locations-manager.md) da una destinazione cloud sono mostrati qui e possono essere utilizzati. Tuttavia, non è possibile utilizzare le posizioni configurate per l’importazione dei dati di classificazione. Aggiungi invece una nuova destinazione come descritto di seguito.

   1. Seleziona la destinazione associata all’account da [!UICONTROL **Seleziona destinazione**] menu a discesa. <!-- Is this correct? -->

1. (Condizionale) Se non hai configurato in precedenza un account:

   1. Seleziona [!UICONTROL **Aggiungi account**], quindi specifica le seguenti informazioni:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Tipo di account**] | Seleziona il tipo di account cloud. È consigliabile disporre di un singolo account per ogni tipo di account, con più posizioni in base alle esigenze all’interno dell’account. <p>Dopo aver scelto un tipo di conto, vengono visualizzati i campi specifici per tale tipo di conto. </p> |
      | [!UICONTROL **Nome account**] | Specifica un nome per l’account. Questo nome viene visualizzato durante la creazione di una posizione. <!-- true? --> |
      | [!UICONTROL **Descrizione account**] | Fornisci una breve descrizione dell’account per distinguerlo da altri account dello stesso tipo. |

      Per le istruzioni di configurazione, espandi la sezione seguente che corrisponde a [!UICONTROL **Tipo di account**] che hai selezionato.

      Utilizza uno dei seguenti tipi di account durante la configurazione di una destinazione di rapporto. Per istruzioni di configurazione, espandi il tipo di account. (aggiuntivo [destinazioni legacy](#legacy-destinations) sono disponibili, ma non sono consigliati.)

      +++Amazon S3

      Specifica le seguenti informazioni per configurare un account ARN per il ruolo Amazon S3:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **ARN per ruolo**] | È necessario fornire un ARN per il ruolo (Amazon Resource Name) che l’Adobe può utilizzare per accedere all’account Amazon S3. A tale scopo, creare un criterio di autorizzazione IAM per l&#39;account di origine, associare il criterio a un utente e quindi creare un ruolo per l&#39;account di destinazione. Per informazioni specifiche, consulta [questa documentazione di AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/).<p>Per informazioni su come impostare l’autorizzazione del bucket, consulta l’articolo [Come posso fornire l’accesso tra account diversi per gli oggetti che si trovano nei bucket di Amazon S3?](https://repost.aws/knowledge-center/cross-account-access-s3) nel knowledge center di Amazon. |
      | [!UICONTROL **ARN utente**] | L’ARN utente (Amazon Resource Name) è fornito da Adobe. È necessario collegare questo utente al criterio creato. |

      {style="table-layout:auto"}

+++

      +++Piattaforma cloud Google

      Specifica le seguenti informazioni per configurare un account di Google Cloud Platform:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **ID Progetto**] | ID progetto Google Cloud. Consulta la [Documentazione di Google Cloud sull’ottenimento di un ID progetto](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

      {style="table-layout:auto"}

+++

      +++SAS di Azure

      Specificare le informazioni seguenti per configurare un account SAS di Azure:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **ID applicazione**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Panoramica** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **ID tenant**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Panoramica** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **URI insieme di credenziali delle chiavi**] | <p>Percorso del token SAS nell&#39;insieme di credenziali delle chiavi di Azure.  Per configurare Azure SAS, è necessario memorizzare un token SAS come segreto utilizzando Azure Key Vault. Per informazioni, vedere [Documentazione di Microsoft Azure su come impostare e recuperare un segreto dall&#39;insieme di credenziali delle chiavi di Azure](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Dopo la creazione dell’URI dell’insieme di credenziali delle chiavi, aggiungi un criterio di accesso nell’insieme di credenziali delle chiavi per concedere l’autorizzazione all’applicazione Azure creata. Per informazioni, vedere [Documentazione di Microsoft Azure su come assegnare un criterio di accesso all’insieme di credenziali delle chiavi](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
      | [!UICONTROL **Nome segreto archivio chiavi**] | Nome segreto creato quando si aggiunge il segreto all&#39;insieme di credenziali delle chiavi di Azure. In Microsoft Azure, queste informazioni si trovano nell&#39;insieme di credenziali delle chiavi creato, nel **Key Vault** pagine delle impostazioni. Per informazioni, vedere [Documentazione di Microsoft Azure su come impostare e recuperare un segreto dall&#39;insieme di credenziali delle chiavi di Azure](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
      | [!UICONTROL **Segreto**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Certificati e segreti** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      Specificare le informazioni seguenti per configurare un account RBAC di Azure:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **ID applicazione**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Panoramica** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **ID tenant**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Panoramica** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **Segreto**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Certificati e segreti** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++E-mail

      Specifica le seguenti informazioni per configurare un account e-mail:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Recipients (Destinatari)**] | Le notifiche e-mail possono essere inviate a utenti specifici quando il rapporto viene inviato. Specifica un singolo indirizzo e-mail o un elenco di indirizzi e-mail separati da virgole. <!-- How does this differ from the Notification email tab? --> |

   1. Seleziona [!UICONTROL **Aggiungi posizione**], quindi specifica le seguenti informazioni: |Campo | Funzione | ---------- --------- | [!UICONTROL **Nome**] | Nome della posizione.  | | [!UICONTROL **Descrizione**] | Fornisci una breve descrizione dell’account per distinguerlo da altri account dello stesso tipo. | | [!UICONTROL **Account località**] | Selezionare il conto ubicazione creato in [Aggiungi un account](#add-an-account). |

   1. In [!UICONTROL **Proprietà posizione**] , specificare informazioni specifiche sul tipo di account dell&#39;account di posizione.

      Per le istruzioni di configurazione, espandi la sezione seguente che corrisponde a [!UICONTROL **Tipo di account**] selezionato in precedenza.

      +++Amazon S3

      Per configurare un percorso Amazon S3, specifica le seguenti informazioni:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Nome bucket**] | Il bucket all’interno dell’account Amazon S3 in cui desideri inviare i dati di Adobe Analytics. Assicurati che l’ARN utente fornito da Adobe abbia accesso al caricamento di file in questo bucket. |
      | [!UICONTROL **Prefisso chiave**] | La cartella all’interno del bucket in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio, nome_cartella/ |

      {style="table-layout:auto"}

+++

      +++Piattaforma cloud Google

      Per configurare il percorso di una piattaforma Google Cloud, specifica le seguenti informazioni:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Nome bucket**] | Il bucket all’interno dell’account GCP in cui desideri inviare i dati di Adobe Analytics. Assicurati di aver concesso all’entità fornita da Adobe l’autorizzazione per caricare i file in questo bucket. Per informazioni sulla concessione delle autorizzazioni, consulta [Aggiungere un’entità a un criterio a livello di bucket](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) nella documentazione di Google Cloud. |
      | [!UICONTROL **Prefisso chiave**] | La cartella all’interno del bucket in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio, nome_cartella/ |

      {style="table-layout:auto"}

+++

      +++SAS di Azure

      Specificare le informazioni seguenti per configurare un percorso SAS di Azure:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Nome contenitore**] | Il contenitore all’interno dell’account specificato nel punto in cui desideri inviare i dati di Adobe Analytics. |
      | [!UICONTROL **Prefisso chiave**] | La cartella all’interno del contenitore in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio: `folder_name/` |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      Specificare le informazioni seguenti per configurare un percorso RBAC di Azure:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Nome contenitore**] | Il contenitore all’interno dell’account specificato nel punto in cui desideri inviare i dati di Adobe Analytics. Accertati di concedere le autorizzazioni per caricare i file nell’applicazione Azure creata in precedenza. |
      | [!UICONTROL **Prefisso chiave**] | La cartella all’interno del contenitore in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio: `folder_name/` |
      | [!UICONTROL **Nome account**] | Account di archiviazione Azure. |

      {style="table-layout:auto"}

+++

   1. Seleziona [!UICONTROL **Salva**].

      Ora puoi importare i dati nell’account e nella posizione configurati.

1. Continua a configurare la richiesta Data Warehouse in [!UICONTROL **Opzioni di report**] scheda. Per ulteriori informazioni, consulta [Configurare le opzioni di rapporto per una richiesta Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-options.md).

## Destinazioni legacy

>[!IMPORTANT]
>
>Le destinazioni descritte in questa sezione sono legacy e non sono consigliate. Al contrario, utilizza una delle seguenti destinazioni durante la creazione di una destinazione di data warehouse: Amazon S3, Google Cloud Platform, Azure RBAC, Azure SAS o E-mail. Per informazioni dettagliate su ciascuna di queste destinazioni consigliate, consulta le informazioni precedenti.

Le informazioni seguenti forniscono informazioni di configurazione per ciascuna destinazione legacy:

### FTP

I dati di data warehouse possono essere inviati a un Adobe o a una posizione FTP ospitata dal cliente. Richiede un host FTP, un nome utente e una password. Utilizza il campo percorso per inserire i file di feed in una cartella. Le cartelle devono già esistere. I feed generano un errore se il percorso specificato non esiste.

Per completare i campi disponibili, utilizza le seguenti informazioni:

#### Campi account

* [!UICONTROL **Nome account**]: nome dell’account FTP.

* [!UICONTROL **Descrizione account**]: descrizione dell’account FTP.

* [!UICONTROL **Nome host**]: immetti l’URL di destinazione FTP desiderato. Esempio: `ftp.company.com`.

  >[!NOTE]
  >
  >  Non includere `ftp://` all’inizio dell’URL.

* [!UICONTROL **Nome utente**]: immetti il nome utente per accedere al sito FTP.

* [!UICONTROL **Password e conferma password**]: immetti la password per accedere al sito FTP.

#### Campi posizione

* [!UICONTROL **Nome posizione**]: nome del percorso sull’account FTP in cui desideri inviare i file.

* [!UICONTROL **Descrizione della posizione**]: descrizione della posizione sull’account FTP.

* [!UICONTROL **Percorso directory**]: percorso della posizione sull’account FTP.

### SFTP

È disponibile il supporto SFTP per data warehouse. Richiede un host SFTP, un nome utente e il sito di destinazione per contenere una chiave pubblica RSA o DSA valida. Puoi scaricare la chiave pubblica appropriata durante la creazione della destinazione del data warehouse.

Per completare i campi disponibili, utilizza le seguenti informazioni:

#### Campi account

* [!UICONTROL **Nome account**]: nome dell’account FTP.

* [!UICONTROL **Descrizione account**]: descrizione dell’account FTP.

* [!UICONTROL **Nome host**]: immetti l’URL di destinazione SFTP desiderato. Esempio: `sftp.company.com`.

  >[!NOTE]
  >
  >  Non includere `sftp://` all’inizio dell’URL.

* [!UICONTROL **Nome utente**]: immetti il nome utente per accedere al sito SFTP.

* [!UICONTROL **Utilizzare estensioni di file temporanee durante il caricamento**]: quando questa opzione è abilitata, `.part` durante il processo di caricamento viene utilizzata l’estensione file. Mantieni attiva questa opzione a meno che il server SFTP non limiti la modifica dei nomi dei file al termine del caricamento.

* [!UICONTROL **Chiavi pubbliche**]: scarica la chiave pubblica appropriata durante la creazione della destinazione del data warehouse.

#### Campi posizione

* [!UICONTROL **Nome posizione**]: nome della posizione sull’account SFTP in cui desideri inviare i file.

* [!UICONTROL **Descrizione della posizione**]: descrizione della posizione sull’account SFTP.

* [!UICONTROL **Percorso directory**]: percorso della posizione sull’account SFTP.

Per ulteriori informazioni sulla configurazione SFTP, vedi [Inviare richieste Data Warehouse ai server SFTP](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md).

### S3

Puoi inviare i dati di magazzino direttamente ai bucket Amazon S3. Questo tipo di destinazione richiede un nome bucket, un ID chiave di accesso e una chiave segreta. Consulta [Requisiti di denominazione del bucket Amazon S3](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) nella documentazione di Amazon S3 per ulteriori informazioni.

L’utente fornito per il caricamento dei dati del data warehouse deve disporre dei seguenti [autorizzazioni](https://docs.aws.amazon.com/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html):

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
>L&#39;area cn-north-1 non è supportata.

### BLOB di Azure

Data warehouse supporta le destinazioni BLOB di Azure. Richiede un contenitore, un account e una chiave. Amazon crittografa automaticamente i dati inattivi. Quando scarichi i dati, questi vengono decrittografati automaticamente. Consulta [Creare un account di archiviazione](https://docs.microsoft.com/en-us/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) nei documenti di Microsoft Azure per ulteriori informazioni.

>[!NOTE]
>
>È necessario implementare un processo personalizzato per gestire lo spazio su disco nella destinazione del data warehouse. Adobe non elimina dati dal server.
