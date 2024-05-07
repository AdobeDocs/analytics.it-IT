---
title: Interfaccia utente feed dati
description: Scopri come navigare nell’interfaccia del feed dati.
feature: Data Feeds
exl-id: 4d4f0062-e079-48ff-9464-940c6425ad54
source-git-commit: 6b8366b451be1612331f517ee80fd57744deafdc
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 2%

---

# Gestire i feed dati

Data Feed Manager consente di creare, modificare ed eliminare feed di dati per l’organizzazione. Se disponi delle autorizzazioni per accedere al gestore dei feed dati, puoi gestire i feed dati per tutte le suite di rapporti visibili.

Video sull’interfaccia utente di gestione dei feed di dati:

>[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

Accedi alla gestione dei feed dati seguendo questi passaggi:

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.
1. Seleziona l’icona a 9 quadrati in alto a destra, quindi seleziona [!UICONTROL **Analytics**].
1. Nella barra di navigazione superiore, vai a [!UICONTROL **Amministratore**] > [!UICONTROL **Feed dati**].

## Navigare nell’interfaccia

Quando si accede alla pagina di gestione dei feed di dati, l’interfaccia ha un aspetto simile al seguente:

![Feed dati](assets/feeds.png)

Se non è stato configurato alcun feed, nella pagina viene visualizzato un messaggio [!UICONTROL Create New Data Feed] pulsante.

### Filtri e ricerca

Utilizza la ricerca o i filtri per individuare un feed specifico.

* Nel campo di ricerca, inizia a digitare il nome di un feed. Solo i feed corrispondenti vengono visualizzati nell’elenco dei feed disponibili.

* A sinistra, fai clic sull’icona del filtro per mostrare o nascondere le opzioni di filtro. I filtri sono organizzati per categoria. È possibile comprimere o espandere le categorie di filtro. Seleziona la casella di controllo accanto a qualsiasi filtro che desideri applicare.

  ![Filtro](assets/filters.png)

### Feed e processi

Seleziona la [!UICONTROL **Processi**] per visualizzare i singoli processi creati da ciascun feed. Consulta [Gestire i processi dei feed dati](df-manage-jobs.md).

### Add

Il [!UICONTROL Add] consente di creare un nuovo feed. Consulta [Creare un feed di dati](create-feed.md) per ulteriori informazioni.

### Colonne

Ogni feed creato mostra diverse colonne che forniscono informazioni al riguardo. Seleziona un’intestazione di colonna per ordinarla in ordine crescente. Seleziona di nuovo un’intestazione di colonna per ordinarla in ordine decrescente. Se non riesci a visualizzare una colonna specifica, fai clic sull’icona della colonna in alto a destra.

![Icona colonna](assets/cols.jpg)

* **Nome feed**: colonna obbligatoria. Visualizza il nome del feed.
* **ID feed**: visualizza l’ID feed, un identificatore univoco.
* **Suite di rapporti**: la suite di rapporti da cui il feed fa riferimento ai dati.
* **ID suite di rapporti**: identificatore univoco della suite di rapporti.
* **Colonne dati**: quali colonne di dati sono attive per il feed. Nella maggior parte dei casi, sono presenti troppe colonne da visualizzare in questo formato.
* **Interval**: indica se il feed è orario o giornaliero.
* **Tipo di destinazione**: tipo di destinazione per il feed. Ad esempio, Amazon S3, GCP o Azure.
* **Host di destinazione**: posizione in cui viene inserito il file.
* **Proprietario**: account utente che ha creato il feed.
* **Stato**: stato del feed.
   * Attivo: il feed è operativo.
   * Approvazione in sospeso: in alcune circostanze, un feed richiede l’approvazione dell’Adobe prima di poter iniziare a generare processi.
   * Eliminato: il feed viene eliminato.
   * Completato: l&#39;elaborazione del feed è stata completata. Un feed completato può essere modificato, sospeso o annullato.
   * In sospeso: il feed viene creato ma non ancora attivo. I feed rimangono in questo stato per un breve periodo di transizione.
   * Inattivo: equivalente allo stato &#39;sospeso&#39; o &#39;in attesa&#39;. Se viene riattivato un feed di backfill (un feed che elabora solo dati storici), riprende a consegnare i processi da quando è stato interrotto. Se un feed live viene riattivato, riprende la consegna dei processi da quando è stato interrotto.
* **Ultima modifica**: data dell’ultima modifica apportata al feed. La data e l’ora vengono visualizzate nel fuso orario della suite di rapporti con offset GMT.
* **Data di inizio**: data del primo processo per questo feed. La data e l’ora vengono visualizzate nel fuso orario della suite di rapporti con offset GMT.
* **Data di fine**: data dell’ultimo processo per questo feed. I feed di dati in corso non hanno una data di fine.

## Azioni feed dati

Fai clic sulla casella di controllo accanto a un feed di dati per visualizzare le azioni disponibili.

* **Cronologia processi**: visualizza tutti i processi associati a questi feed di dati. Consente di accedere automaticamente al [interfaccia per la gestione dei processi](df-manage-jobs.md).
* **Elimina**: elimina il feed di dati, impostandone lo stato su [!UICONTROL Deleted].
* **Copia**: ti porta a [crea un nuovo feed](create-feed.md) con tutte le impostazioni del feed corrente. Non è possibile copiare un feed di dati se ne è selezionato più di uno.
* **Pausa**: interrompe l’elaborazione del feed, impostandone lo stato su [!UICONTROL Inactive].
* **Attiva**: disponibile solo per i feed inattivi. I feed di backfill (feed che elaborano solo dati storici) riprendono l’elaborazione dei dati dal punto in cui si sono interrotti, eseguendo la backfill di eventuali date, se necessario. I feed attivi riprendono l’elaborazione dei dati dall’ora corrente.
