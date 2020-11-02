---
description: L'opzione FTP classificazioni (SAINT) assicura una maggior flessibilità nel caricamento di grandi set di dati e consente inoltre di caricare i dati in più suite di report e di caricare set di dati con più di 50.000 righe.
keywords: ftp;sftp
title: Classificazioni
uuid: 35936c98-b785-43eb-89f4-ab42a10db256
translation-type: tm+mt
source-git-commit: 7a70a5185b768dbc09deca5c8989693501af0cca
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 40%

---


# Classificazioni

L&#39;opzione FTP classificazioni offre maggiore flessibilità nel caricamento di set di dati di classificazione di grandi dimensioni, inclusa la possibilità di caricare dati in più suite di rapporti e di caricare set di dati di dimensioni superiori a 50.000 righe.

Consulta [classificazioni](https://docs.adobe.com/content/help/it-IT/analytics/components/classifications/classifications-importer/c-working-with-saint.html) per conoscere i passaggi necessari a scaricare i dati di classificazione tramite FTP e per sapere come caricare file dati tramite FTP (inclusi i passaggi per creare un account FTP).

Il tempo necessario al sistema per l&#39;importazione dei file varia in base a diversi fattori. Se un file caricato è presente sul server FTP per più di tre giorni, chiedi agli utenti supportati della tua organizzazione di contattare  Assistenza clienti del Adobe.

Un import corretto visualizza immediatamente le modifiche corrette in un&#39;esportazione, mentre le modifiche ai dati in Analytics possono richiedere fino a 4 ore nel caso di un&#39;importazione tramite browser e fino a 24 ore del caso di un&#39;importazione tramite FTP.

Per informazioni sulla conservazione dei dati e sui limiti dell&#39;FTP, consulta [Conservazione dei dati e limitazioni dell&#39;FTP](/help/export/ftp-and-sftp/ftp-limits.md).

## About the `.fin` file for Classifications and Data Sources Uploads {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a Classification or Data Source file (`.tab` or `.txt`), the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a .`.fin` Estensione. This `.fin` file is a finish file. Lo scopo del file è quello di comunicare al sistema che il file di dati è stato completamente caricato sull&#39;account FTP. The `.fin` file lets Adobe recognize that you are done with your import.

Dopo aver inviato sia il file di origine che il `.fin` file, è importante disconnettersi dal sito FTP. Il motivo è che  Adobe Analytics utilizza gli eventi di logout come attivatore che i file sono pronti per l&#39;elaborazione. Al termine dell&#39;importazione,  Adobe rimuove entrambi i file dal percorso FTP.

Fine file: [!DNL Classifications.fin]

If you upload your Data Sources or Classification file without an accompanying `.fin` file, Adobe does not add it to the queue for processing. I file resteranno sull&#39;FTP e non verranno applicati ai tuoi dati in [!UICONTROL Experience Cloud]. You are notified of this only if you have entered your email address as the [!UICONTROL Notification Recipient] in the [!UICONTROL Create FTP Account] window of Analytics. Se non hai inserito nessun indirizzo e-mail, non verrà inviata alcuna notifica.

If you do upload your file with a `.fin` file, but there is an error in the file, it is submitted for processing, but the error causes the processing to cease and the file to be sent to an error folder. If this occurs, a notification is sent to the email address listed in the [!UICONTROL Notification Recipient] field in the [!UICONTROL Create FTP Account] window. Se non è stato inserito alcun indirizzo e-mail, non viene inviata alcuna notifica.
