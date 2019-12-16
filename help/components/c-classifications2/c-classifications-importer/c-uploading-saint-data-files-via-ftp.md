---
description: Procedura che descrive come caricare i file di dati tramite FTP.
subtopic: Classifications
title: Importazione FTP
topic: Admin tools
uuid: a914970d-ba02-4111-9dcf-06448f71b9f3
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Importazione FTP

Procedura che descrive come caricare i file di dati tramite FTP.

## Importazione FTP {#concept_2F965BE873254546A61FB755F25299FD}

Procedura che descrive come caricare i file di dati tramite FTP.

**[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.

I seguenti limiti consigliati sono importanti:

* Molti file di piccole dimensioni si tradurranno in un processo di elaborazione più lento rispetto a pochi file di grandi dimensioni. Ciò è dovuto alla quantità di code e priorità richieste per i processi più piccoli.
* Suddividere i file grandi in blocchi da 50 MB. Questo non è necessario, ma è consigliato perché offre una migliore visibilità del progresso sul lato posteriore. Inoltre, se si verificano errori durante l’elaborazione del processo, il processo verrà riavviato; i file di grandi dimensioni restituiscono grandi quantità di lavoro rifatto in questo scenario.

L'impostazione iniziale popola il database delle classificazioni con un ampio set di dati originali, o ristruttura le classificazioni, anziché riclassificare alcune righe o aggiungere altre righe.

Dopo un caricamento iniziale in una suite di rapporti (per una determinata variabile o rapporto), Adobe consiglia di caricare solo righe nuove e aggiornate nelle importazioni successive. Le righe che non vengono modificate devono essere omesse dai caricamenti futuri.

Ogni nuovo valore chiave caricato viene conteggiato rispetto alle uniche per quella variabile per il mese.

Se hai superato i valori univoci per il mese, non vedrai i dati di classificazione corrispondenti per i valori univoci superati nel report. Puoi visualizzare tali classificazioni in data warehouse o in analisi ad hoc.

> [!NOTE] Il tempo necessario per elaborare un file di dati di classificazione varia in base alle dimensioni del file e al numero corrente di file già elaborati dai server Adobe. L'elaborazione dei file di dati in genere non richiede più di 72 ore.

Prima di caricare i dati tramite FTP, create un account FTP. For more information, see [Create an FTP account](/help/components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

## Importazione di classificazioni tramite FTP {#task_132C36830B69418B8C929E39838EF01D}

<!-- 

t_upload_a_saint_data_file_via_ftp.xml

 -->

Procedura che descrive come utilizzare un account FTP per importare classificazioni in Adobe Analytics.

Per ulteriori informazioni sulla creazione di un account FTP, consultate [Creare un account](/help/components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF)FTP.

1. Fai clic su **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Fai clic su **[!UICONTROL Import File]**, quindi su **[!UICONTROL FTP Import]**.
1. Accanto all'account FTP che desideri utilizzare, fai clic su **[!UICONTROL View]**.
1. Utilizzate le informazioni di accesso FTP (Host, Login, Password) per accedere al server FTP utilizzando un client FTP di vostra scelta.
1. Caricate il file di dati ( [!DNL .tab] o [!DNL .txt]) sul server FTP.
1. Dopo aver caricato il file di dati, caricate un file FIN che indichi che il file è pronto per l'elaborazione.

   Il file FIN è un file vuoto con lo stesso nome del file di dati, con estensione [!DNL .fin] del nome file. Ad esempio, se il file di dati è [!DNL classdata1.tab], il nome del file FIN è [!DNL classdata1.fin].

A intervalli regolari, Adobe recupera i file di dati caricati con un file FIN associato. Adobe li importa nelle suite di rapporti e nei set di dati specificati nella configurazione dell'account FTP.

## Creare un account FTP {#task_C019268E6C934C7C95F4326F42A22CCF}

Prima di caricare i dati tramite FTP, create un account FTP. &gt;

<!-- 

t_create_an_ftp_account.xml

 -->

Per ulteriori informazioni sui server Adobe FTP, consultate [FTP e sFTP](https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/) .

1. Fai clic su **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Fai clic su **[!UICONTROL Import File]**, quindi su **[!UICONTROL FTP Import]**.
1. Nella **[!UICONTROL Import File]** scheda fare clic su **[!UICONTROL Add New]**.
1. Specificate i dettagli dell'account FTP:

   | Elemento | Descrizione |
   |---|---|
   | Nome | Nome account FTP. |
   | Set di dati da classificare | Dall'elenco a discesa, selezionate il set di dati (variabile del rapporto di marketing) da classificare. |
   | Selezionare suite di rapporti | Selezionare le suite di rapporti in cui si desidera classificare il set di dati selezionato. Per selezionare più suite di rapporti, le classificazioni per ciascuna delle suite selezionate devono essere identiche. |
   | Sovrascrivi dati sui conflitti | Selezionare questa opzione per sovrascrivere i dati duplicati. Questa opzione è utile se state aggiornando le classificazioni esistenti. Se state aggiungendo classificazioni aggiuntive, questa opzione non è consigliata. |
   | Dopo l'importazione è stata completata | Selezionate questa opzione per esportare automaticamente il set di dati aggiornato sullo stesso account FTP una volta che Specificate l'indirizzo e-mail per la ricezione delle notifiche su questo account FTP al termine dell'importazione. |
   | Destinatario delle notifiche | Specificate l'indirizzo e-mail per ricevere le notifiche su questo account FTP. |
   | Autorizza | (Obbligatorio) Autorizza Adobe a importare automaticamente tutti i file di dati inviati al nuovo account FTP. |

1. Fai clic su **[!UICONTROL Save]** (Genera).

Una volta creati, potete modificare o eliminare gli account FTP facendo clic sul collegamento appropriato accanto all'account FTP desiderato.
