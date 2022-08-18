---
title: Creare o modificare un feed dati
description: Scopri come creare o modificare un feed di dati.
feature: Data Feeds
exl-id: 36c8a40e-6137-4836-9d4b-bebf17b932bc
source-git-commit: 60335be9a60b467969f5e1796ce465a7d453951f
workflow-type: tm+mt
source-wordcount: '1514'
ht-degree: 4%

---

# Creare o modificare un feed dati

La creazione di un feed dati consente ad Adobe di sapere dove inviare i file di dati non elaborati e cosa si desidera includere in ciascun file. In questa pagina sono elencate le singole impostazioni che è possibile personalizzare durante la creazione di un feed di dati.

Prima di leggere questa pagina è consigliabile conoscere i feed di dati di base. Vedi [Panoramica sui feed dati](data-feed-overview.md) per essere certi di soddisfare i requisiti per la creazione di un feed di dati.

## Campi di informazioni sui feed

* **Nome**: Nome del feed di dati. Deve essere univoco all’interno della suite di rapporti selezionata e può contenere fino a 255 caratteri.
* **Suite di rapporti:** La suite di rapporti su cui si basa il feed di dati. Se vengono creati più feed di dati per la stessa suite di rapporti, devono avere definizioni di colonna diverse. Solo le suite di rapporti di origine supportano i feed di dati; le suite di rapporti virtuali non sono supportate.
* **Invia e-mail al completamento**: L’indirizzo e-mail da notificare al termine dell’elaborazione di un feed. L’indirizzo e-mail deve essere formattato correttamente.
* **Intervallo di feed**: I feed orari contengono dati di un&#39;ora. I feed giornalieri contengono dati del valore di una giornata intera; includono dati da mezzanotte a mezzanotte nel fuso orario della suite di rapporti.
* **Elaborazione ritardata**: Attendi un periodo di tempo specificato prima di elaborare un file di feed di dati. Un ritardo può essere utile per dare alle implementazioni mobili un’opportunità per i dispositivi offline di venire online e inviare dati. Può essere utilizzato anche per gestire i processi lato server della tua organizzazione nella gestione dei file elaborati in precedenza. Nella maggior parte dei casi non è necessario alcun ritardo. Un feed può essere ritardato fino a 120 minuti.
* **Date di inizio e fine**: La data di inizio indica la prima data desiderata per un feed di dati. Imposta questa data in passato per iniziare immediatamente l’elaborazione dei feed di dati per i dati storici. I feed continuano l’elaborazione fino alla data di fine. Le date di inizio e di fine si basano sul fuso orario della suite di rapporti.
* **Alimentazione continua**: Questa casella di controllo rimuove la data di fine, consentendo l’esecuzione indefinita di un feed. Al termine dell’elaborazione dei dati storici da parte di un feed, questi attende che i dati terminino la raccolta per un’ora o un giorno specifici. Al termine dell’ora o del giorno corrente, l’elaborazione inizia dopo il ritardo specificato.

## Campo di destinazione

I campi disponibili nei campi di destinazione dipendono dal tipo di destinazione.

### Piattaforma Google Cloud

Accedere ai bucket di archiviazione GCP come destinazione sicura

**Campi**
* *Tipo:* Tipo di destinazione della piattaforma Google Cloud
* *ID progetto:* ID del progetto GCP in cui esiste il bucket di archiviazione
* *Nome bucket di archiviazione:* I nomi dei bucket senza punti sono limitati a 3-63 caratteri. I nomi contenenti punti possono contenere fino a 222 caratteri, ma ogni componente separato da punti non può superare i 63 caratteri.
* *Percorso (facoltativo):* &amp; *Aggiungi ID suite di rapporti al percorso:* Posizione delle risorse da recuperare o archiviare

![Informazioni GCP](assets/dest-gcp.png)

**Processo di creazione dell&#39;account di servizio**

L’utente dovrà creare un account di servizio per la destinazione Google Cloud Platform selezionata.

Per ogni organizzazione di analisi sarà consentito un solo account di servizio GCP. Una volta creato l’account del servizio per il datafed, tutti i datafeeds aggiuntivi all’interno dell’organizzazione verranno precompilati con l’account del servizio.

![Informazioni sull&#39;account del servizio GCP](assets/service-account.png)


### Amazon S3

Archiviazione bucket Amazon S3 accessibile tramite IAM Role all’interno di un’entità attendibile.

**Campi**

* *Tipo:* Tipo di destinazione di Amazon S3
* *Intervallo:* Nome del bucket S3
* *ARN entità attendibile:* ARN di entità AWS IAM `arn:aws:iam::<12 digit account number>:user/<username>`
* *Ruolo ARN:* ARN ruolo AWS IAM `arn:aws:iam::<12 digit account number>:role/<role name>`
* *Percorso (facoltativo):* &amp; *Aggiungi ID suite di rapporti al percorso:* Posizione delle risorse da recuperare o archiviare
* *Specifica area geografica (facoltativo):* Elenco a discesa di tutte le aree AWS disponibili, incluse le aree CN

![Informazioni su Amazon S3](assets/dest-s3-secure.png)


**Creazione e selezione di un&#39;entità attendibile**

L&#39;utente può selezionare un&#39;entità affidabile da qualsiasi opzione elencata nel menu a discesa oppure crearne e recuperarne una nuova facendo clic sul pulsante `Create Entity` pulsante .

Dopo aver fatto clic su `Create Entity` l&#39;utente verrà reindirizzato a un processo di autenticazione. Una volta che l&#39;utente si autentica, l&#39;entità affidabile viene creata e aggiunta alle opzioni nel menu a discesa.

Il menu a discesa elenca tutte le entità attendibili create nell&#39;organizzazione da questo utente.

![Informazioni entità](assets/entity-creation.png)

Puoi inviare feed direttamente ai bucket Amazon S3 tramite il metodo legacy . Vedi [Requisiti di denominazione dei bucket Amazon S3](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) per ulteriori informazioni, consulta la documentazione di Amazon S3 .

**Campi - Obsoleto**

* *Tipo:* Tipo di destinazione del metodo S3 obsoleto
* *Intervallo:* Nome bucket Amazon S3
* *Percorso (facoltativo):* &amp; *Aggiungi ID suite di rapporti al percorso:* Posizione delle risorse da recuperare o archiviare
* *Chiave di accesso:* ID chiave di accesso dell’utente AWS
* *Chiave segreta:* Chiave segreta dell’utente di AWS
* *Conferma chiave segreta:* Immetti nuovamente la chiave segreta dell’utente AWS

![Informazioni S3](assets/dest-s3-dpr.png)

L’utente fornito per il caricamento dei feed di dati deve avere i seguenti [permissions](https://docs.aws.amazon.com/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html):

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

Per ogni caricamento su un bucket Amazon S3, [!DNL Analytics] aggiunge il proprietario del bucket all&#39;ACL BucketOwnerFullControl, indipendentemente dal fatto che il bucket abbia o meno un criterio che lo richieda. Per ulteriori informazioni, consulta &quot;[Qual è l’impostazione BucketOwnerFullControl per i feed di dati Amazon S3?](df-faq.md#BucketOwnerFullControl)&quot;

**Aree geografiche AWS supportate**:
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
* ue-nord-1
* sa-east-1
* cn-nord-1
* cn-northwest-1


### BLOB di Azure

Destinazione protetta BLOB di Azure che utilizza il controllo dell’accesso basato su ruoli (RBAC) o la firma di accesso condiviso (SAS). Selezionando il controllo di accesso, il contenuto del pannello viene aggiornato per riflettere i campi corrispondenti.

**Campi - RBAC**
* *Tipo:* Tipo di destinazione del BLOB di Azure
* *Controllo di accesso:* Opzione per utilizzare RBAC o SAS
* *ID tenant Active Directory:* ID organizzazione dell’account Azure
* *ID applicazione:* ID applicazione dalla scheda di Active Directory
* *Segreto client:* Segreto client di Azure
* *Nome account di archiviazione:* Nome dell&#39;account contenente oggetti dati
* *Nome contenitore:* Contenitore appartenente a un dato account di archiviazione.
* *Percorso (facoltativo):* &amp; *Aggiungi ID suite di rapporti al percorso:* Posizione delle risorse da recuperare o archiviare

![Informazioni RBAC di Azure](assets/dest-azure-rbac.png)

**Campi - SAS**
* *Tipo:* Tipo di destinazione del BLOB di Azure
* *Controllo di accesso:* Opzione per utilizzare RBAC o SAS
* *ID tenant Active Directory:* ID dell&#39;istanza di Azure Active Directory
* *ID applicazione:* ID applicazione dalla scheda di Active Directory
* *Segreto client:* Segreto client di Azure
* *URI archivio chiavi:* Posizione dell’insieme di credenziali delle chiavi di Azure
* *Nome segreto archivio chiavi:* Nome segreto per accedere all&#39;insieme di credenziali delle chiavi sicuro
* *Percorso (facoltativo):* &amp; *Aggiungi ID suite di rapporti al percorso:* Posizione delle risorse da recuperare o archiviare

![Informazioni SAS di Azure](assets/dest-azure-sas.png)

**Campi - Obsoleto**
* *Tipo:* Tipo di destinazione del BLOB di Azure
* *Contenitore:* Nome del contenitore Azure
* *Percorso (facoltativo):* &amp; *Aggiungi ID suite di rapporti al percorso:* Posizione delle risorse da recuperare o archiviare
* *Account:* Segreto account di Azure
* *URI archivio chiavi:* Posizione dell’insieme di credenziali delle chiavi di Azure
* *Nome segreto archivio chiavi:* Nome segreto per accedere all&#39;insieme di credenziali delle chiavi sicuro

È necessario implementare un processo personalizzato per gestire lo spazio su disco nella destinazione del feed. Adobe non elimina alcun dato dal server.
Vedi [Creare un account di archiviazione](https://docs.microsoft.com/en-us/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) nella documentazione di Microsoft Azure per ulteriori informazioni.

![Informazioni obsolete di Azure](assets/dest-azure-dpr.png)

>[!NOTE]
>
>È necessario implementare un processo personalizzato per gestire lo spazio su disco nella destinazione del feed. Adobe non elimina alcun dato dal server.

### FTP - Obsoleto

**Campi**
* *Tipo:* Tipo di destinazione dell&#39;FTP
* *Host:* Endpoint per accedere all&#39;host
* *Percorso (facoltativo):* &amp; *Aggiungi ID suite di rapporti al percorso:* Posizione delle risorse da recuperare o archiviare
* *Nome utente:* Nome utente dell&#39;host
* *Password:* Password per host
* *Conferma password:* Immetti nuovamente e verifica la password per l&#39;host

![Informazioni FTP](assets/dest-ftp-dpr.png)

### SFTP - Obsoleto

È disponibile il supporto SFTP per i feed di dati. Richiede un host SFTP, un nome utente e il sito di destinazione per contenere una chiave pubblica RSA o DSA valida. Puoi scaricare la chiave pubblica adatta al momento della creazione del feed.

**Campi**
* *Tipo:* Tipo di destinazione SFTP
* *Host:* Endpoint per accedere all&#39;host
* *Percorso (facoltativo):* &amp; *Aggiungi ID suite di rapporti al percorso:* Posizione delle risorse da recuperare o archiviare
* *Chiave pubblica RSA:* o *Chiave pubblica DSA:* Chiave pubblica per accedere all&#39;host

![Informazioni SFTP](assets/dest-sftp-dpr.png)

## Definizioni delle colonne dati

Sono disponibili tutte le colonne, indipendentemente dai dati disponibili. Un feed di dati deve includere almeno una colonna.

* **Rimuovere i caratteri di escape**: Quando si raccolgono i dati, alcuni caratteri (come le righe nuove) possono causare problemi. Selezionare questa casella se si desidera rimuovere questi caratteri dai file di feed.
* **Formato di compressione**: Tipo di compressione utilizzato. File di output Gzip in `.tar.gz` formato. File di output ZIP in `.zip` formato.
* **Tipo di pacchetto**: Uscite di file singolo `hit_data.tsv` file in un unico file potenzialmente massiccio. Più file impaginano i dati in blocchi da 2 GB (non compressi). Se sono selezionati più file e i dati non compressi per l’intervallo di reporting sono inferiori a 2 GB, viene inviato un file. Adobe consiglia di utilizzare più file per la maggior parte dei feed di dati.
* **Manifesto**: Se Adobe deve o meno fornire un [file manifest](c-df-contents/datafeeds-contents.md#feed-manifest) alla destinazione quando non vengono raccolti dati per un intervallo di feed. Se selezioni Manifest File, riceverai un file manifesto simile al seguente quando non vengono raccolti dati:

```text
   Datafeed-Manifest-Version: 1.0
    Lookup-Files: 0
    Data-Files: 0
    Total-Records: 0
```

* **Modelli di colonna**: Quando si creano molti feed di dati, Adobe consiglia di creare un modello di colonna. Quando si seleziona un modello di colonna, vengono automaticamente incluse le colonne specificate nel modello. In Adobe sono inoltre disponibili diversi modelli per impostazione predefinita.
* **Colonne disponibili**: Tutte le colonne di dati disponibili in Adobe Analytics. Fai clic su [!UICONTROL Add all] per includere tutte le colonne in un feed di dati.
* **Colonne incluse**: Le colonne da includere in un feed di dati. Fai clic su [!UICONTROL Remove all] per rimuovere tutte le colonne da un feed di dati.
* **Scarica CSV**: Scarica un file CSV contenente tutte le colonne incluse.
