---
description: Puoi utilizzare Analytics per creare e gestire origini dati basate su FTP, che si basano sul trasferimento di file FTP per importare dati di cronologia o offline in Experience Cloud.
keywords: ftp; sftp
seo-description: Puoi utilizzare Analytics per creare e gestire origini dati basate su FTP, che si basano sul trasferimento di file FTP per importare dati di cronologia o offline in Experience Cloud.
seo-title: 'Origini dati '
solution: Analytics
title: 'Origini dati '
uuid: 41 ba 2 de 7-d 33 d -4394-b 7 d 8-04 a 116 f 45419
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Origini dati 

Puoi utilizzare Analytics per creare e gestire origini dati basate su FTP, che si basano sul trasferimento di file FTP per importare dati di cronologia o offline in Experience Cloud.

Dopo aver creato un'istanza Origini dati, lo strumento fornisce una posizione FTP che puoi utilizzare per caricare i file Origini dati. Una volta caricati, Origini dati li individua automaticamente e li elabora. Al termine dell'elaborazione dei file, i dati sono disponibili per l'attività di report di Analytics.

La scheda [!UICONTROL Create] (Crea) in Gestione delle origini dati ti consente di configurare una nuova istanza Origini dati per la suite di report selezionata. [!UICONTROL Data Sources Wizard] (Procedura guidata Origini dati) ti guida attraverso il processo di creazione di un modello Origini dati e crea una posizione FTP per il caricamento dei dati.

Nella finestra [!UICONTROL Manage Data Sources] (Gestisci Origini dati) individua la tua origine dati e seleziona il link FTP Info. Your FTP login information is displayed in the [!UICONTROL Activate a Data Source] window in the [!UICONTROL Upload/FTP Information] section.

For information on FTP limits and data retention, see [FTP Limits and Data Retention](../../../export/ftp-and-sftp/ftp-limits.md#concept_8CAA1D8F27B3411AB902520AD6C9A70E).

## Informazioni sul file .fin per gli upload Classificazioni e Origini dati {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classifications or [!UICONTROL Data Source] file ( [!DNL .tab] or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. [!DNL .fin] Questo file è un file di fine. Lo scopo del file è quello di comunicare al sistema che il file di dati è stato completamente caricato sull'account FTP. [!DNL .fin] Il file consente ad Adobe di riconoscere che l'importazione è terminata. Dopo l'invio, Adobe rimuove entrambi i file dall'FTP e inizia a elaborare l'import.
Import File: [!DNL Classifications.tab]

Finish File: [!DNL Classifications.fin]

If you upload your Data Sources or SAINT file without an accompanying [!DNL .fin] file, Adobe does not add it to the queue for processing. I file resteranno sull'FTP e non verranno applicati ai tuoi dati in [!UICONTROL Experience Cloud]. You are notified of this only if you have entered your email address as the [!UICONTROL Notification Recipient] in the [!UICONTROL Create FTP Account] window of reporting. Se non hai inserito nessun indirizzo e-mail, non verrà inviata alcuna notifica.

If you do upload your file with a [!DNL .fin] file, but there is an error in the file, it is submitted for processing, but the error causes the processing to cease and the file to be sent to an error folder. If this occurs, a notification is sent to the email address listed in the [!UICONTROL Notification Recipient] field in the [!UICONTROL Create FTP Account] window. Se non è stato inserito nessun indirizzo e-mail, non viene inviata alcuna notifica.
