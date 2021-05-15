---
title: Creare o modificare un feed dati
description: Scopri come creare o modificare un feed di dati.
exl-id: 36c8a40e-6137-4836-9d4b-bebf17b932bc
source-git-commit: 7312b61b8d73f45afa3eb9aac73cc4d5fd39bc82
workflow-type: tm+mt
source-wordcount: '870'
ht-degree: 3%

---

# Creare o modificare un feed dati

La creazione di un feed di dati consente ad Adobe di sapere dove inviare i file di dati non elaborati e cosa si desidera includere in ciascun file. In questa pagina sono elencate le singole impostazioni che è possibile personalizzare durante la creazione di un feed di dati.

Prima di leggere questa pagina è consigliabile conoscere i feed di dati di base. Consulta [Panoramica sui feed di dati](data-feed-overview.md) per essere certo di soddisfare i requisiti per creare un feed di dati.

## Campi di informazioni sui feed

* **Nome**: Nome del feed di dati. Deve essere univoco all’interno della suite di rapporti selezionata e può contenere fino a 255 caratteri.
* **Suite di rapporti:** la suite di rapporti su cui si basa il feed di dati. Se vengono creati più feed di dati per la stessa suite di rapporti, devono avere definizioni di colonna diverse. Solo le suite di rapporti di origine supportano i feed di dati; le suite di rapporti virtuali non sono supportate.
* **E-mail al termine**: L’indirizzo e-mail da notificare al termine dell’elaborazione di un feed. L’indirizzo e-mail deve essere formattato correttamente.
* **Intervallo** feed: I feed orari contengono dati di un&#39;ora. I feed giornalieri contengono dati del valore di una giornata intera; includono dati da mezzanotte a mezzanotte nel fuso orario della suite di rapporti.
* **Elaborazione** ritardata: Attendi un periodo di tempo specificato prima di elaborare un file di feed di dati. Un ritardo può essere utile per dare alle implementazioni mobili un’opportunità per i dispositivi offline di venire online e inviare dati. Può essere utilizzato anche per gestire i processi lato server della tua organizzazione nella gestione dei file elaborati in precedenza. Nella maggior parte dei casi non è necessario alcun ritardo. Un feed può essere ritardato fino a 120 minuti.
* **Date** di inizio e fine: La data di inizio indica la prima data desiderata per un feed di dati. Imposta questa data in passato per iniziare immediatamente l’elaborazione dei feed di dati per i dati storici. I feed continuano l’elaborazione fino alla data di fine. Le date di inizio e di fine si basano sul fuso orario della suite di rapporti.
* **Feed** continuo: Questa casella di controllo rimuove la data di fine, consentendo l’esecuzione indefinita di un feed. Al termine dell’elaborazione dei dati storici da parte di un feed, questi attende che i dati terminino la raccolta per un’ora o un giorno specifici. Al termine dell’ora o del giorno corrente, l’elaborazione inizia dopo il ritardo specificato.

## Campi di destinazione

I campi disponibili nei campi di destinazione dipendono dal tipo di destinazione.

### FTP

I dati dei feed di dati possono essere inviati a una posizione FTP ospitata da un Adobe o da un cliente. Richiede un host FTP, un nome utente e una password. Utilizzare il campo percorso per inserire i file di feed in una cartella. Le cartelle devono già esistere; i feed generano un errore se il percorso specificato non esiste.

![Informazioni FTP](assets/dest-ftp.jpg)

### SFTP

È disponibile il supporto SFTP per i feed di dati. Richiede un host SFTP, un nome utente e il sito di destinazione per contenere una chiave pubblica RSA o DSA valida. Puoi scaricare la chiave pubblica appropriata al momento della creazione del feed.

![Informazioni SFTP](assets/dest-sftp.jpg)

### S3

Puoi inviare feed direttamente ai bucket Amazon S3. Richiede un nome bucket, un ID chiave di accesso e una chiave segreta. Per ulteriori informazioni, consulta [Requisiti per la denominazione dei bucket Amazon S3](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) nella documentazione di Amazon S3 .

![Informazioni S3](assets/dest-s3.jpg)

Sono supportate le 16 aree AWS standard seguenti (utilizzando, se necessario, l’algoritmo di firma appropriato):

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

>[!NOTE]
>
>L&#39;area cn-North-1 non è supportata.

### BLOB di Azure

I feed di dati supportano le destinazioni BLOB di Azure. Richiede un contenitore, un account e una chiave. Amazon crittografa automaticamente i dati a riposo. Quando scarichi i dati, viene decrittografato automaticamente. Per ulteriori informazioni, consulta [Creare un account di archiviazione](https://docs.microsoft.com/en-us/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) all’interno dei documenti di Microsoft Azure .

![Informazioni di Azure](assets/azure.png)

>[!NOTE]
>
>È necessario implementare un processo personalizzato per gestire lo spazio su disco nella destinazione del feed. Adobe non elimina alcun dato dal server.

## Definizioni delle colonne dati

Sono disponibili tutte le colonne, indipendentemente dai dati disponibili. Un feed di dati deve includere almeno una colonna.

* **Rimuovi i caratteri** di escape: Quando si raccolgono i dati, alcuni caratteri (come le righe nuove) possono causare problemi. Selezionare questa casella se si desidera rimuovere questi caratteri dai file di feed.
* **Formato** di compressione: Tipo di compressione utilizzato. Gzip restituisce i file in formato `.tar.gz`. Lo ZIP restituisce i file in formato `.zip`.
* **Tipo** di imballaggio: Un file singolo genera il  `hit_data.tsv` file in un unico file potenzialmente enorme. Più file impaginano i dati in blocchi da 2 GB (non compressi). Se sono selezionati più file e i dati non compressi per l’intervallo di reporting sono inferiori a 2 GB, viene inviato un file. Adobe consiglia di utilizzare più file per la maggior parte dei feed di dati.
* **Manifesto**: Indica se Adobe deve o meno inviare un  [file ](c-df-contents/datafeeds-contents.md#feed-manifest) manifesto alla destinazione quando non vengono raccolti dati per un intervallo di feed. Se selezioni Manifest File, riceverai un file manifesto simile al seguente quando non vengono raccolti dati:

```text
   Datafeed-Manifest-Version: 1.0
    Lookup-Files: 0
    Data-Files: 0
    Total-Records: 0
```

* **Modelli** colonna: Quando si creano molti feed di dati, Adobe consiglia di creare un modello di colonna. Quando si seleziona un modello di colonna, vengono automaticamente incluse le colonne specificate nel modello. In Adobe sono inoltre disponibili diversi modelli per impostazione predefinita.
* **Colonne** disponibili: Tutte le colonne di dati disponibili in Adobe Analytics. Fai clic su [!UICONTROL Add all] per includere tutte le colonne in un feed di dati.
* **Colonne** incluse: Le colonne da includere in un feed di dati. Fai clic su [!UICONTROL Remove all] per rimuovere tutte le colonne da un feed di dati.
* **Scarica CSV**: Scarica un file CSV contenente tutte le colonne incluse.
