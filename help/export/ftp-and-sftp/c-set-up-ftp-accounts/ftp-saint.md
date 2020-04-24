---
description: L'opzione FTP classificazioni (SAINT) assicura una maggior flessibilità nel caricamento di grandi set di dati e consente inoltre di caricare i dati in più suite di report e di caricare set di dati con più di 50.000 righe.
keywords: ftp;sftp
title: Classificazioni
uuid: 35936c98-b785-43eb-89f4-ab42a10db256
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Classificazioni

L&#39;opzione FTP classificazioni offre maggiore flessibilità nel caricamento di set di dati di classificazione di grandi dimensioni, inclusa la possibilità di caricare dati in più suite di rapporti e di caricare set di dati di dimensioni superiori a 50.000 righe.

Consulta [classificazioni](https://marketing.adobe.com/resources/help/it_IT/reference/c_working_with_saint.html) per conoscere i passaggi necessari a scaricare i dati di classificazione tramite FTP e per sapere come caricare file dati tramite FTP (inclusi i passaggi per creare un account FTP).

Il tempo necessario al sistema per l&#39;importazione dei file varia in base a diversi fattori. Se un file caricato è ancora presente sul server FTP dopo sei ore, chiedi agli utenti supportati della tua organizzazione di contattare l&#39;Assistenza clienti Adobe.

Un import corretto visualizza immediatamente le modifiche corrette in un&#39;esportazione, mentre le modifiche ai dati in Analytics possono richiedere fino a 4 ore nel caso di un&#39;importazione tramite browser e fino a 24 ore del caso di un&#39;importazione tramite FTP.

Per informazioni sulla conservazione dei dati e sui limiti dell&#39;FTP, consulta [Conservazione dei dati e limitazioni dell&#39;FTP](/help/export/ftp-and-sftp/ftp-limits.md).

## Informazioni sul file .fin per gli upload Classificazioni e Origini dati {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classification or [!UICONTROL Data Source] file ( [!DNL .tab]or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. This [!DNL .fin] file is a finish file. Lo scopo del file è quello di comunicare al sistema che il file di dati è stato completamente caricato sull&#39;account FTP. The [!DNL .fin] file lets Adobe recognize that you are done with your import. Dopo l&#39;invio, Adobe rimuove entrambi i file dall&#39;FTP e inizia a elaborare l&#39;importazione.
Importa file: [!DNL Classifications.tab]

Fine file: [!DNL Classifications.fin]

If you upload your Data Sources or classification file without an accompanying [!DNL .fin] file, Adobe does not add it to the queue for processing. I file resteranno sull&#39;FTP e non verranno applicati ai tuoi dati in [!UICONTROL Experience Cloud]. You are notified of this only if you have entered your email address as the [!UICONTROL Notification Recipient] in the [!UICONTROL Create FTP Account] window of Analytics. Se non hai inserito nessun indirizzo e-mail, non verrà inviata alcuna notifica.

If you do upload your file with a [!DNL .fin] file, but there is an error in the file, it is submitted for processing, but the error causes the processing to cease and the file to be sent to an error folder. If this occurs, a notification is sent to the email address listed in the [!UICONTROL Notification Recipient] field in the [!UICONTROL Create FTP Account] window. Se non è stato inserito nessun indirizzo e-mail, non viene inviata alcuna notifica.
