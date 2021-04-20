---
description: Nel pannello Opzioni puoi specificare le impostazioni di data, latenza (Dati correnti), informazioni di registro e configurare gli aggiornamenti.
title: Opzioni di Report Builder
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 2%

---


# Opzioni di Report Builder

Nel pannello Opzioni puoi specificare le impostazioni di data, latenza (Dati correnti), informazioni di registro e configurare gli aggiornamenti.

1. Nella barra degli strumenti Componenti aggiuntivi, fai clic su **[!UICONTROL Options]** ![](assets/options_icon.png):

| Elemento | Descrizione |
|--- |--- |
| [!UICONTROL As Of Date] |  |
| Imposta sulla data corrente | Consente di specificare o reimpostare il valore [!UICONTROL As Of Date] in modo che Report Builder utilizzi la data corrente o richieda la data da utilizzare al momento dell&#39;aggiornamento. |
| Chiedimi di impostare al momento dell&#39;aggiornamento | Consente di impostare [!UICONTROL As Of Date] quando si aggiorna una richiesta. |
| [!UICONTROL Data Recency] |  |
| [!UICONTROL Include Current Data] | Consente di visualizzare la latenza dei dati (nota anche come [!UICONTROL Data Recency]) al minuto nei rapporti, talvolta anche prima che tali dati siano stati elaborati da Adobe Analytics.<br>Quando non utilizzi questa opzione, viene utilizzata la modalità finalizzata (elaborata), che in genere è più  [latente](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/current-data.html).<br>Questa impostazione si applica a tutte le richieste della cartella di lavoro che sono compatibili con i dati correnti. Se la richiesta non è compatibile, viene applicata la modalità finale.<br>Tieni presente le situazioni seguenti per l’utilizzo della  [!UICONTROL Include Current Data] modalità:<br>**Opzioni di formato**: Puoi specificare se visualizzare queste informazioni ([!UICONTROL Data Recency]) durante la  [formattazione delle intestazioni](/help/analyze/report-builder/layout/t-format-display-headers.md) di visualizzazione.<br>**Suddivisioni**: Non supportato. Se la modalità [!UICONTROL Data Recency] è impostata su Dati correnti e una delle richieste contiene un elemento di suddivisione, questa richiesta ritorna alla modalità dati non corrente. Altre richieste, tuttavia, continuano a utilizzare la modalità Dati correnti .<br>**Request Manager**: Puoi visualizzare una colonna Dati correnti in Request Manager (Gestore richieste) per verificare se l’impostazione è applicata a una richiesta pianificata.<br>**Cartelle di lavoro pianificate**: Questa modalità viene memorizzata durante il processo di pianificazione a livello di cartella di lavoro. Se si apre una cartella di lavoro pianificata che utilizza dati finalizzati e si applica [!UICONTROL Include Current Data], in seguito verrà utilizzata la modalità corrente.<br>**Autorizzazioni**: Per gli utenti che non hanno accesso ai dati correnti, questa opzione è nascosta.  Quando si abilita questa opzione, se non è possibile applicare una o più richieste, viene visualizzato un avviso. |
| Disattiva avvisi di richiesta incompatibili di dati correnti | Visualizza gli avvisi se è selezionata la modalità [!UICONTROL Include Current Data] , ma non è possibile applicare la modalità dati alla richiesta modificata.  Ad esempio, se imposti [!UICONTROL Include Current Data] e quindi modifichi una richiesta con un segmento selezionato, viene emesso un avviso. |
| Registra le richieste del generatore di report nel file locale (per la risoluzione dei problemi) | Consente di registrare le richieste in un file locale. Usa questo file di registro per la risoluzione dei problemi. |
| Interpreta valore digitato.. | Interpreta un valore digitato in un controllo filtro come posizione di cella prima di considerarlo un&#39;espressione di filtro.<br>Ad esempio, se crei una richiesta Primi 10 pagine utilizzando le scarpe filtro, nella richiesta viene visualizzata una cella contenente qualcosa di simile a: Filtro: Top 1-10 Pagina, Pagina contiene Scarpe |
| Aggiorna quando è disponibile una nuova versione | Indica al sistema di notificare all&#39;utente se è disponibile una nuova versione per l&#39;installazione. |
