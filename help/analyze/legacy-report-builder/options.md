---
description: Scopri le opzioni di Report Builder.
title: Informazioni sulle opzioni di Report Builder
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
feature: Report Builder
role: User, Admin
exl-id: d3388990-7919-461d-a96e-4c996b8bdb8b
source-git-commit: 12d048b42c6a61e03dbbe73acb9d34df3e37693c
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 1%

---

# Opzioni di Report Builder

Nel pannello Opzioni è possibile specificare le impostazioni di data, le impostazioni di latenza (dati correnti), le informazioni di registro e configurare gli aggiornamenti.

1. Nella barra degli strumenti Componenti aggiuntivi fare clic su **[!UICONTROL Options]** ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg):

| Elemento | Descrizione |
|--- |--- |
| [!UICONTROL As Of Date] |  |
| Imposta sulla data corrente | Consente di specificare o reimpostare [!UICONTROL As Of Date] in modo che il Report Builder utilizzi la data corrente o ti chieda quale data utilizzare al momento dell&#39;aggiornamento. |
| Chiedi di impostare al momento dell&#39;aggiornamento | Consente di impostare [!UICONTROL As Of Date] durante l&#39;aggiornamento di una richiesta. |
| [!UICONTROL Data Recency] |  |
| [!UICONTROL Include Current Data] | Consente di visualizzare la latenza dei dati (nota anche come [!UICONTROL Data Recency]) al minuto nei rapporti, occasionalmente anche prima che questi dati siano stati elaborati da Adobe Analytics.<br>Se non si utilizza questa opzione, viene utilizzata la modalità finalizzata (elaborata), che in genere è più [latente](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html).<br>Questa impostazione si applica a tutte le richieste della cartella di lavoro compatibili con i dati correnti. Se la richiesta non è compatibile, viene applicata la modalità finalizzata.<br>Per l&#39;utilizzo della modalità [!UICONTROL Include Current Data], prendere nota delle seguenti situazioni:<br>**Opzioni di formattazione**: è possibile specificare se visualizzare queste informazioni ([!UICONTROL Data Recency]) durante la [formattazione delle intestazioni di visualizzazione](/help/analyze/legacy-report-builder/layout/t-format-display-headers.md).<br>**Raggruppamenti**: non supportato. Se la modalità [!UICONTROL Data Recency] è impostata su Dati correnti e una delle richieste contiene un elemento di suddivisione, questa richiesta viene ripristinata alla modalità dati non corrente. Altre richieste, tuttavia, continuano a utilizzare la modalità Dati correnti.<br>**Gestione richieste**: è possibile visualizzare una colonna Dati correnti in Gestione richieste per verificare se l&#39;impostazione è applicata a una richiesta pianificata.<br>**Cartelle di lavoro pianificate**: questa modalità viene memorizzata durante il processo di pianificazione a livello di cartella di lavoro. Se si apre una cartella di lavoro pianificata che utilizza dati finalizzati e si applica [!UICONTROL Include Current Data], verrà utilizzata la modalità corrente.<br>**Autorizzazioni**: per gli utenti che non hanno accesso ai dati correnti, questa opzione è nascosta.  Quando si abilita questa opzione, se una o più richieste non possono essere applicate, viene visualizzato un avviso. |
| Disabilita avvisi di richiesta incompatibili con i dati correnti | Visualizza avvisi se è selezionata la modalità [!UICONTROL Include Current Data] ma non è possibile applicare la modalità dati alla richiesta modificata.  Ad esempio, se imposti [!UICONTROL Include Current Data] e successivamente modifichi una richiesta per la quale è selezionato un segmento, viene visualizzato un avviso. |
| Registra le richieste di Report Builder nel file locale (per la risoluzione dei problemi) | Consente di registrare le richieste in un file locale. Utilizzare questo file di registro per la risoluzione dei problemi. |
| Interpreta valore digitato... | Interpreta un valore digitato in un controllo filtro come posizione di cella prima di considerarlo un&#39;espressione di filtro.<br>Ad esempio, se crei una richiesta di 10 pagine principali utilizzando un filtro scarpe, nella richiesta verrà visualizzata una cella simile alla seguente:   Filtro: Prima pagina 1-10, la pagina contiene le scarpe |
| Aggiorna quando è disponibile una nuova versione | Indica al sistema di inviare una notifica se è disponibile una nuova versione per l&#39;installazione. |
