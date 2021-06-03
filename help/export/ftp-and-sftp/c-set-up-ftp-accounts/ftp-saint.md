---
description: L'opzione FTP classificazioni (SAINT) assicura una maggior flessibilità nel caricamento di grandi set di dati e consente inoltre di caricare i dati in più suite di report e di caricare set di dati con più di 50.000 righe.
keywords: ftp;sftp
title: Classificazioni
uuid: 35936c98-b785-43eb-89f4-ab42a10db256
exl-id: fc783328-a70b-4af3-b3d3-c59ab79d6b8f
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 38%

---

# Classificazioni

L&#39;opzione FTP classificazioni offre maggiore flessibilità nel caricamento di set di dati di classificazione di grandi dimensioni, inclusa la possibilità di caricare dati in più suite di rapporti e di caricare set di dati di dimensioni superiori a 50.000 righe.

Consulta [classificazioni](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html) per conoscere i passaggi necessari a scaricare i dati di classificazione tramite FTP e per sapere come caricare file dati tramite FTP (inclusi i passaggi per creare un account FTP).

Il tempo necessario al sistema per l&#39;importazione dei file varia in base a diversi fattori. Se un file caricato è presente sul server FTP per più di tre giorni, rivolgiti agli utenti supportati della tua organizzazione per contattare l’Assistenza clienti Adobe.

Un import corretto visualizza immediatamente le modifiche corrette in un&#39;esportazione, mentre le modifiche ai dati in Analytics possono richiedere fino a 4 ore nel caso di un&#39;importazione tramite browser e fino a 24 ore del caso di un&#39;importazione tramite FTP.

Per informazioni sulla conservazione dei dati e sui limiti dell&#39;FTP, consulta [Conservazione dei dati e limitazioni dell&#39;FTP](/help/export/ftp-and-sftp/ftp-limits.md).

## Informazioni sul file `.fin` per i caricamenti di classificazioni e origini dati {#section_1484719F8A134EAE91212DBD8F15174F}

Quando carichi un file di classificazione o di origine dati (`.tab` o `.txt`), il caricamento richiede anche di caricare un file vuoto con lo stesso nome del file di dati da importare, ma con un .`.fin` Estensione. Questo file `.fin` è un file di fine. Lo scopo del file è quello di comunicare al sistema che il file di dati è stato completamente caricato sull&#39;account FTP. Il file `.fin` consente ad Adobe di riconoscere che l’importazione ha completato.

Dopo aver inviato sia il file di origine che il file `.fin`, è importante disconnettersi dal sito FTP. Il motivo è che Adobe Analytics utilizza gli eventi di logout come attivatore e i file sono pronti per l’elaborazione. Al termine dell’importazione, Adobe rimuove entrambi i file dalla posizione FTP.

Fine file: [!DNL Classifications.fin]

Se carichi le Origini dati o il file di classificazione senza un file di accompagnamento `.fin`, Adobe non lo aggiunge alla coda di elaborazione. I file resteranno sull&#39;FTP e non verranno applicati ai tuoi dati in [!UICONTROL Experience Cloud]. Questo ti viene comunicato solo se hai inserito il tuo indirizzo e-mail come [!UICONTROL Notification Recipient] nella finestra [!UICONTROL Create FTP Account] di Analytics. Se non hai inserito nessun indirizzo e-mail, non verrà inviata alcuna notifica.

Se carichi il file con un file `.fin` ma si verifica un errore nel file, questo viene inviato per l’elaborazione, ma l’errore causa la cessazione dell’elaborazione e l’invio del file a una cartella di errore. In questo caso, viene inviata una notifica all’indirizzo e-mail elencato nel campo [!UICONTROL Notification Recipient] nella finestra [!UICONTROL Create FTP Account]. Se non è stato inserito alcun indirizzo e-mail, non viene inviata alcuna notifica.
