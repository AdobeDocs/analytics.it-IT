---
description: Puoi utilizzare Analytics per creare e gestire Origini dati basate su FTP, che sfrutta il trasferimento di file FTP per importare dati offline o storici in Experience Cloud.
keywords: ftp;sftp
title: Panoramica su Origini dati
feature: FTP Export
exl-id: 777917bd-bd11-4360-a149-e4fd0bb2f99e
source-git-commit: 7dc97ad5225baf56c829efc8c21b07154bdd8ff9
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 24%

---

# Origini dati basate su FTP

Puoi utilizzare Analytics per creare e gestire Origini dati basate su FTP, che sfrutta il trasferimento di file FTP per importare dati offline o storici in Experience Cloud.

Dopo aver creato un&#39;istanza Origini dati, lo strumento fornisce una posizione FTP che puoi utilizzare per caricare i file Origini dati. Una volta caricati, Origini dati li individua automaticamente e li elabora. Al termine dell&#39;elaborazione dei file, i dati sono disponibili per l&#39;attività di report di Analytics.

La scheda [!UICONTROL Create] in Gestione origini dati consente di configurare una nuova istanza Origini dati per la suite di rapporti selezionata. [!UICONTROL Data Sources Wizard] ti guida attraverso il processo di creazione di un modello Origini dati e crea un percorso FTP per il caricamento dei dati.

Nella finestra [!UICONTROL Manage Data Sources], individua l&#39;origine dati e seleziona il collegamento Informazioni FTP. Le informazioni di accesso FTP vengono visualizzate nella finestra [!UICONTROL Activate a Data Source] nella sezione [!UICONTROL Upload/FTP Information].

Per informazioni sui limiti FTP e sulla conservazione dei dati, vedere [Limiti FTP e conservazione dei dati](/help/export/ftp-and-sftp/ftp-limits.md).

## Informazioni sul file .fin per gli upload Classificazioni e Origini dati {#section_1484719F8A134EAE91212DBD8F15174F}

Quando carichi una classificazione o un file [!UICONTROL Data Source] ( [!DNL .tab] o [!DNL .txt]), è necessario caricare anche un file vuoto con lo stesso nome del file di dati da importare, ma con estensione [!DNL .fin]. Questo file [!DNL .fin] è un file completo. Lo scopo del file è quello di comunicare al sistema che il file di dati è stato completamente caricato sull&#39;account FTP. Il file [!DNL .fin] consente ad Adobe di riconoscere che l&#39;importazione è stata completata. Dopo l’invio, Adobe rimuove entrambi i file dall’FTP e inizia a elaborare l’importazione.
Importa file: [!DNL Classifications.tab]

Fine file: [!DNL Classifications.fin]

Se carichi il file Origini dati o SAINT senza un file [!DNL .fin] associato, Adobe non lo aggiunge alla coda per l&#39;elaborazione. Il file rimane sull&#39;FTP e non viene applicato ai tuoi dati in [!UICONTROL Experience Cloud]. Riceverai una notifica solo se hai inserito il tuo indirizzo e-mail come [!UICONTROL Notification Recipient] nella finestra di reporting [!UICONTROL Create FTP Account]. Se non hai inserito nessun indirizzo e-mail, non verrà inviata alcuna notifica.

Se si carica il file con un file [!DNL .fin] ma nel file è presente un errore, il file viene inviato per l&#39;elaborazione, ma l&#39;errore causa la cessazione dell&#39;elaborazione e l&#39;invio del file a una cartella di errori. In questo caso, viene inviata una notifica all&#39;indirizzo di posta elettronica elencato nel campo [!UICONTROL Notification Recipient] nella finestra [!UICONTROL Create FTP Account]. Se non è stato inserito nessun indirizzo e-mail, non viene inviata alcuna notifica.
