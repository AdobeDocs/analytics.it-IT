---
title: Guida introduttiva alle origini dati
description: Carica dati di esempio in una suite di rapporti per lo sviluppo.
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 1%

---

# Guida introduttiva alle origini dati

Puoi seguire questi passaggi per caricare facilmente dati di esempio in una suite di rapporti per lo sviluppo per visualizzare il flusso di lavoro in azione. Una volta compreso il processo, puoi espanderlo e personalizzarlo in base all’implementazione della tua organizzazione.

>[!IMPORTANT]
>
>Segui questi passaggi utilizzando una suite di rapporti di sviluppo o di test. I dati caricati tramite origini dati sono **permanente**. Ha un impatto sui dati della suite di rapporti di produzione se caricati lì.

1. Accedi ad Adobe Analytics tramite [https://experience.adobe.com](https://experience.adobe.com).
1. Passa a **[!UICONTROL Admin]** > **[!UICONTROL All Admin]** > **[!UICONTROL Data sources]**.
1. Seleziona una suite di rapporti per lo sviluppo utilizzando il menu a discesa in alto a destra.
1. Fai clic sul pulsante **[!UICONTROL Create]** in alto a sinistra.
1. Sotto [!UICONTROL Select Category], scegli &quot;[!UICONTROL Generic]&quot;, e [!UICONTROL Select Type], scegli &quot;[!UICONTROL Generic Data Source (Summary Data Only)]&quot;.
1. Fai clic su **[!UICONTROL Activate]**. Viene visualizzata una finestra a comparsa che mostra il [!UICONTROL Data Source Activation Wizard].
   1. Passaggio 1: Assegna un nome all&#39;origine dati e fai clic sulla casella di controllo liberatoria.
   1. Passaggio 2: Questo passaggio è stato più utilizzato nelle versioni precedenti di Adobe Analytics. Fare clic su una casella di controllo, quindi digitare un valore nel campo di testo accanto a essa.
   1. Passaggio 3: Scegli la metrica da includere nel file modello di origine dati. Seleziona &quot;Evento 1&quot; dal menu a discesa.
   1. Passaggio 4: Questo passaggio è stato più utilizzato nelle versioni precedenti di Adobe Analytics. Fare clic su una casella di controllo, quindi digitare un valore nel campo di testo accanto a essa.
   1. Passaggio 5: Scegli la dimensione da includere nel file modello di origine dati. Seleziona &quot;eVar1&quot; dal menu a discesa.
   1. Passaggio 6: Rivedi il riepilogo, mostrando le dimensioni e le metriche incluse nel file modello.
   1. Passaggio 7: Fai clic sul pulsante **[!UICONTROL Download]** per scaricare il file modello origini dati. Prendi anche nota delle credenziali di accesso al sito FTP, in quanto verranno utilizzate a breve.
1. L&#39;origine dati viene ora creata; il passaggio successivo consiste nel fornirle i dati da elaborare. Apri il file scaricato nell’editor di testo desiderato.
1. Il file modello contiene tre righe; due righe di commento (a partire da &quot;`#`&quot;) e una riga di intestazione:

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 2)
   #	eVar1	event1
   Date	Evar 1	Event 1
   ```

1. Immetti in diverse righe di dati, separando ogni voce da una scheda. Non utilizzare spazi o virgole per separare i valori.
   * La prima colonna è la data nel seguente formato: `MM/DD/YYYY/HH/mm/SS`.
   * La seconda colonna è il valore di testo che si desidera includere in eVar1.
   * La terza colonna è la quantità che desideri aumentare l&#39;evento 1.

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 5)
   #	eVar1	event1
   Date	Evar 1	Event 1
   09/07/YYYY/11/23/00	Data source example value	3
   09/07/YYYY/15/59/00	Another data source value	18
   ```

1. Salvate il file. Se lo desideri, puoi assegnare un nome file diverso. Una volta salvato il file, puoi chiudere l’editor di testo.
1. In Esplora risorse, Finder o il client FTP desiderato, passa a [ftp://ftp.omniture.com](ftp://ftp.omniture.com).
1. Quando viene richiesto di specificare le credenziali di accesso, utilizza il nome utente e la password forniti nell’ultimo passaggio della procedura guidata di creazione dell’origine dati. Per farvi nuovamente riferimento, vai a [!UICONTROL Data sources] e facendo clic su **[!UICONTROL FTP Info]** accanto all’origine dati creata.
1. Dopo aver eseguito l&#39;autenticazione, trascina il file modificato nella finestra FTP autenticata.
1. Crea un file di testo vuoto in qualsiasi posizione al di fuori della finestra FTP. Assegna lo stesso nome file del file origini dati caricato sul sito FTP, con un&#39;eccezione. Invece di un `.txt` tipo di file, fornisci un `.fin` tipo di file. Assicurati che le impostazioni del sistema operativo ti consentano di visualizzare e modificare i tipi di file.
1. Trascina il campo vuoto `.fin` nella stessa posizione FTP del file di origine dati. La presenza di `.fin` file comunica ad Adobe che il file di origine dati è completamente caricato e pronto per essere acquisito.
1. Dopo diversi minuti, il file scompare dalla posizione FTP ed è visibile nel reporting.
1. Aggiorna la pagina Origini dati e verifica che il file sia stato acquisito correttamente.
1. Passa ad Analysis Workspace e crea un progetto.
1. Trascina eVar1 come dimensione nell’area di lavoro e l’evento 1 come metrica. Assicurati che l’intervallo di date di Workspace includa le date specificate nell’origine dati.

   ![Esempio di rapporto](assets/success-report.png)

## Passaggi successivi

[Formato file](file-format.md): Scopri i dettagli sulla creazione di un file origini dati personalizzato per la tua organizzazione.