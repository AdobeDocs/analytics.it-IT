---
description: Scopri le opzioni di Report Builder.
title: Informazioni sulle opzioni di Report Builder
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
feature: Report Builder
role: User, Admin
exl-id: d3388990-7919-461d-a96e-4c996b8bdb8b
source-git-commit: d218d07ec16e981d7e148092b91fbbd5711e840f
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 1%

---

# Opzioni di Report Builder

Nel pannello Opzioni è possibile specificare le impostazioni di data, le impostazioni di latenza (dati correnti), le informazioni di registro e configurare gli aggiornamenti.

1. Nella barra degli strumenti Componenti aggiuntivi fare clic su **[!UICONTROL Options]** ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg):

| Elemento | Descrizione |
|--- |--- |
| [!UICONTROL As Of Date] |  |
| Imposta sulla data corrente | Consente di specificare o reimpostare  [!UICONTROL As Of Date] in modo che il Report Builder utilizzi la data corrente o chieda quale data utilizzare al momento dell&#39;aggiornamento. |
| Chiedi di impostare al momento dell&#39;aggiornamento | Consente di impostare  [!UICONTROL As Of Date] durante l’aggiornamento di una richiesta. |
| [!UICONTROL Data Recency] |  |
| [!UICONTROL Include Current Data] | Consente di visualizzare la latenza dei dati (nota anche come  [!UICONTROL Data Recency]) fino al minuto nel reporting, occasionalmente anche prima che questi dati siano stati elaborati da Adobe Analytics.<br>Quando non utilizzi questa opzione, viene utilizzata la modalità finalizzata (elaborata), che in genere è più [latente](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html).<br>Questa impostazione si applica a tutte le richieste della cartella di lavoro compatibili con i dati correnti. Se la richiesta non è compatibile, viene applicata la modalità finalizzata.<br>Tieni presente le seguenti situazioni per l’utilizzo di [!UICONTROL Include Current Data] modalità:<br>**Opzioni di formato**: puoi specificare se visualizzare o meno queste informazioni ([!UICONTROL Data Recency]) quando [formattazione delle intestazioni di visualizzazione](/help/analyze/report-builder/layout/t-format-display-headers.md).<br>**Raggruppamenti**: non supportato. Se il  [!UICONTROL Data Recency] La modalità è impostata su Dati correnti e una delle richieste contiene un elemento di suddivisione; questa richiesta viene ripristinata alla modalità dati non corrente. Altre richieste, tuttavia, continuano a utilizzare la modalità Dati correnti.<br>**Request Manager**: puoi visualizzare una colonna Dati correnti in Request Manager, in modo da poter vedere se l’impostazione è applicata a una richiesta pianificata.<br>**Cartelle di lavoro pianificate**: questa modalità viene memorizzata durante il processo di pianificazione a livello di cartella di lavoro. Se si apre una cartella di lavoro pianificata che utilizza dati finalizzati e si applica [!UICONTROL Include Current Data], la modalità corrente viene utilizzata successivamente.<br>**Autorizzazioni**: per gli utenti che non hanno accesso ai dati correnti, questa opzione è nascosta.  Quando si abilita questa opzione, se una o più richieste non possono essere applicate, viene visualizzato un avviso. |
| Disabilita avvisi di richiesta incompatibili con i dati correnti | Visualizza avvisi se  [!UICONTROL Include Current Data] è selezionata, ma la modalità dati non può essere applicata alla richiesta modificata.  Ad esempio, se imposti [!UICONTROL Include Current Data]e quindi modificare una richiesta in cui è selezionato un segmento, viene visualizzato un avviso. |
| Registra le richieste di Report Builder nel file locale (per la risoluzione dei problemi) | Consente di registrare le richieste in un file locale. Utilizzare questo file di registro per la risoluzione dei problemi. |
| Interpreta valore digitato... | Interpreta un valore digitato in un controllo filtro come posizione di cella prima di considerarlo un&#39;espressione di filtro.<br>Ad esempio, se crei una richiesta Primi 10 pagine utilizzando un filtro scarpe, la richiesta visualizzerà una cella simile alla seguente: Filtro: Primi 1-10 pagine, Pagina contiene scarpe |
| Aggiorna quando è disponibile una nuova versione | Indica al sistema di inviare una notifica se è disponibile una nuova versione per l&#39;installazione. |
