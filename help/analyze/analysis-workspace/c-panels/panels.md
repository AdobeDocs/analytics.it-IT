---
description: I pannelli sono raccolte di tabelle e visualizzazioni.
title: Panoramica dei pannelli
feature: Panels
role: User, Admin
exl-id: dd1a3c40-8b5b-47dd-86d9-da766575ee46
source-git-commit: 5ba12c243a8013c52b487d048c54461ebdf7bd85
workflow-type: tm+mt
source-wordcount: '1404'
ht-degree: 52%

---

# Panoramica dei pannelli

Un [!UICONTROL panel] è una raccolta di tabelle e visualizzazioni. Puoi accedere ai pannelli dall’icona in alto a sinistra in Workspace o da una [pannello vuoto](blank-panel.md). I pannelli sono utili per organizzare i progetti in base a specifici periodi di tempo, suite di rapporti o casi di utilizzo di analisi.

## Tipi di pannello

In Analysis Workspace sono disponibili i seguenti tipi di pannello:

| Nome pannello | Descrizione |
| --- | --- |
| [Pannello vuoto](blank-panel.md) | Per iniziare a eseguire analisi, scegli tra i pannelli e le visualizzazioni disponibili. |
| [Pannello Quick Insights](quickinsight.md) | Crea una tabella a forma libera e una relativa visualizzazione per analizzare e individuare più rapidamente le informazioni. |
| [Pannello Analytics for Target](a4t-panel.md) | Analizza le attività ed esperienze Target in Analysis Workspace. |
| [Pannello Attribution](attribution.md) | Confronta e visualizza rapidamente più modelli di attribuzione utilizzando qualsiasi dimensione e metrica di conversione. |
| [Pannello a forma libera](freeform-panel.md) | Esegui confronti illimitati e raggruppamenti, quindi aggiungi visualizzazioni per raccontare una storia ricca di dati. |
| [Pannello Pubblico medio per minuto](average-minute-audience-panel.md) | Analizza il pubblico medio per minuto nel tempo, con dettagli sulle visualizzazioni di picco e con la possibilità di suddividerlo e confrontarlo. |
| [Pannello Visualizzatori simultanei di contenuti multimediali](media-concurrent-viewers.md) | Analizza i visualizzatori simultanei nel tempo, con dettagli sui picchi di concorrenza e con la possibilità di suddividerli e confrontarli. |
| [Pannello Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali)](media-playback-timespent/media-playback-time-spent.md) | Analizza i visualizzatori simultanei nel tempo, con dettagli sui picchi di concorrenza e con la possibilità di suddividerli e confrontarli. |
| [Pannello Segment Comparison](c-segment-comparison/segment-comparison.md) | Confronta rapidamente due segmenti su tutti i punti dati per trovare automaticamente differenze rilevanti. |

![](assets/panel-overview.png)

I pannelli [!UICONTROL Quick Insights], [!UICONTROL Blank] e [!UICONTROL Freeform] sono ideali per iniziare con le attività di analisi, mentre [!UICONTROL Analytics for Target], [!UICONTROL Attribution IQ], [!UICONTROL Media Concurrent Viewers] e [!UICONTROL Segment Comparison] si prestano ad analisi più avanzate. Nei progetti è disponibile un pulsante `"+"` che consente di aggiungere pannelli vuoti in qualsiasi momento.

Il pannello iniziale predefinito è [!UICONTROL Freeform], ma puoi impostare come predefinito il [pannello vuoto](/help/analyze/analysis-workspace/c-panels/blank-panel.md).

## Suite di rapporti {#report-suite}

Le tabelle e le visualizzazioni all’interno di un pannello derivano i dati dalla [!UICONTROL report suite] selezionata in alto a destra nel pannello. La suite di rapporti determina anche i componenti disponibili nella barra a sinistra. All’interno di un progetto, puoi utilizzare una o [più suite di rapporti](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html?lang=it) a seconda dei casi di utilizzo dell’analisi. Per applicare una singola suite di rapporti a tutti i pannelli di un progetto, **fai clic con il pulsante destro del mouse sull’intestazione del pannello e scegli Applica suite di rapporti a tutti i pannelli**.

L’elenco delle suite di rapporti è ordinato in base alla rilevanza, che Adobe definisce in base a quanto recentemente e con quale frequenza l’utente corrente ha utilizzato la suite, e alla frequenza con cui questa viene utilizzata all’interno dell’organizzazione.

![](assets/panel-report-suite.png)

## Calendario {#calendar}

Il calendario del pannello controlla l’intervallo di reporting per tabelle e visualizzazioni all’interno di un pannello.

>[!NOTE]
>Se un componente di intervallo date (viola) viene utilizzato all’interno di una tabella, di una visualizzazione o di una zona di rilascio di un pannello, questo sovrascrive il calendario del pannello.

![](assets/panel-calendar.png)

Puoi applicare un intervallo di date a livello di minuto nelle impostazioni avanzate del calendario del pannello. Se esegui rapporti su un intervallo di date che dura molti giorni, l’ora di inizio si applica al primo giorno e l’ora di fine si applica all’ultimo giorno dell’intervallo.

## Zona di rilascio {#dropzone}

La zona di rilascio del pannello consente di applicare segmenti e filtri a discesa a tutte le tabelle e visualizzazioni di un pannello. Puoi applicare uno o più filtri a un pannello. Per modificare il titolo sopra ogni filtro, fai clic sull’icona della matita (Modifica); per rimuoverlo, fai clic con il pulsante destro del mouse.

### Filtri dei segmenti

Per iniziare a filtrare il pannello., trascina un segmento dalla barra a sinistra fino alla zona di rilascio del pannello.

![Filtro](/help/admin/admin/assets/filter.png)

### Filtri di segmenti ad hoc

Puoi anche trascinare componenti diversi da segmenti direttamente nella zona di rilascio, per creare segmenti ad hoc in modo più rapido e senza dover passare al Generatore di segmenti. I segmenti creati in questo modo vengono automaticamente definiti come segmenti a livello di hit. Puoi modificarli come di consueto facendo clic sull’icona delle informazioni (i) accanto al segmento, quindi sull’icona Modifica a forma di matita per accedere al Generatore di segmenti.

I segmenti ad hoc sono un tipo di segmento rapido e sono locali per il progetto. Non vengono visualizzati nella barra a sinistra, a meno che non li rendi pubblici.

Per ulteriori informazioni, consulta [Segmenti rapidi](/help/analyze/analysis-workspace/components/segments/quick-segments.md).

### Filtri a discesa statici

I filtri a discesa consentono di interagire con i dati in modo controllato. Ad esempio, puoi aggiungere un filtro a discesa per i tipi di dispositivi mobili, in modo da segmentare il pannello per Tablet, Telefono o Desktop.

I filtri a discesa possono essere utilizzati per consolidare più progetti in un progetto unico. Ad esempio, se hai creato più versioni dello stesso progetto, assegnando a ciascuna un segmento Paese diverso, puoi consolidarle tutte in un unico progetto e aggiungere un filtro a discesa Paese.

![](assets/dropdown-filter-intro.png)

Per creare un filtro a discesa statico:

* Per i filtri a discesa che utilizzano elementi dimensionali, fai clic sull’icona a forma di freccia destra accanto alla dimensione desiderata nella barra a sinistra. Questa azione espone tutti gli elementi dimensionali disponibili. Seleziona più elementi dimensione da questo elenco tramite `[Shift + Click]` o `[Ctrl + Click]`, quindi rilasciale nella zona di rilascio del pannello **durante la tenuta`[Shift]`**.
* Per i filtri a discesa che utilizzano altri componenti, come metriche, segmenti o intervalli di date, seleziona più componenti utilizzando `[Shift + Click]` o `[Ctrl + Click]`. Rilascia la selezione nella zona di rilascio del pannello **durante la tenuta`[Shift]`**. In questo contesto, tutti i tipi di componenti vengono trattati come segmenti.
* Un singolo filtro a discesa può contenere solo un singolo tipo di componente. Se nella selezione includi più tipi di componente, viene creato un filtro a discesa separato per ciascun tipo di componente. Ad esempio, se includi nella selezione sia le metriche che gli elementi dimensionali, vengono creati due filtri a discesa separati. Un filtro a discesa include gli elementi dimensionali, l’altro le metriche.

Seleziona una delle opzioni dall’elenco a discesa per modificare i dati nel pannello. Puoi anche scegliere di non filtrare nessuno dei dati del pannello selezionando **[!UICONTROL No filter]**.

![](assets/create-dropdown.png)

Facendo clic con il pulsante destro del mouse su un filtro a discesa sono disponibili le seguenti opzioni:

* **[!UICONTROL Add label]**: quando aggiungi un filtro a discesa a un progetto, un’etichetta viene impostata automaticamente sul nome del componente. Se elimini l’etichetta, puoi aggiungerla nuovamente con questa opzione.
* **[!UICONTROL Delete label]**: rimuovi il testo sopra un filtro a discesa.
* **[!UICONTROL Delete drop-down filter]**: rimuove il filtro a discesa dal pannello.

Per ulteriori informazioni su come aggiungere filtri a discesa a un progetto, [guarda questo video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html?lang=it).

### Filtri a discesa dinamici

I filtri a discesa dinamici consentono di determinare i valori disponibili in base ai dati all’interno dell’intervallo di reporting del pannello e ai valori in altri filtri a discesa. Ad esempio, puoi creare due elenchi a discesa dinamici utilizzando [Paesi](/help/components/dimensions/countries.md) dimensione e [Città](/help/components/dimensions/cities.md) dimensione. Quando selezioni un paese da [!UICONTROL Countries] elenco a discesa, la [!UICONTROL Cities] L’elenco a discesa si adatta in modo dinamico per mostrare solo le città all’interno di quel paese.

Lo stesso concetto si applica a tutte le dimensioni; sono visibili solo gli elementi dimensionali che compaiono nell’intervallo di date del pannello e i filtri selezionati. Gli elementi Dimension selezionati nei filtri a discesa statici influiscono sui valori disponibili nei filtri a discesa dinamici. Tuttavia, l’inverso non è vero; gli elementi di Dimension selezionati nei filtri a discesa dinamici non influiscono sui valori disponibili nei filtri a discesa statici.

La selezione manuale degli elementi dimensionali è disponibile se prevedi che un determinato elemento dimensionale verrà raccolto in futuro. È inoltre possibile cancellare un filtro a discesa dinamico in modo che non contenga un valore, consentendo ad altri filtri a discesa dinamici di contenere più valori. Seleziona **[!UICONTROL Reset all]** per cancellare la selezione da tutti i filtri a discesa per quel pannello.

Per creare un filtro a discesa dinamico:

* Trascina una singola dimensione nella zona di rilascio del pannello **durante la tenuta`[Shift]`**.
* I filtri a discesa dinamici non sono disponibili per metriche, segmenti o intervalli di date.
* Fai clic con il pulsante destro del mouse su un filtro a discesa e seleziona (Confronta periodi di tempo) **[!UICONTROL Delete filter]** per eliminarlo.

Facendo clic con il pulsante destro del mouse su un filtro a discesa dinamico, è possibile visualizzare le stesse opzioni disponibili per i filtri a discesa statici.

## Menu di scelta rapida {#right-click}

Ulteriori funzionalità per un pannello sono disponibili nel menu di scelta rapida che compare quando fai clic con il pulsante destro del mouse sull’intestazione del pannello.

![Menu di scelta rapida](assets/right-click-menu.png)

Sono disponibili le seguenti impostazioni:

| Impostazione | Descrizione |
| --- | --- |
| Inserisci visualizzazione/pannello copiato | Consente di incollare (&quot;inserire&quot;) un pannello o una visualizzazione copiata in un’altra posizione all’interno del progetto o in un altro progetto. |
| Copia pannello | Consente di fare clic con il pulsante destro del mouse e copiare un pannello, in modo da poterlo inserire in un’altra posizione all’interno del progetto o in un altro progetto. |
| Applica suite di rapporti a tutti i pannelli | Consente di applicare la suite di rapporti del pannello attivo a tutti i pannelli del progetto. |
| Duplica pannello | Crea una copia del pannello corrente, che potrai quindi modificare. |
| Comprimi/Espandi tutti i pannelli | Comprime ed espande tutti i pannelli del progetto. |
| Comprimi/Espandi tutte le visualizzazioni nel pannello | Comprime ed espande tutte le visualizzazioni nel pannello corrente. |
| Modifica descrizione | Aggiungi (o modifica) un testo descrittivo per il pannello. |
| Ottieni collegamento pannello | Consente di indirizzare un utente a uno specifico pannello in un progetto. Quando fai clic sul collegamento, al destinatario verrà richiesto di effettuare l’accesso prima di essere indirizzato al pannello a cui è collegato. |
