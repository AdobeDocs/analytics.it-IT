---
description: È possibile utilizzare Analytics per creare e gestire origini dati basate su FTP, che sfrutta il trasferimento di file FTP per importare dati non in linea o storici in CX Enterprise.
keywords: ftp;sftp
title: Panoramica su Origini dati
feature: FTP Export
exl-id: 777917bd-bd11-4360-a149-e4fd0bb2f99e
TQID: https://experienceleague.adobe.com/Mq4r5p1872tIxfjts7HOq50XWky12Oy4fTi9ajzbAsc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 157cc2bde1047063014aff39319d5cfaa1de9b5c
workflow-type: tm+mt
source-wordcount: 432
ht-degree: 1%

---

# Origini dati basate su FTP

È possibile utilizzare Analytics per creare e gestire origini dati basate su FTP, che sfrutta il trasferimento di file FTP per importare dati non in linea o storici in CX Enterprise.

Dopo aver creato un’istanza Origini dati, lo strumento fornisce una posizione FTP da utilizzare per caricare i file Origini dati. Una volta caricati, Origini dati li individua ed elabora automaticamente. Una volta elaborati i file, i dati sono disponibili per la generazione di rapporti di Analytics.

La scheda [!UICONTROL Create] in Gestione origini dati consente di configurare una nuova istanza Origini dati per la suite di rapporti selezionata. La Creazione guidata origini dati guida l&#39;utente nel processo di creazione di un modello Origini dati e crea un percorso FTP per il caricamento dei dati.

Nella finestra [!UICONTROL Manage Data Sources], individua l&#39;origine dati e seleziona il collegamento Informazioni FTP. Le informazioni di accesso FTP vengono visualizzate nella finestra [!UICONTROL Activate a Data Source] nella sezione [!UICONTROL Upload/FTP Information].

Per informazioni sui limiti FTP e sulla conservazione dei dati, vedere [Limiti FTP e conservazione dei dati](/help/export/ftp-and-sftp/ftp-limits.md).

## Informazioni sul file .fin per i caricamenti di classificazioni e origini dati {#section_1484719F8A134EAE91212DBD8F15174F}

Quando carichi un file di classificazioni o di origine dati ( `.tab` o `.txt`), è necessario caricare anche un file vuoto con lo stesso nome del file di dati da importare, ma con estensione `.fin`. Questo file `.fin` è un file completo. Lo scopo del file è quello di comunicare al sistema che il file di dati è stato completamente caricato sull&#39;account FTP. Il file `.fin` consente ad Adobe di riconoscere che l&#39;importazione è stata completata. Dopo l’invio, Adobe rimuove entrambi i file dall’FTP e inizia a elaborare l’importazione.

Importa file: `Classifications.tab`

Fine file: `Classifications.fin`

Se carichi il file Origini dati o SAINT senza un file `.fin` associato, Adobe non lo aggiunge alla coda per l&#39;elaborazione. Il file rimane sull&#39;FTP e non viene applicato ai dati dell&#39;organizzazione CX. Riceverai una notifica solo se hai inserito il tuo indirizzo e-mail come [!UICONTROL Notification Recipient] nella finestra di reporting [!UICONTROL Create FTP Account]. Se in questo campo non viene inserito alcun indirizzo e-mail, non viene inviata alcuna notifica.

Se si carica il file con un file `.fin` ma nel file è presente un errore, il file viene inviato per l&#39;elaborazione, ma l&#39;errore causa la cessazione dell&#39;elaborazione e l&#39;invio del file a una cartella di errori. In questo caso, viene inviata una notifica all&#39;indirizzo di posta elettronica elencato nel campo [!UICONTROL Notification Recipient] nella finestra [!UICONTROL Create FTP Account]. Se non viene inserito alcun indirizzo e-mail, non viene inviata alcuna notifica.
