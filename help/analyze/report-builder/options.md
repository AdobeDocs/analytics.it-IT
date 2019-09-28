---
description: Nel pannello Opzioni, potete specificare le impostazioni di data, latenza (Dati correnti), informazioni di registro e configurare gli aggiornamenti.
seo-description: Nel pannello Opzioni, potete specificare le impostazioni di data, latenza (Dati correnti), informazioni di registro e configurare gli aggiornamenti.
seo-title: Opzioni di Report Builder
solution: Analytics
title: Opzioni di Report Builder
topic: Generatore di report
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Opzioni di Report Builder

Nel pannello Opzioni, potete specificare le impostazioni di data, latenza (Dati correnti), informazioni di registro e configurare gli aggiornamenti.

1. Nella barra degli strumenti Componenti aggiuntivi, fate clic su **[!UICONTROL Options]**![](assets/options_icon.png):

| Elemento | Descrizione |
|--- |--- |
| [!UICONTROL As Of Date] |  |
| Imposta sulla data corrente | Consente di specificare o reimpostare la data in [!UICONTROL As Of Date] modo che il generatore di report utilizzi la data corrente o ti chieda quale data utilizzare al momento dell'aggiornamento. |
| Chiedetemi di impostare al momento dell'aggiornamento | Consente di impostare l’impostazione [!UICONTROL As Of Date] durante l’aggiornamento di una richiesta. |
| [!UICONTROL Data Recency] |  |
| [!UICONTROL Include Current Data] | Consente di visualizzare la latenza dei dati (nota anche come [!UICONTROL Data Recency]) al minuto nei rapporti, talvolta anche prima che tali dati siano stati elaborati da Adobe Analytics.<br>Se non si utilizza questa opzione, viene utilizzata la modalità finale (elaborata), che in genere è più [latente](https://marketing.adobe.com/resources/help/en_US/reference/data_latency.html).<br>Questa impostazione si applica a tutte le richieste nella cartella di lavoro che sono compatibili con Dati correnti. Se la richiesta non è compatibile, viene applicata la modalità finale.<br>Tenere presente le situazioni seguenti per l’utilizzo della [!UICONTROL Include Current Data] modalità:Opzioni<br>**** formato: È possibile specificare se visualizzare tali informazioni ([!UICONTROL Data Recency]) durante la [formattazione delle intestazioni](../../analyze/report-builder/layout/t-format-display-headers.md)di visualizzazione.<br>**Suddivisioni**: Non supportato. Se la [!UICONTROL Data Recency] modalità è impostata su Dati correnti e una delle richieste contiene un elemento di suddivisione, la richiesta ritorna alla modalità dati non corrente. Altre richieste, tuttavia, continuano a utilizzare la modalità Dati correnti.<br>**Request Manager**: È possibile visualizzare una colonna Dati correnti in Gestore richieste per verificare se l'impostazione è applicata a una richiesta pianificata.<br>**Cartelle di lavoro** pianificate: Questa modalità viene memorizzata durante il processo di programmazione a livello di cartella di lavoro. Se si apre una cartella di lavoro pianificata che utilizza dati finalizzati e si applica [!UICONTROL Include Current Data], in seguito verrà utilizzata la modalità corrente.<br>**Autorizzazioni**: Per gli utenti che non hanno accesso ai dati correnti, questa opzione è nascosta.  Quando si abilita questa opzione, se non è possibile applicare una o più richieste, viene emesso un avviso. |
| Disattiva avvisi di richiesta incompatibili con i dati correnti | Visualizza gli avvisi se la [!UICONTROL Include Current Data] modalità è selezionata ma la modalità dati non può essere applicata alla richiesta modificata.  Ad esempio, se imposti [!UICONTROL Include Current Data]e quindi modifichi una richiesta con un segmento selezionato, viene emesso un avviso. |
| Richieste del generatore di report di registro al file locale (per la risoluzione dei problemi) | Consente di registrare le richieste in un file locale. Utilizzate questo file di registro per la risoluzione dei problemi. |
| Interpreta valore digitato... | Interpreta un valore digitato in un controllo filtro come posizione di cella prima di considerarlo come espressione di filtro.<br>Ad esempio, se create una richiesta per le 10 pagine principali utilizzando le scarpe filtro, nella richiesta viene visualizzata una cella contenente qualcosa di simile a:   Filtro: Top 1-10 Page, Page contains Shoes |
| Aggiorna quando è disponibile una nuova versione | Indica al sistema di notificare all'utente se è disponibile una nuova versione per l'installazione. |
