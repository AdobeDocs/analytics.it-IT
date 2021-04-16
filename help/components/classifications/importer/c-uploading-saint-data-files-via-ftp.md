---
description: Passaggi che descrivono come caricare i file di dati tramite FTP.
subtopic: Classifications
title: Importazione FTP
feature: Strumenti di amministrazione
uuid: a914970d-ba02-4111-9dcf-06448f71b9f3
exl-id: 3e93b35c-6f65-4a93-887d-d94e4d359bdc
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 5%

---

# Importazione FTP

Passaggi che descrivono come caricare i file di dati tramite FTP.

## Importazione FTP {#concept_2F965BE873254546A61FB755F25299FD}

Passaggi che descrivono come caricare i file di dati tramite FTP.

**[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.

I seguenti limiti consigliati sono importanti:

* Un sacco di file di piccole dimensioni si tradurrà in un&#39;elaborazione più lenta di alcuni file di grandi dimensioni. Ciò è dovuto alla quantità di code e priorità richieste per i lavori più piccoli.
* Per favore, suddividi i file di grandi dimensioni in blocchi da 50 MB. Questo non è necessario, ma è consigliato perché offre una migliore visibilità dei progressi sul back-end. Inoltre, se si verificano errori durante l&#39;elaborazione del tuo lavoro, il lavoro verrà riavviato; file di grandi dimensioni si traducono in grandi quantità di lavoro rifatto in questo scenario.

La configurazione iniziale popola il database delle classificazioni con un ampio set di dati originali o ristruttura le classificazioni, anziché riclassificare alcune righe o aggiungere altre righe.

Dopo un caricamento iniziale in una suite di rapporti (per una determinata variabile o rapporto), Adobe consiglia di caricare solo righe nuove e aggiornate nelle importazioni successive. Le righe che non vengono modificate devono essere omesse dai caricamenti futuri.

Ogni nuovo valore chiave caricato viene conteggiato rispetto agli univoci per quella variabile per il mese.

Se hai superato gli univoci per il mese, non vedrai i dati di classificazione corrispondenti per gli univoci superati nei rapporti. Puoi vedere queste classificazioni nella Data Warehouse.

>[!NOTE]
>
>Il tempo necessario per elaborare un file di dati di classificazione varia in base alle dimensioni del file e al numero corrente di file già elaborati dai server di Adobe. L&#39;elaborazione dei file di dati in genere richiede non più di 72 ore.

Prima di caricare i dati tramite FTP, crea un account FTP. Per ulteriori informazioni, consulta [Creare un account FTP](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

## Importare classificazioni tramite FTP {#task_132C36830B69418B8C929E39838EF01D}

<!-- 

t_upload_a_saint_data_file_via_ftp.xml

 -->

Passaggi che descrivono come utilizzare un account FTP per importare classificazioni in Adobe Analytics.

Per ulteriori informazioni sulla creazione di un account FTP, consulta [Creare un account FTP](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

1. Fai clic su **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Fai clic su **[!UICONTROL Import File]**, quindi su **[!UICONTROL FTP Import]**.
1. Accanto all&#39;account FTP che desideri utilizzare, fai clic su **[!UICONTROL View]**.
1. Utilizza le informazioni di accesso FTP (Host, Accesso, Password) per accedere al server FTP utilizzando un client FTP scelto.
1. Carica il file di dati ( [!DNL .tab] o [!DNL .txt]) sul server FTP.
1. Dopo aver caricato il file di dati, carica un file FIN che indica che il file è pronto per l&#39;elaborazione.

   Il file FIN è un file vuoto con lo stesso nome del file di dati, con estensione del nome del file [!DNL .fin]. Ad esempio, se il file di dati è [!DNL classdata1.tab], il nome del file FIN è [!DNL classdata1.fin].

A intervalli regolari, Adobe recupera i file di dati caricati con un file FIN associato. Adobe li importa nelle suite di rapporti e nei set di dati specificati nella configurazione dell’account FTP.

## Creare un account FTP {#task_C019268E6C934C7C95F4326F42A22CCF}

Prima di caricare i dati tramite FTP, crea un account FTP. >

<!-- 

t_create_an_ftp_account.xml

 -->

Per ulteriori informazioni sui server FTP Adobe, consulta [FTP e sFTP](https://docs.adobe.com/content/help/en/analytics/export/ftp-and-sftp/ftp-overview.html) .

1. Fai clic su **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Fai clic su **[!UICONTROL Import File]**, quindi su **[!UICONTROL FTP Import]**.
1. Nella scheda **[!UICONTROL Import File]** fai clic su **[!UICONTROL Add New]**.
1. Specifica i dettagli dell&#39;account FTP:

   | Elemento | Descrizione |
   |---|---|
   | Nome | Nome account FTP. |
   | Set di dati da classificare | Dall’elenco a discesa, seleziona il set di dati (variabile del rapporto di marketing) da classificare. |
   | Selezionare suite di rapporti | Seleziona le suite di rapporti in cui desideri classificare il set di dati selezionato. Per selezionare più suite di rapporti, le classificazioni per ciascuna suite di rapporti selezionata devono essere identiche. |
   | Sovrascrivi i dati sui conflitti | Selezionare questa opzione per sovrascrivere i dati duplicati. Questa opzione è utile se stai aggiornando le classificazioni esistenti. Se stai aggiungendo classificazioni aggiuntive, questa opzione non è consigliata. |
   | Dopo il completamento dell’importazione | Seleziona questa opzione per esportare automaticamente il set di dati aggiornato sullo stesso account FTP una volta Specificate l’indirizzo e-mail per ricevere le notifiche su questo account FTP una volta completata l’importazione. |
   | Destinatario delle notifiche | Specifica l&#39;indirizzo e-mail per ricevere le notifiche relative a questo account FTP. |
   | Autorizzare | (Obbligatorio) Autorizza Adobe ad importare automaticamente tutti i file di dati inviati al nuovo account FTP. |

1. Fai clic su **[!UICONTROL Save]**.

Una volta creato, puoi modificare o eliminare gli account FTP facendo clic sul collegamento appropriato accanto all&#39;account FTP desiderato.

>[!NOTE]
>
>Le notifiche non vengono inviate se un’importazione non introduce modifiche a una classificazione. Un messaggio e-mail viene inviato solo se ha esito positivo e determina modifiche a una classificazione.
