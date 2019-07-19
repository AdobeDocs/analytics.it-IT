---
description: L'opzione FTP classificazioni (SAINT) assicura una maggior flessibilità nel caricamento di grandi set di dati e consente inoltre di caricare i dati in più suite di report e di caricare set di dati con più di 50.000 righe.
keywords: ftp; sftp
seo-description: L'opzione FTP classificazioni (SAINT) assicura una maggior flessibilità nel caricamento di grandi set di dati e consente inoltre di caricare i dati in più suite di report e di caricare set di dati con più di 50.000 righe.
seo-title: Classificazioni
solution: Analytics
title: Classificazioni
uuid: 35936 c 98-b 785-43 eb -89 f 4-ab 42 a 10 db 256
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Classificazioni

L'opzione FTP classificazioni offre maggiore flessibilità nel caricamento di grandi set di dati di classificazione, inclusa la possibilità di caricare dati in più suite di rapporti e di caricare set di dati più grandi di 50,000 righe.

Consulta [classificazioni](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) per conoscere i passaggi necessari a scaricare i dati di classificazione tramite FTP e per sapere come caricare file dati tramite FTP (inclusi i passaggi per creare un account FTP).

Il tempo necessario al sistema per l'importazione dei file varia in base a diversi fattori. Se un file caricato è ancora presente sul server FTP dopo sei ore, chiedi agli utenti supportati della tua organizzazione di contattare l'Assistenza clienti Adobe.

Un import corretto visualizza immediatamente le modifiche corrette in un'esportazione, mentre le modifiche ai dati in Analytics possono richiedere fino a 4 ore nel caso di un'importazione tramite browser e fino a 24 ore del caso di un'importazione tramite FTP.

Per informazioni sulla conservazione dei dati e sui limiti dell'FTP, consulta [Conservazione dei dati e limitazioni dell'FTP](../../../export/ftp-and-sftp/ftp-limits.md#concept_8CAA1D8F27B3411AB902520AD6C9A70E).

## Informazioni sul file .fin per gli upload Classificazioni e Origini dati {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classification or [!UICONTROL Data Source] file ( [!DNL .tab]or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. [!DNL .fin] Questo file è un file di fine. Lo scopo del file è quello di comunicare al sistema che il file di dati è stato completamente caricato sull'account FTP. [!DNL .fin] Il file consente ad Adobe di riconoscere che l'importazione è terminata. Dopo l'invio, Adobe rimuove entrambi i file dall'FTP e inizia a elaborare l'importazione.
Import File: [!DNL Classifications.tab]

Finish File: [!DNL Classifications.fin]

If you upload your Data Sources or classification file without an accompanying [!DNL .fin] file, Adobe does not add it to the queue for processing. I file resteranno sull'FTP e non verranno applicati ai tuoi dati in [!UICONTROL Experience Cloud]. You are notified of this only if you have entered your email address as the [!UICONTROL Notification Recipient] in the [!UICONTROL Create FTP Account] window of Analytics. Se non hai inserito nessun indirizzo e-mail, non verrà inviata alcuna notifica.

If you do upload your file with a [!DNL .fin] file, but there is an error in the file, it is submitted for processing, but the error causes the processing to cease and the file to be sent to an error folder. If this occurs, a notification is sent to the email address listed in the [!UICONTROL Notification Recipient] field in the [!UICONTROL Create FTP Account] window. Se non è stato inserito nessun indirizzo e-mail, non viene inviata alcuna notifica.
