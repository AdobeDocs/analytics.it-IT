---
description: L'opzione FTP classificazioni (SAINT) assicura una maggior flessibilità nel caricamento di grandi set di dati e consente inoltre di caricare i dati in più suite di report e di caricare set di dati con più di 50.000 righe.
keywords: ftp;sftp
title: Classificazioni
feature: FTP Export
exl-id: fc783328-a70b-4af3-b3d3-c59ab79d6b8f
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 33%

---

# Classificazioni

L’opzione FTP delle classificazioni offre maggiore flessibilità nel caricare set di dati di classificazione di grandi dimensioni, inclusa la possibilità di caricare dati in più suite di rapporti e set di dati di dimensioni superiori a 50.000 righe.

Consulta [classificazioni](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html?lang=it) per conoscere i passaggi necessari a scaricare i dati di classificazione tramite FTP e per sapere come caricare file dati tramite FTP (inclusi i passaggi per creare un account FTP).

Il tempo necessario al sistema per l&#39;importazione dei file varia in base a diversi fattori. Se un file caricato è presente sul server FTP per più di tre giorni, contatta l’Assistenza clienti Adobe insieme agli utenti supportati della tua organizzazione.

Un import corretto visualizza immediatamente le modifiche corrette in un&#39;esportazione, mentre le modifiche ai dati in Analytics possono richiedere fino a 4 ore nel caso di un&#39;importazione tramite browser e fino a 24 ore del caso di un&#39;importazione tramite FTP.

Per informazioni sui limiti FTP e sulla conservazione dei dati, vedere [Limiti FTP e conservazione dei dati](/help/export/ftp-and-sftp/ftp-limits.md).

## Informazioni sul file `.fin` per i caricamenti di classificazioni e origini dati {#section_1484719F8A134EAE91212DBD8F15174F}

Quando carichi un file di classificazione o di Data Source (`.tab` o `.txt`), è necessario caricare anche un file vuoto con lo stesso nome del file di dati da importare, ma con un .Estensione `.fin`. Questo file `.fin` è un file completo. Lo scopo del file è quello di comunicare al sistema che il file di dati è stato completamente caricato sull&#39;account FTP. Il file `.fin` consente ad Adobe di riconoscere che l&#39;importazione è stata completata.

Dopo aver inviato sia il file di origine che il file `.fin`, è importante disconnettersi dal sito FTP. Il motivo è che Adobe Analytics utilizza gli eventi di disconnessione come attivatore per rendere i file pronti per l’elaborazione. Al termine dell&#39;importazione, Adobe rimuove entrambi i file dal percorso FTP.

Fine file: [!DNL Classifications.fin]

Se carichi il file Origini dati o di Classificazione senza un file `.fin` associato, Adobe non lo aggiunge alla coda per l&#39;elaborazione. Il file rimane sull&#39;FTP e non viene applicato ai tuoi dati in [!UICONTROL Experience Cloud]. Questo messaggio viene notificato solo se hai inserito il tuo indirizzo e-mail come [!UICONTROL Notification Recipient] nella finestra [!UICONTROL Create FTP Account] di Analytics. Se non hai inserito nessun indirizzo e-mail, non verrà inviata alcuna notifica.

Se si carica il file con un file `.fin` ma nel file è presente un errore, il file viene inviato per l&#39;elaborazione, ma l&#39;errore causa la cessazione dell&#39;elaborazione e l&#39;invio del file a una cartella di errori. In questo caso, viene inviata una notifica all&#39;indirizzo di posta elettronica elencato nel campo [!UICONTROL Notification Recipient] nella finestra [!UICONTROL Create FTP Account]. Se non è stato immesso alcun indirizzo e-mail, non viene inviata alcuna notifica.
