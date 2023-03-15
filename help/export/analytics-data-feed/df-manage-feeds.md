---
title: Interfaccia utente feed dati
description: Scopri come navigare nell’interfaccia del feed dati.
feature: Data Feeds
exl-id: 4d4f0062-e079-48ff-9464-940c6425ad54
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 2%

---

# Gestire i feed dati

Data Feed Manager consente di creare, modificare ed eliminare feed di dati per l’organizzazione. Se disponi delle autorizzazioni per accedere al gestore dei feed dati, puoi gestire i feed dati per tutte le suite di rapporti visibili.

Video sull’interfaccia utente di gestione dei feed di dati:

>[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

Accedi alla gestione dei feed dati seguendo questi passaggi:

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com).
2. Fai clic sul menu a 9 griglie in alto a destra, quindi fai clic su [!UICONTROL Analytics].
3. Nel menu principale, fai clic su [!UICONTROL Admin] > [!UICONTROL Data Feeds].

![Menu feed dati](assets/AdminMenu.png)

## Navigazione nell’interfaccia

Quando si accede alla pagina di gestione dei feed di dati, l’interfaccia ha un aspetto simile al seguente:

![Feed di dati](assets/feeds.png)

Se non è stato configurato alcun feed, nella pagina viene visualizzato un messaggio [!UICONTROL Create New Data Feed] pulsante.

### Filtri e ricerca

Utilizza i filtri e cerca per individuare il feed esatto che stai cercando.

A sinistra, fai clic sull’icona del filtro per mostrare o nascondere le opzioni di filtro. I filtri sono organizzati per categoria. Fai clic sulla freccia per comprimere o espandere le categorie di filtro. Fai clic sulla casella di controllo per applicare il filtro.

![Filtro](assets/filters.jpg)

Utilizza la ricerca per individuare un feed in base al nome.

![Ricerca](assets/search.jpg)

### Feed e processi

Fai clic sulla scheda Processi per visualizzare i singoli processi creati da ciascuno dei tuoi feed. Consulta [Gestire i processi dei feed dati](df-manage-jobs.md).

### Add

Fai clic su + accanto alle schede feed e processi [!UICONTROL Add] per creare un nuovo feed. Consulta [Aggiungere un feed](create-feed.md) per ulteriori informazioni.

### Colonne

Ogni feed creato mostra diverse colonne che forniscono informazioni al riguardo. Fai clic su un’intestazione di colonna per ordinarla in ordine crescente. Fai di nuovo clic su un’intestazione di colonna per ordinarla in ordine decrescente. Se non riesci a visualizzare una colonna specifica, fai clic sull’icona della colonna in alto a destra.

![Icona colonna](assets/cols.jpg)

* **Nome feed**: colonna obbligatoria. Visualizza il nome del feed.
* **ID feed**: visualizza l’ID feed, un identificatore univoco.
* **Suite di rapporti**: la suite di rapporti da cui il feed fa riferimento ai dati.
* **ID suite di rapporti**: identificatore univoco della suite di rapporti.
* **Colonne dati**: quali colonne di dati sono attive per il feed. Nella maggior parte dei casi, sono presenti troppe colonne da visualizzare in questo formato.
* **Interval**: indica se il feed è orario o giornaliero.
* **Tipo di destinazione**: tipo di destinazione per il feed. Ad esempio, FTP, Amazon S3 o Azure.
* **Host di destinazione**: posizione in cui viene inserito il file. Esempio: `ftp.example.com`.
* **Proprietario**: account utente che ha creato il feed.
* **Stato**: stato del feed.
   * Attivo: il feed è operativo.
   * Approvazione in sospeso: in alcune circostanze, un feed richiede l’approvazione dell’Adobe prima di poter iniziare a generare processi.
   * Eliminato: il feed viene eliminato.
   * Completato: l&#39;elaborazione del feed è stata completata. Un feed completato può essere modificato, sospeso o annullato.
   * In sospeso: il feed viene creato ma non ancora attivo. I feed rimangono in questo stato per un breve periodo di transizione.
   * Inattivo: equivalente allo stato &#39;sospeso&#39; o &#39;in attesa&#39;. Quando il feed viene riattivato, riprende la consegna dei processi da quando è stato interrotto.
* **Ultima modifica**: data dell’ultima modifica apportata al feed. La data e l’ora vengono visualizzate nel fuso orario della suite di rapporti con offset GMT.
* **Data di inizio**: data del primo processo per questo feed. La data e l’ora vengono visualizzate nel fuso orario della suite di rapporti con offset GMT.
* **Data di fine**: data dell’ultimo processo per questo feed. I feed di dati in corso non hanno una data di fine.

## Azioni feed dati

Fai clic sulla casella di controllo accanto a un feed di dati per visualizzare le azioni disponibili.

* **Cronologia processi**: visualizza tutti i processi associati a questi feed di dati. Consente di accedere automaticamente al [interfaccia per la gestione dei processi](df-manage-jobs.md).
* **Elimina**: elimina il feed di dati, impostandone lo stato su [!UICONTROL Deleted].
* **Copia**: ti porta a [crea un nuovo feed](create-feed.md) con tutte le impostazioni del feed corrente. Non è possibile copiare un feed di dati se ne è selezionato più di uno.
* **Pausa**: interrompe l’elaborazione del feed, impostandone lo stato su [!UICONTROL Inactive].
* **Attiva**: disponibile solo per i feed inattivi. Raccoglie i dati di elaborazione nel punto in cui sono stati interrotti, fornendo le date precedenti, se necessario.
