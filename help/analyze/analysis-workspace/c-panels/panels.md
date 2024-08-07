---
description: I pannelli sono raccolte di tabelle e visualizzazioni.
title: Panoramica dei pannelli
feature: Panels
role: User, Admin
exl-id: dd1a3c40-8b5b-47dd-86d9-da766575ee46
source-git-commit: aacba26d0eb612146a9e0bf6386f9e755a9e8f07
workflow-type: tm+mt
source-wordcount: '1551'
ht-degree: 50%

---

# Panoramica dei pannelli

Un [!UICONTROL panel] è una raccolta di tabelle e visualizzazioni. Puoi accedere ai pannelli dall’icona in alto a sinistra in Workspace o da un [pannello vuoto](blank-panel.md). I pannelli sono utili per organizzare i progetti in base a specifici periodi di tempo, suite di rapporti o casi di utilizzo di analisi.

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
| [Pannello Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali)](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md) | Analizza i visualizzatori simultanei nel tempo, con dettagli sui picchi di concorrenza e con la possibilità di suddividerli e confrontarli. |
| [Pannello Segment Comparison](c-segment-comparison/segment-comparison.md) | Confronta rapidamente due segmenti su tutti i punti dati per trovare automaticamente differenze rilevanti. |

![](assets/panel-overview.png)

I pannelli [!UICONTROL Quick Insights], [!UICONTROL Blank] e [!UICONTROL Freeform] sono ideali per iniziare con le attività di analisi, mentre [!UICONTROL Analytics for Target], [!UICONTROL Attribution], [!UICONTROL Media Concurrent Viewers] e [!UICONTROL Segment Comparison] si prestano ad analisi più avanzate. Nei progetti è disponibile un pulsante `"+"` che consente di aggiungere pannelli vuoti in qualsiasi momento.

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

La zona di rilascio del pannello consente di applicare segmenti e filtri a discesa a tutte le tabelle e visualizzazioni di un pannello. Puoi applicare uno o più filtri a un pannello.

### Filtri dei segmenti

Per iniziare a filtrare il pannello, trascina un segmento dalla barra a sinistra fino alla zona di rilascio del pannello. Ripeti questa procedura per aggiungere altri filtri al pannello. I filtri vengono visualizzati uno accanto all’altro nella parte superiore del pannello.

![Filtro](assets/segment-filter.png)

### Filtri di segmenti ad hoc

Puoi anche trascinare componenti diversi da segmenti direttamente nella zona di rilascio, per creare segmenti ad hoc in modo più rapido e senza dover passare al Generatore di segmenti. I segmenti creati in questo modo vengono automaticamente definiti come segmenti a livello di hit. Puoi modificarli come di consueto facendo clic sull’icona delle informazioni (i) accanto al segmento, quindi sull’icona Modifica a forma di matita per accedere al Generatore di segmenti.

I segmenti ad hoc sono un tipo di segmento rapido e sono locali per il progetto. Non vengono visualizzati nella barra a sinistra, a meno che tu non li renda pubblici.

Per ulteriori informazioni, consultare [Segmenti rapidi](/help/analyze/analysis-workspace/components/segments/quick-segments.md).

### Segmenti a discesa statici

I segmenti a discesa statici consentono di interagire con i dati in modo controllato. Ad esempio, puoi aggiungere un segmento a discesa per i tipi di dispositivi mobili, in modo da segmentare il pannello per Tablet, Telefono cellulare o Desktop.

I segmenti a discesa statici possono essere utilizzati anche per consolidare più progetti in un unico progetto. Ad esempio, se hai creato più versioni dello stesso progetto, assegnando a ciascuna un segmento Paese diverso, puoi consolidarle tutte in un unico progetto e aggiungere un segmento a discesa Paese.

![](assets/dropdown-filter-intro.png)

#### Creare segmenti a discesa statici

* Per i segmenti a discesa che utilizzano elementi dimensionali, seleziona una singola dimensione dalla barra a sinistra e rilasciala nella zona di rilascio del pannello **tenendo premuto`[Shift]`**. In questo modo viene creato un segmento a discesa con tutti gli elementi dimensionali associati a tale dimensione.

  Oppure, se desideri che il segmento a discesa includa solo elementi dimensionali specifici associati a una dimensione, fai clic sull’icona a forma di freccia verso destra accanto alla dimensione desiderata nella barra a sinistra. Questa azione espone tutti gli elementi dimensionali disponibili. Seleziona più elementi dimensionali da questo elenco utilizzando `[Shift + Click]` o `[Ctrl + Click]`, quindi rilasciali nella zona di rilascio del pannello **mentre tieni premuto** `[Shift]`.

* Per i segmenti a discesa che utilizzano un singolo tipo di componente (ad esempio, solo dimensioni, segmenti o solo metriche), seleziona più elementi dello stesso tipo nella barra a sinistra utilizzando `[Shift + Click]` o `[Ctrl + Click]`, quindi rilasciali nella zona di rilascio del pannello **mantenendo`[Shift]`**.

  Viene creato un singolo segmento a discesa con i componenti selezionati.

* Per i segmenti a discesa che utilizzano una combinazione di tipi di componenti (ad esempio 2 metriche e 3 filtri), selezionare più componenti utilizzando `[Shift + Click]` o `[Ctrl + Click]`. Rilascia la selezione nella zona di rilascio del pannello **mentre tieni premuto`[Shift]`**. In questo contesto, tutti i tipi di componenti vengono trattati come segmenti a discesa separati. Ad esempio, se nella selezione includi sia metriche che elementi dimensionali, vengono creati due segmenti a discesa separati: uno include gli elementi dimensionali e l’altro include le metriche.

  ![La finestra del pannello con il campo del segmento del cliente mobile è disponibile per rilasciare un segmento a discesa statico. ](assets/create-dropdown.png)

Facendo clic con il pulsante destro del mouse su un segmento a discesa, sono disponibili le seguenti opzioni:

* **[!UICONTROL Delete drop-down]**: rimuove il segmento a discesa dal pannello.
* **[!UICONTROL Delete label]**: rimuovere il testo sopra un segmento a discesa. Per modificare l’etichetta, seleziona l’icona della matita.
* **[!UICONTROL Add label]**: quando si aggiunge un segmento a discesa a un progetto, l&#39;etichetta viene impostata automaticamente sul nome del componente. Se elimini l’etichetta, puoi aggiungerla nuovamente con questa opzione.
* **[!UICONTROL Require selection]**: richiede che nel pannello sia impostato un segmento.

Per ulteriori informazioni su come aggiungere filtri a discesa a un progetto, [guarda questo video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html?lang=it).

#### Utilizzare segmenti a discesa statici

Per filtrare il pannello, utilizza il menu a discesa dei segmenti in uno dei seguenti modi:

* Applica un singolo segmento al pannello selezionando il segmento dal menu a discesa.

* Applica più segmenti al pannello selezionando più segmenti dal menu a discesa. Il pannello viene filtrato per includere uno qualsiasi dei segmenti selezionati.

  Per rimuovere un segmento dall’elenco, selezionalo nuovamente nel menu a discesa.

  ![Seleziona più segmenti](assets/dropdown-filter-multiselect.png)

### Segmenti a discesa dinamici

I segmenti a discesa dinamici consentono di determinare i valori disponibili in base ai dati all’interno dell’intervallo di reporting del pannello e ai valori in altri segmenti a discesa. Ad esempio, puoi creare due elenchi a discesa dinamici utilizzando la dimensione [Paesi](/help/components/dimensions/countries.md) e la dimensione [Città](/help/components/dimensions/cities.md). Quando si seleziona un paese dall&#39;elenco a discesa [!UICONTROL Countries], l&#39;elenco a discesa [!UICONTROL Cities] viene modificato in modo dinamico in modo da visualizzare solo le città del paese.

Lo stesso concetto si applica a tutte le dimensioni; sono visibili solo gli elementi dimensionali che compaiono nell’intervallo di date del pannello e nei segmenti selezionati. Gli elementi di Dimension selezionati nei segmenti a discesa statici influiscono sui valori disponibili nei segmenti a discesa dinamici. Tuttavia, l’inverso non è vero; gli elementi di Dimension selezionati nei segmenti a discesa dinamici non influiscono sui valori disponibili nei segmenti a discesa statici.

La selezione manuale degli elementi dimensionali è disponibile se prevedi che un certo elemento dimensionale verrà raccolto in futuro. Puoi anche cancellare un segmento a discesa dinamico in modo che non contenga un valore, consentendo ad altri segmenti a discesa dinamici di contenere più valori. Selezionare **[!UICONTROL Reset all]** per cancellare la selezione da tutti i segmenti del menu a discesa per quel pannello.

Per creare un segmento a discesa dinamico:

* trascina una singola dimensione nella zona di rilascio del pannello **mentre tieni premuto`[Shift]`**.
* I segmenti a discesa dinamici non sono disponibili per metriche, segmenti o intervalli di date.
* Fare clic con il pulsante destro del mouse su un segmento a discesa e selezionare **[!UICONTROL Delete dropdown]** per eliminarlo.

Facendo clic con il pulsante destro del mouse su un filtro a discesa dinamico, è possibile visualizzare le stesse opzioni disponibili per i filtri a discesa statici.

## Menu di scelta rapida {#right-click}

Ulteriori funzionalità per un pannello sono disponibili nel menu di scelta rapida che compare quando fai clic con il pulsante destro del mouse sull’intestazione del pannello.

![Menu di scelta rapida](assets/right-click-menu.png)

Sono disponibili le seguenti impostazioni:

| Impostazione | Descrizione |
| --- | --- |
| Inserisci visualizzazione/pannello copiato | Consente di incollare (“inserire”) un pannello o una visualizzazione copiati in un’altra posizione all’interno del progetto o in un progetto diverso. |
| Copia pannello | Consente di fare clic con il pulsante destro del mouse e copiare un pannello, in modo da poterlo inserire in un’altra posizione all’interno di un progetto o in un progetto diverso. |
| Applica suite di rapporti a tutti i pannelli | Consente di applicare la suite di rapporti del pannello attivo a tutti i pannelli del progetto. |
| Duplica pannello | Crea una copia del pannello corrente, che potrai quindi modificare. |
| Comprimi/Espandi tutti i pannelli | Comprime ed espande tutti i pannelli del progetto. |
| Comprimi/Espandi tutte le visualizzazioni nel pannello | Comprime ed espande tutte le visualizzazioni nel pannello corrente. |
| Modifica descrizione | Aggiungi (o modifica) un testo descrittivo per il pannello. |
| Ottieni collegamento pannello | Consente di indirizzare un utente a uno specifico pannello in un progetto. Quando fai clic sul collegamento, al destinatario verrà richiesto di effettuare l’accesso prima di essere indirizzato al pannello a cui è collegato. |
