---
title: Interfaccia feed dati
description: Scopri come navigare nell’interfaccia del feed di dati.
translation-type: tm+mt
source-git-commit: c9b3471b138c2e056a5abadb4ace6bb4eccd1d72

---


# Gestire i feed dati

Il gestore dei feed di dati consente di creare, modificare ed eliminare feed di dati per la propria organizzazione. Se disponete delle autorizzazioni per accedere al gestore feed di dati, potete gestire i feed di dati per tutte le suite di rapporti che vi sono visibili.

Accedi alla gestione dei feed di dati eseguendo la procedura seguente:

1. Effettuate l&#39;accesso a [Experience ecCloud.adobe.com](https://experiencecloud.adobe.com).
2. Fare clic sul menu a 9 griglia in alto a destra, quindi fare clic [!UICONTROL Analytics].
3. In the top menu, click [!UICONTROL Admin] > [!UICONTROL Data Feeds].

![Feed dati, menu](assets/AdminMenu.png)

## Navigazione nell’interfaccia

Quando si arriva alla pagina di gestione dei feed di dati, l&#39;interfaccia è simile alla seguente:

![Feed dati](assets/feeds.png)

Se non sono stati impostati feed, la pagina mostra un [!UICONTROL Create New Data Feed] pulsante.

### Filtri e ricerca

Utilizzate i filtri e cercate per individuare il feed esatto che state cercando.

A sinistra, fate clic sull&#39;icona del filtro per mostrare o nascondere le opzioni di filtro. I filtri sono organizzati per categoria. Fate clic sulla freccia per comprimere o espandere le categorie di filtri. Fate clic sulla casella di controllo per applicare il filtro.

![Filtro](assets/filters.jpg)

Utilizzate la ricerca per individuare un feed per nome.

![Cerca](assets/search.jpg)

### Feed e processi

Fate clic sulla scheda Processi per visualizzare i singoli processi creati da ciascun feed. See [Manage data feed jobs](df-manage-jobs.md).

### Aggiungi

Vicino alle schede dei feed e dei processi, fate clic sul pulsante + [!UICONTROL Add] per creare un nuovo feed. Per ulteriori informazioni, consultate [Aggiungere un feed](create-feed.md) .

### Colonne

Ogni feed creato mostra diverse colonne con informazioni al riguardo. Fate clic sull’intestazione di una colonna per ordinarla in ordine crescente. Fate di nuovo clic sull’intestazione di una colonna per ordinarla in ordine decrescente. Se non è possibile visualizzare una colonna specifica, fate clic sull&#39;icona della colonna in alto a destra.

![Icona Colonna](assets/cols.jpg)

* **Nome** feed: Colonna obbligatoria. Visualizza il nome del feed.
* **ID** feed: Visualizza l&#39;ID feed, un identificatore univoco.
* **Suite** di rapporti: La suite di rapporti da cui vengono forniti i dati dei riferimenti ai feed.
* **ID** suite di rapporti: Identificatore univoco della suite di rapporti.
* **Colonne** dati: Le colonne di dati attive per il feed. Nella maggior parte dei casi, le colonne da visualizzare in questo formato sono troppe.
* **Intervallo**: Indicatore se il feed è su base oraria o giornaliera.
* **Tipo** di destinazione: Il tipo di destinazione per il feed. Ad esempio, FTP, Amazon S3 o Azure.
* **Host** di destinazione: Posizione in cui viene posizionato il file. Ad esempio, `ftp.example.com`.
* **Proprietario**: L&#39;account utente che ha creato il feed.
* **Stato**: Stato del feed.
   * Attivo: Il feed è operativo.
   * Approvazione in sospeso: In alcuni casi, un feed richiede l’approvazione di Adobe prima di poter iniziare a generare processi.
   * Eliminato: Il feed viene eliminato.
   * Completa: Elaborazione del feed completata. Un feed completato può essere modificato, messo in pausa o annullato.
   * In sospeso: Il feed viene creato ma non è ancora attivo. I mangimi rimangono in questo stato per un breve periodo transitorio.
   * Inattivo: Equivalente allo stato &#39;pause&#39; o &#39;in pausa&#39;. Quando il feed viene riattivato, riprende la distribuzione dei processi da quando viene interrotto.
* **Ultima modifica**: Data dell’ultima modifica del feed. La data e l&#39;ora sono visualizzate nel fuso orario della suite di rapporti con l&#39;offset GMT.
* **Data** inizio: Data del primo processo per questo feed. La data e l&#39;ora sono visualizzate nel fuso orario della suite di rapporti con l&#39;offset GMT.
* **Data** finale: Data dell&#39;ultimo processo per questo feed. I feed di dati in corso non dispongono di una data di fine.

## Azioni feed di dati

Fai clic sulla casella di controllo accanto a un feed di dati per visualizzare le azioni disponibili.

* **Cronologia** processo: Visualizza tutti i processi collegati ai feed di dati. Viene automaticamente visualizzata l’interfaccia [](df-manage-jobs.md)Gestisci processi.
* **Elimina**: Elimina il feed di dati impostandone lo stato su [!UICONTROL Deleted].
* **Copia**: Consente di [creare un nuovo feed](create-feed.md) con tutte le impostazioni del feed corrente. Non è possibile copiare un feed di dati se sono selezionati più feed.
* **Pausa**: Interrompe l&#39;elaborazione del feed, impostandone lo stato su [!UICONTROL Inactive].
* **Attiva**: Disponibile solo per i feed inattivi. Raccoglie i dati di elaborazione nel punto in cui sono stati interrotti, restituendo eventuali date.
