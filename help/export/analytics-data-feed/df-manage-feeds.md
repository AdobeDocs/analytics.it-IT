---
title: Gestire i feed dati
description: Scopri come navigare nell’interfaccia del feed dati. Scopri come creare, modificare e visualizzare un feed di dati.
feature: Data Feeds
exl-id: 4d4f0062-e079-48ff-9464-940c6425ad54
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 3%

---

# Gestire i feed dati

Data Feed Manager consente di creare, modificare ed eliminare feed di dati per l’organizzazione. Se disponi delle autorizzazioni per accedere al gestore dei feed dati, puoi gestire i feed dati per tutte le suite di rapporti visibili.


>[!BEGINSHADEBOX]

Per un video dimostrativo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Gestione feed dati](https://video.tv.adobe.com/v/25452?quality=12&learn=on){target="_blank"}.

>[!ENDSHADEBOX]


## Visualizzare feed di dati

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.
1. Seleziona l&#39;icona a 9 quadrati in alto a destra, quindi seleziona [!UICONTROL **Analytics**].
1. Nella barra di navigazione superiore, passa a [!UICONTROL **Amministratore**] > [!UICONTROL **Feed dati**].

   Vengono visualizzati i feed di dati per tutte le suite di rapporti a cui hai accesso. Oppure, se non è stato configurato alcun feed, la pagina mostra un pulsante [!UICONTROL Create New Data Feed].

   ![Feed dati](assets/feeds.png)

## Creare un feed di dati

Il pulsante [!UICONTROL Add] consente di creare un nuovo feed. Per ulteriori informazioni, vedere [Creare un feed di dati](create-feed.md).

## Modificare un feed dati

1. In Adobe Analytics, seleziona [!UICONTROL **Amministratore**] > [!UICONTROL **Feed dati**].

1. Individua il feed di dati da modificare. Per individuare un feed di dati, puoi [filtrare e cercare nell&#39;elenco dei feed di dati](#filter-and-search-the-list-of-data-feeds).

1. Selezionare il feed di dati nella colonna [!UICONTROL **Nome feed**].

1. Apporta le modifiche desiderate al feed dati.

   Quando aggiorni la sezione [!UICONTROL **Destinazione**] per un feed di dati che stai modificando, puoi scegliere un account e un percorso diversi da utilizzare per il nuovo feed di dati nei campi a discesa [!UICONTROL **Account**] e [!UICONTROL **Posizione**].

   Gli account e i percorsi possono essere modificati come descritto in [Configurare gli account di importazione ed esportazione cloud](/help/components/locations/configure-import-accounts.md) e [Configurare i percorsi di importazione ed esportazione cloud](/help/components/locations/configure-import-locations.md). La modifica di un account o di una posizione ha effetto su tutti gli elementi associati a tale account o posizione.

   Le versioni precedenti di Data Feeds Manager consentivano di creare destinazioni BLOB FTP, SFTP, S3 e Azure. Le destinazioni create in queste versioni precedenti di Data Feeds Manager non possono essere modificate o copiate.

1. Seleziona [!UICONTROL **Salva**].

## Filtrare ed eseguire ricerche nell’elenco dei feed di dati

1. In Adobe Analytics, seleziona [!UICONTROL **Amministratore**] > [!UICONTROL **Feed dati**].

1. Utilizza la ricerca o i filtri per individuare un feed specifico.

   * Nel campo di ricerca, inizia a digitare il nome di un feed. Solo i feed corrispondenti vengono visualizzati nell’elenco dei feed disponibili.

   * A sinistra, fai clic sull’icona del filtro per mostrare o nascondere le opzioni di filtro. I filtri sono organizzati per categoria. È possibile comprimere o espandere le categorie di filtro. Seleziona la casella di controllo accanto a qualsiasi filtro che desideri applicare.

![Filtro](assets/filters.png)

## Visualizzare i processi di feed dati

1. In Adobe Analytics, seleziona [!UICONTROL **Amministratore**] > [!UICONTROL **Feed dati**].

1. Seleziona la scheda [!UICONTROL **Processi**] per visualizzare i singoli processi creati da ciascun feed.

   Oppure

   Per visualizzare i processi per feed di dati specifici, seleziona la casella di controllo accanto a uno o più feed di dati, quindi seleziona [!UICONTROL **Cronologia processi**].

   Per ulteriori informazioni, consulta [Gestire i processi dei feed dati](df-manage-jobs.md).

## Copiare un feed dati

1. In Adobe Analytics, seleziona [!UICONTROL **Amministratore**] > [!UICONTROL **Feed dati**].

1. Seleziona la casella di controllo accanto al feed di dati da copiare, quindi seleziona [!UICONTROL **Copia**].

   Consente di [creare un nuovo feed](create-feed.md) con tutte le impostazioni del feed corrente. Questa opzione non è visibile se è selezionato più di un feed di dati.

   Quando aggiorni la sezione [!UICONTROL **Destinazione**] per un feed di dati che stai copiando, puoi scegliere un account e un percorso diversi da utilizzare per il nuovo feed di dati nei campi a discesa [!UICONTROL **Account**] e [!UICONTROL **Posizione**].

   Gli account e i percorsi possono essere modificati come descritto in [Configurare gli account di importazione ed esportazione cloud](/help/components/locations/configure-import-accounts.md) e [Configurare i percorsi di importazione ed esportazione cloud](/help/components/locations/configure-import-locations.md). La modifica di un account o di una posizione ha effetto su tutti gli elementi associati a tale account o posizione.

   Le versioni precedenti di Data Feeds Manager consentivano di creare destinazioni BLOB FTP, SFTP, S3 e Azure. Le destinazioni create in queste versioni precedenti di Data Feeds Manager non possono essere modificate o copiate.

## Mettere in pausa un feed dati

È possibile interrompere l&#39;elaborazione del feed impostandone lo stato su [!UICONTROL Inactive].

1. In Adobe Analytics, seleziona [!UICONTROL **Amministratore**] > [!UICONTROL **Feed dati**].

1. Selezionare la casella di controllo accanto al feed di dati che si desidera sospendere, quindi selezionare [!UICONTROL **Pausa**].

## Attivare un feed dati

È possibile attivare i feed inattivi.

I feed di backfill (feed che elaborano solo dati storici) riprendono l’elaborazione dei dati dal punto in cui si sono interrotti, eseguendo la backfill di eventuali date, se necessario. I feed live riprendono anche l’elaborazione dei dati da dove si sono interrotti.

>[!AVAILABILITY]
>
>La seguente modifica al modo in cui i feed live riprendono l’elaborazione dei dati si trova nella fase di test limitato del rilascio:
> 
>**I feed attivi riprendono l&#39;elaborazione dei dati dall&#39;ora corrente.**
>
>Questa modifica potrebbe non essere ancora disponibile nel tuo ambiente.
>
>Questa nota verrà rimossa quando questa modifica sarà generalmente disponibile. Per informazioni sul processo di rilascio di Analytics, consulta [Rilascio delle funzioni di Adobe Analytics](/help/release-notes/releases.md).

Per attivare un feed di dati:

1. In Adobe Analytics, seleziona [!UICONTROL **Amministratore**] > [!UICONTROL **Feed dati**].

1. Selezionare la casella di controllo accanto al feed dati inattivo che si desidera attivare, quindi selezionare [!UICONTROL **Attiva**].

## Eliminare un feed dati

Quando si elimina un feed di dati, lo stato è impostato su [!UICONTROL Deleted]. I feed di dati devono avere lo stato Attivo prima di poter essere eliminati.

Per eliminare un feed di dati:

1. In Adobe Analytics, seleziona [!UICONTROL **Amministratore**] > [!UICONTROL **Feed dati**].

1. Selezionare la casella di controllo accanto al feed di dati che si desidera eliminare, quindi selezionare [!UICONTROL **Elimina**].

## Configurare le colonne nel gestore dei feed dati

Ogni feed creato mostra diverse colonne che forniscono informazioni al riguardo. Seleziona un’intestazione di colonna per ordinarla in ordine crescente. Seleziona di nuovo un’intestazione di colonna per ordinarla in ordine decrescente. Se non riesci a visualizzare una colonna specifica, fai clic sull’icona della colonna in alto a destra.

![Icona colonna](assets/cols.jpg)

Sono disponibili le seguenti colonne:

* **Nome feed**: colonna obbligatoria. Visualizza il nome del feed.
* **ID feed**: visualizza l&#39;ID feed, un identificatore univoco.
* **Suite di rapporti**: la suite di rapporti da cui il feed fa riferimento ai dati.
* **ID suite di rapporti**: identificatore univoco della suite di rapporti.
* **Colonne dati**: quali colonne di dati sono attive per il feed. Nella maggior parte dei casi, sono presenti troppe colonne da visualizzare in questo formato.
* **Intervallo**: indica se il feed è orario o giornaliero.
* **Tipo di destinazione**: il tipo di destinazione per il feed. Ad esempio, Amazon S3, GCP o Azure.
* **Host di destinazione**: percorso in cui è inserito il file.
* **Proprietario**: account utente che ha creato il feed.
* **Stato**: lo stato del feed.
   * Attivo: il feed è operativo.
   * Approvazione in sospeso: in alcune circostanze, un feed richiede l’approvazione dell’Adobe prima di poter iniziare a generare processi.
   * Eliminato: il feed viene eliminato.
   * Completato: l&#39;elaborazione del feed è stata completata. Un feed completato può essere modificato, sospeso o annullato.
   * In sospeso: il feed viene creato ma non ancora attivo. I feed rimangono in questo stato per un breve periodo di transizione.
   * Inattivo: equivalente allo stato &#39;sospeso&#39; o &#39;in attesa&#39;. Per informazioni su ciò che accade con i feed di backfill e i feed live quando viene riattivato un feed inattivo, consulta [Attivare un feed di dati](#activate-a-data-feed).
* **Ultima modifica**: data dell&#39;ultima modifica del feed. La data e l’ora vengono visualizzate nel fuso orario della suite di rapporti con offset GMT.
* **Data inizio**: la data del primo processo per questo feed. La data e l’ora vengono visualizzate nel fuso orario della suite di rapporti con offset GMT.
* **Data di fine**: la data dell&#39;ultimo processo per questo feed. I feed di dati in corso non hanno una data di fine.

