---
description: L’opzione FTP delle classificazioni (SAINT) offre maggiore flessibilità nel caricare set di dati di classificazione di grandi dimensioni, inclusa la possibilità di caricare dati in più suite di rapporti e set di dati di dimensioni superiori a 50.000 righe.
keywords: ftp;sftp
title: Classificazioni
feature: FTP Export
exl-id: fc783328-a70b-4af3-b3d3-c59ab79d6b8f
TQID: 'https://experienceleague.adobe.com/s6IsPVTe5aCHFiKUULLzcqOLaZ24LWqdVtDiIeu7hfs'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 439
ht-degree: 0%

---

# Classificazioni

L’opzione FTP delle classificazioni offre maggiore flessibilità nel caricare set di dati di classificazione di grandi dimensioni, inclusa la possibilità di caricare dati in più suite di rapporti e set di dati di dimensioni superiori a 50.000 righe.

Il tempo necessario affinché il sistema possa importare questi file varia in base a diversi fattori. Se un file caricato è presente sul server FTP per più di tre giorni, contatta l’Assistenza clienti di Adobe insieme agli utenti supportati dalla tua organizzazione.

Un’importazione corretta mostra immediatamente le modifiche appropriate in un’esportazione, mentre le modifiche ai dati in Analytics possono richiedere fino a quattro ore con un’importazione browser e fino a 24 ore con un’importazione FTP.

Per informazioni sui limiti FTP e sulla conservazione dei dati, vedere [Limiti FTP e conservazione dei dati](/help/export/ftp-and-sftp/ftp-limits.md).

## Informazioni sul file `.fin` per i caricamenti di classificazioni e origini dati {#section_1484719F8A134EAE91212DBD8F15174F}

Quando si carica un file di classificazione o di Data Source (`.tab` o `.txt`), è necessario caricare anche un file vuoto con lo stesso nome del file di dati da importare, ma con un .`.fin` estensione. Questo file `.fin` è un file completo. Lo scopo del file è quello di comunicare al sistema che il file di dati è stato completamente caricato sull&#39;account FTP. Il file `.fin` consente ad Adobe di riconoscere che l&#39;importazione è stata completata.

Dopo aver inviato sia il file di origine che il file `.fin`, è importante disconnettersi dal sito FTP. Il motivo è che Adobe Analytics utilizza gli eventi di disconnessione come attivatore per rendere i file pronti per l’elaborazione. Al termine dell’importazione, Adobe rimuove entrambi i file dal percorso FTP.

Fine file: [!DNL Classifications.fin]

Se carichi il file Origini dati o di Classificazione senza un file `.fin` associato, Adobe non lo aggiunge alla coda per l&#39;elaborazione. Il file rimane sull&#39;FTP e non viene applicato ai dati in CX Enterprise. Questo messaggio viene notificato solo se hai inserito il tuo indirizzo e-mail come [!UICONTROL Notification Recipient] nella finestra [!UICONTROL Create FTP Account] di Analytics. Se in questo campo non viene inserito alcun indirizzo e-mail, non viene inviata alcuna notifica.

Se si carica il file con un file `.fin` ma nel file è presente un errore, il file viene inviato per l&#39;elaborazione, ma l&#39;errore causa la cessazione dell&#39;elaborazione e l&#39;invio del file a una cartella di errori. In questo caso, viene inviata una notifica all&#39;indirizzo di posta elettronica elencato nel campo [!UICONTROL Notification Recipient] nella finestra [!UICONTROL Create FTP Account]. Se non è stato immesso alcun indirizzo e-mail, non viene inviata alcuna notifica.
