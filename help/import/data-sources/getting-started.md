---
title: Guida introduttiva alle origini dati
description: Carica dati di esempio in una suite di rapporti per lo sviluppo.
exl-id: d9f74f55-abbb-4ceb-b4db-8d3c32aacd4a
feature: Data Sources
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 1%

---

# Guida introduttiva alle origini dati

Puoi seguire questi passaggi per caricare facilmente i dati di esempio in una suite di rapporti per lo sviluppo per visualizzare il flusso di lavoro in azione. Una volta compreso il processo, puoi espanderlo e personalizzarlo in base all’implementazione della tua organizzazione.

>[!IMPORTANT]
>
>Segui questi passaggi utilizzando una suite di rapporti di sviluppo o di test. I dati caricati tramite origini dati sono **permanente**. Se caricato lì, influisce sui dati della suite di rapporti di produzione.

1. Accedi ad Adobe Analytics tramite [https://experience.adobe.com](https://experience.adobe.com).
1. Passa a **[!UICONTROL Admin]** > **[!UICONTROL All Admin]** > **[!UICONTROL Data sources]**.
1. Seleziona una suite di rapporti per lo sviluppo utilizzando l’elenco a discesa in alto a destra.
1. Fai clic su **[!UICONTROL Create]** in alto a sinistra.
1. Sotto [!UICONTROL Select Category], scegli &quot;[!UICONTROL Generic]&quot;, e sotto [!UICONTROL Select Type], scegli &quot;[!UICONTROL Generic Data Source (Summary Data Only)]&quot;.
1. Fai clic su **[!UICONTROL Activate]**. Viene visualizzata una finestra a comparsa che mostra [!UICONTROL Data Source Activation Wizard].
   1. Passaggio 1: assegnare un nome all&#39;origine dati e fare clic sulla casella di controllo della liberatoria.
   1. Passaggio 2: questo passaggio è stato utilizzato in misura maggiore nelle versioni precedenti di Adobe Analytics. Fare clic su una casella di controllo, quindi digitare un valore nel campo di testo accanto a tale casella.
   1. Passaggio 3: scegliere la metrica da includere nel file del modello di origine dati. Seleziona &quot;Evento 1&quot; dall’elenco a discesa.
   1. Passaggio 4: questo passaggio è stato utilizzato in misura maggiore nelle versioni precedenti di Adobe Analytics. Fare clic su una casella di controllo, quindi digitare un valore nel campo di testo accanto a tale casella.
   1. Passaggio 5: scegliere la dimensione da includere nel file del modello di origine dati. Seleziona &quot;eVar1&quot; dall’elenco a discesa.
   1. Passaggio 6: rivedi il riepilogo, mostrando le dimensioni e le metriche incluse nel file modello.
   1. Passaggio 7: fai clic su **[!UICONTROL Download]** per scaricare il file modello origini dati. Nota inoltre le credenziali di accesso al sito FTP, in quanto vengono utilizzate a breve.
1. L&#39;origine dati viene ora creata e il passaggio successivo consiste nel fornire i dati da elaborare. Apri il file scaricato nell’editor di testo desiderato.
1. Il file modello contiene tre righe, due righe di commento (a partire da &quot;`#`&quot;) e una riga di intestazione:

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 2)
   #    eVar1    event1
   Date    Evar 1    Event 1
   ```

1. Immettere in più righe di dati, separando ogni voce con una tabulazione. Non utilizzare spazi o virgole per separare i valori.
   * La prima colonna è la data nel seguente formato: `MM/DD/YYYY/HH/mm/SS`.
   * La seconda colonna è il valore di testo che si desidera includere in eVar1.
   * La terza colonna è l&#39;importo che si desidera aumentare nell&#39;evento 1.

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 5)
   #    eVar1    event1
   Date    Evar 1    Event 1
   09/07/YYYY/11/23/00    Data source example value    3
   09/07/YYYY/15/59/00    Another data source value    18
   ```

1. Salvate il file. Facoltativamente, puoi assegnargli un nome file diverso, se lo desideri. Una volta salvato il file, puoi chiudere l’editor di testo.
1. In Esplora risorse, nel Finder o nel client FTP desiderato, passare a [ftp://ftp.omniture.com](ftp://ftp.omniture.com).
1. Quando vengono richieste le credenziali di accesso, utilizzare il nome utente e la password forniti nell&#39;ultimo passaggio della procedura guidata di creazione dell&#39;origine dati. Puoi fare nuovamente riferimento a essa navigando su [!UICONTROL Data sources] e clic **[!UICONTROL FTP Info]** accanto all&#39;origine dati creata.
1. Dopo aver eseguito l&#39;autenticazione, trascinare il file modificato nella finestra FTP autenticata.
1. Creare un file di testo vuoto in qualsiasi posizione all&#39;esterno della finestra FTP. Assegna al file lo stesso nome del file delle origini dati caricato sul sito FTP, con una eccezione. Invece di un `.txt` tipo di file, assegna un `.fin` tipo di file. Verificare che le impostazioni del sistema operativo consentano di visualizzare e modificare i tipi di file.
1. Trascina il campo vuoto `.fin` nello stesso percorso FTP del file di origine dati. La presenza del `.fin` file indica all’Adobe che il file dell’origine dati è completamente caricato e pronto per essere acquisito.
1. Dopo alcuni minuti, il file scompare dalla posizione FTP ed è visibile nel reporting.
1. Aggiorna la pagina Origini dati e verifica che il file sia stato acquisito correttamente.
1. Passa ad Analysis Workspace e crea un progetto.
1. Trascina eVar1 come dimensione nell’area di lavoro e l’evento 1 come metrica. Assicurati che l’intervallo di date di Workspace includa le date fornite nell’origine dati.

   ![Esempio di rapporto](assets/success-report.png)

## Passaggi successivi

[Formato file](file-format.md): scopri i dettagli sulla creazione di un file di origini dati su misura per la tua organizzazione.
