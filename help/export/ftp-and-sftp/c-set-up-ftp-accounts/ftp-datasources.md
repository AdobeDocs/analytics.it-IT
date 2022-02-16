---
description: Puoi utilizzare Analytics per creare e gestire origini dati basate su FTP, che si basano sul trasferimento file FTP per importare dati di cronologia o offline nell’Experience Cloud.
keywords: ftp;sftp
title: Origini dati
feature: FTP Export
exl-id: 777917bd-bd11-4360-a149-e4fd0bb2f99e
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 44%

---

# Origini dati

Puoi utilizzare Analytics per creare e gestire origini dati basate su FTP, che si basano sul trasferimento file FTP per importare dati di cronologia o offline nell’Experience Cloud.

Dopo aver creato un&#39;istanza Origini dati, lo strumento fornisce una posizione FTP che puoi utilizzare per caricare i file Origini dati. Una volta caricati, Origini dati li individua automaticamente e li elabora. Al termine dell&#39;elaborazione dei file, i dati sono disponibili per l&#39;attività di report di Analytics.

La scheda [!UICONTROL Create] (Crea) in Gestione delle origini dati ti consente di configurare una nuova istanza Origini dati per la suite di report selezionata. [!UICONTROL Data Sources Wizard] (Procedura guidata Origini dati) ti guida attraverso il processo di creazione di un modello Origini dati e crea una posizione FTP per il caricamento dei dati.

Nella finestra [!UICONTROL Manage Data Sources] (Gestisci Origini dati) individua la tua origine dati e seleziona il link FTP Info. Le informazioni di accesso all&#39;FTP vengono visualizzate nel [!UICONTROL Activate a Data Source] nella finestra [!UICONTROL Upload/FTP Information] sezione .

Per informazioni sui limiti dell&#39;FTP e sulla conservazione dei dati, vedi [Conservazione dei dati e limitazioni dell&#39;FTP](/help/export/ftp-and-sftp/ftp-limits.md).

## Informazioni sul file .fin per gli upload Classificazioni e Origini dati {#section_1484719F8A134EAE91212DBD8F15174F}

Quando carichi una classificazione o [!UICONTROL Data Source] file ( [!DNL .tab] o [!DNL .txt]) il caricamento richiede anche di caricare un file vuoto con lo stesso nome del file di dati da importare, ma con un [!DNL .fin] estensione. Questo [!DNL .fin] file è un file di fine. Lo scopo del file è quello di comunicare al sistema che il file di dati è stato completamente caricato sull&#39;account FTP. La [!DNL .fin] consente ad Adobe di riconoscere che l’importazione ha completato. Dopo l&#39;invio, Adobe rimuove entrambi i file dall&#39;FTP e inizia a elaborare l&#39;import.
File di importazione: [!DNL Classifications.tab]

Fine file: [!DNL Classifications.fin]

Se carichi le tue Origini dati o il file SAINT senza un accompagnamento [!DNL .fin] file, Adobe non lo aggiunge alla coda di elaborazione. I file resteranno sull&#39;FTP e non verranno applicati ai tuoi dati in [!UICONTROL Experience Cloud]. Questo ti viene comunicato solo se hai inserito il tuo indirizzo e-mail come [!UICONTROL Notification Recipient] in [!UICONTROL Create FTP Account] intervallo di reporting. Se non hai inserito nessun indirizzo e-mail, non verrà inviata alcuna notifica.

Se si carica il file con un [!DNL .fin] file, ma si verifica un errore nel file, viene inviato per l’elaborazione, ma l’errore causa la cessazione dell’elaborazione e l’invio del file a una cartella di errore. In questo caso, viene inviata una notifica all’indirizzo e-mail elencato in [!UICONTROL Notification Recipient] nel campo [!UICONTROL Create FTP Account] finestra. Se non è stato inserito nessun indirizzo e-mail, non viene inviata alcuna notifica.
