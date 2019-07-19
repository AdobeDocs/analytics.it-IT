---
description: Procedura che descrive come caricare i file di dati mediante FTP.
seo-description: Procedura che descrive come caricare i file di dati mediante FTP.
seo-title: Importazione FTP
solution: Analytics
subtopic: Classificazioni
title: Importazione FTP
topic: Strumenti di amministrazione
uuid: a 914970 d-ba 02-4111-9 dcf -06448 f 71 b 9 f 3
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Importazione FTP

Procedura che descrive come caricare i file di dati mediante FTP.

## FTP import {#concept_2F965BE873254546A61FB755F25299FD}

Procedura che descrive come caricare i file di dati mediante FTP.

**[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.

I seguenti limiti consigliati sono importanti:

* Molti file di piccole dimensioni generano un'elaborazione più lenta rispetto ad alcuni file di grandi dimensioni. Ciò è dovuto alla quantità di in coda e alla priorità necessaria per i processi più piccoli.
* Suddividete i file di grandi dimensioni in blocchi di 50 MB. Questo non è richiesto, ma è consigliato perché offre una visibilità migliore sullo stato di avanzamento. Inoltre, se si verificano degli errori durante l'elaborazione del processo, il processo verrà riavviato; i file di grandi dimensioni producono grandi quantità di lavoro in questo scenario.

La configurazione iniziale compila il database delle classificazioni con un set di dati originale, o ristruttura le classificazioni, piuttosto che classificare alcune righe o aggiungere righe.

Dopo un caricamento iniziale in una suite di rapporti (per una determinata variabile o rapporto), Adobe consiglia di caricare solo righe nuove e aggiornate nelle importazioni successive. Le righe che non vengono modificate devono essere omesse dai caricamenti futuri.

Ogni nuovo valore chiave consente di caricare conteggio rispetto alle unitari per quella variabile per il mese.

Se avete superato le unitarie per il mese, in reporting non saranno visualizzati i dati di classificazione corrispondenti per i valori unificati superati. Puoi visualizzare tali classificazioni in data warehouse o analisi ad hoc.

>[!NOTE]
>
>Il tempo necessario per elaborare un file di dati di classificazione varia in base alle dimensioni del file e al numero corrente di file già elaborati dai server Adobe. L'elaborazione dei file di dati in genere non dura più di 72 ore.

Prima di caricare i dati mediante FTP, create un account FTP. For more information, see [Create an FTP account](../../../components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

## Import classifications via FTP {#task_132C36830B69418B8C929E39838EF01D}

<!-- 

t_upload_a_saint_data_file_via_ftp.xml

 -->

Procedura che descrive come utilizzare un account FTP per importare classificazioni in Adobe Analytics.

For more information about creating an FTP account, see [Create an FTP account](../../../components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Import File]**, then click **[!UICONTROL FTP Import]**.
1. Next to the FTP account that you want to use, click **[!UICONTROL View]**.
1. Usa le informazioni di accesso FTP (Ospitante, Login, Password) per accedere al server FTP tramite un client FTP scelto.
1. Upload the data file ( [!DNL .tab] or [!DNL .txt]) to the FTP server.
1. Dopo aver caricato il file di dati, caricate un file FIN che indichi che il file è pronto per essere elaborato.

   The FIN file is an empty file that has the same name as your data file, with a [!DNL .fin] filename extension. For example, if your data file is [!DNL classdata1.tab], the FIN filename is [!DNL classdata1.fin].

Ad intervalli regolari, Adobe recupera i file di dati caricati con un file FIN associato. Adobe li importa nelle suite di rapporti e nei set di dati specificati nella configurazione dell'account FTP.

## Create an FTP account {#task_C019268E6C934C7C95F4326F42A22CCF}

Prima di caricare i dati mediante FTP, create un account FTP. &gt;

<!-- 

t_create_an_ftp_account.xml

 -->

See [FTP and sFTP](https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/) for additional details on Adobe FTP servers.

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Import File]**, then click **[!UICONTROL FTP Import]**.
1. On the **[!UICONTROL Import File]** tab, click **[!UICONTROL Add New]**.
1. Specifica i dettagli dell'account FTP:

   | Elemento | Descrizione |
   |---|---|
   | Nome | Il nome dell'account FTP. |
   | Set di dati da classificare | Dall'elenco a discesa, selezionate il set di dati (variabile di rapporto di marketing) che desiderate classificare. |
   | Selezionare suite di rapporti | Seleziona le suite di rapporti in cui vuoi classificare il set di dati selezionato. Per selezionare più suite di rapporti, le classificazioni per ciascuna suite di rapporti selezionata devono essere identiche. |
   | Sovrascrivi dati in conflitto | Selezionate questa opzione per sovrascrivere i dati duplicati. Questa opzione è utile se state aggiornando classificazioni esistenti. Se state aggiungendo ulteriori classificazioni, questa opzione è sconsigliata. |
   | Al termine dell'importazione | Selezionate questa opzione per esportare automaticamente il set di dati aggiornato sullo stesso account FTP Una volta specificate l'indirizzo e-mail per ricevere le notifiche su questo account FTP una volta completata l'importazione. |
   | Destinatario delle notifiche | Specificate l'indirizzo e-mail per ricevere le notifiche su questo account FTP. |
   | Autorizza | (Obbligatorio) Autorizza Adobe a importare automaticamente tutti i file di dati inviati al nuovo account FTP. |

1. Fai clic su **[!UICONTROL Save]**.

Una volta creati, potete modificare o eliminare gli account FTP facendo clic sul collegamento appropriato accanto all'account FTP desiderato.
