---
title: Creare o modificare un feed dati
description: Scopri come creare o modificare un feed di dati.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '798'
ht-degree: 3%

---


# Creare o modificare un feed dati

La creazione di un feed di dati consente ad Adobe di sapere dove inviare i file di dati non elaborati e cosa si desidera includere in ciascun file. In questa pagina sono elencate le singole impostazioni che potete personalizzare durante la creazione di un feed di dati.

Prima di leggere questa pagina è consigliabile conoscere i feed di dati di base. Consulta Panoramica sui feed di [dati](data-feed-overview.md) per essere certi di soddisfare i requisiti per creare un feed di dati.

## Campi Informazioni sui feed

* **Nome**: Nome del feed di dati. Deve essere univoco all&#39;interno della suite di rapporti selezionata e può contenere fino a 255 caratteri.
* **Suite di rapporti:** La suite di rapporti su cui si basa il feed di dati. Se per la stessa suite di rapporti vengono creati più feed di dati, questi devono avere definizioni di colonna diverse. Solo le suite di rapporti di origine supportano i feed di dati; le suite di rapporti virtuali non sono supportate.
* **E-mail al termine**: L&#39;indirizzo e-mail da notificare al termine dell&#39;elaborazione di un feed. L&#39;indirizzo e-mail deve essere formattato correttamente.
* **Intervallo** feed: I feed orari contengono dati di un&#39;ora. I feed giornalieri contengono dati di un&#39;intera giornata.
* **Elaborazione** ritardata: Attendi un periodo di tempo specificato prima di elaborare un file di feed di dati. Un ritardo può essere utile per dare alle implementazioni per dispositivi mobili l&#39;opportunità di essere online e inviare dati. Può essere utilizzato anche per gestire i processi lato server della propria azienda nella gestione dei file elaborati in precedenza. Nella maggior parte dei casi, non è necessario alcun ritardo. Un feed può essere ritardato fino a 120 minuti.
* **Date** di inizio e fine: La data di inizio indica la prima data in cui si desidera inserire un feed di dati. Imposta questa data in passato per iniziare immediatamente l&#39;elaborazione dei feed di dati per i dati storici. I feed continuano l&#39;elaborazione fino alla data di fine.
* **Feed** continuo: Questa casella di controllo rimuove la data di fine, consentendo l&#39;esecuzione indefinita di un feed. Quando un feed termina l&#39;elaborazione dei dati storici, un feed attende che i dati finiscano la raccolta per una data ora o giorno. Al termine dell&#39;ora o del giorno corrente, l&#39;elaborazione inizia dopo il ritardo specificato.

## Campi di destinazione

I campi disponibili nei campi di destinazione dipendono dal tipo di destinazione.

### FTP

I dati del feed di dati possono essere inviati a una posizione FTP ospitata da Adobe o dal cliente. Richiede un host FTP, un nome utente e una password. Usate il campo del percorso per inserire i file di feed in una cartella. Le cartelle devono già esistere; i feed generano un errore se il percorso specificato non esiste.

![Informazioni FTP](assets/dest-ftp.jpg)

### SFTP

È disponibile il supporto SFTP per i feed di dati. Richiede un host SFTP, un nome utente e il sito di destinazione per contenere una chiave pubblica RSA o DSA valida. Potete scaricare la chiave pubblica appropriata al momento della creazione del feed.

![Informazioni SFTP](assets/dest-sftp.jpg)

### S3

Potete inviare feed direttamente ai bucket Amazon S3. Richiede un nome del socket, un ID chiave di accesso e una chiave segreta. Per ulteriori informazioni, consulta Requisiti [di denominazione per bucket](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) Amazon S3 all&#39;interno dei documenti Amazon S3.

![Informazioni S3](assets/dest-s3.jpg)

Sono supportate le seguenti 11 aree AWS standard (utilizzando, se necessario, l&#39;algoritmo di firma appropriato):

* us-east-1
* us-west-1
* us-west-2
* ap-south-1
* ap-northeast-2
* ap-southeast-1
* ap-southeast-2
* ap-northeast-1
* eu-central-1
* eu-west-1
* sa-east-1

>[!NOTE]
>
>L&#39;area cn-north-1 non è supportata.

### BLOB di Azure

I feed di dati supportano le destinazioni BLOB di Azure. Richiede un contenitore, un account e una chiave. Amazon esegue automaticamente la cifratura dei dati a riposo. Quando scaricate i dati, questi vengono decrittografati automaticamente. Per ulteriori informazioni, vedere [Creazione di un account](https://docs.microsoft.com/en-us/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) di archiviazione all&#39;interno dei documenti di Microsoft Azure.

![Informazioni Azure](assets/azure.png)

>[!NOTE]
>
>È necessario implementare un processo personalizzato per gestire lo spazio su disco nella destinazione del feed. Adobe non elimina alcun dato dal server.

## Definizioni delle colonne dati

Sono disponibili tutte le colonne, indipendentemente dai dati in loro possesso. Un feed di dati deve includere almeno una colonna.

* **Rimuovi caratteri** di escape: Durante la raccolta dei dati, alcuni caratteri (come le righe di testo) possono causare problemi. Selezionate questa casella se desiderate rimuovere questi caratteri dai file di feed.
* **Formato** di compressione: Tipo di compressione utilizzato. Gzip produce i file in `.tar.gz` formato. Lo ZIP produce i file in `.zip` formato.
* **Tipo** di pacchetto: Un singolo file produce il `hit_data.tsv` file in un unico file potenzialmente molto grande. Più file impaginano i dati in blocchi da 2 GB (non compressi). Se più file sono selezionati e i dati non compressi per la finestra di rapporto sono inferiori a 2 GB, viene inviato un file. Adobe consiglia di utilizzare più file per la maggior parte dei feed di dati.
* **Modelli** colonna: Quando create molti feed di dati, Adobe consiglia di creare un modello di colonna. Quando si seleziona un modello di colonna, vengono automaticamente incluse le colonne specificate nel modello. Per impostazione predefinita, Adobe fornisce anche diversi modelli.
* **Colonne** disponibili: Tutte le colonne di dati disponibili in Adobe  Analytics. Fare clic [!UICONTROL Add all] per includere tutte le colonne in un feed di dati.
* **Colonne** incluse: Le colonne da includere in un feed di dati. Fare clic [!UICONTROL Remove all] per rimuovere tutte le colonne da un feed di dati.
* **Scarica CSV**: Scarica un file CSV contenente tutte le colonne incluse.
